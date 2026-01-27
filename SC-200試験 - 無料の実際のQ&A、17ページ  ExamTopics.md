---
title: "SC-200試験 - 無料の実際のQ&A、17ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/17/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#34 トピック3

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。質問セットによっては、複数の正解が存在する場合もあれば、正解が存在しない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Azure  
Sentinel を構成しています。  
悪意のある IP アドレスからの Azure 仮想マシンへのサインインが検出された場合、Azure Sentinel でインシデントを作成する必要があります。  
解決策: クエリからライブストリームを作成します。  
これは目標を達成していますか?  

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)

**正解:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)  
参考:  
<https://docs.microsoft.com/en-us/azure/sentinel/connect-azure-security-center>

**解説:**
悪意のあるIPからのサインインを検出し、**インシデントを作成する**ことが目標です。
**「クエリからライブストリームを作成します」**: ライブストリームはリアルタイムの監視ツールであり、アラートやインシデントを自動生成する機能ではありません。したがって、目標は達成されません。インシデントを作成するには「スケジュールされたクエリールール」を作成する必要があります。

*コミュニティ投票の配分*

B（100％）

質問#35 トピック3

ワークブック用のクエリを作成する必要があります。クエリは以下の要件を満たす必要があります。
✑  すべてのインシデントをインシデント番号順に一覧表示する。
✑  各インシデントの最新のログのみを含める。  
クエリはどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
注：正しい選択は1つにつき1ポイントです。  
ホットエリア：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0013800003.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0013900001.jpg) 参照:  
<https://www.drware.com/whats-new-soc-operational-metrics-now-available-in-sentinel/>

**解説:**
このクエリの目的は「各インシデントの**最新のログ**を取得する」ことです。

- **summarize**: データを特定の列（この場合は `IncidentNumber`）でグループ化するために使用します。
    
- **arg_max(LastModifiedTime, *)**: これは `summarize` 演算子の中で使用される集計関数です。指定した列（`LastModifiedTime`）が**最大値（最新）**である行全体を取得します。
    
    - `*` を指定することで、その行にあるすべての列を保持します。
        

なぜ他の選択肢ではないのか？

- **project**: 列の選択や名前変更を行うものですが、グループ化や最新行の抽出はできません。
    
- **sort**: 並べ替えを行うだけで、重複するインシデント番号から最新の1つに絞り込むことはできません。
    
- **top / limit**: 単純に上位の行を取得するだけで、各インシデント番号ごとの最新行を特定するロジックには不向きです。

質問#36 トピック3

ドラッグ＆ドロップ -  
次の表に示すリソースがあります。
![](https://www.examtopics.com/assets/media/exam-media/04261/0013900002.png)  
SW1  で重複したイベントが発生しないようにする必要があります。  
各アクションには何を使用すればよいでしょうか？ 適切なリソースを正しいアクションにドラッグして答えてください。各リソースは1回、複数回、または全く使用されない場合があります。コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
注：正しい選択ごとに1ポイント獲得できます。  
選択して配置：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0014000001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)   [議論   16](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)

**正解:** ![](https://img.examtopics.com/sc-200/image425.png)

**解説:**
この構成では、**CEF1** が「ログフォワーダー（コレクター）」として機能しています。重複を避けるために CEF1 で以下の制御が必要になります。

1. Syslog構成からのファシリティ削除

**CEF1** 上の Syslog デーモン（rsyslog または syslog-ng）は、受信したメッセージをローカルの Log Analytics エージェントに渡します。もし CEF メッセージとして送信されているファシリティが Syslog としても収集対象になっていると、同じログが **CommonSecurityLog** テーブルと **Syslog** テーブルの両方に書き込まれ、重複が発生します。そのため、**CEF1** の Syslog 設定から CEF 用のファシリティを除外する必要があります。

2. Syslog 同期の無効化

Azure Sentinel (SW1) のポータル設定で Syslog 収集が有効になっている場合、エージェントはその設定を自動的に同期してローカルログを収集しようとします。**CEF1** において、標準的な Syslog 収集プロセスと CEF 専用の転送プロセスが競合しないよう、**CEF1** 上のエージェントで Syslog 同期を無効化（または設定の除外）することが推奨されます。

質問#37 トピック3

Microsoft Sentinel を使用する Azure サブスクリプションを所有しています。  
インシデントへの対応と、Microsoft Sentinel によって検出されたセキュリティ脅威の修復に必要な管理作業を最小限に抑える必要があります。  
どの 2 つの機能を使用すべきでしょうか？ 正解はそれぞれ解決策の一部を示しています。  
注: 正解は 1 点です。  

- A. Microsoft Sentinel ブックマーク
- B. Azure Automation ランブック
- C. Microsoft Sentinel 自動化ルール
- D. Microsoft Sentinel プレイブック
- E. Azure Functions アプリ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)

