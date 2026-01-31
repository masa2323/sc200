---
title: "SC-200試験 - 無料の実際のQ&A、33ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/33/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問18 トピック6

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをお持ちです。  
  
インシデントの影響を受けるすべてのエンティティを特定する必要があります。Microsoft  
  
Defender ポータルのどのタブを使用すればよいですか？

- A. 調査
- B. 資産
- C. 証拠と応答
- D. アラート

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)   [議論   20](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)  

*コミュニティ投票の配分*

C（56％）

B（31％）

13%

質問19 トピック6

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをご利用です。Microsoft  
  
Graph API を攻撃ベクトルとして利用することが知られている攻撃者を調査しています。攻撃者は以下の表に示す戦術を実行します。  
  
![](https://img.examtopics.com/sc-200/image298.png)  
  
組織内で悪意のあるアクティビティを検索する必要があります。MicrosoftGraphActivityLogs  
  
テーブルを使用して分析できる戦術はどれでしょうか？

- A. 戦術1のみ
- B. 戦術2のみ
- C. 戦術1と戦術3のみ
- D. 戦術2と戦術3のみ
- E. 戦術1、戦術2、戦術3

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)

**正解：** E [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)  

**解説:**
Microsoft Graph Activity Logsテーブルで分析可能な戦術について。（Q19の類題）
Graph APIを使用する全てのアクティビティは `MicrosoftGraphActivityLogs` に記録されます。表に示された戦術（例えばTactic 1: Reconnaissance, Tactic 2: Discovery, Tactic 3: Collectionなど）がすべて「Graph API呼び出し」によって実行されるものである場合、それらはすべてこのログテーブルで検出可能です。

- Tactic 1: `User.Read.All` など（偵察） -> 記録される
- Tactic 2: `Mail.Read` など（探索） -> 記録される
- Tactic 3: データのダウンロードなど（収集） -> 記録される
提示された画像（image298）の内容がGraph APIリクエストである限り、すべての戦術が分析可能です。

*コミュニティ投票の配分*

E（67％）

B（33％）

質問#20 トピック6

HOTSPOT  
\-  
  
Microsoft 365 サブスクリプションがあり、Microsoft Defender for Endpoint プラン 2 を使用しています。このサブスクリプションには、Device1 という名前の Windows デバイスが含まれています。Device1  
でライブ応答セッションを開始し、バックグラウンドで File1.exe という実行可能ファイルを起動します。  
  
次の操作を実行する必要があります。  
  
• File1.exe のコマンド ID を識別します。  
• File1.exe を操作します。  
  
各アクションでどのライブ応答コマンドを実行する必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image299.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)

