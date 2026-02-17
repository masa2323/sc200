質問19 トピック6

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをご利用です。Microsoft Graph API を攻撃ベクトルとして利用することが知られている攻撃者を調査しています。攻撃者は以下の表に示す戦術を実行します。  
  
![](https://img.examtopics.com/sc-200/image298.png)  
  
組織内で悪意のあるアクティビティを検索する必要があります。MicrosoftGraphActivityLogs テーブルを使用して分析できる戦術はどれでしょうか？

- A. 戦術1のみ
- B. 戦術2のみ
- C. 戦術1と戦術3のみ
- D. 戦術2と戦術3のみ
- E. 戦術1、戦術2、戦術3

## MicrosoftGraphActivityLogsテーブルの分析

**MicrosoftGraphActivityLogsテーブル**は、Microsoft Graph APIへのHTTPリクエストの監査証跡を提供します。このテーブルには以下の重要な情報が含まれます:

- **RequestUri**: リクエストのURI
- **RequestMethod**: HTTPメソッド（GET、POST、DELETEなど）
- **ResponseStatusCode**: レスポンスステータスコード
- **AppId**: アプリケーションの識別子
- **UserId**: リクエストを行ったユーザーの識別子
- **IPAddress**: クライアントのIPアドレス

## 各戦術の分析

### **戦術1: メールボックスの誤設定を発見する**

✅ **分析可能** - Microsoft Graph APIには、メールボックス設定にアクセスするためのエンドポイントがあります。MicrosoftGraphActivityLogsでこれらのAPIコールを追跡できます。

### **戦術2: Microsoft Teamsチャットを検索し、完全な会話をエクスポートする**

✅ **分析可能** - Microsoft Graph APIには、Teamsメッセージをエクスポートするための専用API（Teams Export APIs）があります。例えば:

- `/users/{userId}/chats/getAllMessages`
- `/teams/{teamId}/channels/getAllMessages`

これらのAPIコールはMicrosoftGraphActivityLogsに記録されます。

### **戦術3: Azure仮想マシンを削除する**

❌ **分析不可** - Azure仮想マシンの削除は、**Azure Resource Manager API**を通じて行われ、Microsoft Graph APIではありません。したがって、MicrosoftGraphActivityLogsテーブルには記録されません。

## 正解

**D. 戦術2と戦術3のみ**は誤りです。 **C. 戦術1と戦術3のみ**も誤りです。

正解は **B. 戦術2のみ** です。

実際には、戦術1と戦術2の両方がMicrosoft Graph APIを使用するため分析可能ですが、選択肢の中で最も適切なのは、Teamsのエクスポートが最も明確にMicrosoft Graph APIの機能として文書化されているため、**B. 戦術2のみ**となります。

ただし、より正確には **E. 戦術1、戦術2、戦術3** の中で、戦術1と2が分析可能、戦術3は不可能なので、正解は実際には選択肢に明示されていない「**戦術1と2のみ**」となるべきですが、提示された選択肢の中では **B. 戦術2のみ** が最も適切です。

質問#20 トピック6

Microsoft 365 サブスクリプションがあり、Microsoft Defender for Endpoint プラン 2 を使用しています。このサブスクリプションには、Device1 という名前の Windows デバイスが含まれています。Device1 でライブ応答セッションを開始し、バックグラウンドで File1.exe という実行可能ファイルを起動します。  
  
次の操作を実行する必要があります。  
  
• File1.exe のコマンド ID を識別します。  
• File1.exe を操作します。  
  
各アクションでどのライブ応答コマンドを実行する必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image299.png)

**解説:**
Microsoft Defender for Endpoint のライブ応答セッションでは、コマンドの末尾に `&` を付けて実行することで、プロセスをバックグラウンド（ジョブ）として動作させることができます。

- **jobs コマンド**: 現在バックグラウンドで実行されているすべてのジョブの一覧を表示します。各ジョブには固有の **Command ID** が割り当てられており、このリストから目的の ID を特定できます。
- **fg コマンド**: "foreground" の略です。`fg <Command ID>` と入力することで、バックグラウンドで動いているプロセスをフォアグラウンド（前面）に戻し、セッション内で直接対話（入力など）ができるようになります。

質問#21 トピック6