**正解** [：](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)CD🗳️  

**解説:**
インシデント対応の自動化により管理作業を最小化する組み合わせです。

1. **C. Microsoft Sentinel 自動化ルール (Automation rules)**: インシデント発生時や更新時にトリガーされ、インシデントの割り当て、タグ付け、終了などの単純なタスクを実行したり、プレイブックを呼び出したりする「司令塔」の役割を果たします。
2. **D. Microsoft Sentinel プレイブック (Playbooks)**: Logic Appsをベースにしたワークフローで、外部システムとの連携（チケット起票、Teams通知、ユーザーブロックなど）を含む複雑な修復アクションを実行します。
※Automation rulesのみでは複雑なアクションができず、Playbooksのみでは自動トリガー（現在の仕様ではAutomation rule経由が基本）ができないため、両方を組み合わせます。

*コミュニティ投票の配分*

CD（86％）

14%

質問#38 トピック3

カスタム Kusto クエリを含む、workspace1 という Microsoft Sentinel ワークスペースがあります。  
ビジュアルを作成するための Python ベースの Jupyter Notebook を作成する必要があります。ビジュアルにはクエリの結果が表示され、ダッシュボードにピン留めされます。このソリューションは開発の労力を最小限に抑える必要があります。  
ビジュアルを作成するには何を使用すればよいでしょうか？  

- A. 陰謀的な
- B. テンソルフロー
- C. ムスティッピー
- D. matplotlib

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)  

**解説:**
Jupyter Notebookでクエリ結果を可視化するためのライブラリで、Sentinel向けに特化されており開発労力を最小限に抑えられるものです。
**「Msticpy (Microsoft Threat Intelligence Python Security Tools)」**: Microsoftが開発したセキュリティ専門のPythonライブラリです。Sentinelからのデータ取得、エンティティ情報の拡充、タイムラインやプロセツリーなどの高度な可視化を、少ないコード行数で実現するための機能が豊富に含まれています。
※Matplotlib (D) も可視化に使えますが、汎用ライブラリであり、Sentinelのデータ構造に合わせた可視化をゼロから作るには手間がかかります。

*コミュニティ投票の配分*

C（100％）

質問#39 トピック3

ホットスポット -  
sws1 という Microsoft Sentinel ワークスペースがあります。  
複数の Azure Storage アカウントのストレージキーを一覧表示するユーザーを特定するためのハンティングクエリを作成する必要があります。このソリューションでは、単一のストレージアカウントのストレージキーを一覧表示するユーザーを除外する必要があります。  
クエリをどのように完成させるべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正しい選択肢は 1 つにつき 1 ポイント付与されます。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0014300001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)

**Correct Answer:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0014400001.jpg) Box 1: AzureActivity -  

**解説:**
複数のストレージアカウントキーを一覧表示している（偵察行為の可能性がある）ユーザーを特定し、正当な単一アクセスを除外するHuntingクエリです。

1. **AzureActivity**: Azureアクティビティログテーブルを対象にします。
2. **autocluster()**: データセット内の共通パターン（クラスタ）を見つけるためのプラグインです。ここでは、ユーザーごとの通常のアクセスパターンを学習し、そこから逸脱する（複数のリソースにまたがるような）異常な動作を識別するために使用されていると考えられます。
※提供されたGitHubリンクのクエリロジックに基づくと、`autocluster()` を使って「期待されるIPアドレス」などを学習し、それと異なるアクセスを抽出することで異常を検知しています。

