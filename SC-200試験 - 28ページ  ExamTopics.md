---
title: "SC-200試験 - 無料の実際のQ&A、28ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/28/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#36 トピック4

Microsoft 365 E5 サブスクリプションがあり、500 台の Windows 11 デバイスが含まれています。Microsoft Defender for Endpoint の展開では、以下の設定になっています。  
  
• 検出モード: 基本  
• ライブレスポンス: 無効  
• ブロックモードでの EDR の有効化: オフ  
• 改ざん防止: オフ  
  
Microsoft Defender XDR に自動攻撃阻止機能を実装する必要があります。  
  
どうすればよいでしょうか？

- A. 検出モードを標準検出に変更します。
- B. ライブレスポンスをオンに設定します。
- C. 改ざん防止をオンに設定します。
- D. ブロック モードで EDR を有効にするをオンに設定します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**解説：**
EDRのブロックモードにより、Microsoft Defender for Endpointは、主要なウイルス対策ソリューションがMicrosoft製以外の製品である場合やパッシブモードで実行されている場合でも、侵入後に検出された悪意のあるアーティファクトや動作を自動的に修復できます。このプロアクティブなブロック機能は、攻撃を阻止する自動封じ込め機能にとって不可欠です。

質問#37 トピック4

Microsoft Security Copilot を使用している Microsoft 365 サブスクリプションをお持ちです。Copilot 用のカスタム GPT プラグインを構成する予定です。  
  
どの GPT モデルを使用すればよいでしょうか？

- A. gpt-4o
- B. o1-ミニ
- C. ダヴィンチ-002
- D. gpt-35-ターボ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**解説:**
Security Copilotのカスタムプラグインで使用するGPTモデルです。
**「gpt-4o」**: Microsoft Copilot for Securityは、OpenAIの最新モデル（**GPT-4**や**GPT-4o**）を使用しています。カスタムプラグイン（OpenAIプラグイン互換）を作成する場合、Copilot for Securityがベースとしているモデルとの互換性や推奨モデルとして、**GPT-4**系が選択肢になります。GPT-3.5-turboやDavinciは古いモデルです。

質問#38 トピック4

Microsoft Security Copilot をご利用の Azure サブスクリプションをお持ちです。  
  
セキュリティ コンピューティング ユニットの数を一時的に増やす必要があります。  
  
課金対象となる最短の期間はどのくらいですか？

- A. 1秒
- B. 1分
- C. 1時間
- D. 1日

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**解説:**
Microsoft Copilot for Security（Security Copilot）のコンピュートユニット（SCU）の課金単位です。
SCUはプロビジョニングされた容量に基づいて**1時間単位**で課金されます。一時的に増良した場合、最短でも1時間分の料金が発生します。

質問#39 トピック4

Workspace1 という Microsoft Sentinel ワークスペースがあります。Workspace1 の AzureActivity テーブルの保持期間は以下のとおりです。  
  
• Interactive: 180 日  
• Total: 180 日  
  
以下の要件を満たすように保持期間を変更する必要があります。  
  
• テーブルへのデータ保存にかかるコストを最小限に抑える。  
• テーブルデータの利用可能期間を最大化する。  
  
各保持期間をどのように構成すればよいでしょうか？ 回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image462.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**正解:間違っている！** ![](https://img.examtopics.com/sc-200/image463.png)

**解説:**
Log Analyticsワークスペースのデータ保持期間とアーカイブ設定です。AzureActivityテーブルの180日分のデータを、コスト最小化かつ利用期間最大化の要件で構成します。

1. **Interactive Retention**: **「90 days」**。Azure Sentinel (Microsoft Sentinel) を利用している場合、最初の90日間（AzureActivityなどは無料の場合があるが、通常ワークスペース設定に依存）はデータ取り込み料に含まれるか、比較的安価ですが、長期のインタラクティブ保持は高価です。コストを最小化するため、必要最低限（デフォルトの30日や、無料枠の90日など）に設定します。ここでは選択肢次第ですが、アーカイブへの移行を早めるなら短くします。
2. **Total Retention**: **「730 days」**（またはそれ以上）。アーカイブ層（Archive Tier）は非常に安価です。インタラクティブ期間が終わった後、アーカイブ期間としてデータを保持することで「利用可能期間を最大化」しつつ「コストを最小化」できます。Log Analyticsでは最大7年（一部12年）まで保持可能です。選択肢にある最大値（730日など）を選びます。
※画像の正解を確認すると、Interactiveを**90日**（Sentinel特典で無料範囲）、Totalを**730日**（アーカイブ活用）に設定していると思われます。

質問#40トピック4

Linux を実行するオンプレミス サーバーが 200 台あります。Workspace1 という Microsoft Sentinel ワークスペースがあります。Azure Monitor の Log Ingestion API を使用して、これらのサーバーから Common Event Format (CEF) 形式の Syslog イベントを収集し、Workspace1 に取り込む予定です。API 要求を使用して、イベントのデータ収集ルール (DCR) を構成する必要があります。  
  
この API 要求をどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image476.png)

