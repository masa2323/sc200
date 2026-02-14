質問#55 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。  
  
新しい Microsoft Secure Score アクションが生成されたときに、会社の IT 部門に Microsoft Teams メッセージを送信するワークフローを作成する必要があります。  
  
どの 3 つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答領域に移動し、正しい順序に並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image223.png)

**正しい順序は以下の3つのアクション:**
1. **Create an Azure logic app that includes the Defender for Cloud recommendation trigger.** (Defender for Cloud 推奨事項トリガーを含む Azure ロジック アプリを作成する)
2. **Configure workflow automation.** (ワークフロー自動化を構成する)
3. **Configure a trigger condition.** (トリガー条件を構成する)

**解説:**
- まず、Defender for Cloud の推奨事項トリガーを持つ Logic App を作成します
- 次に、Defender for Cloud のワークフロー自動化機能を使用して、この Logic App を実行するように構成します
- 最後に、特定の条件(例: 特定の推奨事項や重要度)でトリガーされるように条件を設定します

質問#56 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションがあり、Windows Server を実行する仮想マシンが 100 台含まれています。  
  
これらの仮想マシンからイベントデータを収集するように Defender for Cloud を構成する必要があります。このソリューションでは、管理の手間とコストを最小限に抑える必要があります。  
  
実行すべきアクションは 2 つあります。正解はそれぞれソリューションの一部です。  
  
注: 正解は 1 つにつき 1 ポイントです。

- A. セキュリティ イベント ストレージを共通に設定して、自動プロビジョニングを構成します。
- B. Microsoft Endpoint Manager 管理センターから、自動登録を有効にします。
- C. Azure ポータルから、Azure Event Grid サブスクリプションを作成します。
- D. セキュリティ イベント ストレージを \[すべてのイベント\] に設定して、自動プロビジョニングを構成します。
- E. Azure ポータルの Defender for Cloud から、Microsoft Defender for Servers を有効にします。

**正解:** AE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)  

**解説:**
100台のVMからイベントデータを収集し、コストと管理負荷を最小限に抑える構成です。

1. **A. Common (共通) に設定**: 「All events」は全イベントを収集するため高コストです。「Common」は監査に必要な標準セットであり、コスト対効果が高い設定です。
2. **E. 自動プロビジョニングを有効にする**: Defender for Cloudの設定で自動プロビジョニングを有効にすることで、全VMへのエージェント（AMA/Log Analyticsエージェント）導入を自動化し、管理負荷を最小化します。

質問#57 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションがあります。Amazon Web Services (AWS) サブスクリプションもあります。サブスクリプションには、Windows Server を実行する複数の仮想マシンが含まれています。  
  
これらの仮想マシンで Microsoft Defender for Servers を有効にする必要があります。  
  
実行すべき 2 つのアクションはどれですか？ 正解はそれぞれ解答の一部です。  
  
注: 正解は 1 点です。

- A. Defender for Cloud からエージェントレス スキャンを有効にします。
- B. 仮想マシンを Microsoft Defender for Endpoint にオンボードします。
- C. Defender for Cloud から AWS コネクタを構成します。
- D. 各仮想マシンに Azure 仮想マシン エージェント (VM エージェント) をインストールします。
- E. Defender for Cloud から自動プロビジョニングを構成します。

**正解:** CE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)  

**解説:**
AWS VMとオンプレミスVM（文脈上含まれる場合や、Azure外リソース全般）でDefender for Serversを有効にするための手順です。

1. **C. AWSコネクタを構成します**: AWS環境をDefender for Cloudに接続するために必要です。これによりAzure Arcの自動デプロイなどが可能になります。
2. **E. 自動プロビジョニングを構成します**: 接続されたAWS VMやオンプレミス・他クラウドサーバーに対して、必要なエージェント（Log Analyticsエージェント/AMA、およびAzure Arcエージェント）を自動的にインストールする設定を有効にします。
（※選択肢Dの「VMエージェント」はAzure VM専用です。Azure外サーバーにはAzure Arcエージェントが必要です。）