The AzureActivity table includes data from many services, including Microsoft Sentinel. To filter in only data from Microsoft Sentinel, start your query with the following code:  

Box 2: autocluster()  
Example: description: |  
'Listing of storage keys is an interesting operation in Azure which might expose additional secrets and PII to callers as well as granting access to VMs. While there are many benign operations of this type, it would be interesting to see if the account performing this activity or the source IP address from which it is being done is anomalous.  
The query below generates known clusters of ip address per caller, notice that users which only had single operations do not appear in this list as we cannot learn from it their normal activity (only based on a single event). The activities for listing storage account keys is correlated with this learned clusters of expected activities and activity which is not expected is returned.'  
  
AzureActivity -  
| where OperationNameValue =~ "microsoft.storage/storageaccounts/listkeys/action"  
| where ActivityStatusValue == "Succeeded"  
| join kind= inner (  
  
AzureActivity -  
| where OperationNameValue =~ "microsoft.storage/storageaccounts/listkeys/action"  
| where ActivityStatusValue == "Succeeded"  
| project ExpectedIpAddress=CallerIpAddress, Caller  
| evaluate autocluster()  
) on Caller  
| where CallerIpAddress != ExpectedIpAddress  
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated), ResourceIds = make\_set(ResourceId), ResourceIdCount = dcount  
(ResourceId) by OperationNameValue, Caller, CallerIpAddress  
| extend timestamp = StartTime, AccountCustomEntity = Caller, IPCustomEntity = CallerIpAddress  
Reference:  
<https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/AzureActivity/Anomalous\_Listing\_Of\_Storage\_Keys.yaml>

質問#40 トピック3

ドラッグ＆ドロップ -  
Microsoft Sentinel ワークスペース「workspace1」と Azure 仮想マシン「VM1」があります。VM1  
で PowerShell の不審な使用に関するアラートを受信しました。  
インシデントを調査し、アラートをトリガーしたイベントを特定し、アラート後に VM1 で以下のアクションが発生したかどうかを確認する必要があります。  
ローカルグループメンバーシップの変更  
![](https://www.examtopics.com/assets/media/exam-media/04261/0014500001.png)  
✑ イベントログの消去  
Azure ポータルで順番に実行する必要がある 3 つのアクションはどれですか。回答するには、アクションの一覧から適切なアクションを回答領域に移動し、正しい順序で並べ替えてください。  
選択して配置:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0014600002.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)

**Correct Answer:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0014600003.jpg) Step 1: From the Investigation blade, select Insights  

**解説:**
インシデントに関連する特定のVM（エンティティ）について、グループ変更やログ消去などの詳細なアクション履歴を確認する手順です。

1. **Step 1: From the Investigation blade, select Insights**: 調査画面（Investigation blade）から、詳細情報を見るために「Insights」を選択します。（※現在のUIでは「Entity info」や「Timeline」タブなどが該当しますが、設問の文脈ではInvestigation Insights Workbookへの遷移を指しています）
2. **Step 2: From the Investigation blade, select the entity that represents VM1**: 調査グラフ上で対象のVMエンティティをクリックして選択します。
3. **Step 3: From the details pane of the incident, select Investigate**: まず最初にインシデント詳細から「Investigate（調査）」ボタンをクリックして調査グラフを開く必要があります。（※手順の順序としては3→2→1の流れが自然ですが、Drag&Dropの選択肢としてはこれらが正解となります）

The Investigation Insights Workbook is designed to assist in investigations of Azure Sentinel Incidents or individual IP/Account/Host/URL entities.  

Step 2: From the Investigation blade, select the entity that represents VM1.  
The Investigation Insights workbook is broken up into 2 main sections, Incident Insights and Entity Insights.  
  
Incident Insights -  
The Incident Insights gives the analyst a view of ongoing Sentinel Incidents and allows for quick access to their associated metadata including alerts and entity information.  
  
