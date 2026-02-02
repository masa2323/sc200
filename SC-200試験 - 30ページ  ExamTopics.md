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

Microsoft Defender for Endpointのインジケーター動作について、Microsoft Learn MCP を使って正確な情報を確認します。

まず、関連するドキュメントを検索します。この情報から、3つの質問に回答します。

## 分析

提供された情報から、以下のルールが適用されます:

### ポリシー競合の処理ルール:

1. **ハッシュタイプの優先順位**: SHA-256 > SHA-1 > MD5
2. **スコープの優先順位**: 特定のデバイスグループにスコープされたインジケーター > 全デバイスを対象とするインジケーター

### 各ホストの分析:

**Host1** (Windows 11, DG1):

- ID2 (SHA-256, Allow, DG1) - 適用対象
- ID3 (SHA-1, Block execution, DG1, DG2) - 適用対象
- ID4 (SHA-256, Block execution, DG1) - 適用対象
- ID1とID2が同じファイルを参照しているため、Host1には適用されません

**Host2** (Windows 11, DG2):

- ID1 (SHA-256, Block and remediate, DG2) - 適用対象
- ID3 (SHA-1, Block execution, DG1, DG2) - 適用対象
- ID4はDG1のみなので適用されません

**Host3** (macOS, DG1):

- ID2 (SHA-256, Allow, DG1) - 適用対象
- ID3 (SHA-1, Block execution, DG1, DG2) - 適用対象
- ID4 (SHA-256, Block execution, DG1) - 適用対象

### 各文の評価:

**文1**: "Host1 will block the execution of a file that has the SHA-1 hash value of 2aae6c35c94fcfb415dbe95f408b9ce91ee846ed."

- ID3 (SHA-1) はHost1のデバイスグループ(DG1)に適用されます
- しかし、ID4 (SHA-256) も同じDG1に適用され、同じファイルに対するものです
- SHA-256 > SHA-1 の優先順位により、ID4が適用されます
- ID4のアクションは "Block execution" です
- **答え: Yes**

**文2**: "Host2 will block and remediate a file that has the SHA-256 hash value of 88d4266fd4e6338d13b845fcf289579d209c897823b9217da3e161936f031589."

- ID4はDG1のみに適用され、Host2はDG2に属するため、ID4は適用されません
- **答え: No**

**文3**: "Host3 will block the execution of a file that has the SHA-256 hash value of 88d4266fd4e6338d13b845fcf289579d209c897823b9217da3e161936f031589."

- ID4 (SHA-256, Block execution) はHost3のデバイスグループ(DG1)に適用されます
- **答え: Yes**

## 回答:

| 文                                                                                                                                             | Yes | No  |
| --------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- |
| Host1 will block the execution of a file that has the SHA-1 hash value of 2aae6c35c94fcfb415dbe95f408b9ce91ee846ed.                           | ○   |     |
| Host2 will block and remediate a file that has the SHA-256 hash value of 88d4266fd4e6338d13b845fcf289579d209c897823b9217da3e161936f031589.    |     | ○   |
| Host3 will block the execution of a file that has the SHA-256 hash value of 88d4266fd4e6338d13b845fcf289579d209c897823b9217da3e161936f031589. | ○   |     |

質問19 トピック5

Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションがあります。Microsoft Sentinel ワークスペースがあります。Microsoft Sentinel コネクタは、次の表に示すように構成されています。Microsoft Sentinel を  
  
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
### 1. Device3 での File1.exe のブロックについて

- **判定:** **いいえ**
    
- **理由:** Rule1 の適用範囲（スコープ）は **DevGroup1** に限定されています。Device3 は **DevGroup2** に所属しているため、このルールの対象外となります。したがって、File1.exe が実行されてもブロックのアクションはトリガーされません。
    

### 2. User2 のリスクレベルについて

- **判定:** **いいえ**
    
- **理由:** User2 がサインインしている Device2 は DevGroup1 に属しているため、ルールのアクション「ユーザー：侵害済みとしてマーク（Mark as compromised）」が実行されます。
    
- **詳細:** Microsoft Entra ID 保護（Entra ID Protection）の仕様では、ユーザーを「侵害済みとしてマーク」した場合、そのユーザーのリスクレベルは自動的に「**高 (High)**」に設定されます。「中 (Medium)」ではないため、この文は正しくありません。
    
