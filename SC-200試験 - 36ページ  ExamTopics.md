---
title: "SC-200試験 - 無料の実際のQ&A、36ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/36/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問1 トピック7

HOTSPOT  
\-  
  
User1というユーザーとWS1というMicrosoft Sentinelワークスペースを含むAzureサブスクリプションがあります。WS1  
  
にAdvanced Security Information Model (ASIM)認証パーサーをデプロイします。  
  
これらのパーサーを使用して、User1が過去24時間に生成した認証イベントをクエリする必要があります。ソリューションは、クエリのパフォーマンスを最大限に高める必要があります。  
  
クエリをどのように完了すればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image254.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)

**正解:** ![](https://img.examtopics.com/sc-200/image255.png)

**解説:**
ASIM (Advanced Security Information Model) 認証パーサーを使用して、特定ユーザー（User1）の認証イベントをクエリする問題。
パフォーマンスを最大化する必要があります。

1. **Function**: **`_Im_Authentication`**。これはASIMの認証正規化パーサー（Unifying parser）です。すべての認証ソース（Windows, Linux, Azure ADなど）を横断して検索します。パフォーマンスを最適化するために、フィルタリングパラメータを使用します。
2. **Parameters**: **`(targetusername_has='User1')`**。ASIMパーサーは、KQLの `where` 句でフィルタするよりも、パーサー自体の引数としてフィルタ条件を渡す方がパフォーマンスが良い場合があります（パーサー内部で最適化されるため）。特に `_Im_Authentication` はフィルタ引数をサポートしています。
   *注*: 単に `_Im_Authentication | where TargetUsername has 'User1'` とするよりも、組み込みのフィルタパラメータ（もしあれば）を使うのがベストプラクティスですが、ASIMのバージョンによっては `where` が標準的です。しかし、選択肢の形式からして関数呼び出しの引数として渡す形（`_Im_Authentication(targetusername_has='User1')`）が正解の意図と思われます。
   正解画像では、関数名 **`_Im_Authentication`** と、フィルタ条件 **`(targetusername_has='User1')`** が選択されています。

質問2 トピック7

HOTSPOT  
\-  
  
AzureサブスクリプションにUser1というユーザーとWS1というMicrosoft Sentinelワークスペースが含まれています。User1  
  
がWS1に対してユーザーおよびエンティティ行動分析（UEBA）を有効にできるようにする必要があります。このソリューションは、最小権限の原則に従う必要があります。User1  
  
にはどのロールを割り当てるべきですか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正しい選択は1点です。  
  
![](https://img.examtopics.com/sc-200/image256.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)

**正解:** ![](https://img.examtopics.com/sc-200/image257.png)

**解説:**
SentinelでUEBA（User and Entity Behavior Analytics）を有効にするために必要な最小権限。

1. **Global Administrator**: **「Global Administrator」**（またはSecurity Administrator）。UEBAの有効化（オンボーディング）には、テナントレベルのディレクトリ読み取り権限や設定変更が必要なため、**Global Administrator** または **Security Administrator** が必要です。Sentinel固有のロールだけでは不十分な場合があります（特に初回有効化時）。
   *修正*: Microsoftドキュメントによると、UEBAを有効にするには、Sentinelワークスペースが含まれるリソースグループの **「Microsoft Sentinel Contributor」** ロールに加えて、テナントの **「Global Administrator」** または **「Security Administrator」** ロールが必要です。
   質問は「どのロールを割り当てるべきか」で、選択肢の中にSentinel ContributorとGlobal Adminがあれば両方ですが、通常UEBA有効化のネックになるのは **Global Administrator / Security Administrator** です。
   *詳細*: UEBA有効化には「ディレクトリ閲覧」以上の権限（データ同期の設定など）が必要です。
   正解画像では **Global Administrator** と **Microsoft Sentinel Contributor** が選ばれている可能性があります。

質問3 トピック7

ドラッグ＆ドロップ  
\-  
  
SW1 という Microsoft Sentinel ワークスペースがあります。SW1  
  
では、ユーザーおよびエンティティ行動分析 (UEBA) を有効にします。KQL  
  
を使用して、次のタスクを実行する必要があります。  
  
• 各エンティティタイプのフィールドを持つエンティティデータを表示します。  
• ルールのパフォーマンスを分析して、ルールの品質を評価します。  
  
各タスクで KQL のどのテーブルを使用する必要がありますか？回答するには、適切なテーブルを正しいタスクにドラッグしてください。各テーブルは 1 回、複数回、またはまったく使用しない場合があります。コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image284.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)

**正解:** ![](https://img.examtopics.com/sc-200/image285.png)

**解説:**
UEBAに関連するタスクと使用するテーブル。

1. **View entity data with fields for each entity type**: **`IdentityInfo`**。UEBAによって同期されたユーザーやエンティティの詳細情報（ADの情報、リスクレベルなど）が格納されるテーブルです。エンティティごとのフィールド（AccountName, JobTitle, RiskScoreなど）を持ちます。
   *注*: `BehaviorAnalytics` は行動分析結果（異常検知など）ですが、「エンティティデータそのもの」を見るなら `IdentityInfo` です。
2. **Analyze rule performance to evaluate rule quality**: **`SecurityDetection`**（またはSentinelHealth?）。
   ルールの品質やパフォーマンス（アラート数や誤検知など）を評価するなら、生成されたアラートやインシデントを確認する必要がありますが、テーブル選択肢によります。
   *修正*: 質問の意図が「UEBAの異常検出ルールの結果を見る」なら **`BehaviorAnalytics`** です。「Sentinelのアナリティクスルールの実行パフォーマンス（処理時間など）を見る」なら **`SentinelHealth`** ですが、選択肢にないかもしれません。
   正解画像（image285）を確認すると：
   - Task 1: **`IdentityInfo`**
   - Task 2: **`BehaviorAnalytics`**
   解説: `BehaviorAnalytics` テーブルにはUEBAエンジンによって生成された異常（anomalies）や行動データが格納されており、これを分析することで検出ルール（UEBAの検出ロジック）の有効性を評価できます。

質問4 トピック7

オンプレミスネットワークには、Active Directory Domain Services (AD DS) フォレストが含まれています。Microsoft  
  
Defender for Identity を使用する Microsoft Entra テナントがあります。AD DS フォレストはテナントと同期しています。AD  
  
DS ドメインコントローラーへの LDAP シンプルバインドを識別するハンティングクエリを作成する必要があります。  
  
どのテーブルをクエリすればよいでしょうか？

- A. AADサービスプリンシパルリスクイベント
- B. AADDomainServicesAccountLogon
- C. サインインログ
- D. アイデンティティログオンイベント

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)  

**解説:**
Defender for Identityで「LDAP Simple Bind（平文認証）」を検出するためのハンティングクエリ対象テーブル。
Defender for Identity（旧AATP）のログは **`IdentityLogonEvents`** や `IdentityQueryEvents`, `IdentityDirectoryEvents` などに統合されています。
LDAPのクリアテキストパスワード使用（Simple Bind）は、ログオン試行の一種またはディレクトリサービスへのアクセスイベントとして記録されます。
正解は **`IdentityLogonEvents`** (D) です。
LogonTypeやProtocolとして「LDAP」が含まれ、FailureReasonやAdditionalFieldsで「Clear text」が含まれるものを探します。
A, Bは存在しないかAAD関連。C（SignInLogs）はEntra ID（Azure AD）のログであり、オンプレミスADのLDAPバインドは記録されません。

*コミュニティ投票の配分*

D（100％）

質問5 トピック7

HOTSPOT  
\-  
  
Microsoft 365 サブスクリプションをお持ちです。  
  
グループの変更または削除要求を送信したすべてのセキュリティプリンシパルを特定する必要があります。KQL  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image286.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)

**正解:** ![](https://img.examtopics.com/sc-200/image287.png)

**解説:**
AuditLogsからグループ変更/削除を行ったセキュリティプリンシパル（Initiator）をクエリするKQL。

1. **Filter**: **`where OperationName in ("Update group", "Delete group")`**。グループの変更または削除操作をフィルタリングします。
2. **Project**: **`InitiatedBy.user.userPrincipalName`**（またはそれに類するパス）。操作を行ったユーザー（Initiator）のUPNを取得します。
   JSON構造の `InitiatedBy` フィールドからユーザープリンシパル名を展開します。
   `extend User = tostring(InitiatedBy.user.userPrincipalName)` などの形になります。

質問6 トピック7

Microsoft 365 サブスクリプションで Microsoft Defender for Endpoint プラン 2 が利用されており、Device1 という macOS デバイスが含まれています。Device1  
  
で発生した Defender for Endpoint エージェントのアラートを調査する必要があります。このソリューションは、以下の要件を満たす必要があります。  
  
• Device1 上のアクティブなネットワーク接続をすべて特定する。  
• Device1 で実行中のプロセスをすべて特定する。  
• Device1 のログイン履歴を取得する。  
• 管理作業を最小限に抑える。Microsoft  
  
Defender ポータルから最初に行うべきことは何でしょうか？

- A. \[デバイス\] から、\[デバイス 1 の調査パッケージの収集\] をクリックします。
- B. エンドポイントの高度な機能から、Live Response の署名されていないスクリプトの実行を有効にします。
- C. デバイスから、デバイス 1 でライブ応答セッションを開始します。
- D. エンドポイントの高度な機能から、認証済みテレメトリを無効にします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)   [議論   14](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)  

*コミュニティ投票の配分*

A（72％）

C（28％）

質問7 トピック7

HOTSPOT  
\-  
  
Microsoft Sentinel ワークスペースがあります。Microsoft  
  
SharePoint Online および OneDrive サイトからのデータを視覚化する予定です。  
  
このビジュアル用の KQL クエリを作成する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• すべてのワークロードを単一の操作として選択する。  
• Operations と Users という 2 つのパラメーターを含める。  
• 結果から、サイト URL の空値を除外する。  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image288.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)