Entity Insights -  
The Entity Insights allows the analyst to take entity data either from an incident or through manual entry and explore related information about that entity. This workbook presently provides view of the following entity types:  
  
IP Address -  
  
Account -  
  
Host -  
  
URL -  
Step 3: From the details pane of the incident, select Investigate.  
Choose a single incident and click View full details or Investigate.  
Reference:  
<https://github.com/Azure/Azure-Sentinel/wiki/Investigation-Insights---Overview> <https://docs.microsoft.com/en-us/azure/sentinel/investigate-cases>

質問#41 トピック3

Microsoft Sentinel ワークスペースに以下のインシデントが発生しています。Azure  
Portal 分析ルールに対するブルートフォース攻撃が発生しました。  
このインシデントに対応する位置情報を特定する必要があります。  
どうすればよいですか？  

- A. 「概要」から、潜在的な悪意のあるイベントのマップを確認します。
- B. 「インシデント」から、インシデントに関連付けられている IPCustomEntity エンティティの詳細を確認します。
- C. 「インシデント」から、インシデントに関連付けられている AccountCustomEntity エンティティの詳細を確認します。
- D. 調査から、インシデントエンティティに関する洞察を確認します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)   [議論   19](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)  

**解説:**
ブルートフォース攻撃の位置情報（Geolocation）を特定するために確認すべきエンティティ詳細です。
**「B. IPCustomEntity」**: 攻撃元のIPアドレス情報が含まれるエンティティです。SentinelではIPエンティティに関連付けられた地理的位置情報（国、都市など）を確認することができます。
※AccountCustomEntity (C) は攻撃対象のアカウント情報であり、攻撃元の位置情報は含まれません。

*Community vote distribution*

B (92%)

8%

質問#42 トピック3

Microsoft Defender for Cloud を使用する Azure サブスクリプションが 2 つあります。  
ルート管理グループ レベルで、特定の Defender for Cloud セキュリティアラートを抑制する必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。Azure  
ポータルで何をすればよいでしょうか？  

- A. Azure Policy 割り当てを作成します。
- B. Defender for Cloud のワークロード保護設定を変更します。
- C. Azure Monitor でアラート ルールを作成します。
- D. Defender for Cloud のアラート設定を変更します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)   [議論   16](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)

**Correct Answer:** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)  

**解説:**
ルート管理グループ階層全体で、特定のアラートを抑制（Suppress）するための設定を最小労力で行う方法です。
**「Azure Policy割り当てを作成します」**: 「Azure Security Centerのアラートの抑制ルールを展開する (Deploy - Configure suppression rules for Azure Security Center alerts)」という組み込みポリシー定義を使用し、ルート管理グループに割り当てることで、組織全体に一貫した抑制ルールを適用できます。個々のサブスクリプションで設定する手間が省けます。

*Community vote distribution*

A (90%)

10%

質問#43 トピック3

Microsoft Defender for Cloud の強化されたセキュリティ機能が有効になっている Azure サブスクリプションがあり、User1 というユーザーが登録されています。User1  
が Defender for Cloud からアラートデータをエクスポートできるようにする必要があります。このソリューションでは、最小権限の原則を適用する必要があります。User1  
にはどのロールを割り当てるべきでしょうか？  

- A. ユーザーアクセス管理者
- B. オーナー
- C. 貢献者
- D. リーダー

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)   [議論   61](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)

**Correct Answer:** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/17/#)  

**解説:**
アラートデータをエクスポートできる最小権限のロールです。
**「リーダー (Reader)」**: Security Readerロール（またはサブスクリプションのReader）であっても、画面上の「CSVとしてダウンロード」機能を使用して現在表示されているアラート一覧をエクスポートすることは可能です。
※もし「連続エクスポート (Continuous Export)」の設定を行う必要がある場合は、Security AdminやContributor以上の権限が必要になりますが、単に「アラートデータをエクスポートする」という要件だけであれば、Readerでも手動エクスポートは可能です。最小権限の原則に従うためDが正解とされます。

*Community vote distribution*

D (43%)

C (29%)

B (28%)

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/16/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 17 ページを表示しています。

410問中**161 - 170**問 を表示