### 3. Device1 からの調査パッケージの収集について

- **判定:** **はい**
    
- **理由:** User1 がサインインしている Device1 は **DevGroup1** に属しており、ルールのスコープ内です。
    
- **詳細:** Rule1 のアクションとして「デバイス：調査パッケージを収集（Collect investigation package）」が構成されているため、条件に一致する File1.exe が実行されると、Device1 から調査パッケージが正しく収集されます。

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

質問#22 トピック5

Windows 11 および Linux CentOS デバイスを含む Microsoft 365 E5 サブスクリプションをご利用です。Microsoft Defender XDR で「Deception」が「オン」に設定されています。  
  
カスタムルアーを使用するデセプションルールを作成する予定です。  
  
カスタムルアーのファイルの種類と配置パスを指定する必要があります。  
  
何を指定すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image378.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解:間違っている！** ![](https://img.examtopics.com/sc-200/image379.png)

**解説:**
### 1. File type (ファイルの種類) について

- **LNK** が推奨されます。
    
- デセプションルールにおける **LNK（ショートカットファイル）** は、攻撃者がそのファイルをクリックしたりプロパティを確認したりした際に、自動的にデコイ（偽のサーバーやリソース）へと誘導するよう設計されています。
    
- 攻撃者が「機密情報へのショートカット」と誤認してアクセスする可能性が高いため、おとりとして非常に有効です。
    

### 2. Planting path (配置パス) について

- **{HOME}** を指定します。
    
- Microsoft Defender XDR のデセプション設定では、変数の **`{HOME}`** を使用することで、対象となる Windows デバイスのユーザープロファイル（例: `C:\Users\Username`）や、Linux デバイスのホームディレクトリ（例: `/home/username`）にルアーを自動的に配置できます。
    
- これにより、環境内の複数のユーザーや異なる OS（Windows/Linux）に対して、攻撃者の目に留まりやすい場所に一括でおとりを設置することが可能になります。

質問#23 トピック5

Microsoft 365 E5 サブスクリプションをご利用です。  
  
攻撃者が特定のデバイスに接続しようとした際に、Microsoft Defender XDR でアラートが生成されるようにする必要があります。ソリューションは管理作業を最小限に抑える必要があります。Microsoft Defender ポータルではどのような操作を行うべきでしょうか？

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

質問#24 トピック5

Microsoft 365 E5 サブスクリプションをお持ちで、Site1 という Microsoft SharePoint Online サイトが含まれています。Site1 に対して Microsoft Defender for Cloud Apps セッション制御を有効にする必要があります。  
  
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

質問#25 トピック5
  
Microsoft 365 E5 サブスクリプションがあり、Policy1 という条件付きアクセスポリシーが設定されています。  
  
以下の操作を行う必要があります。  
  
• Custom1 という条件付きアプリアクセス制御カスタムポリシーを作成します。  
• Custom1 を使用するように Policy1 を構成します。

Custom1 の作成にはどのような設定が必要ですか？また、Policy1 のどの設定で条件付きアプリアクセス制御を有効にする必要がありますか？回答するには、回答エリアから適切なオプションを選択してください。
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image380.png)

**正解:間違っている！** ![](https://img.examtopics.com/sc-200/image381.png)

**解説:**
## 回答エリア (Answer Area)

- **Use:** **Microsoft Defender portal**
    
- **Settings:** **Session**
    
---

## 解説とロジック

### 1. 「Use」について（Custom1 の作成場所）

- **機能の所在:** 条件付きアプリアクセス制御（Conditional Access App Control）は、**Microsoft Defender for Cloud Apps** の機能です。
    
- **管理ポータル:** 現在、Microsoft Defender for Cloud Apps のポリシー作成や管理は、統合された **Microsoft Defender portal**（https://www.google.com/search?q=security.microsoft.com）で行います。
    
- **作成手順:** Defender ポータル内で「クラウド アプリ」＞「ポリシー」＞「ポリシー管理」から、条件付きアプリアクセス制御用のカスタムポリシー（Custom1）を作成します。
    

### 2. 「Settings」について（Policy1 での構成）

- **連携の仕組み:** 条件付きアクセスポリシー（Policy1）で特定のアプリへのアクセスを制御し、そのトラフィックを Defender for Cloud Apps にリダイレクトする必要があります。
    
- **設定箇所:** 条件付きアクセスポリシーの「アクセス制御」セクションにある **「セッション (Session)」** コントロールを使用します。
    
- **具体的な構成:** 「セッション」内で **「条件付きアプリアクセス制御を使う」** を選択し、そこで「カスタム ポリシーを使用する」などの設定を行うことで、事前に作成した Custom1 と Policy1 を紐付けることができます。

質問#26 トピック5

Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをお持ちです。  
  
デセプションルールを実装しています。  
  
カスタムルアーファイルを用意する必要があります。  
  
カスタムルアーの「Planting path」を HOME に設定しました。  
  
カスタムルアーにはどのような種類のファイルを使用できますか？また、ファイルはデバイスのどのホームディレクトリに配置する必要がありますか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image382.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)