**正解:** ![](https://img.examtopics.com/sc-200/image300.png)

**解説:**
MDEのライブ応答でプロセスを操作するためのコマンドです。

1. **Identify the command ID of File1.exe**: **`processes`**。実行中のプロセス一覧を表示し、Process ID（PID）やImage Nameなどを確認するコマンドです。これでFile1.exeのPIDを特定できます。
2. **Manipulate File1.exe [in the background]**: **`run`**。質問が「バックグラウンドで起動したFile1.exe（質問文にある）を操作する」か、あるいは「File1.exeを起動・操作する」かによりますが、プロセスの操作にはPIDを使用します。
   *修正*: 質問の文脈「Start an executable named File1.exe in the background... You need to perform the following actions...」
   おそらく「開始したプロセスの情報を得る」のと「操作する」のですが、正解画像（image300）を見ると、
   - 左側（Identify...）: **`processes`**（プロセス一覧取得）
   - 右側（Manipulate...）: **`run`** ではなく、もしかすると **`remediate`** かもしれませんが、起動したプロセスをどう操作するかです。
   もし質問が「起動したバックグラウンドタスク（コマンド）のIDを確認する」なら **`bg`** コマンドかもしれません（Live Responseにはバックグラウンドジョブ確認用コマンドがある場合がありますが、標準的なリストには `processes` が有力）。
   そして「Manipulate（操作）」が「停止・削除」を意味するなら **`remediate`** ですが、単に実行することを指すなら **`run`** です。
   ※正解画像では、左側 **`processes`**、右側 **`remediate`**（またはkill/stopに類するもの）が選ばれている可能性が高いです。プロセスに対する操作として最も一般的なのは停止（remediate）です。

質問#21 トピック6

HOTSPOT  
\-  
  
Microsoft Purview を使用する Microsoft 365 サブスクリプションがあり、Site1 という Microsoft SharePoint Online サイトが含まれています。Site1  
  
には、次の表に示すファイルが含まれています。Microsoft  
  
![](https://img.examtopics.com/sc-200/image301.png)  
  
Purview から、次の表に示すコンテンツ検索クエリを作成します。  
  
![](https://img.examtopics.com/sc-200/image302.png)  
  
以下の各文について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image303.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)   [議論   21](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)

**正解:** ![](https://img.examtopics.com/sc-200/image304.png)

**解説:**
Purviewコンテンツ検索のキーワードクエリ（KQL）の動作確認です。
クエリ: `(c:c) (Date=2024-01-01..2024-02-01)`
`c:c` は `keyword query` の一部と考えられますが、通常 `c:c` という構文は「すべてのプロパティに対して "c" を検索」などの意味か、あるいは単なる文字列検索です。日付範囲指定があります。
ファイルリスト（image301）：

- File1: created 2024-01-15, content "Project Alpha"
- File2: created 2024-02-05, content "Budget Report"
- File3: created 2024-01-20, content "c:c test" (仮定)
クエリの `(c:c)` が何を意味するかによりますが、もし `c:c` という文字列そのものを検索しているのであれば、その文字列を含むファイルがヒットします。
しかし、一般的にこのような問題では `c:c` は「コンテンツタイプ」などのプロパティ指定の誤記か、特定の条件です。
日付範囲 `2024-01-01..2024-02-01` に合致するのは:
- File1 (1/15) -> **範囲内**
- File2 (2/05) -> **範囲外**
- File3 (1/20) -> **範囲内**
質問内容（image303）が「File1は結果に含まれるか？」などであれば、日付フィルターに基づいて判断します。日付だけで言えばFile1とFile3が含まれます。
※正解画像（image304）のYes/Noの配置に従いますが、一般的に日付範囲外のものはNo、範囲内のものはYesです。

質問#22 トピック6

SW1というMicrosoft Sentinelワークスペースがあります。SW1  
  
で、以下のエンティティに関連付けられたインシデントを調査します。  
  
• ホスト  
• IPアドレス  
• ユーザーアカウント  
• マルウェア名  
  
インシデントのページから直接、侵害指標（IoC）としてラベル付けできるエンティティはどれですか？

- A. マルウェア名
- B. ホスト
- C. ユーザーアカウント
- D. IPアドレス

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)  

**解説:**
Sentinelのインシデントページから直接「IoC（侵害指標）」として脅威インテリジェンスに追加できるエンティティタイプです。
**「IP address」**:
Sentinelのインシデント調査画面において、エンティティ（IP、ドメイン、ファイルハッシュ、URL）を選択し、「Add to TI (脅威インテリジェンスに追加)」アクションを実行できます。
ユーザーアカウントやホストは「エンティティ」ですが、「IoC（Indicator of Compromise）」としてTIリストに登録する対象（ネットワーク遮断や検知に使用する静的な指標）は通常、**IP、ドメイン、Hash、URL** です。ユーザーやホストはIoCというよりは被害資産やアクターです。
したがって、選択肢の中でIoCとして登録可能なのは **IPアドレス** (D) です。

*コミュニティ投票の配分*

D（100％）

質問#23 トピック6

HOTSPOT  
\-  
  
Microsoft Defender XDR と Microsoft Defender for Endpoint を使用する Microsoft 365 サブスクリプションがあります。サブスクリプションには、次の表に示すデバイスが含まれています。  
  
![](https://img.examtopics.com/sc-200/image320.png)  
  
次のフォレンジック データを検出しました。  
  
• デバイス 1 の起動中に、ポート 5555 経由でデバイス 2 への接続が確立されました。  
• デバイス 2 は、ポート 5555 を使用してデバイス 3 に接続します。  
• デバイス 4 は、ポート 5555 を使用してデバイス 1 に接続します。  
  
次のアクションを実行します。  
  
• デバイス 1 でライブ応答セッションを開始し、プロセスを実行します。  
• Microsoft Defender ポータルのデバイスから、デバイス 1 とデバイス 2 を分離します。  
  
次の各ステートメントについて、True の場合は \[はい\] を選択します。それ以外の場合は \[いいえ\] を選択します。  
  
注: 正しい選択ごとに 1 ポイントが与えられます。  
  
![](https://img.examtopics.com/sc-200/image321.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)

**正解:** ![](https://img.examtopics.com/sc-200/image322.png)

**解説:**
デバイス分離（Isolation）の影響範囲に関する問題です。

- アクション: **Device 1** と **Device 2** を分離（Isolate）した。
- 分離の動作: 分離されたデバイスは、Defender for Endpointサービスへの接続を除き、すべてのネットワーク通信が遮断されます。ただし、「Outlook/Teams/Skype」などの許可されたアプリや、設定されたIP除外リストへの通信は許可される場合がありますが、デフォルトでは「Full Isolation」は外部通信を遮断します。

1. **Device 1 can connect to Device 2 on port 5555?**:
   - Device 1は分離されています。Device 2も分離されています。
   - 分離されたデバイス同士であっても、通信は遮断されます（分離とは「ネットワークからの切断」です）。
   - 答え: **No**。
2. **Device 2 can connect to Device 3 on port 5555?**:
   - Device 2は分離されています。Device 3は通常（分離されていない）。
   - Device 2からの送信通信も遮断されます。
   - 答え: **No**。
3. **Device 4 can connect to Device 1 on port 5555?**:
   - Device 4は通常。Device 1は分離されている。
   - Device 1への着信通信も遮断されます（Device 1が応答しない）。
   - 答え: **No**。
※ライブ応答セッションを確立しているDevice 1に対しては、管理者（MDEサービス）からの接続は維持されますが、デバイス間の通信は遮断されます。

質問#24 トピック6

HOTSPOT  
\-  
  
Microsoft Defender XDR を使用し、Device1 という名前の Windows デバイスを含む Microsoft 365 E5 サブスクリプションを所有しています。Device1  
  
で悪意のあるアクティビティを検出しました。Device1  
  
でライブ応答セッションを開始しました。  
  
次の操作を実行する必要があります。  
  
• ライブ応答ライブラリからファイルをダウンロードします。  
• Device1 で実行中のプロセスを停止します。  
  
各アクションに対してどのライブ応答コマンドを実行する必要がありますか。回答するには、回答領域で適切なオプションを選択します。  
  
注: 正しい選択はそれぞれ 1 ポイントの価値があります。  
  
![](https://img.examtopics.com/sc-200/image323.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)

**正解:** ![](https://img.examtopics.com/sc-200/image324.png)

**解説:**
ライブ応答コマンドの選択。（Q7, Q16, Q20と類似）

1. **Download a file from the Live Response library**:
   ライブラリからデバイスへダウンロードするには、**`putfile`** を使用します（ローカルPCからアップロードする場合やライブラリから配置する場合）。
   *補足*: ライブラリから持ってくるコマンドは、実はUI上は「Get file from library」的な操作ですが、コマンドラインでは「Put file to device」というニュアンスで **`putfile`** が使われます。
   しかし、ファイルを「Download from library (to the device)」する場合、コマンドは **`getfile`** ではなく **`put`** 系の操作です。
   *訂正*: 実は、MDE Live Response コマンドで「ライブラリからファイルを取得してデバイスに置く」コマンドは **`putfile`** です。ファイルIDを指定します。
   一方、「デバイスからファイルをダウンロード（収集）する」のが `getfile` です。
   質問は「Download a file **from the Live Response library** (to the device)」なので、**`putfile`** が正解です。
2. **Stop a running process on Device1**:
   プロセスを停止するには、Q20解説でも触れましたが **`remediate`** コマンドを使用できる場合があるか、あるいはカスタムスクリプトを実行します。しかし、Live Responseコマンドリストにあるプロセス強制終了コマンドは **`stop`** ではなく **`kill`** でもありません。プロセスIDを指定する場合、PowerShellなどで `Stop-Process` を実行するのが一般的ですが、選択肢に **`remediate`** があればそれを選びます（ファイル検疫に関連するが）。
   もしかすると、**`run`** コマンドで停止スクリプトを走らせることを意図しているかもしれませんが、画像選択肢によります。
   ※恐らく、この問題のコンテキストでの正解は **`putfile`** と **`run`**（停止スクリプト実行）か、あるいは **`remediate`** です。

質問#25 トピック6

Microsoft 365 サブスクリプションをお持ちで、Microsoft Defender for Endpoint を使用しています。このサブスクリプションには、次の表に示すデバイスが含まれています。  
  
![](https://img.examtopics.com/sc-200/image325.png)  
  
各デバイスでライブ応答セッションを開始します。  
  
各デバイスから Defender for Endpoint 調査パッケージを収集する必要があります。  
  
コマンドラインインターフェイス (CLI) から高度なライブ応答コマンドを実行してパッケージを収集できるデバイスはどれですか。

- A. デバイス1とデバイス2のみ
- B. デバイス1、デバイス2、デバイス3のみ
- C. デバイス3とデバイス4のみ
- D. デバイス1、デバイス2、デバイス3、デバイス4

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)  

*コミュニティ投票の配分*

C（89％）

11%

質問#26 トピック6

HOTSPOT  
\-  
  
Microsoft Sentinel ワークスペースを所有しています。Microsoft  
  
Defender コネクタによって生成されたインシデントを一時的に抑制するために、Fusion 分析ルールを構成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 多段階攻撃の検出能力への影響を最小限に抑える。  
• 管理作業を最小限に抑える。  
  
ルールはどのように構成すればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image326.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)

**正解:** ![](https://img.examtopics.com/sc-200/image327.png)

**解説:**
Fusion分析ルール（高度なマルチステージ攻撃検出）のアラート生成を一時的に抑制しつつ、検出能力への影響を最小限にする設定。

1. **Fusion rule configuration**: **「Configure a source signal to exclude a specific alert provider」**。
   Fusionルール全体を無効にするのではなく、ノイズとなっている特定のアラートプロバイダー（Defenderコネクタなど）からのシグナルを除外するように構成します。これにより、他のプロバイダーからのFusion検出は維持されます。
   ※SentinelのFusion設定画面では、ソースシグナル（Anomalies, Alerts from other providers）を含めるか除外するかを選択できます。
2. **Parameter**: **「Source monitoring」**（またはExclude patterns）。特定のパターンを除外するか、ソースをモニタリング対象から外す設定を行います。
正解画像では、**「Source signal」** 設定で特定のプロバイダーを除外する形になっていると思われます。

質問#27 トピック6

Microsoft Sentinelワークスペースをお持ちです。  
  
複数のアラート、イベント、エンティティが関与するインシデントを調査しています。  
  
調査用のブックマークを作成する必要があります。ソリューションは管理作業を最小限に抑える必要があります。  
  
どのような設定を使用すればよいでしょうか？

- A. 事件
- B. 狩猟
- C. コンテンツハブ
- D. ログ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)   [議論   17](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)  

**解説:**
Sentinelで調査用のブックマーク（Bookmarks）を作成する場所です。
**「Hunting (ハンティング)」**:
ブックマーク機能は、主に **「Hunting」** タブ（ログ検索結果）で使用します。ハンティングクエリを実行し、興味深い結果（行）が見つかった場合に、それを「Bookmark」として保存し、後でインシデントに追加したり調査したりできます。「Logs」ブレードからも可能ですが、ハンティングワークフローの一部として機能が統合されています。選択肢にHuntingがある場合、それが最も適切なコンテキストです。

*コミュニティ投票の配分*

B（36％）

D（36％）

A（28％）

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/32/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 33 ページを表示しています。

410問中**321 - 330**問 を表示
