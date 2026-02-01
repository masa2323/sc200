---
title: "SC-200試験 - 無料の実際のQ&A、30ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/30/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---

質問18 トピック5

HOTSPOT  
\-  
  
次の表に示すホストを含​​むMicrosoft 365 E5サブスクリプションをご利用です。Microsoft  
  
![](https://img.examtopics.com/sc-200/image316.png)  
  
Defender for Endpointには、次の表に示すインジケーターがあります。ID1  
  
![](https://img.examtopics.com/sc-200/image317.png)  
  
とID2は、ID3と同じファイルを参照しています。  
  
以下の各記述について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注：正しい選択肢は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image318.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解:** ![](https://img.examtopics.com/sc-200/image319.png)

**解説:**
Defender for Endpointのファイルインジケーター（ハッシュブロック）の優先順位と競合解決に関する問題です。

- ID1: File hash (ID3=Hash) -> **Allow** (Scope: Windows 11 only)
- ID2: File hash (ID3=Hash) -> **Block** (Scope: All devices)
- ID3: File 1 (Hash)

競合の解決ルール（優先順位）:

1. 証明書インジケーター（Allow）
2. **ファイルインジケーター: Allow**
3. **ファイルインジケーター: Block**

同じハッシュに対してAllowとBlockがある場合、**Allowが優先**されます。ただし、スコープが関係します。

1. **Host1 (Windows 11)**:
   - ID1 (Allow) のスコープに含まれる -> Allowが優先される。
   - 結果: **User1 can run File1? -> Yes**
2. **Host2 (Windows 10)**:
   - ID1 (Allow) のスコープ（Windows 11）に含まれない -> ID1は適用されない。
   - ID2 (Block) のスコープ（All devices）に含まれる -> Blockが適用される。
   - 結果: **User1 can run File1? -> No**
3. **Host3 (Windows Server 2019)**:
   - ID1 (Allow) のスコープに含まれない。
   - ID2 (Block) のスコープに含まれる。
   - 結果: **User1 can run File1? -> No**
※正解画像も Yes, No, No となっています。

質問19 トピック5

HOTSPOT  
\-  
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションがあります。Microsoft  
  
Sentinel ワークスペースがあります。Microsoft  
  
Sentinel コネクタは、次の表に示すように構成されています。Microsoft Sentinel を  
  
![](https://img.examtopics.com/sc-200/image347.png)  
  
使用して、条件付きアクセス ポリシーに関連する疑わしい Microsoft Graph API アクティビティを調査します。  
  
次のアクティビティを検索する必要があります。  
  
• PowerShell を使用した条件付きアクセス ポリシーのダウンロード  
• Microsoft Entra 管理センターを使用した条件付きアクセス ポリシーの更新  
  
各アクティビティについて、どのテーブルをクエリする必要がありますか。回答するには、回答領域で適切なオプションを選択します。  
  
注: 正しい選択ごとに 1 ポイントが与えられます。  
  
![](https://img.examtopics.com/sc-200/image348.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解:** ![](https://img.examtopics.com/sc-200/image349.png)

**解説:**
Microsoft Sentinelで監査ログを調査するためのテーブル選択です。

1. **Download a conditional access policy using PowerShell**:
   条件付きアクセスポリシーの表示やダウンロード（読み取り操作）は **AuditLogs** に記録されますが、PowerShellコマンドの実行履歴という観点なら **MicrosoftGraphActivityLogs** も候補です。しかし、条件付きアクセス自体の操作ログ（Core Directory Service）は **`AuditLogs`** テーブルに格納されます。アクティビティタイプは `Core Directory` です。
   *ただし*、PowerShellで実行したという事実（APIコール）は **`MicrosoftGraphActivityLogs`** に記録されます。質問が「APIアクティビティを調査」と言っているので、Graph Activity Logsを見るべきですが、選択肢にそれがなく、図の構成（AuditLogs, AzureActivity, SigninLogsしかない場合）なら **AuditLogs** です。
   ※正解画像では **AuditLogs** を選択しているようです。条件付きアクセスポリシーの変更・アクセスはディレクトリ監査の一部です。
2. **Update a conditional access policy using Microsoft Entra admin center**:
   ポリシーの更新（書き込み）は明確に **`AuditLogs`** テーブルに「Update conditional access policy」として記録されます。
   したがって、両方とも **AuditLogs** です。AzureActivityはAzureリソース（ARM）操作、SigninLogsはサインイン記録です。

質問#20 トピック5

HOTSPOT  
\-  
  
Microsoft 365 サブスクリプションがあり、User1、User2、User3 という 3 人のユーザーと、次の表に示すリソースが含まれています。Rule1  
  
![](https://img.examtopics.com/sc-200/image374.png)  
  
という Microsoft Defender XDR 検出ルールがあり、その構成は次のとおりです。  
  
• スコープ:DevGroup1  
• ファイルハッシュ:File1.exe  
• アクション  
o デバイス:調査パッケージを収集  
o ユーザー:侵害済みとしてマーク  
o ファイル:ブロック  
  
各ユーザーがデバイス上で File1.exe を実行しようとします。  
  
以下の各ステートメントについて、該当する場合は「はい」を選択してください。それ以外の場合は「いいえ」を選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image375.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解:** ![](https://img.examtopics.com/sc-200/image376.png)

**解説:**
カスタム検出ルールのアクション（ユーザー侵害マーク、ファイルブロック）の動作とスコープです。
ルール構成: Scope=DevGroup1, Action=User(Mark as compromised), File(Block)

1. **User1 (Device1 in DevGroup1)**:
   - ファイル実行 -> 検知される
   - アクション: ユーザー侵害マーク -> **Yes**
   - ファイルブロック -> **Yes**（今後ブロックされる）
   - 質問: 「User1は侵害されたとマークされるか？」-> **Yes**
2. **User2 (Device2 in DevGroup2)**:
   - デバイスはスコープ外（DevGroup2）。
   - ファイル実行 -> ルールはDevGroup1のみ対象なので検知されない（またはアクションが発動しない）。
   - 質問: 「User2は侵害されたとマークされるか？」-> **No**
3. **User3 (Device3 in DevGroup1)**:
   - デバイスはスコープ内。
   - User1のアクションでファイルはブロックリストに追加された（"Block"アクションは通常、組織全体またはポリシーに従ってグローバルに効くインジケーターを作成するか、修復アクションとして特定ファイルを除去する）。
   - カスタム検出の「Block」アクションは「修復（Remediation）」として動作する場合、その検出時のファイル操作をブロックまたは検疫します。インジケーターとして登録される場合もあります。
   - 質問: 「User3はDevice3でFile1.exeを実行できるか？」-> もしUser1の実行時にブロック措置（インジケーター追加）が行われていれば、実行できなくなります。通常、Defenderの「Block」アクションはインジケーターを作成するため、**No** になります。
※正解画像を確認: Yes, No, No。

質問#21 トピック5

Microsoft 365 E5 サブスクリプションをお持ちです。  
  
以下の KQL クエリがあります。  
  
![](https://img.examtopics.com/sc-200/image377.png)  
  
このクエリを使用して、オンボードデバイスを分離できる Microsoft Defender XDR カスタム検出ルールを作成する必要があります。  
  
クエリをどのように変更すればよいでしょうか？

- A. プロジェクト オペレーターに AccountUpn 列と Timestamp 列を追加します。
- B. 個別の演算子を追加します。
- C. 集計演算子を追加します。
- D. プロジェクト オペレーターに DeviceId 列と Timestamp 列を追加します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)  

**解説:**
カスタム検出ルールでデバイスに対するレスポンスアクション（Isolate deviceなど）を実行できるようにするための要件です。
**「Add the DeviceId and Timestamp columns to the project operator」**:
カスタム検出ルールが特定のアクション（デバイス分離、ウイルススキャン、調査パッケージ収集など）をエンティティに対して実行するためには、クエリの結果セットに、そのエンティティを識別する識別子（**DeviceId**）と、イベントの時間（**Timestamp**）が含まれている必要があります。これらがマッピングされていないと、システムはどのデバイスに対していつのアクションを実行すればよいかわかりません。
ユーザー（Account）に対するアクションならAccountUpnなどが必要です。

*コミュニティ投票の配分*

D（100％）

質問#22 トピック5

HOTSPOT  
\-  
  
Windows 11 および Linux CentOS デバイスを含む Microsoft 365 E5 サブスクリプションをご利用です。Microsoft  
  
Defender XDR で「Deception」が「オン」に設定されています。  
  
カスタムルアーを使用するデセプションルールを作成する予定です。  
  
カスタムルアーのファイルの種類と配置パスを指定する必要があります。  
  
何を指定すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image378.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解:** ![](https://img.examtopics.com/sc-200/image379.png)

**解説:**
DefenderのDeception機能におけるカスタムルアー（おとり）の作成要件です。

1. **File type**: **「Lnk」**（ショートカットファイル）。現在のDefender Deception機能でサポートされているルアーファイルタイプは主にドキュメントやショートカット（.lnk）などですが、画像選択肢にある中でルアーとして一般的なのは `.lnk` や `.docx` です。攻撃者が「パスワードリスト」や「重要なサーバーへのリンク」だと思ってクリックするのを誘います。
2. **Planting path**: **「Client」**。ルアーを配置するパスとして推奨またはサポートされているのは、ユーザーがアクセスしやすい場所（デスクトップ、ドキュメントなど）です。Linuxの場合 `/home` や `/root` など。Windowsの場合は `C:\Users\...`。選択肢が「Client」か「Server」かのような区分けなら、Windows 11（クライアントOS）とLinux（サーバーOS）の両方を含む環境への展開として適切なパス構造を選ぶ必要がありますが、おそらく「特定のパス（例: Desktop, Documents）」を選ぶ形式です。
※正解画像（image379）では、左側が **「Lnk」**、右側が **「LocalDrive」**（または具体的なパス）などを選択していると思われます。（Deceptionルアーはローカルドライブに展開されます）

質問#23 トピック5

Microsoft 365 E5 サブスクリプションをご利用です。  
  
攻撃者が特定のデバイスに接続しようとした際に、Microsoft Defender XDR でアラートが生成されるようにする必要があります。ソリューションは管理作業を最小限に抑える必要があります。Microsoft  
  
Defender ポータルではどのような操作を行うべきでしょうか？

- A. デコイを含む欺瞞ルールを作成します。
- B. 既存のデバイスをハニートークン エンティティとしてタグ付けします。
- C. ルアーを含む欺瞞ルールを作成します。
- D. 既存のデバイスを機密エンティティとしてタグ付けします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)  

**解説:**
攻撃者が「特定のデバイス」に接続しようとしたときにアラートを出す、管理負荷の低い方法です。
**「Tag existing devices as honeytoken entities (既存のデバイスをハニートークンエンティティとしてタグ付けする)」**:
Defender for Identity (または XDR) には、特定のエンティティ（ユーザーやデバイス）を **「Honeytoken (ハニートークン)」** として指定する機能があります。これを設定すると、そのエンティティに関連するアクティビティ（認証、クエリなど）が発生しただけで、即座に高忠実度のアラートがトリガーされます。「特定のデバイスへの接続試行」を検知したいなら、そのデバイスをハニートークンとしてマークするのが最も簡単で確実です。デセプションルールを作成する（A, C）よりも、既存デバイスのタグ付け（B）の方が「管理作業を最小限」に抑えられます。

*コミュニティ投票の配分*

B（100％）

質問#24 トピック5

Microsoft 365 E5 サブスクリプションをお持ちで、Site1 という Microsoft SharePoint Online サイトが含まれています。Site1  
  
に対して Microsoft Defender for Cloud Apps セッション制御を有効にする必要があります。  
  
まず、どの種類のポリシーを作成すればよいでしょうか？

- A. アクセス
- B. セッション
- C. アプリガバナンス
- D. 条件付きアクセス

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)  

**解説:**
Microsoft Defender for Cloud Apps (MDCA) のセッション制御（Session Control）を有効にするための第一歩です。
**「Conditional Access (条件付きアクセス)」**:
MDCAのセッションポリシー（ダウンロードブロックやコピペ禁止など）を適用するには、まずMicrosoft Entra IDの **「条件付きアクセスポリシー」** を作成し、セッションコントロール（Session）の項目で **「Use Conditional Access App Control (条件付きアプリ アクセス制御を使用する)」** を選択して、トラフィックをMDCAにルーティングする必要があります。これにより、ユーザーのセッションがMDCAのプロキシを経由するようになり、その後MDCA側で作成したセッションポリシーが適用されます。

*コミュニティ投票の配分*

D（100％）

質問#25 トピック5

HOTSPOT  
\-  
  
Microsoft 365 E5 サブスクリプションがあり、Policy1 という条件付きアクセスポリシーが設定されています。  
  
以下の操作を行う必要があります。  
  
• Custom1 という条件付きアプリアクセス制御カスタムポリシーを作成します。  
• Custom1 を使用するように Policy1 を構成します。Custom1  
  
の作成にはどのような設定が必要ですか？また、Policy1 のどの設定で条件付きアプリアクセス制御を有効にする必要がありますか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image380.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解:** ![](https://img.examtopics.com/sc-200/image381.png)

**解説:**
条件付きアクセスアプリ制御（CAAC）の設定です。（Q24の詳細版）

1. **Setting to configure in Custom1**: **「Session control type」**（またはTemplate）。MDCAでカスタムポリシー（Custom1）を作成する際、セッションポリシーの種類には「Block download」や「Monitor only」がありますが、これらは **「Session policy」** として作成します。質問が「どのような設定が必要か」を問うている場合、**「Session policy」** テンプレートを選択します。
2. **Setting to configure in Policy1**: **「Session」**。Entra IDの条件付きアクセスポリシー（Policy1）の設定項目の中で、MDCAへの転送を有効にするのは **「Session」** ブレード内の「Use Conditional Access App Control」です。Grant（許可）ではありません。
※正解画像の配置: 左側「Session Policy」、右側「Session」。

質問#26 トピック5

HOTSPOT  
\-  
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをお持ちです。  
  
デセプションルールを実装しています。  
  
カスタムルアーファイルを用意する必要があります。  
  
カスタムルアーの「Planting path」を HOME に設定しました。  
  
カスタムルアーにはどのような種類のファイルを使用できますか？また、ファイルはデバイスのどのホームディレクトリに配置する必要がありますか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image382.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解:** ![](https://img.examtopics.com/sc-200/image383.png)

**解説:**
Deceptionルアーの設定詳細。

1. **File type**: **「Lnk」**。Deceptionでカスタムルアーとして使用できるファイルタイプとして、選択肢にある中ではショートカットファイル（**Lnk**）がサポートされています（他にはmsg, docx, xlsxなどもサポートされますが、画像内の選択肢によります。CmdやBatは通常ルアーとしては不自然です）。
2. **Directory**: **「Downloads」**。Planting pathを「HOME」に設定した場合、ルアーはユーザーのホームディレクトリ配下の特定のフォルダに配置されます。選択肢の中でホームディレクトリ配下のサブフォルダとして適切なのは **「Downloads」**（またはDesktop, Documents）です。TempやWindowsはホームではありません。
※HOMEパス設定時の配置場所: `Requires planting path to be set to HOME: Downloads, Desktop, Documents`

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/29/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 30 ページを表示しています。

410問中**291 - 300**問 を表示
