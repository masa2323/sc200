---
title: "SC-200試験 - 無料の実際のQ&A、35ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/35/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#38 トピック6

Microsoft 365 E5 サブスクリプションを所有しており、Device1 というデバイスが含まれています。Microsoft  
  
Defender ポータルで、Device1 でアラートがトリガーされたことを確認しました。  
  
デバイスインベントリページで Device1 を特定しました。Device1  
  
にインストールされているプログラムの一覧を収集する必要があります。  
  
どうすればよいでしょうか？

- A. ライブ応答セッションを開始し、プロセス コマンドを実行します。
- B. 自動調査を開始し、アクション センターで結果を表示します。
- C. ライブ応答セッションを開始し、分析コマンドを実行します。
- D. DeviceTvmSoftwareInventory テーブルに対して高度なハンティング クエリを実行します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)  

**解説:**
特定デバイスのインストール済みプログラム一覧を収集する方法（Q29の重複問題）。
Answerは **D**。`DeviceTvmSoftwareInventory` テーブルに対するAdvanced Huntingクエリが、インストール済みソフトウェアの一覧を取得するための標準的な方法です。
※Q29では選択肢Bでしたが、この問題では選択肢Dに配置されています。内容は同じです。
A: Live Responseでコマンド実行も可能ですが、Advanced Huntingの方が効率的。
B: 自動調査は脅威の修復用。
C: Live Response分析コマンド（例：Analyze）はファイル提出用。

*Community vote distribution*

D (100%)

質問#39 トピック6

Microsoft 365 E5 サブスクリプションを所有しており、Device1 というデバイスが含まれています。Microsoft  
  
Defender ポータルで、Device1 でアラートがトリガーされたことを確認しました。  
  
デバイスインベントリページで Device1 を特定しました。Device1  
  
にインストールされているプログラムの一覧を収集する必要があります。  
  
どうすればよいでしょうか？

- A. 調査パッケージを収集し、アクション センターから結果をダウンロードします。
- B. ライブ応答セッションを開始し、分析コマンドを実行します。
- C. DeviceProcessEvents テーブルに対して高度なハンティング クエリを実行します。
- D. DeviceTvmInfoGathering テーブルに対して高度なハンティング クエリを実行します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)

**Correct Answer:** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)  

**解説:**
特定デバイスのプログラム一覧収集（Q38の類題ですが、選択肢が異なります）。
質問：プログラム一覧を収集する。
選択肢:

- A. **Collect an investigation package (調査パッケージを収集)** and download from Action Center.
- B. Live Response...
- C. DeviceProcessEvents...
- D. DeviceTvmInfoGathering...
**「DeviceTvmSoftwareInventory」が選択肢にない場合**の代替案です。
調査パッケージ（Investigation Package）には、システム情報、ネットワーク接続、実行プロセス、**インストール済みソフトウェアリスト** などが含まれています。したがって、選択肢D（TvmInfoGatheringは情報収集イベントでありインベントリそのものではない）やC（プロセス）よりも、**調査パッケージの収集 (A)** が要件（プログラム一覧の収集）を満たす最も確実な方法になります。
Advanced HuntingのSoftwareInventoryテーブルがあればそれが一番ですが、ない場合は調査パッケージです。

*Community vote distribution*

A (88%)

13%

質問#40 トピック6

Tenant1 と Tenant2 という 2 つの Microsoft Entra テナントがあります。各テナントは Azure サブスクリプションにリンクされています。Tenant1 には Group1 というグループが含まれています。Tenant2 には Group2 というグループが含まれています。  
  
各テナントに Microsoft Sentinel を実装する必要があります。ソリューションは、次の要件を満たす必要があります。  
  
• Group1 が単一のワークスペースで Tenant1 と Tenant2 のセキュリティ インシデントを管理できることを確認する  
。• Group2 が Tenant2 のセキュリティ インシデントのみを管理できることを確認する。  
• ゲスト アカウントの使用を最小限に抑える。  
• 管理の労力を最小限に抑える。  
• コストを最小限に抑える。  
  
ソリューションには何を含める必要がありますか？

