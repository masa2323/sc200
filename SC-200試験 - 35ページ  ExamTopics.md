質問#39 トピック6

Microsoft 365 E5 サブスクリプションを所有しており、Device1 というデバイスが含まれています。Microsoft Defender ポータルで、Device1 でアラートがトリガーされたことを確認しました。  
  
デバイスインベントリページで Device1 を特定しました。Device1 にインストールされているプログラムの一覧を収集する必要があります。  
  
どうすればよいでしょうか？

- A. 調査パッケージを収集し、アクション センターから結果をダウンロードします。
- B. ライブ応答セッションを開始し、分析コマンドを実行します。
- C. DeviceProcessEvents テーブルに対して高度なハンティング クエリを実行します。
- D. DeviceTvmInfoGathering テーブルに対して高度なハンティング クエリを実行します。

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

質問#40 トピック6

Tenant1 と Tenant2 という 2 つの Microsoft Entra テナントがあります。各テナントは Azure サブスクリプションにリンクされています。Tenant1 には Group1 というグループが含まれています。Tenant2 には Group2 というグループが含まれています。  
  
各テナントに Microsoft Sentinel を実装する必要があります。ソリューションは、次の要件を満たす必要があります。  
  
• Group1 が単一のワークスペースで Tenant1 と Tenant2 のセキュリティ インシデントを管理できることを確認する 。
• Group2 が Tenant2 のセキュリティ インシデントのみを管理できることを確認する。  
• ゲスト アカウントの使用を最小限に抑える。  
• 管理の労力を最小限に抑える。  
• コストを最小限に抑える。  
  
ソリューションには何を含める必要がありますか？

- A. 1つのワークスペースと特権ID管理（PIM）
- B. 1つのワークスペースと複数のロールベースアクセス制御（RBAC）ロールの割り当て
- C. 2つのワークスペースとAzure Lighthouse
- D. 2つのワークスペースと細分化された委任管理者権限（GDAP）

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

質問#41 トピック6

contoso.com という Microsoft Entra テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。contoso.com のロールの変更を識別するために、Microsoft Graph アクティビティ ログをクエリする必要があります。KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image465.png)

このクエリは、Microsoft Graph API を介してディレクトリ ロールに新しいメンバーが追加された操作を特定しようとしています。

- **ResponseStatusCode in ("204"):** Microsoft Graph API において、ロールへのメンバー追加（`POST .../members/$ref`）が成功した場合、標準的なレスポンスコードは **`204 No Content`** です。
    
    - `302` はリダイレクト、`401` は認証エラーを意味するため、操作の成功（ロールの変更）を特定する目的には適しません。
        
- **extend Role = tostring(split(RequestUri, "/")[-3]):** この部分は、リクエストの URL から「どのロールに変更があったか（ロール ID）」を抽出しようとしています。
    
    - 一般的なリクエスト URL の形式は `https://graph.microsoft.com/v1.0/directoryRoles/{role-id}/members/$ref` です。
        
    - これを `/` で分割（split）すると、末尾（`[-1]`）が `$ref`、その前（`[-2]`）が `members`、さらにその前（**`[-3]`**）が目的の **`{role-id}`** になります。
        
    - したがって、分割の対象として **`RequestUri`** を選択するのが正解です。

質問#42 トピック6

Microsoft Defender for Endpoint を使用する Microsoft 365 サブスクリプションがあり、以下のデバイスが含まれています。  
  
• デバイス1: Windows 11 Pro を実行  
• デバイス2: Windows Server を実行  
• デバイス3: Ubuntu Linux を実行  
  
File1.exe、File2.zip、File3.ps1 という 3 つの不審なファイルを特定しました。  
  
これらのファイルを詳細分析で調査する必要があります。  
  
詳細分析をサポートしているデバイスと、詳細分析に提出できるファイルはどれですか？ 回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
### **サポートされるデバイス**

公式ドキュメントによると、詳細分析（Deep Analysis）機能は以下のデバイスからファイルを収集できます：

✅ **Windows 10**（バージョン1703以降） ✅ **Windows 11** ✅ **Windows Server 2012 R2以降**