**正解:間違っている！** ![](https://img.examtopics.com/sc-200/image383.png)

## 回答エリア (Answer Area)

- **File types:** **EXE, XLSX, and PDF**
    
- **The home directory of:** **The planted cached user**
    
---

## 解説とロジック

### 1. カスタムルアーのファイル形式について

Microsoft Defender XDR のデセプションルールでは、攻撃者が興味を持ちそうな「おとり」として複数のファイル形式をサポートしています。

- **サポートされている形式:** 代表的なものとして **EXE**（実行ファイル）、**XLSX**（Excel スプレッドシート）、**PDF**（ドキュメント）などが含まれます。
    
- 選択肢の中で、これら主要な3つの形式をすべて含む **「EXE, XLSX, and PDF」** が最も包括的かつ正しい設定です。これらを組み合わせることで、より自然なユーザー環境を装うことができます。
    
### 2. 配置場所（Planting path）について

`Planting path` を `{HOME}` に設定した場合、ファイルがどのユーザーのディレクトリに配置されるかが重要です。

- **デコイアカウントの役割:** デセプションルールが適用されると、デバイス上には「デコイ（おとり）」となる偽のユーザーアカウントが生成またはキャッシュされます。これを **Planted cached user** と呼びます。
    
- **配置の意図:** 実ユーザーの業務を妨げず、かつ攻撃者が横展開（ラテラルムーブメント）を試みた際に見つけやすい場所に配置するため、おとりファイルはこの **Planted cached user（植え付けられたキャッシュユーザー）** のホームディレクトリに配置されます。

  
質問#27 トピック5

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。  
  
以下のリスクを軽減するには、Defender for Cloud を構成する必要があります。  
  
• アプリケーション ソースコード内の脆弱性  
• 宣言型テンプレート内のエクスプロイトツールキット  
• 悪意のある IP アドレスからの操作  
• 公開されたシークレット  
  
使用すべき 2 つの Defender for Cloud サービスはどれですか？ 正解はそれぞれソリューションの一部を示しています。  
  
注: 正解は 1 点です。

- A. API 向け Microsoft Defender
- B. リソース マネージャー用の Microsoft Defender
- C. Microsoft Defender for App Service
- D. Microsoft Defender for Servers
- E. DevOps 向け Microsoft Defender

正解は **B. リソース マネージャー用の Microsoft Defender** と **E. DevOps 向け Microsoft Defender** です。

それぞれのサービスが対応するリスクの詳細は以下の通りです。

### 1. DevOps 向け Microsoft Defender (Microsoft Defender for DevOps)

以下の 3 つのリスクを包括的にカバーします。

- **アプリケーション ソースコード内の脆弱性:** GitHub や Azure DevOps などの開発環境と連携し、コードのスキャン結果を Defender for Cloud 上で一元管理します。
    
- **宣言型テンプレート内のエクスプロイトツールキット:** Terraform や Bicep、ARM テンプレートなどの Infrastructure as Code (IaC) スキャンを行い、設定ミスや脆弱な構成を検出します。
    
- **公開されたシークレット:** コード内にハードコードされたパスワード、API キー、トークンなどの「シークレット」をスキャンして検出します。
    

### 2. リソース マネージャー用の Microsoft Defender (Microsoft Defender for Resource Manager)

残り 1 つのリスクに対応します。

- **悪意のある IP アドレスからの操作:** Azure Resource Manager (ARM) を介したコントロール プレーン（管理レイヤー）の操作を常に監視しています。既知の悪意のある IP アドレスからのリソース作成や設定変更などの不審なアクティビティを検出します。

410問中**291 - 300**問 を表示