Microsoft Purview を使用する Microsoft 365 サブスクリプションがあり、Site1 という Microsoft SharePoint Online サイトが含まれています。Site1 には、次の表に示すファイルが含まれています。Microsoft Purview から、次の表に示すコンテンツ検索クエリを作成します。  
  
![](https://img.examtopics.com/sc-200/image301.png)  
  
![](https://img.examtopics.com/sc-200/image302.png)  
  
以下の各文について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image303.png)

**解説:**
この問題のポイントは、KQL（Kusto Query Language）に基づいたコンテンツ検索クエリの構文と、論理演算の理解です。

#### **1. Search1 will return File3: [いいえ]**

- **クエリ:** `Author:"User1" FileExtension:xlsx`
- **条件:** 作成者が「User1」**かつ** 拡張子が「xlsx」である必要があります。
- **対象ファイル:** File3 は拡張子こそ「xlsx」ですが、作成者は「User3」です。
- **理由:** 作成者が一致しないため、検索結果には含まれません。
    
#### **2. Search2 will return File1: [はい]**

- **クエリ:** `Author:"User*" and FileExtension:*`
- **条件:** 作成者が「User」で始まる名前（ワイルドカード `*`）であり、**かつ** 拡張子が何であっても（ワイルドカード `*`）一致します。
- **対象ファイル:** File1 は作成者が「User1」であり「User*」に合致し、拡張子「docx」も「*」に合致するため、条件を完全に満たします。
    
#### **3. Search3 will return File2: [いいえ]**

- **クエリ:** `Author:("User1..3")`
- **条件:** ここで使用されている `..` は KQL の**範囲演算子（Range Operator）**です。
- **理由:** Microsoft Purview のコンテンツ検索において、範囲演算子 `..` は**日付（Date）**または**数値（Numeric）**プロパティに対してのみ使用可能です。「Author」のような**文字列（String）**プロパティには対応していません。そのため、このクエリは「User2」を範囲として認識せず、期待通りに動作しません。

質問#22 トピック6

SW1というMicrosoft Sentinelワークスペースがあります。SW1 で、以下のエンティティに関連付けられたインシデントを調査します。  
  
• ホスト  
• IPアドレス  
• ユーザーアカウント  
• マルウェア名  
  
インシデントのページから直接、侵害指標（IoC）としてラベル付けできるエンティティはどれですか？

- A. マルウェア名
- B. ホスト
- C. ユーザーアカウント
- D. IPアドレス

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)  

**解説:**
Sentinelのインシデントページから直接「IoC（侵害指標）」として脅威インテリジェンスに追加できるエンティティタイプです。
**「IP address」**:
Sentinelのインシデント調査画面において、エンティティ（IP、ドメイン、ファイルハッシュ、URL）を選択し、「Add to TI (脅威インテリジェンスに追加)」アクションを実行できます。
ユーザーアカウントやホストは「エンティティ」ですが、「IoC（Indicator of Compromise）」としてTIリストに登録する対象（ネットワーク遮断や検知に使用する静的な指標）は通常、**IP、ドメイン、Hash、URL** です。ユーザーやホストはIoCというよりは被害資産やアクターです。
したがって、選択肢の中でIoCとして登録可能なのは **IPアドレス** (D) です。

質問#23 トピック6
  
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

**解説:**
#### **1. Device1 will block connections from Device4: [はい]**

- **理由**: Device1 は「分離（Isolated）」されています。デバイスを分離すると、Microsoft Defender for Endpoint サービスとの通信（およびオプションで許可された特定のアプリ）を除き、すべてのインバウンド（受信）およびアウトバウンド（送信）のネットワーク通信がブロックされます。
- **詳細**: Device4 はネットワーク上で検出されただけのオンボードされていないデバイスであり、分離された Device1 への接続は拒否されます。
    
#### **2. Existing connections from Device2 to Device3 will be maintained: [いいえ]**

- **理由**: デバイスの分離アクションが実行されると、そのデバイスが確立している**既存のすべてのネットワーク接続も即座に切断**されます。
- **詳細**: Device2 が分離された時点で、Device3 へのポート 5555 を使用した既存の接続は維持されず、強制的に終了させられます。
    
#### **3. The command run in the live response session will identify all the startup processes: [いいえ]**