### 回答

- **streams:** `Microsoft-CommonSecurityLog`
    
- **Property:** `facilityNames: [`
    

---

### 解説

1. streams (ストリーム) の選択

Azure Monitor で **CEF (Common Event Format)** ログを取り込む際、リンク先となるシステムテーブルは **`CommonSecurityLog`** です。

- **Microsoft-CommonSecurityLog:** これが正解です。DCR の定義において、CEF 形式のログを標準の `CommonSecurityLog` テーブルにルーティングするための予約済みストリーム名です。
    
- **Microsoft-Syslog:** これは標準の Syslog 形式（RFC3164/5424）を取り込む際に使用されるため、CEF の場合は適しません。
    
- **SecurityEvent:** これは Windows のセキュリティイベントログ用です。
    

2. Property (プロパティ) の選択

JSON の構造と、後続のデータ（`"cron"`, `"daemon"`）から判断します。

- **facilityNames: [:** これが正解です。Syslog 設定において、収集対象とするファシリティ（`cron`, `daemon`, `auth` など）をリスト形式で指定するためのプロパティです。
    
- **outputStream: [:** これは DCR 内の `destinations` セクションに関連するものであり、`dataSources` 内の `syslog` 構成の中で個別のファシリティを指定するために使うプロパティではありません。
    
- **type: [:** ここでは適切なプロパティではありません。
    
---
#### DCR 構成のポイント

この構成により、200 台の Linux サーバーから送られる CEF ログのうち、指定したファシリティ（cron, daemon）かつ、指定したログレベル（Error, Critical, Alert, Emergency）に合致するものだけが Microsoft Sentinel (Workspace1) の `CommonSecurityLog` テーブルへ取り込まれるようになります。

質問#41トピック4

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをお持ちです。このサブスクリプションには、Microsoft Entra に参加し、Microsoft Defender for Endpoint の既定のデバイスグループに属し、Microsoft Intune を使用して管理されているデバイスが 500 台含まれています。Microsoft Defender の脆弱性管理を実装する必要があります。このソリューションは、管理の手間を最小限に抑える必要があります。Microsoft Defender ポータルでまず何をすべきでしょうか？

- A. 構成管理から、適用範囲設定を構成します。
- B. デフォルトのデバイス グループの自動修復を構成します。
- C. Microsoft Intune 接続をオンに設定します。
- D. ライブレスポンスをオンに設定します。

### 正解
**C. Microsoft Intune 接続をオンに設定します** です。

### 解説

Microsoft Defender の脆弱性管理（Vulnerability Management）を実装し、かつ「管理の手間を最小限に抑える」ためには、セキュリティポータルとエンドポイント管理ツールを連携させることが最優先となります。

- **なぜ「C」なのか:** Defender ポータルの設定で **Microsoft Intune 接続**（[設定] > [エンドポイント] > [高度な機能] 内の「Microsoft Intune 接続」）をオンにすることで、Defender 側で見つかった脆弱性データが自動的に Intune と共有されます。これにより、セキュリティ管理者がポータル上で「修復」ボタンをクリックするだけで、Intune 側にセキュリティタスク（修復リクエスト）を自動作成できるようになり、チーム間の連携や手動の管理コストを大幅に削減できます。
    
- **他の選択肢が不適切な理由:**
    
    - **A. 適用範囲設定を構成:** 脆弱性管理の前提として、まずはサービス間のパイプライン（接続）を確立する必要があります。
        
    - **B. 自動修復を構成:** これは主にアンチウイルス検知後の修復アクションに関連する設定であり、脆弱性（パッチ未適用など）の管理プロセスとは異なります。
        
    - **D. ライブレスポンスをオンに設定:** ライブレスポンスはデバイスにリモート接続して調査やファイル操作を行う機能であり、脆弱性管理の初期構成とは直接関係ありません。

質問#42トピック4

複数の Microsoft Sentinel ワークスペースを含む複数の Azure サブスクリプションがあります。AzureActivity テーブルへの参照を含む Microsoft Sentinel ブックを作成しています。  
  
次のアクションを実行する KQL クエリを作成する必要があります。  
  
• 各ワークスペースに AzureActivity テーブルが存在するかどうかを確認します。  
• テーブルが存在する場合は、isMissing 列が 0 に設定された単一の行を返します。• テーブルが存在しない場合は、isMissing 列が 1 に設定された単一の行を返します。  
  
クエリをどのように完了する必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image478.png)

## 回答

- **1つ目の選択肢:** `datatable`
    
- **2つ目の選択肢:** `isfuzzy=true`
    

---

## 解説

このクエリの目的は、ワークスペース内に `AzureActivity` テーブルが存在するかどうかでフラグ（`isMissing`）を切り替えることです。

1. `datatable` の選択

`let mTable =` の直後に続く構文 `(isMissing:int) [1]` は、メモリ内に一時的な静的テーブルを作成する **`datatable`** 演算子の標準的な書き方です。

- **datatable:** スキーマ（列名と型）を定義し、値を直接入力してテーブルを作成します。ここでは `isMissing` 列に `1` が入った1行のテーブルを作成しています。
    
- **extend / makelist:** これらは既存のデータセットに対して列を追加したりリストを作成したりする演算子であるため、この構文の開始点としては不適切です。
    
2. `isfuzzy=true` の選択

`union` 演算子における **`isfuzzy=true`** は、結合対象のテーブル（この場合は `AzureActivity`）が**存在しない場合にエラーを出さず、そのテーブルを無視して処理を続行させる**ための非常に重要なパラメータです。

- **なぜこれか:** `AzureActivity` テーブルが存在しないワークスペースでこのクエリを実行すると、通常は「テーブルが見つからない」というエラーで停止してしまいます。`isfuzzy=true` を指定することで、テーブルがない場合は空の結果として扱い、エラーを回避して `mTable`（isMissing=1）側の結果を出力できるようになります。
    
- **kind=outer / withsource:** これらは結合の方法やソースの特定を指定するものですが、テーブル自体の「欠落」によるエラーを防ぐ機能はありません。
---
### クエリの動作ロジック

1. まず、`isMissing` が `1` の `mTable` を作成します。
    
2. 次に、実際の `AzureActivity` テーブルを確認し、存在すれば `isMissing` を `0` に変換した行を生成します。
    
3. `union isfuzzy=true` で両者を結合します。
    
4. テーブルが存在すれば `0` と `1` の行が混ざりますが、`top 1`（ソート順によりますが、このロジックでは存在確認が優先されます）により、最終的なステータスを判定します。

質問#43トピック4
  
Microsoft 365 E5 サブスクリプションをお持ちです。Microsoft Entra からログを収集するには、Microsoft Sentinel を構成する必要があります。Microsoft Defender ポータルで使用する 2 つのノードはどれですか？回答するには、回答エリアで適切なノードを選択してください。  
  
注：正解は 1 点です  
  
![](https://img.examtopics.com/sc-200/image480.png)

## 回答

- **Content hub (コンテンツ ハブ):** 「Content management (コンテンツ管理)」セクション内
    
- **Data connectors (データ コネクタ):** 「Configuration (構成)」セクション内
    

---

## 解説

Microsoft Sentinel の新しい運用モデル（統合セキュリティ運用プラットフォーム）では、特定のソースからログを収集するために以下の 2 段階のステップが必要になります。

1. **Content hub (コンテンツ ハブ):** まず、Microsoft Entra ID 用の「ソリューション」を検索して**インストール**する必要があります。 ソリューションには、データコネクタ本体だけでなく、関連する分析ルールやブック（可視化ツール）が含まれています。
    
2. **Data connectors (データ コネクタ):** ソリューションのインストール後、このノードから **Microsoft Entra ID コネクタ**を選択し、「コネクタ ページを開く」から実際のログ（サインインログ、監査ログなど）の取り込みを有効にします。

質問#44トピック4

Workspace1 という Microsoft Sentinel ワークスペースがあり、そこには CommonSecurityLog というテーブルがあります。  
  
ログを CommonSecurityLog に取り込みます。CommonSecurityLog の平均ログ取り込み時間は 5 分です。7 分間のルックバック期間を持ち、CommonSecurityLog テーブルのデータを使用する分析ルールを作成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 同じイベントが 2 回処理されないようにする。  
• ログ取り込みの遅延によって見逃されるイベントの数を最小限に抑える。  
  
このルールを定義する KQL クエリをどのように完成させるべきでしょうか。回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが与えられます。  

![](https://img.examtopics.com/sc-200/image482.png)

## 回答

- **1つ目の選択肢 (TimeGenerated):** `(ingestion_delay + rule_look_back)`
    
- **2つ目の選択肢 (ingestion_time):** `(rule_look_back)`
    
---
## 解説

この問題は、ログの取り込み遅延（インジェスチョン・ディレイ）が発生する環境において、**「漏れなく、かつ重複なく」**分析ルールを実行するための標準的な手法を問うています。

1. `TimeGenerated >= ago(ingestion_delay + rule_look_back)`

`TimeGenerated` はイベントが実際に発生した時刻です。

- **理由:** ログがワークスペースに届くまでに平均 5 分かかるため、本来のルックバック期間（7 分）だけを遡ると、発生してから届くまでに時間がかかったイベントを取りこぼす可能性があります。
    
- **計算:** $5\text{分（遅延）} + 7\text{分（実行間隔）} = 12\text{分}$ 前まで遡って検索対象とすることで、遅れて届いたイベントも確実にスキャン範囲に含めます。
    
2. `ingestion_time() > ago(rule_look_back)`

`ingestion_time()` は、ログが実際に Azure Monitor に格納された時刻です。

- **理由:** 分析ルールの実行間隔である 7 分（`rule_look_back`）の間に「新しく届いた」ログのみを対象にします。
    
- **重複防止:** `TimeGenerated` で広い範囲をスキャンしていても、この `ingestion_time()` フィルタによって「前回のルール実行時（7 分前以前）に既に取り込まれたログ」は除外されるため、同じイベントを 2 回処理することを防げます。

質問#45トピック4

50 個のサブスクリプションが含まれる Azure 環境があり、その中には Sub1 というサブスクリプションもあります。Sub1 には、他のサブスクリプションからログを収集する Workspace1 という Microsoft Sentinel ワークスペースが含まれています。Workspace1 には WB1 というブックが含まれています。WB1  
  
に、Item1 というパラメーター項目を追加します。Item1 に、Parameter1 というパラメーターを追加します。  
  
次の要件を満たすように、Parameter1 のドロップダウン メニューを構成する必要があります。  
  
• ユーザーがクエリを実行するサブスクリプションを 1 つ以上選択できるようにします。  
• すべてのサブスクリプションをクエリするための単一のオプションをユーザーに提供します。  
  
ソリューションでは、WB1 にデータを入力するための時間を最小限に抑える必要があります。ソリューションでは、管理の労力を最小限に抑える必要があります。  
  
どうすればよいでしょうか。回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image484.png)

## 回答

- **Set Parameter type for Parameter1 to (Parameter1 の型):** `Subscription picker`
    
- **To enable users to query all the subscriptions (すべてのサブスクリプションをクエリ可能にする):** `Select Allow multiple selections.`
    
---
## 解説

この構成は、管理コストを抑えつつ、ユーザーが複数のサブスクリプションを柔軟に選択できるようにするための標準的な手法です。

1. Subscription picker (サブスクリプション ピッカー) の選択

- **管理の手間の最小化:** `Drop down` を選択すると、Azure Resource Graph クエリなどを記述してサブスクリプション一覧を取得する必要があります。一方、`Subscription picker` は Microsoft Sentinel（Azure Monitor Workbooks）に組み込まれた専用の型であり、クエリを書く必要が一切ないため、管理の手間が最小限になります。
    
- **データ読み込み時間の最小化:** 外部クエリを実行してリストを生成する `Drop down` よりも、ネイティブなピッカーである `Subscription picker` の方が高速に動作します。
    

2. Select Allow multiple selections. (複数選択を許可する) の選択

- **「1つ以上」の要件:** ユーザーが複数のサブスクリプションを選択できるようにするためには、この設定を有効にする必要があります。
    
- **「単一のオプションで全クエリ」の要件:** `Subscription picker` の設定で `Allow multiple selections` を有効にすると、その詳細設定の中に **「Include All（すべてを含む）」** というチェックボックスが表示されます。これをオンにすることで、ドロップダウン内に「All」という単一の選択肢が追加され、要件を満たすことができます。

質問#46トピック4

Azureサブスクリプションを3つ持っています。各サブスクリプションには、Windows Serverを実行する複数の仮想マシンが含まれています。Microsoft Sentinelワークスペースがあります。  

すべての仮想マシンからの失敗したサインイン試行をMicrosoft Sentinelを使用して分析できるようにする必要があります。ソリューションは管理の労力を最小限に抑える必要があります。  

まず何をすべきでしょうか？

- A. Microsoft Defender ポータルから、Windows セキュリティ イベント ソリューションをインストールします。
- B. 各仮想マシンでイベント サブスクリプションを作成します。
- C. 各仮想マシンに Azure Connected Machine エージェントをインストールします。
- D. Microsoft Defender ポータルから Syslog ソリューションをインストールします。

### 解答
A

### 解説
Microsoft SentinelでWindows Server VMからの失敗したサインイン試行を分析するには、Windowsセキュリティイベントログ（イベントID 4625など）が必要です。Microsoft Learnによると、Windowsセキュリティイベントソリューション（従来のセキュリティイベントコネクタの最新の代替品）は、Azure Monitor Agent（AMA）とデータ収集ルール（DCR）を使用します。一度有効化すれば複数のサブスクリプションに適用できます。VMごとの最小限の構成で、オンボーディングとログフローを自動的に処理します。WindowsセキュリティイベントをSentinelに取り込むための推奨される最新の方法です。

質問47トピック4

Windows Server を実行するオンプレミスの仮想マシン VM1 があります。Microsoft Sentinel ワークスペース Workspace1 があります。VM1 に Azure Connected Machine エージェントをインストールします。VM1 からイベントを収集し、Workspace1 に送信する必要があります。  
  
実行すべき 2 つのアクションはどれですか？ 正解はそれぞれ解答の一部です。  
  
注: 正解は 1 点です。

- A. VM1 に Microsoft Monitoring Agent をインストールします。
- B. VM1 に Log Analytics エージェントをインストールします。
- C. Microsoft Defender ポータルから、AMA データ コネクタ経由で Wi​​ndows セキュリティ イベントを追加します。
- D. Microsoft Defender ポータルから、AMA データ コネクタ経由で Syslog を追加します。
- E. VM1 で、Azure Monitor エージェント拡張機能を有効にします。
- F. Microsoft Defender ポータルから、VM1 を対象とするデータ収集ルール (DCR) を作成します。
正解は **E. VM1 で、Azure Monitor エージェント拡張機能を有効にする** と **F. Microsoft Defender ポータルから、VM1 を対象とするデータ収集ルール (DCR) を作成する** です。

## 解説
オンプレミスのサーバー（VM1）に **Azure Connected Machine エージェント (Azure Arc)** がインストールされている状態は、そのサーバーが Azure リソースとして管理可能であることを意味します。ここから Microsoft Sentinel へログを送るための現代的（AMAベース）な手順は以下の 2 つです。

1. Azure Monitor エージェント (AMA) の導入 (選択肢 E)

Azure Arc 対応サーバーからログを収集するには、マシン上で実際にログを読み取る「手足」となる **Azure Monitor エージェント (AMA)** が必要です。

- **アクション:** Azure ポータルまたは Defender ポータルから、VM1 に対して AMA 拡張機能をデプロイ（有効化）します。
    
- **なぜこれか:** 以前の Log Analytics エージェント（選択肢 A, B）はレガシーであり、現在は AMA への移行が推奨されています。
    

2. データ収集ルール (DCR) の作成と割り当て (選択肢 F)

AMA はインストールしただけでは動作しません。「どのログを」「どこ（Workspace1）に送信するか」という指示書が必要です。これが **データ収集ルール (DCR)** です。

- **アクション:** Defender ポータル（または Azure Monitor）で DCR を作成し、収集対象として VM1 を指定します。
    
- **なぜこれか:** DCR を作成・適用することで初めて、Windows イベントログの収集が開始されます。
    
---
#### 他の選択肢が不適切な理由

- **A & B (MMA/Log Analytics エージェント):** これらは旧式のエージェントです。現在の SC-200 試験や実務のベストプラクティスでは、新世代の AMA を使用することが前提となっています。
    
- **C (Windows セキュリティ イベントの追加):** 「データコネクタを構成する」という作業の中に DCR の作成が含まれますが、設問が求める「実行すべき具体的なアクション」としては、DCR の作成（F）とエージェントの有効化（E）がより正確な技術的ステップとなります。
    
- **D (Syslog の追加):** VM1 は Windows Server であるため、Linux 用の収集プロトコルである Syslog は不適切です。


質問#48トピック4
  
User1というユーザーとWorkspace1というMicrosoft Sentinelワークスペースを含むAzureサブスクリプションがあります。User1 がWorkspace1でワークブックとプレイブックを作成できるようにする必要があります。ソリューションは次の要件を満たす必要があります。  
  
• User1に割り当てるロールの数を最小限に抑える。  
• 最小権限の原則に従う。User1  
  
にはどのロールを割り当て、どのスコープでロールを割り当てる必要がありますか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1点です  
  
![](https://img.examtopics.com/sc-200/image486.png)

## 回答

- **Roles:** `Microsoft Sentinel Contributor and Logic App Contributor`
    
- **Scope:** `Resource group`
    
---
## 解説

1. ロール (Roles) の選択

要件である「ワークブック」と「プレイブック」の作成には、それぞれ異なる権限セットが必要です。

- **Microsoft Sentinel Contributor:** ワークブックの作成、編集、および Sentinel の主要なリソース（分析ルールなど）を管理するために必要です。
    
- **Logic App Contributor:** Microsoft Sentinel の「プレイブック」は実体として **Azure Logic Apps** であるため、これを作成・管理するにはこのロールが不可欠です。Sentinel の標準ロール（Contributor等）だけでは、Logic App 自体の作成権限は含まれません。
    
- **なぜ他が不適切か:**
    
    - `Microsoft Sentinel Contributor only` では、プレイブックを作成できません。
        
    - `Microsoft Sentinel Automation Contributor` は主にオートメーションルールの管理やプレイブックの「実行」権限を付与するものであり、プレイブック自体の「作成」には不十分です。
        

2. スコープ (Scope) の選択

「最小権限の原則」に基づき、権限の影響範囲を必要最小限に抑える必要があります。

- **Resource group:** プレイブック（Logic Apps）はワークスペースの「外」にある独立した Azure リソースとしてリソースグループ内に配置されます。ワークスペースとプレイブックが同じリソースグループにある場合、このスコープで権限を割り当てるのが、両方のリソースを管理できる最小かつ最適な単位となります。
    
- **なぜ他が不適切か:**
    
    - `Subscription` は、そのサブスクリプション内の全リソースに権限が及ぶため、権限が強すぎます。
        
    - `Workspace` スコープでは、ワークスペース外のリソースである Logic App (プレイブック) の作成権限を適切にカバーできません。
