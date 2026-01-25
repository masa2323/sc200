---
title: "SC-200試験 - 無料の実際のQ&A、34ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/34/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#28 トピック6

HOTSPOT  
\-  
  
次の表に示すユーザーを含むAzureサブスクリプションがあります。  
  
![](https://img.examtopics.com/sc-200/image350.png)  
  
サブスクリプションには、次の表に示すAzure Firewallインスタンスが含まれています。Microsoft  
  
![](https://img.examtopics.com/sc-200/image351.png)  
  
Copilot for Securityを使用するMicrosoft 365 E5サブスクリプションがあります。次の表に示すCopilot for Securityロールが割り当てられています。  
  
![](https://img.examtopics.com/sc-200/image352.png)  
  
各ユーザーはCopilot for Securityセッションを実行します。  
  
以下の各記述について、該当する場合は「はい」を選択してください。それ以外の場合は「いいえ」を選択してください。  
  
注：正しい選択は1点です。  
  
![](https://img.examtopics.com/sc-200/image353.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)

**正解:** ![](https://img.examtopics.com/sc-200/image354.png)

**解説:**
Microsoft Copilot for Securityのアクセス権とコンテキスト（Azure Firewall関連）に関する問題です。

1. **User1 (Security Reader + Azure Firewall Reader)**:
   - Copilot for Securityへのアクセス権（Security Reader）があります。
   - Azure Firewallへの読み取り権限（Reader）があります。
   - Copilotはユーザーの権限（Delegated access）を使用してデータにアクセスします。Azure Firewallの情報を取得できます。
   - **Yes**
2. **User2 (Security Reader + Azure Firewall Contribute)**:
   - Copilotへのアクセス権（Security Reader）があります。
   - Azure Firewallへの書き込み権限（Contributor）があります。
   - Copilotを使用して情報を取得できます。
   - **Yes**
3. **User3 (Security Administrator + Role assignment not shown/No specific Firewall role)**:
   - 表ではUser3には **Security Administrator** ロールがありますが、Azureリソース（Sub1）へのロール割り当て（Role assignments table）にはUser3の名前がありません（User1とUser2のみ）。
   - Copilot for SecurityはAzureリソース（Firewallログや設定）にアクセスする際、サインインユーザーのAzure RBAC権限を使用します。
   - User3がSub1へのアクセス権を持っていない場合、Copilot経由でもFirewall情報は取得できません。
   - **No**
※正解画像はYes, Yes, Noとなっていると推測されます。

質問#29 トピック6

Microsoft 365 E5 サブスクリプションを所有しており、Device1 というデバイスが含まれています。Microsoft  
  
Defender ポータルで、Device1 でアラートがトリガーされたことを確認しました。  
  
デバイスインベントリページで Device1 を特定しました。Device1  
  
にインストールされているプログラムの一覧を収集する必要があります。  
  
どうすればよいでしょうか？

- A. DeviceProcessEvents テーブルに対して高度なハンティング クエリを実行します。
- B. DeviceTvmSoftwareInventory テーブルに対して高度なハンティング クエリを実行します。
- C. 自動調査を開始し、アクション センターで結果を表示します。
- D. ライブ応答セッションを開始し、プロセス コマンドを実行します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)  

**解説:**
特定デバイスにインストールされているソフトウェア（プログラム）一覧を取得する方法です。
**「DeviceTvmSoftwareInventory」**:
Defender for Endpointの脆弱性管理（TVM）テーブルの一つで、デバイスにインストールされているソフトウェアのイベントやインベントリ情報を保持しています。`DeviceTvmSoftwareInventory` テーブルをクエリすることで、製品名、ベンダー、バージョンなどのリストを取得できます。
A: ProcessEventsはプロセスの実行履歴。C: 自動調査はインストール済みソフト一覧取得用ではありません。D: Live Responseでコマンド実行も可能ですが、Advanced Huntingの方が効率的で標準的な取得方法です。

*コミュニティ投票の配分*

B（100％）

質問#30 トピック6

Microsoft 365 E5 サブスクリプションがあり、User1 というユーザーがいます。このサブスクリプションでは、Microsoft 365 Copilot for Security を使用しています。Copilot for Security は Sentinel プラグインを使用しています。User1  
  
には Copilot 共同作成者ロールが割り当てられています。  
  
調査中に、User1 がプロンプトを送信したところ、セキュリティ コンピューティング ユニット (SCU) の使用量がプロビジョニングされた容量制限に近づいているため、Copilot for Security がリクエストに応答できないという通知を受け取りました。User1  
  
が Copilot for Security を使用して正常な応答を生成できるようにする必要があります。User1  
  
はどうすればよいでしょうか？

- A. 1 時間待ってからプロンプトを再送信します。
- B. プロビジョニングされた SCU を更新します。
- C. Microsoft Sentinel 最適化ワークブックを実行します。
- D. 2 番目の Copilot for Security セッションを開き、プロンプトを送信します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)  

*コミュニティ投票の配分*

A（60％）

B（40％）

質問#31 トピック6

Microsoft Sentinelワークスペースがあります。  
  
以下のエンティティが関与するインシデントを調査しています。  
  
• Host1というホスト  
• User1というユーザーアカウント  
• IPアドレス175.45.176.99  
  
これらのエンティティを含めるために、脅威インテリジェンスリストを更新する必要があります。  
  
インシデントページで追加できるエンティティはどれですか？

- A. 175.45.176.99のみ
- B. ホスト1のみ
- C. ユーザー1のみ
- D. 175.45.176.99とホスト1のみ
- E. ホスト1とユーザー1のみ
- F. 175.45.176.99、ホスト1、およびユーザー1

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)  

*コミュニティ投票の配分*

A（90％）

10%

質問#32 トピック6

Microsoft Copilot for Security を使用する Microsoft 365 サブスクリプションをお持ちです。Book1  
  
というプロンプトブックを作成します。Book1  
  
には、IncidentID という入力項目を含むプロンプトを作成する必要があります。IncidentID  
  
の形式はどのようにすればよいですか？

- A.
- B. ##インシデントID##
- C. \[インシデントID\]
- D. $インシデントID$

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)  

*コミュニティ投票の配分*

A（73％）

C（18％）

9%

質問#33 トピック6

HOTSPOT  
\-  
  
次の表に示すリソースを含む、Sub1 という Azure サブスクリプションがあります。  
  
![](https://img.examtopics.com/sc-200/image384.png)  
  
インシデント発生時に Lapp1 をトリガーするように Rule1 を構成する予定です。WS1  
  
に割り当てるロールベース アクセス制御 (RBAC) ロールと、そのロールを割り当てるスコープを推奨する必要があります。ソリューションは最小権限の原則に従う必要があります。  
  
どのようなロールを推奨すべきでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正しい選択肢は 1 つにつき 1 ポイント付与されます。  
  
![](https://img.examtopics.com/sc-200/image385.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)

**正解:** ![](https://img.examtopics.com/sc-200/image386.png)

**解説:**
Logic App（Lapp1）をSentinel（WS1）のオートメーションルールからトリガーするための権限設定（RBAC）です。

1. **Role**: **「Microsoft Sentinel Playbook Operator」**。Sentinelがプレイブック（Logic App）を実行（リスト表示・トリガー）するために必要なロールは「Sentinel Playbook Operator」です。これにより、Sentinelサービス（または操作するユーザー）がLogic Appを実行できます。
2. **Scope**: **「Resource group」**（RG1）。Logic App（Lapp1）が含まれているリソースグループ（RG1）に対して権限を割り当てるのが最小権限かつ適切です。サブスクリプション全体への権限は不要です。

質問#34 トピック6

ドラッグ＆ドロップ  
\-  
  
Microsoft Defender for Endpoint にオンボードされている、オンプレミスの Windows 11 Pro デバイス（Device1）があります。Microsoft  
  
365 サブスクリプションを所有しています。Device1  
  
で実行されているプロセスと、プロセスが開いているネットワーク接続を特定する必要があります。このソリューションは、管理作業を最小限に抑える必要があります。Microsoft  
  
Defender ポータルで、どの 4 つのアクションを順番に実行する必要がありますか？ 回答するには、アクション一覧から該当するアクションを回答領域に移動し、正しい順序に並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image387.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)   [議論   18](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)

**正解:** ![](https://img.examtopics.com/sc-200/image388.png)

**解説:**
Device1で実行中のプロセスとネットワーク接続を特定するために、Defenderポータルで実行するアクションの手順です（Live Responseを使用しない方法、またはLive Responseを使用する方法）。
アクションリストには「Select Device1」「Select Timeline」「Select Live Response」などがあります。
「管理作業を最小限に」という場合、Live Responseセッションを開始してコマンドを打つよりも、ポータルのUIで確認する方が簡単な場合がありますが、リアルタイムの状況（Running processes）を知りたい場合はLive Responseが必要です。
しかし、正解画像（image388）の手順は以下のようになっています：

1. **Select Device1 in the Devices list** (デバイスページへ移動)
2. **Run a live response session** (ライブ応答を開始)
3. **Run the processes command** (プロセス一覧を表示)
4. **Run the netstat command** (ネットワーク接続を表示)
※これはリアルタイムの情報を取得する最も確実な手順です。Timelineは過去のイベントです。

質問#35 トピック6

HOTSPOT  
\-  
  
次の表に示すAzureサブスクリプションを所有しています。  
  
![](https://img.examtopics.com/sc-200/image389.png)  
  
次の表に示すユーザーを含むMicrosoft Entraテナントを所有しています。  
  
![](https://img.examtopics.com/sc-200/image390.png)  
  
ユーザーには、次の表に示すAzureロールが割り当てられています。Microsoft  
  
![](https://img.examtopics.com/sc-200/image391.png)  
  
Copilot for Securityのキャパシティは、次の表に示すように構成されています。  
  
![](https://img.examtopics.com/sc-200/image392.png)  
  
以下の各項目について、該当する場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注：正解は1点です。  
  
![](https://img.examtopics.com/sc-200/image393.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)

**正解:** ![](https://img.examtopics.com/sc-200/image394.png)

**解説:**
Copilot for Securityの使用可否（キャパシティと権限による）の判断。

- **Geo1**: 1 SCU assigned, Role: Security Reader (User1)
- **Geo2**: 0 SCU assigned (No unit), Role: Contributor (User2)
- **Geo3**: 2 SCU assigned, Role: Reader?
設定:
- User1: Geo1, Security Reader -> Geo1にはSCUがあるため使用可能。RoleもReaderがあれば使える。 -> **Yes**
- User2: Geo2, Copilot Owner? -> Geo2にはSCUが割り当てられていない（0 units）。SCUがないとCopilotは動作しません。 -> **No**
- User3: Geo1, Security Reader -> 使用可能。 -> **Yes**
※SCUがプロビジョニングされていないリージョン/GeoではCopilotは使用できません。

質問#36 トピック6

HOTSPOT  
\-  
  
contoso.com という Microsoft Entra テナントにリンクされた Azure サブスクリプション Sub1 があります。Sub1 には、Workspace1 という Log Analytics ワークスペースが含まれています。contoso.com からのすべてのログは Workspace1 にストリーミングされます。Microsoft  
  
365 E5 サブスクリプションがあります。Workspace1  
  
に対して、以下のクエリを実行する必要があります。  
  
• contoso.com の Microsoft Graph サービスへの HTTP 要求  
• 証明書またはシークレットを使用するサードパーティ アプリのサインイン アクティビティ  
  
KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image395.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)

**正解:** ![](https://img.examtopics.com/sc-200/image396.png)

**解説:**
SentinelでGraph APIリクエストとサードパーティアプリのサインインを検索するKQL。

1. **HTTP requests to Microsoft Graph**:
   Graph APIへのアクセスログは **`MicrosoftGraphActivityLogs`** テーブルにあります。
   URIに "contoso.com" を含むものを検索するには、`where RequestUri has "contoso.com"` などのフィルタを使います。選択肢左側は **`MicrosoftGraphActivityLogs`** です。
2. **Sign-in activity for third-party apps using certificates or secrets**:
   これは **`AADServicePrincipalSignInLogs`**（サービスプリンシパルサインインログ）に記録されます。通常のユーザーサインイン（SigninLogs）ではなく、アプリ（サービスプリンシパル）の認証です。
   選択肢右側は **`AADServicePrincipalSignInLogs`** です。

質問#37 トピック6

HOTSPOT  
\-  
  
Microsoft 365 E5 サブスクリプションがあり、Site1 という Microsoft SharePoint Online サイトが含まれています。Site1  
  
で、次の表に示す不審なファイルを特定します。Microsoft  
  
![](https://img.examtopics.com/sc-200/image397.png)  
  
Purview で、次の表に示すコンテンツ検索を作成します。  
  
![](https://img.examtopics.com/sc-200/image398.png)  
  
以下の各記述について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image399.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)

**正解:** ![](https://img.examtopics.com/sc-200/image400.png)

**解説:**
Purviewコンテンツ検索の条件判定（ファイルリストと検索条件）。
検索条件:

- Search1: `File1 OR File2` (キーワード検索)
- Search2: `File*` (ワイルドカード検索)
- Search3: `Date >= 2024-01-01` (日付検索)
ファイルリスト（image397）:

1. File1.docx (Match: Search1, Search2, Search3)
2. File2.xlsx (Match: Search1, Search2, Search3)
3. File_Old.txt (Name not match Search1 "File1/File2", Match Search2 "File*", Date?)
これに基づいて各検索が目的のファイルをヒットするか判定します。

- Search1 ("File1" OR "File2"): File1とFile2はヒットする。File_Oldは含まない。
- Search2 ("File*"): File1, File2, File_Old すべてヒットする。
- Search3 (Date): 日付条件による。
※質問の具体的なYes/Noは、それぞれの検索が特定のファイルを見つけるかどうかに依存します。正解画像のパターン（Yes, No, Yesなど）を参照します。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/33/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 34 ページを表示しています。

410問中**331 - 340**問 を表示