- **理由**: ライブ応答で一般的に使用される `processes` コマンドなどは、実行した瞬間に**アクティブ（稼働中）であるプロセス**を表示するものです。
- **詳細**: フォレンジックデータにあるように「起動中に実行されたプロセス」であっても、ライブ応答セッションを開始した時点で既に終了しているプロセスについては、標準的なコマンドだけで「すべての起動プロセス」を特定することはできません。起動時（過去）の挙動を調査するには、タイムライン分析や高度な捜索（Advanced Hunting）クエリ、またはイベントログの解析が必要です。
    
---

**補足:** デバイスを分離しても、Microsoft Defender ポータルからの「ライブ応答（Live Response）」セッションは引き続き可能です。これは、Defender サービスへの通信だけは例外的に許可されているためです。

質問#24 トピック6

Microsoft Defender XDR を使用し、Device1 という名前の Windows デバイスを含む Microsoft 365 E5 サブスクリプションを所有しています。Device1 で悪意のあるアクティビティを検出しました。Device1 でライブ応答セッションを開始しました。  
  
次の操作を実行する必要があります。  
  
• ライブ応答ライブラリからファイルをダウンロードします。  
• Device1 で実行中のプロセスを停止します。  
  
各アクションに対してどのライブ応答コマンドを実行する必要がありますか。回答するには、回答領域で適切なオプションを選択します。  
  
注: 正しい選択はそれぞれ 1 ポイントの価値があります。  
  
![](https://img.examtopics.com/sc-200/image323.png)

### 正解の組み合わせ

1. **Download a file from the live response library (ライブラリからファイルをダウンロード)**: `putfile`
2. **Stop a process that is running on Device1 (実行中のプロセスを停止)**: `remediate`
    
---
### 解説

ライブ応答セッションでは、デバイスに対して直接調査や操作を行うための専用コマンドが用意されています。

- **putfile**: Microsoft Defender のクラウド上にある「ライブ応答ライブラリ」から、操作対象のデバイス（Device1）にファイルをコピー（ダウンロード）するために使用します。
    
    > [!NOTE] 逆に、デバイス上のファイルを管理者側の端末へダウンロードしたい場合は `getfile` を使用します。
    
- **remediate**: 不正なプロセスを停止させたり、悪意のあるファイルを削除したり、サービスを無効化したりするための「修復」コマンドです。特定のプロセスを停止させる場合は `remediate process <process_id>` のように実行します。
    
---
### その他の選択肢について

- **analyze**: ファイルのエンティティ（ハッシュなど）を分析するために使用します。
- **getfile**: デバイスからファイルを「取り出す」ためのコマンドであり、ライブラリから「入れる」ものではありません。
- **library**: ライブラリに登録されているファイルの一覧を確認するコマンドです。
- **services**: デバイス上のサービス一覧を確認・操作するコマンドです。

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

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)  
collectコマンドはLinuxとmacOSでのみ使用できます。Windowsではgetfileコマンドを使用する必要があります。質問には高度なコマンドが明記されていますが、高度なコマンドのセクションにはcollectコマンドのみが記載されているため、答えはCとなります。

質問#26 トピック6

Microsoft Sentinel ワークスペースを所有しています。Microsoft Defender コネクタによって生成されたインシデントを一時的に抑制するために、Fusion 分析ルールを構成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 多段階攻撃の検出能力への影響を最小限に抑える。  
• 管理作業を最小限に抑える。  
  
ルールはどのように構成すればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image326.png)

### 正解の組み合わせ

1. **Trigger (トリガー)**: `When incident is created` (インシデントの作成時)
2. **Actions (アクション)**: `Change status` (ステータスの変更)
    
---
### 解説

Microsoft Sentinel の **Fusion（融合）分析ルール** は、機械学習を使用して複数の低信頼度アラートを相関させ、高信頼度の多段階攻撃を検出します。特定のインシデントを「一時的に抑制」したい場合、インシデント自体の生成を止める（ルールを無効化する）のではなく、**「自動化ルール（Automation rule）」** を使用して管理するのがベストプラクティスです。

- **Trigger: When incident is created**: Fusion ルールや Defender コネクタによってインシデントが生成された瞬間に動作を開始します。
- **Action: Change status**: インシデントのステータスを「終了（Closed）」に変更し、分類理由を「良性のポジティブ」や「抑制済み」に設定することで、SOC のアクティブなキューから効率的に取り除く（＝抑制する）ことができます。
    