質問#58 トピック2

Sub1 という Azure サブスクリプションと AzDO1 という Azure DevOps 組織があります。AzDO1 には Defender for Cloud が使用されており、Pipeline1 という YAML パイプラインを持つプロジェクトが含まれています。Pipeline1 は、発見されたオープンソースソフトウェアの脆弱性の詳細を Defender for Cloud に出力します。  
  
シークレットスキャンの結果を Defender for Cloud に出力するように Pipeline を構成する必要があります。Pipeline1 に何を追加すればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image225.png)

**解説:**
Azure DevOps パイプラインで Microsoft Security DevOps（MSDO）タスクを使用してセキュリティスキャンを実行する場合、YAML 形式でパラメータを指定する必要があります。

1. inputs:
YAML タスクにおいて、そのタスクに渡す設定値（引数）を定義するセクションの名前は **`inputs:`** です。これにより、タスクがどのように動作するかを制御します。

2. categories: 'secrets'
Microsoft Security DevOps 拡張機能のタスク（`MicrosoftSecurityDevOps@1` など）では、**`categories`** という入力パラメータを使用して、実行するスキャンの種類を指定します。

- **'secrets'**: この値を指定することで、コード内のパスワードや API キーなどの機密情報の露出を検出するスキャン（CredScan など）が有効になり、その結果が Defender for Cloud に送信されるようになります。
    
- 他にも `IaC`（インフラ構成のスキャン）や `artifacts` などのカテゴリを指定することが可能です。
    
---
この設定を Pipeline1 に追加することで、ビルドプロセス中にシークレットが自動的に検出され、Defender for Cloud の **DevOps Security** ダッシュボードで一元管理できるようになります。

質問#59 トピック2

sub1 という名前の Azure サブスクリプションを作成します。sub1 内に、workspace1 という名前の Log Analytics ワークスペースを作成します。Microsoft Defender for Cloud を有効にし、workspace1 を使用するように Defender for Cloud を構成します。workspace1 にレポートを送信する Azure 仮想マシンからセキュリティ イベント ログを収集する必要があります。  
  
どうすればよいでしょうか。

- A. Defender for Cloud から、Microsoft Defender for Servers プランの設定を変更します。
- B. サブ1でプロバイダーを登録します。
- C. Defender for Cloud からワークフロー自動化を作成します。
- D. ワークスペース1 でワークブックを作成します。

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)  

**解説:**
特定のLog Analyticsワークスペース（workspace1）にレポートするAzure VMからセキュリティイベントログを収集する方法です。
**「Defender for Cloudから、Microsoft Defender for Serversプランの設定を変更します」**: Defender for Serversプランをワークスペースレベルで有効にするか、サブスクリプションレベルの設定で対象ワークスペースへの自動プロビジョニングとデータ収集設定（Common/Allなど）を構成することで、イベントログの収集が開始されます。

## トピック3 - 質問セット3

質問1 トピック3

Common Event Format (CEF) メッセージを Azure Sentinel に送信する外部ソリューションを接続する予定です。ログフォワーダーをデプロイする必要があります。
3 つのアクションのうち、どのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
選択して配置してください。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0010700001.png)  

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0010800001.png) 参照:  
<https://docs.microsoft.com/en-us/azure/sentinel/connect-cef-agent?tabs=rsyslog>

**解説:**
1. エージェントのダウンロードとインストール

ログフォワーダーとして機能するマシンに **Log Analytics エージェント**をインストールします。これが、オンプレミスまたは他のクラウド環境から Microsoft Sentinel へログを転送するための通信基盤となります。

2. ポート 25226 のリスニング構成

エージェントが **TCP ポート 25226** で待機するように設定します。