- A. 1つのワークスペースと特権ID管理（PIM）
- B. 1つのワークスペースと複数のロールベースアクセス制御（RBAC）ロールの割り当て
- C. 2つのワークスペースとAzure Lighthouse
- D. 2つのワークスペースと細分化された委任管理者権限（GDAP）

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)  

**解説:**
2つのテナント（Tenant1, Tenant2）のSentinelワークスペース設計とMSSP/管理要件の実現。
要件:

- Group1 (Tenant1) -> Tenant1とTenant2の両方を管理したい。
- Group2 (Tenant2) -> Tenant2のみ管理したい。
- ゲストアカウント最小化、管理最小化、コスト最小化。
**「Two workspaces and Azure Lighthouse」**:
各テナントにデータを残すコンプライアンス要件や、テナントごとの管理（Group2がTenant2のみ見る）を考慮すると、**各テナントに1つずつワークスペース（計2つ）** を作成し、**Azure Lighthouse** を使用してTenant1の担当者（Group1）がTenant2のワークスペースを管理できるようにするのがベストプラクティスです。
- Azure Lighthouseを使えば、ゲストアカウントを作成せずに、自テナントのIDで他テナントのリソース（Sentinel）を管理できます。
- Group2は自テナント（Tenant2）のワークスペースに権限を持てばよく、他は見えません。
- 1つのワークスペースに統合する場合（A, B）、ログ転送（Diagnostic Settings）の設定が複雑になり、コスト（データ転送）や遅延が発生する可能性があります。また、アクセス制御（Group2にTenant2のデータだけ見せる）にはリソース中心のRBACが必要で複雑になります。Lighthouseならワークスペース単位の境界を維持しつつ統合管理できます。

*Community vote distribution*

C (100%)

質問#41 トピック6

HOTSPOT  
\-  
  
contoso.com という Microsoft Entra テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。contoso.com  
  
のロールの変更を識別するために、Microsoft Graph アクティビティ ログをクエリする必要があります。KQL  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image464.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image465.png)

**解説:**
Graphアクティビティログから「ロールの変更」を特定するKQL。

1. **Target**: **`MicrosoftGraphActivityLogs`**。Graph APIのログを対象にします。
2. **Filter**: **`RequestUri has "roleManagement"`**。ロールの割り当てや変更はGraph APIの `/roleManagement` エンドポイントに対する操作（POST, PUT, PATCHなど）として記録されます。`DirectoryRole` なども関連しますが、Graph APIでは `roleManagement` パスが使われます。
※選択肢に `DirectoryRole` がある場合、AuditLogs（Core Directory）の話ならそちらですが、質問は「Microsoft Graph activity logs」をクエリすると言っています。Graph API経由でのロール管理は `roleManagement` リソースへのリクエストです。

質問#42 トピック6

HOTSPOT  
\-  
  
Microsoft Defender for Endpoint を使用する Microsoft 365 サブスクリプションがあり、以下のデバイスが含まれています。  
  
• デバイス1: Windows 11 Pro を実行  
• デバイス2: Windows Server を実行  
• デバイス3: Ubuntu Linux を実行  
  
File1.exe、File2.zip、File3.ps1 という 3 つの不審なファイルを特定しました。  
  
これらのファイルを詳細分析で調査する必要があります。  
  
詳細分析をサポートしているデバイスと、詳細分析に提出できるファイルはどれですか？ 回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image466.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image467.png)

**解説:**
Deep Analysis（詳細分析）機能のサポート環境。

1. **Supported devices**: **「Device1 (Windows 11) and Device2 (Windows Server) only」**。現在、Deep Analysis（ファイルのサンドボックス送信・分析）機能は **Windows 10/11** および **Windows Server 2016/2019/2022** などでサポートされています。LinuxやmacOSでのサポートは限定的または非対応です（Linux向けの手動アップロードポータルはあるかもしれませんが、MDE連携機能としてはWindowsが主です）。Device3（Linux）は対象外となる可能性が高いです。
   *注*: MDE for Linuxでもクラウド保護はありますが、Deep Analysisへの「Submit」アクションは主にWindowsエージェントで利用可能です。