ドキュメントには以下の記載があります：

> "Only files from **Windows 10, Windows 11, and Windows Server 2012 R2+** can be automatically collected."

したがって：

- ✅ **Device1**（Windows 11 Pro）- サポート対象
- ✅ **Device2**（Windows Server）- サポート対象
- ❌ **Device3**（Ubuntu Linux）- サポート対象外

**正解：Device1 and Device2 only**
---
### **サポートされるファイル**

公式ドキュメントには明確に以下の記載があります：

> "Only **PE files** are supported, including _**.exe**_ and _**.dll**_ files."

PE（Portable Executable）ファイルのみがサポートされています。

したがって：

- ✅ **File1.exe**（実行可能ファイル）- サポート対象
- ❌ **File2.zip**（アーカイブファイル）- サポート対象外
- ❌ **File3.ps1**（PowerShellスクリプト）- サポート対象外

**正解：File1.exe only**
---
## まとめ

- **Devices**: **Device1 and Device2 only**
- **Files**: **File1.exe only**

質問#43 トピック6

Microsoft 365 E5 サブスクリプションを所有しており、Device1 というデバイスが含まれています。Microsoft Defender ポータルで、Device1 でアラートがトリガーされたことを確認しました。  
  
デバイスインベントリページで Device1 を特定しました。Device1 にインストールされているプログラムの一覧を収集する必要があります。  
  
どうすればよいでしょうか？

- A. 自動調査を開始し、アクション センターで結果を表示します。
- B. 調査パッケージを収集し、アクション センターから結果をダウンロードします。
- C. DeviceTvmInfoGathering テーブルに対して高度なハンティング クエリを実行します。
- D. DeviceProcessEvents テーブルに対して高度なハンティング クエリを実行します。
- 
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

Microsoft 365 E5 サブスクリプションを所有しており、Device1 というデバイスが含まれています。Microsoft Defender ポータルで、Device1 でアラートがトリガーされたことを確認しました。  
  
デバイスインベントリページで Device1 を特定しました。Device1 にインストールされているプログラムの一覧を収集する必要があります。  
  
どうすればよいでしょうか？

- A. DeviceProcessEvents テーブルに対して高度なハンティング クエリを実行します。
- B. 自動調査を開始し、アクション センターで結果を表示します。
- C. DeviceTvmInfoGathering テーブルに対して高度なハンティング クエリを実行します。
- D. DeviceTvmSoftwareInventory テーブルに対して高度なハンティング クエリを実行します。

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
  
Security Copilot を使用する Azure サブスクリプションがあります。Security Copilot で、インシデント ID に関する次の情報を収集するカスタム プロンプトブックを作成する必要があります。  
  
• インシデントの概要  
• 特定された脅威アクターに関する脅威インテリジェンス  
• インシデントの影響を受けたユーザーの詳細な分析  
• インシデントの影響を受けたデバイスの詳細な分析  
  
順番に実行する必要がある 4 つのアクションはどれですか。回答するには、適切なアクションをアクション リストから回答領域に移動し、正しい順序で並べ替えます。  
  