- **専用ポートの使用:** Microsoft Sentinel の CEF コネクタは、標準の Syslog（ポート 514）と混同しないよう、専用の 25226 ポートを使用してメッセージを受信し、クラウドへ転送するように設計されています。
    

3. Syslog デーモンの構成と再起動

マシンの **Syslog デーモン**（rsyslog や syslog-ng）を構成し、受信したセキュリティイベントをローカルのエージェント（127.0.0.1:25226）に転送するように設定します。

- 構成完了後、設定を反映させるために **Syslog デーモンと Log Analytics エージェントの両方を再起動**する必要があります。
    
---
## 補足：他の選択肢について

- **OMS Gateway のデプロイ:** ログフォワーダーが直接インターネットに接続できない閉域網にある場合に検討されますが、標準的な構成における必須ステップではありません。
    
- **Syslog デーモンから直接 Sentinel へ送信:** Syslog デーモン自体が直接クラウドに送信するのではなく、必ずローカルにインストールされたエージェントを介して通信を行うのが正しい構成です。

質問2 トピック3

Azure Sentinel から、以下の図に示すように、重大度の高いインシデントの調査ウィンドウを開きます。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0010900001.jpg)  
ドロップダウンメニューを使用して、図に示された情報に基づいて各文を完成させる選択肢を選択してください。  
注: 正解は1つにつき1ポイントです。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0011000001.jpg)  

**正解:** ![](https://img.examtopics.com/sc-200/image423.png)

**解説:**
1. エンティティ（vm1）のホバー表示

調査グラフ内で仮想マシン（vm1）などのエンティティにマウスを合わせると、そのリソースに関する**「インサイト（Insights）」**の概要が表示されます。

- **the running processes:** 図中のアラート名が「New processes ob...（検出された新しいプロセス）」となっていることから、このインシデントはプロセスの実行に関連しています。センチネルのホスト・インサイトでは、対象マシンで実行されているプロセスの数やリストを確認できるため、この選択肢が最適です。
- 他の選択肢（NSG ルールや 5 件のログなど）は、ホバー時のクイック表示ではなく、詳細プロパティや別途クエリを実行して確認する情報です。
    

2. インシデント関連アイテムへの移動

右側のツールバーにある各ボタンの役割は以下の通りです。

- **Timeline（タイムライン）:** インシデントに関連するアラート、ブックマーク、エンティティの動きを**時系列（Chronological order）**で表示します。インシデントに関連する個々の「アイテム（出来事）」を追跡するために使用します。
- **Entities:** インシデントに関与しているエンティティ（ユーザー、IP、ホストなど）の一覧を表示します。
- **Info:** インシデントの重大度、ステータス、所有者などの基本情報を表示します。
- **Insights:** 選択したエンティティに対して定義済みの分析クエリを実行し、異常な活動がないかを確認します。

質問3 トピック3

Azure Sentinel をデプロイしています。  
不審な資格情報アクセスアクティビティをすべてクエリする必要があります。  
どの 3 つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答領域に移動し、正しい順序に並べ替えてください。  
選択して配置します。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0011100001.png)  

**解説:**
1. Hunting ページの選択

まず、脅威ハンティングを行うための専用ページである **[Hunting（捜索）]** を選択します。ここには、特定の攻撃手法を検知するための定義済みクエリが多数用意されています。

2. 戦術（Tactics）によるフィルタリング

「資格情報アクセス（Credential Access）」は MITRE ATT&CK フレームワークにおける特定の**戦術（Tactic）**にあたります。

- **Filter by tactics** を使用して、「Credential Access」を選択することで、数百あるクエリの中から、資格情報の窃取に関連するものだけに絞り込むことができます。
    
3. Run All Queries の実行

フィルタリングによって対象を絞り込んだ状態で **[Run All Queries（すべてのクエリを実行）]** を選択します。

- これにより、現在リストに表示されている（＝資格情報アクセスに関連する）すべてのハンティングクエリが一括で実行され、異常なアクティビティがないかを確認できます。
