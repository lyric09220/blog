## はじめに

Sparkplugは、産業オートメーションとIoTアプリケーションに特化したMQTTベースの通信プロトコルです。Sparkplugソリューションを実装するためには、[MQTTブローカー](https://www.emqx.com/ja/blog/the-ultimate-guide-to-mqtt-broker-comparison)とエッジノードという2つの重要な要素が必要です。

この記事では、オープンソースの分散MQTTブローカーである[EMQX](https://www.emqx.io/)と、エッジIIoT接続サーバーである[Neuron](https://neugates.io/)を使用して、Sparkplugソリューションを構築するためのスケーラブルで堅牢なプラットフォームを提供します。Sparkplugソリューションのアーキテクチャと、EMQXとNeuronが果たす役割について詳しく掘り下げます。

## EMQXの役割

[EMQX](https://www.emqx.io/) を使用して、Sparkplug 仕様に準拠した [MQTT トピック](https://www.emqx.com/en/blog/advanced-features-of-mqtt-topics)名前空間を作成します。Sparkplug ネームスペースは、デバイスがパブリッシュおよびサブスクライブする MQTT メッセージの構造とコンテンツを定義します。EMQX は、Sparkplug ネームスペースに送受信されるすべてのメッセージが適切にフォーマットされ、Sparkplug 仕様に準拠していることを保証します。

> *EMQXの詳細：* [*EMQX Enterprise：エンタープライズMQTTプラットフォーム*](https://www.emqx.com/ja/products/emqx)

EMQX Enterpriseを無料でお試しください。あらゆるデバイスを、あらゆるスケールで、あらゆる場所に接続する。

<section class="promotion">
    <div>
        EMQX Enterprise を無料トライアル
      <div class="is-size-14 is-text-normal has-text-weight-normal">任意のデバイス、規模、場所でも接続可能です。</div>
    </div>
    <a href="https://www.emqx.com/ja/try?product=enterprise" class="button is-gradient px-5">スタートアップ →</a>
</section>

## Neuronの役割

Neuronは、EMQXブローカー上のSparkplugネームスペースにエッジデバイスを接続するために使用されます。Neuronはゲートウェイとして機能し、ローカルのセンサーやコントローラーからデータを収集し、Sparkplugのペイロードフォーマットを使用してEMQXにパブリッシュします。Neuronはまた、Sparkplugネームスペースのメッセージを購読し、必要に応じてローカルデバイスに転送します。

> *Neuronの詳細：Neuron：*[*産業用IoTコネクティビティ・サーバー*](https://www.emqx.com/ja/products/neuron)

<section class="promotion">
    <div>
        Neuronを無料で試す
    </div>
    <a href="https://www.emqx.com/ja/try?product=neuron" class="button is-gradient px-5">スタートアップ →</a>
</section>

## EMQXとNeuronの新たな役割

EMQXとNeuronを併用することで、産業用IoTアプリケーションの統一ネームスペースを作成できる。統一ネームスペースとは、MQTTトピックに共通の命名規則で、場所やプロトコルに関係なく、デバイスとアプリケーションが相互に通信できるようにするものです。すべてのデバイスとアプリケーションは、共通の命名規則とデータモデルに基づいて、同じMQTTトピック階層を使用します。これにより、デバイスは、複雑なルーティングや変換メカニズムを必要とせずに、お互いを検出し、通信することができます。

![Industrial IoT](https://assets.emqx.com/images/a88f6c54e8877d322f0c1987c9f8e625.png)

EMQX は、システム内のデバイスやアプリケーションが使用する命名規則やデータモデルに準拠したトピック階層を定義することで、統一されたネームスペースをサポートするように構成できます。例えば、トピック階層には、デバイス・データ、制御コマンド、アラーム、イベントのトピックを含めることができ、これらはすべて、デバイスとアプリケーションが互いに発見し、相互作用できるように標準化された方法で構成されます。

Neuronは、MQTTブローカーと同じ命名規則とデータモデルを使用して、統一された名前空間をサポートするように構成できます。これにより、NeuronはIoTシステムの残りの部分とシームレスに統合でき、デバイスが場所やプロトコルを越えて通信できるようになります。

## Sparkplug・ソリューション・アーキテクチャ

EMQX と Neuron を使用した MQTT Sparkplug ソリューションは、3 層アーキテクチャとして設計できます。上の図で統一されたネームスペースに等しく接続されているすべてのデバイスとアプリケーションは、2つのレイヤーに分類することができる。最下層はデータ・プロデューサで、最上層はデータ・コンシューマです。中間レイヤは、EMQX と Neuron がデータ・プロデューサとコンシューマ間のデータ交換を容易にする場所です。

![Sparkplug Solution Architecture](https://assets.emqx.com/images/a97b5c154e3f337c813c1c957b41641d.png)

- **オートメーション・レイヤー**：このレイヤーは、自動化された生産中に大量の生データと非構造化データを生成するデバイスとアプリケーションで構成される。これらのデバイスとアプリケーションは、工場フロアとデータセンターに配置することができます。
- **統一ネームスペース・レイヤー**：このレイヤーはEMQX MQTTブローカーとNeuronゲートウェイで構成され、NeuronはセンサーやデバイスがSparkplugメッセージをEMQXにパブリッシュするのを支援し、EMQXはプロデューサーからデータを受信してサブスクライバーに転送する。EMQXは、デバイスとその関連データを含むシステムの状態を維持する責任を負う。
- **アプリケーション・レイヤー**：このレイヤーは、ユニファイド・ネームスペース・レイヤーからデータを消費し、それを使用して分析、監視、制御、その他の機能を実行するアプリケーションで構成される。これらのアプリケーションは、システムの要件に応じて、オンプレミスまたはクラウドに配置することができる。

以下、各レイヤーについて説明する。

## オートメーション・レイヤー

オートメーション・レイヤーは、工場内の自動化された生産工程全体に関する情報を生成することができる。この情報は以下のデバイスやシステムから得られる。

- フィールド機器：物理的な世界でデータを収集・制御するために使用される装置、CNCマシン、センサー、アクチュエーター。
- 制御装置：PLC、PAC、DCS、およびフィールド機器の動作を管理する各種コントローラ。これらの機器は、制御アルゴリズムの実行とフィールド機器との通信を担当する。
- 監視システム：HMI（Human-Machine Interface）やSCADA（Supervisory Control and Data Acquisition）システムなどの機器。
- 情報システム：データベース、データヒストリアン、MES（製造実行システム）、ERP（企業資源計画）、その他、上記の装置やシステムから収集したデータを保存・分析するソフトウェアアプリケーション。

日々の生産では、フィールド・デバイスが物理世界からデータを収集し、制御デバイスに送信する。制御装置はデータを処理し、フィールド装置にコマンドを送り、その動作を制御する。監督システムは、制御装置のパフォーマンスを監視し、オペレーターと情報システムにフィードバックを提供する。最後に、情報システムは、すべての下位レベルのデバイスとシステムからデータを収集・保存し、他の企業システムの情報へのアクセスを提供する。このような情報の流れにより、オートメーション・システムは効果的かつ効率的に運用される。しかし、これらの情報は生の非構造化データであり、さらなる分析のために正規化され、文脈化されなければならない。

## 統一ネームスペース・レイヤー

Unified Namespace Layerは、Automation Layerからすべての非構造化データと生データを収集し、それにコンテキストを追加する。これは、データの正規化とコンテキスト化のプロセスであり、多くの異なるソースからのデータをタイムスタンプ付きの単一の情報ソースにまとめることを意味する。これらのデータはすべて、データソースや形式に関係なく、一貫性のある標準化された方法で整理され、アクセスできるようになります。

この正規化され、文脈化されたデータには、機器の性能、環境条件、生産高、その他産業オペレーションにとって重要な測定基準など、特定の目的に関連するすべての情報が組み込まれている。言い換えれば、コンテキスト化によって、組織内のすべてのデータの、単一で意味のある統一されたビューが提供されます。このコンテキスト化されたデータを活用することで、産業組織はオペレーションの包括的かつ全体的なビューを得ることができ、より良い情報に基づいた意思決定と、効率性と収益性を高めるためのプロセスの最適化が可能になります。

## アプリケーション・レイヤー

アプリケーション・レイヤーは、アプリケーションがコンテキスト化されたデータを使用して、予知保全やAI(人工知能)/ML(機械学習)などのアナリティクスを実行し、工場運営に関する情報に基づいた意思決定を行う場所である。これらのアプリケーションは、特定のデータ・ポイントまたはデバイス・ノードにサブスクライブしてリアルタイムの更新を受け取ることができ、工場が生産プロセスの変化に迅速に対応できるようにします。

コンテキスト化されたデータは、AI/MLモデルで使用されるデータの質を向上させることができる。追加のコンテキストとメタデータを提供することで、AI/MLモデルはデータをよりよく理解し解釈できるようになり、エラーを減らし精度を向上させることができる。さらに、コンテキスト化されたデータは、AI/MLモデルの予測能力も向上させます。追加のコンテキストを提供することで、モデルは将来の出来事や結果についてより正確な予測を行うことができます。

## まとめ

EMQとNeuronを組み合わせてSparkplugソリューションを使用することで、データの文脈化が容易に実装でき、データがシステム全体で正確かつ一貫して共有されることを確保できます。このソリューションは、デバイスとアプリケーション間の発見と通信を容易にし、それぞれが異なる命名システムを持っていても問題ありません。さらに、AI/ML、BIビジネス分析、予測制御などの分析アプリケーションを強化します。その結果、意思決定者はより正確な洞察と行動可能な結果を得ることができ、信頼性のあるデータと分析に基づいて情報に基づいた決定を下すことができます。