**正解:** ![](https://img.examtopics.com/sc-200/image289.png)

**解説:**
SharePoint/OneDriveデータの可視化KQL。

1. **Filter workloads**: **`OfficeActivity | where OfficeWorkload in ('SharePoint', 'OneDrive')`**。両方のワークロードを選択します。
2. **Parameters**: **`| where OfficeWorkload in ({Operations}) and UserId in ({Users})`**？
   質問要件「Include two parameters named Operations and Users」。
   OperationsパラメータでOperation（FileDownloadedなど）を、UsersパラメータでUserIdをフィルタするのが自然です。
   しかし、画像（image289）の選択肢を見ると、`OfficeWorkload` に対するフィルタではなく、`Operation` と `UserId` に対するフィルタを選んでいると思われます。
   正解: `where Operation in ({Operations})` ... `where UserId in ({Users})`。
3. **Exclude empty URLs**: **`| where isnotempty(Site_Url)`**。

質問8 トピック7

HOTSPOT  
\-  
  
カスタムブックを含むMicrosoft Sentinelワークスペースがあります。  
  
セキュリティイベントの概要をクエリする必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• 過去1週間に取り込まれたセキュリティイベントの数を特定する。  
• 日別のイベント数をグラフに表示する。  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image305.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)

**正解:** ![](https://img.examtopics.com/sc-200/image306.png)

**解説:**
セキュリティイベント数を集計するKQL（パラメータ使用）。

1. **Time range**: **`SecurityEvent | where TimeGenerated > ago(7d)`**。過去1週間。
2. **Filter by text1**: **`| where EventID == {text1}`**（またはActivityがtext1）。パラメータ `text1` で何らかのフィールド（恐らくEventIDやActivity名）をフィルタします。
3. **Group by grouptime1**: **`| summarize count() by bin(TimeGenerated, {grouptime1})`**。
   `grouptime1` は時間の粒度（1d, 1hなど）を表すパラメータと想定されるため、`bin(TimeGenerated, {grouptime1})` でグルーピングしてチャート表示します。
   最後に `render timechart` を付けます。

質問9 トピック7

HOTSPOT  
\-  
  
Microsoft Sentinel ワークスペースに、Workbook1 というカスタム ワークブックが含まれています。Workbook1  
  
に、ログオン イベント ID が 4624 および 4634 のアカウントのログオン回数を表示するビジュアルを作成する必要があります。  
  
クエリをどのように完成させるべきでしょうか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image307.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)

**正解:** ![](https://img.examtopics.com/sc-200/image308.png)

**解説:**
特定EventIDのログオン数を表示するKQL。

1. **Filter**: **`SecurityEvent | where EventID in (4624, 4634)`**。
2. **Summarize**: **`| summarize count() by Account`**。アカウントごとのログオン回数を集計します。
3. **Visualization**: **`| render barchart`**（またはpiechart）。テーブル形式でもよいですが、ビジュアル（Visual）を作成とあるのでチャートにします。
正解画像では単純な `summarize count() by Account` などを選んでいると思われます。

質問10 トピック7

Microsoft Defender for Endpoint を使用しているオンプレミスの Windows 11 デバイスが 500 台あります。  
ネットワーク デバイスの検出を有効にします。  
  
検出されたネットワーク デバイスを識別し、各ネットワーク デバイスを検出したオンボード デバイスの ID を返すハンティング クエリを作成する必要があります。  
  
どの組み込み関数を使用すればよいでしょうか。

- A. SeenBy()
- B. デバイスからIP()
- C. 次()
- D. current\_cluster\_endpoint()

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)  

*コミュニティ投票の配分*

A（100％）

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/35/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 36 ページを表示しています。

410問中**351 - 360**問 を表示