2. **Supported files**: **「File1.exe only」**。
   Deep Analysisがサポートするファイル形式は **実行可能ファイル（.exe, .dll, .sys）** や一部の管理コードです。.zipファイル（File2）やスクリプト（File3.ps1）はDeep Analysisの直接の対象ではありません（.zipは解凍後のexeなら可、ps1はAMSI等で解析されるがDeep Analysis送信対象外）。
   したがって、**Device1/2** と **File1.exe** が正解です。

質問#43 トピック6

Microsoft 365 E5 サブスクリプションを所有しており、Device1 というデバイスが含まれています。Microsoft  
  
Defender ポータルで、Device1 でアラートがトリガーされたことを確認しました。  
  
デバイスインベントリページで Device1 を特定しました。Device1  
  
にインストールされているプログラムの一覧を収集する必要があります。  
  
どうすればよいでしょうか？

- A. 自動調査を開始し、アクション センターで結果を表示します。
- B. 調査パッケージを収集し、アクション センターから結果をダウンロードします。
- C. DeviceTvmInfoGathering テーブルに対して高度なハンティング クエリを実行します。
- D. DeviceProcessEvents テーブルに対して高度なハンティング クエリを実行します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)   [議論](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)  

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)  

**解説:**
プログラム一覧の収集（Q29, Q38, Q39の類題）。
選択肢に:

- A. 自動調査
- B. **調査パッケージを収集 (Collect investigation package)**
- C. DeviceTvmInfoGathering
- D. DeviceProcessEvents (インベントリではない)
Advanced Huntingの `DeviceTvmSoftwareInventory` が選択肢にないパターンです。
この場合、Q39と同様に **B. 調査パッケージの収集** が正解となります。調査パッケージにはインストール済みプログラムの一覧が含まれます。

質問#44 トピック6

Microsoft 365 E5 サブスクリプションを所有しており、Device1 というデバイスが含まれています。Microsoft  
  
Defender ポータルで、Device1 でアラートがトリガーされたことを確認しました。  
  
デバイスインベントリページで Device1 を特定しました。Device1  
  
にインストールされているプログラムの一覧を収集する必要があります。  
  
どうすればよいでしょうか？

- A. DeviceProcessEvents テーブルに対して高度なハンティング クエリを実行します。
- B. 自動調査を開始し、アクション センターで結果を表示します。
- C. DeviceTvmInfoGathering テーブルに対して高度なハンティング クエリを実行します。
- D. DeviceTvmSoftwareInventory テーブルに対して高度なハンティング クエリを実行します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)   [議論](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)  

**Correct Answer:** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)  

**解説:**
プログラム一覧の収集（Q29, Q38と全く同じ問題）。
選択肢に **D. DeviceTvmSoftwareInventory** がある場合、これが最も直接的で推奨される方法です。
Advanced Huntingクエリ: `DeviceTvmSoftwareInventory | summarize ...`
※問題バリエーションによって選択肢が変わるため注意が必要です（SoftwareInventoryテーブルがあればそれ、なければInvestigation Package）。

質問#45 トピック6

ドラッグ アンド ドロップ  
\-  
  
Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションがあります。Microsoft  
  
Security Copilot を使用する Azure サブスクリプションがあります。Security  
  
Copilot で、インシデント ID に関する次の情報を収集するカスタム プロンプトブックを作成する必要があります。  
  
• インシデントの概要  
• 特定された脅威アクターに関する脅威インテリジェンス  
• インシデントの影響を受けたユーザーの詳細な分析  
• インシデントの影響を受けたデバイスの詳細な分析  
  
順番に実行する必要がある 4 つのアクションはどれですか。回答するには、適切なアクションをアクション リストから回答領域に移動し、正しい順序で並べ替えます。  
  