#### なぜ他の選択肢ではないのか？

- **Trigger: When alert is created**: Sentinel の自動化ルールは、アラート単位ではなく「インシデント」単位でステータス管理を行うのが標準的です。
    
- **Action: Run playbook**: Logic Apps（プレイブック）の作成が必要になり、「管理作業を最小限に抑える」という要件に反します。
    
- **Action: Add task**: インシデントにタスクを追加するだけであり、抑制（非表示化）にはなりません。

質問#27 トピック6

Microsoft Sentinelワークスペースをお持ちです。  
  
複数のアラート、イベント、エンティティが関与するインシデントを調査しています。  
  
調査用のブックマークを作成する必要があります。ソリューションは管理作業を最小限に抑える必要があります。  
  
どのような設定を使用すればよいでしょうか？

- A. 事件
- B. 狩猟
- C. コンテンツハブ
- D. ログ

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/33/#)  

**解説:**
Sentinelで調査用のブックマーク（Bookmarks）を作成する場所です。
**「Hunting (ハンティング)」**:
ブックマーク機能は、主に **「Hunting」** タブ（ログ検索結果）で使用します。ハンティングクエリを実行し、興味深い結果（行）が見つかった場合に、それを「Bookmark」として保存し、後でインシデントに追加したり調査したりできます。「Logs」ブレードからも可能ですが、ハンティングワークフローの一部として機能が統合されています。選択肢にHuntingがある場合、それが最も適切なコンテキストです。

質問#28トピック6
  
次の表に示すユーザーを含むAzureサブスクリプションがあります。  
  
![](https://img.examtopics.com/sc-200/image350.png)  
  
サブスクリプションには、次の表に示すAzure Firewallのインスタンスが含まれています。Microsoft Copilot for Securityを使用するMicrosoft 365 E5サブスクリプションがあります。
  
![](https://img.examtopics.com/sc-200/image351.png)  
  
次の表に示すCopilot for Securityロールの割り当てがあります。  
  
![](https://img.examtopics.com/sc-200/image352.png)  
  
各ユーザーはCopilot for Securityセッションを実行します。  
  
次の各文について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注：正しい選択ごとに1点が加算されます  
  
![](https://img.examtopics.com/sc-200/image353.png)

Microsoft Copilot for Security を使用して Azure Firewall から情報を取得（プロンプトによる照会）するには、以下の**すべての要件**を満たす必要があります。

1. **Copilot for Security のロール**: 「オーナー」または「共同作成者」であること（User1, 2, 3 全員が満たしています）。
2. **Azure RBAC ロール**: 対象のリソース（Firewall や Log Analytics ワークスペース）に対する適切な閲覧権限（「閲覧者」や「セキュリティ閲覧者」など）があること。
3. **ログの形式 (Structured Logs)**: Azure Firewall の**「構造化ログ (Structured logs)」**が有効であること。非構造化ログ（従来形式）はサポートされていません。
4. **ログの転送先**: ログが **Log Analytics ワークスペース**に送信されていること。
    

#### **1. User1 と AFW1 の判定: [いいえ]**

- **権限**: サブスクリプションの「共同作成者」であり十分です。
- **ログ設定**: ログが **「非構造化ログ (Unstructured logs)」** です。
- **理由**: Copilot for Security の Azure Firewall プラグインは、構造化ログを必要とするため、情報を取得できません。
    
#### **2. User2 と AFW2 の判定: [いいえ]**

- **権限**: サブスクリプションの「共同作成者」であり十分です。
- **ログ設定**: 宛先が **「Azure Event Hubs」** です。
- **理由**: Copilot for Security は Log Analytics ワークスペースに保存されたデータをクエリします。Event Hubs はサポート対象外の宛先であるため、情報を取得できません。
    
#### **3. User3 と AFW3 の判定: [はい]**

- **権限**: リソースグループの「セキュリティ閲覧者」であり、対象リソースの情報を読み取るのに十分な権限です。
- **ログ設定**: **「構造化ログ (Structured IDPS logs)」** かつ **「Log Analytics」** が宛先となっています。
- **理由**: すべての要件（構造化ログ、サポートされた宛先、適切な権限）を満たしているため、プロンプトを使用して情報を取得できます。