![](https://img.examtopics.com/sc-200/image468.png)

## 回答エリア (Answer Area)

1. **From the Security Copilot standalone portal, create a session.**
    
2. **Enter the four prompts and gather the required information about a sample incident.**
    
3. **Select the prompts to include in the promptbook.**
    
4. **Create the promptbook.**
    
---
## 解説

プロンプトブックを作成する際のロジックは以下の通りです。

### 1. スタンドアロンポータルでのセッション開始

カスタムプロンプトブックの作成（既存の履歴からの作成）は、**Security Copilot スタンドアロンポータル**で行います。Defender XDRポータルの埋め込みパネルではなく、フル機能が使える専用ポータルを使用するのが第一歩です。

### 2. プロンプトの実行と情報収集

プロンプトブックの「材料」となるプロンプトを実際に実行します。今回の要件では「概要」「脅威インテリジェンス」「ユーザー分析」「デバイス分析」の4つの情報を求めているため、これに対応する**4つのプロンプトを入力**し、サンプルインシデントに対して意図した結果が得られるかを確認します。

### 3. プロンプトの選択

セッションの履歴の中から、プロンプトブックに組み込みたい特定のプロンプト（先ほど実行した4つ）を**選択**します。これにより、一連の流れをテンプレート化する準備が整います。

### 4. プロンプトブックの作成

選択したプロンプトを元に、名前や説明を付けて**プロンプトブックとして保存（Create）**します。これで、次回以降はインシデントIDを入力するだけで、定義した4つのステップが自動的に実行されるようになります。

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

- **From the Microsoft Defender XDR portal, select Advanced features.**
    - まず、「詳細機能」設定で「**Live response unsigned script execution**（署名なしスクリプト実行）」を有効化する必要があります
    - ドキュメントには以下の記載があります：
        
        > "If you plan to use an unsigned PowerShell script in the session, you'll need to enable the setting in the Advanced features settings page."
        
- **From the Microsoft Defender XDR portal, upload Script1.ps1 to the library.**
    - ライブ応答でスクリプトを実行する前に、そのスクリプトをライブ応答ライブラリにアップロードする必要があります
    - ドキュメントには以下の記載があります：
        
        > "Before you can run a PowerShell/Bash script, you must first upload it to the library."
        
    - アップロード手順：**Upload file to library** → ファイル選択 → 説明入力 → **Confirm**
- **During the live response session, run the library command.**
    - ライブ応答セッション中に`library`コマンドを実行して、スクリプトが正しくアップロードされたことを確認します
    - ドキュメントには以下の記載があります：
        
        > "(Optional) To verify that the file was uploaded to the library, run the `library` command."

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

### **正解：C. デバイスを分離する（Isolate device）**

## 理由

公式ドキュメントには以下の記載があります：

### **デバイスの分離（Isolate device）について**

> "**Isolate devices from the network**: Depending on the severity of the attack and the sensitivity of the device, you might want to isolate the device from the network. This action can help prevent the attacker from controlling the compromised device and performing further activities such as **data exfiltration and lateral movement**."

> "You can use the device isolation capability on **all supported Microsoft Defender for Endpoint on Linux** listed in System requirements."

> "The device isolation feature **disconnects the compromised device from the network** while retaining connectivity to the Defender for Endpoint service, which continues to monitor the device."

### **重要なポイント：**

1. **Linuxデバイスのサポート**
    - デバイス分離は、Linuxデバイスでサポートされています
    - 前提条件：`iptables`、`ip6tables`、特定のLinuxカーネル設定
2. **要件を満たす効果**
    - 侵害されたデバイスがネットワークから切り離されます
    - **すべてのDefender for Endpointにオンボードされているデバイスとの通信がブロックされます**
    - これにより横方向の移動（lateral movement）とデータ流出を防ぎます

### **他の選択肢が不適切な理由：**

#### **A. ユーザーを含む（Contain user）**

- ユーザーの封じ込めは、IDベースの対応アクションです
- 主に**自動攻撃中断（automatic attack disruption）**によって自動的に適用されます
- デバイスそのものを他のデバイスから隔離する機能ではありません

#### **B. デバイスを封じ込める（Contain device）**

- ドキュメントによると、デバイスの封じ込めは主に：
    
    > "When you have identified an **unmanaged device** that is compromised or potentially compromised..." "Blocking incoming and outgoing communication with a 'contained' device is supported on **onboarded Microsoft Defender for Endpoint Windows 10 and Windows Server 2019+ devices**."
    
- **重要：**「Contain device」は、**オンボードされていないデバイスまたは検出されていないデバイスに対して**、オンボード済みのデバイスが通信をブロックするための機能です
- LinuxデバイスがContain deviceのターゲットとしてはサポートされていません

#### **D. ユーザーが侵害されたことを確認する（Confirm user compromised）**

- これは調査アクションであり、デバイスの通信をブロックする対応アクションではありません

### **まとめ**

侵害されたLinuxデバイスが、Defender for Endpointにオンボードされているすべてのデバイスと通信できないようにするためには、**「デバイスを分離する（Isolate device）」**が正しい対応アクションです。