![](https://img.examtopics.com/sc-200/image468.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image469.png)

**解説:**
Copilot for SecurityのPromptbook作成手順（インシデントIDを入力として詳細情報を収集）。

1. **Start a new session**: 新しいセッションを開始します。
2. **Run prompts for each step**: 必要な情報を収集するためのプロンプト（要件にある4つの項目：サマリー、TI、ユーザー分析、デバイス分析）を順番に実行します。
3. **Select the prompts**: セッション履歴から、Promptbookに含めたいプロンプトを選択します（チェックボックス等で）。
4. **Create a promptbook**: 選択したプロンプトから「Create promptbook」を実行します。この際、Incident IDなどの変数をパラメータ化します（`<IncidentID>`など）。
※Promptbookは、「うまくいったセッションの一連のプロンプト」を保存して再利用する機能なので、まずは実行（Run）して履歴を作り、そこから作成（Create）するフローになります。

質問#46 トピック6

ドラッグ＆ドロップ  
\-  
  
Device1 という名前の Windows 11 デバイスを含む Microsoft 365 E5 サブスクリプションがあります。Device1 は Microsoft Defender XDR にオンボードされています。  
  
次の操作を実行します。  
  
• Script1.ps1 という名前の PowerShell スクリプトを作成します。  
• Microsoft Defender XDR ポータルから、Device1 へのライブ応答セッションを確立します。Device1  
  
で Script1.ps1 を実行できることを確認する必要があります。  
  
どの 3 つの操作を順番に実行する必要がありますか？ 回答するには、適切な操作をアクションの一覧から回答領域に移動し、正しい順序で並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image470.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image471.png)

**解説:**
Live ResponseでPowerShellスクリプト（Script1.ps1）を実行する手順。

1. **Upload Script1.ps1 to the Live Response library**:
   まず、作成したスクリプトをMDEポータルの「Live Response Library」にアップロードします。これにより、セッション内から呼び出せるようになります。
2. **Connect to Device1**:
   Device1に対してライブ応答セッションを開始（Connect）します。
3. **Run the Script1.ps1 command**:
   セッション内で `run Script1.ps1` コマンドを実行します。（単にファイル名を指定して実行します。ライブラリにあるためパス指定は不要です）
※スクリプトを実行するには「Libraryへの登録」が必須ステップです。ローカルから直接 `putfile` して実行する方法もありますが、定型処理ならライブラリ登録が一般的です。正解画像の手順も Upload -> Connect -> Run となっています。

質問#47 トピック6

Microsoft 365 サブスクリプションを所有しています。このサブスクリプションには、Microsoft Defender for Endpoint にオンボードされている Windows 11 デバイスが 500 台含まれています。Linux  
  
を実行するデバイスも 500 台あります。  
  
ユーザーは Microsoft Entra の資格情報を使用して、Windows デバイスと Linux デバイスにサインインします。  
  
侵害された Linux エンドポイントに関連する Microsoft Defender XDR セキュリティ インシデントへの対応プロセスを推奨する必要があります。このソリューションでは、侵害されたデバイスが Defender for Endpoint にオンボードされているすべてのデバイスと通信できないようにする必要があります。  
  
推奨にはどのような対応アクションを含める必要がありますか？

- A. ユーザーを含む
- B. デバイスを封じ込める
- C. デバイスを分離する
- D. ユーザーが侵害されたことを確認する

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/35/#)  

**解説:**
侵害されたLinuxエンドポイントを封じ込める（通信遮断する）アクション。
**「Isolate device (デバイスの分離)」**:
Windowsデバイスだけでなく、**Linuxデバイス（およびmacOS）に対しても「Isolate device」アクションがサポートされています**。これにより、デバイスをネットワークから切断し、Defender for Endpointサービスとの通信のみを許可する状態にできます。
質問の要件「侵害されたデバイスが他のすべてのデバイスと通信できないようにする」を満たすのはこの機能です。
A: ユーザー無効化はデバイス通信を止めません。B: Contain deviceというアクションはMDEには存在しません（App governance等にはあるかもしれませんが）。
したがって、**Isolate device** (C) が正解です。
※コミュニティ投票でB（Contain）が100%になっている場合がありますが、MDEの用語としては「Isolate」が正解です。Contain hostはCrowdStrike等の用語です。Defender for Endpoint on Linuxのドキュメントに「Isolation」のサポートが明記されています。

*Community vote distribution*

B (100%)

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/34/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 35 ページを表示しています。

410問中**341 - 350**問 を表示
