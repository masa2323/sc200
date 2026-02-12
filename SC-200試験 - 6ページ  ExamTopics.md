質問#51 トピック1

Microsoft Purview を使用する Microsoft 365 E5 サブスクリプションがあり、User1 というユーザーがいます。User1 は、Microsoft Teams を使用して、会社の Microsoft OneDrive フォルダーにある Microsoft Power BI レポート ファイルを外部ユーザーと共有しました。  
  
共有された Power BI レポート ファイルを特定する必要があります。  
  
検索はどのように設定すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image192.png)

**正解:** ![](https://img.examtopics.com/sc-200/image414.png)

**解説:**
この問題のポイントは、**「共有されたファイルがどこに保存されているか」**と**「どのアクティビティが記録されるか」**を正しく判断することです。

1. Activities: `Share file, folder, or site`

- 問題文に「外部ユーザーと**共有**しました」とあります。
    
- Microsoft Purview の監査ログにおいて、OneDrive や SharePoint 上のファイル、フォルダーを共有する操作は、汎用的な「Share file, folder, or site (ファイル、フォルダー、またはサイトの共有)」アクティビティとして記録されます。
    
- _Shared Power BI report_ は、Power BI サービス（ブラウザ上のワークスペースなど）でレポートを共有した際のイベントであり、今回のように OneDrive 上の「ファイル」として扱われている場合には適しません。
    

2. Record type および Workload: `OneDrive`

- **保存場所の特定:** 問題文に「**OneDrive フォルダーにある** ... ファイル」と明記されています。
    
- **Teams との関係:** Microsoft Teams の個人チャットやグループチャットでファイルを共有した場合、その実体は送信者の **OneDrive for Business** にアップロードされます。
    
- **ログの発生元:** ファイルの共有設定の変更やアクセス権の付与は、ファイルが保存されているストレージ側（この場合は OneDrive）で発生するため、ワークロードおよびレコードの種類には `OneDrive` を選択するのが適切です。
    
    - _MicrosoftTeams_ ワークロードは、チャットメッセージの送信やチームの作成などのイベントを記録します。
        
    - _PowerBI_ ワークロードは、Power BI サービス内での操作（データセットの更新やダッシュボードの表示など）を記録します。
        

まとめ

User1 が Teams を使って共有したとしても、ファイルの実体が OneDrive にある以上、監査ログは **OneDrive** の **ファイル共有アクティビティ** を検索することで特定できます。

質問#53 トピック1

Microsoft PurviewとMicrosoft Teamsを使用するMicrosoft 365サブスクリプションをご利用です。Team1  というチームがあり、Project1というプロジェクトがあります。  
  
2023年2月1日から2023年2月10日の間にTeam1のチームサイトに保存されたProject1ファイルを特定する必要があります。  
  
どのKQLクエリを実行すればよいでしょうか？

- A. (c:c)(Project1)(date=(2023-02-01)..date=(2023-02-10))
- B. AuditLogs -  
    | where Timestamp between (datetime(2023-02-01)..datetime(2023-02-10))  
    | where FileName contains “Project1”
- C. Project1(c:c)(date=2023-02-01..2023-02-10)
- D. AuditLogs -  
    | where Timestamp > ago(10d)  
    | where FileName contains “Project1”

### 正解: **C. Project1(c:c)(date=2023-02-01..2023-02-10)**

### 解説:

Microsoft Purviewのコンテンツ検索でKQL（Keyword Query Language）を使用する場合、**`(c:c)`** という表記が重要な意味を持ちます。

ドキュメントによると:

- **`(c:s)`** = キーワード同士が **OR** 演算子で接続されていることを示す
- **`(c:c)`** = キーワードと条件が **AND** 演算子で接続されていることを示す

### 各選択肢の分析:

**選択肢A**: `(c:c)(Project1)(date=(2023-02-01)..date=(2023-02-10))`

- 構文が不正確です。日付範囲の指定方法が正しくありません

**選択肢B**: KQLではなく、Azure Log Analytics向けのKustoクエリ言語の構文です

- `AuditLogs`テーブルは、Microsoft PurviewのKQL検索では使用しません
- この形式はLog Analytics/Azure Sentinel用です

**選択肢C**: `Project1(c:c)(date=2023-02-01..2023-02-10)` ✓

- **`(c:c)`** により、キーワード「Project1」と日付条件が AND で接続されます
- 日付範囲の構文 `date=2023-02-01..2023-02-10` が正しい形式です
- `..` 演算子は日付範囲を指定するための標準的な方法です

**選択肢D**: 日付範囲が要件と一致しません

- `ago(10d)` は「10日前から」を意味し、2023年2月1日～10日という特定期間を指定していません

質問#54 トピック1

Microsoft Defender for Endpoint を使用する Microsoft 365 E5 サブスクリプションをお持ちです。AlertInfo、AlertEvidence、DeviceLogonEvents テーブルをリンクするクエリを作成する必要があります。ソリューションは、テーブル内のすべての行を返す必要があります。  
  
どの演算子を使用すればよいでしょうか？

- A. search *
- B. union kind = inner
- C. join kind = inner
- D. evaluate hint.remote =

### 正解: **該当なし（正確には `join kind=fullouter` ですが、選択肢にはありません）**

ただし、**選択肢の中で最も問題の要件に近いのは C. join kind = inner** ですが、これは正解ではありません。

### 詳細な解説:
問題の要件は「**テーブル内のすべての行を返す必要があります**」です。

#### 各Join演算子の動作:

**`join kind=inner`（選択肢C）**:
- 両方のテーブルで一致する行**のみ**を返します
- 一致しない行は除外されます
- ✗ すべての行を返しません

**`join kind=fullouter`（選択肢にない）**:
- 両方のテーブルのすべての行を返します
- 一致しない行にはNULL値が入ります
- ✓ これが正しい答えです

**`union kind=inner`（選択肢B）**:
- `union`は複数テーブルの行を結合しますが、「リンク」するわけではありません
- `kind=inner`は両方のテーブルに存在するカラムのみを保持します
- ✗ 要件を満たしません

**`search *`（選択肢A）**:
- 全テーブル検索に使用されますが、テーブルを「リンク」しません
- ✗ 要件を満たしません

**`evaluate hint.remote`（選択肢D）**:
- リモートクエリ最適化のヒントです
- ✗ テーブルをリンクする演算子ではありません

質問#55 トピック1

100台のWindows 10デバイスを含むMicrosoft 365 E5サブスクリプションを所有しています。  
  
これらのデバイスをMicrosoft Defender 365にオンボードします。Microsoft 365 Defenderポータルから、オンボードしたデバイスへのリモートシェル接続を開始できることを確認する必要があります。  
  
まず何をすべきでしょうか？

- A. Microsoft 365 Defender のアクセス許可を変更します。
- B. デバイス グループを作成します。
- C. Microsoft 365 Defender ポータルのエンドポイント設定の高度な機能から、自動調査を有効にします。
- D. ロールベースのアクセス制御 (RBAC) を構成します。

### 正解: **B. デバイス グループを作成します**

ただし、実際には複数のステップが必要ですが、「まず何をすべきか」という質問に対する答えとして、選択肢の中で最も適切なのはBです。

### 詳細な解説:

ドキュメントによると、Microsoft Defender for Endpointのライブレスポンス（リモートシェル接続）を使用するための前提条件は以下の通りです:

#### 必須の設定手順（順序）:

1. **高度な機能でライブレスポンスを有効化する**
    - `設定 > エンドポイント > 高度な機能 > Live response` をオンにする
    - これは管理者または「ポータル設定の管理」権限を持つユーザーのみが実行可能
2. **RBAC（ロールベースのアクセス制御）を構成する**
    - ユーザーに適切な権限を付与する
    - ライブレスポンスセッションを開始できるのは、適切な権限が付与されたユーザーのみ
3. **デバイスグループの作成**（RBACを使用する場合）
    - デバイスグループを作成し、ユーザーグループに割り当てる

### 各選択肢の分析:

**選択肢A: Microsoft 365 Defender のアクセス許可を変更**

- これはRBACの設定の一部ですが、まず基本機能を有効にする必要があります
- ✗ これだけでは不十分

**選択肢B: デバイス グループを作成**

- デバイスグループはRBACで権限を特定のデバイスセットに制限するために使用されます
- ドキュメントによると、デバイスグループは「RBACのコンテキストで作成され、ユーザーグループをデバイスグループに割り当てることで、誰が特定のアクションを実行できるかを制御します」
- ✓ これが最も適切な最初のステップ

**選択肢C: 自動調査を有効にする**

- 自動調査はライブレスポンスとは別の機能です
- ✗ ライブレスポンスの前提条件ではありません

**選択肢D: ロールベースのアクセス制御 (RBAC) を構成**

- これは必須ステップですが、デバイスグループの作成と組み合わせて行います
- ドキュメントによると、「RBACを有効にして、デバイスグループを作成する」という流れです

### 正しい実装手順:

実際の実装では、以下の順序で設定します:

1. **デバイスグループを作成**（選択肢B）
2. **RBACを構成**（選択肢D）
3. **高度な機能でライブレスポンスを有効化**（設定から）
4. **必要に応じてアクセス許可を調整**（選択肢A）

質問#56 トピック1

Microsoft Defender for Endpoint を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
以下の要件を満たす検出ルールを作成する必要があります。  
  
• 重大なソフトウェア脆弱性を持つデバイスが過去 1 時間以内にアクティブだった場合にトリガーされる  
• 重複する結果の数を制限する  
  
KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択肢は 1 つにつき 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image219.png)

## 正解:
**第1のドロップダウン**: `| distinct DeviceId`
**第2のドロップダウン**: `| project Timestamp, DeviceId, ReportId`

## 詳細な解説:

### クエリの構造分析:

kusto

```kusto
DeviceTvmSoftwareVulnerabilities
| where VulnerabilitySeverityLevel == 'Critical'
```

この部分は、重大な脆弱性を持つデバイスをフィルタリングします。

### 第1のドロップダウン（重複削減）:

**選択肢**:

- `| distinct CveId`
- `| distinct DeviceId` ✓
- `| project-away CveId`
- `| project-keep DeviceId`

**正解: `| distinct DeviceId`**

**理由**:

- 要件は「重複する結果の数を制限する」です
- 1つのデバイスが複数の重大な脆弱性を持つ可能性があります
- `distinct DeviceId` は、各デバイスを1回だけ返すため、重複を完全に排除します
- `distinct CveId` では、同じデバイスが異なるCVEで複数回表示される可能性があります
- `project-away` と `project-keep` は列の選択/除外であり、重複排除ではありません

### 中間のjoin処理:

kusto

```kusto
| join kind=inner DeviceInfo on DeviceId
| where Timestamp between (now(-1h)..now())
```

この部分は、DeviceInfoテーブルと結合し、過去1時間以内にアクティブだったデバイスをフィルタリングします。

### 第2のドロップダウン（最終出力）:

**選択肢**:

- `| distinct DeviceId`
- `| distinct DeviceId, ReportId`
- `| project Timestamp, DeviceId, ReportId` ✓
- `| summarize count() by DeviceId, ReportId`

**正解: `| project Timestamp, DeviceId, ReportId`**

**理由**:

- 検出ルールには、アラートの詳細情報が必要です
- `Timestamp`: いつデバイスがアクティブだったか
- `DeviceId`: どのデバイスか
- `ReportId`: 脆弱性レポートの識別子
- `summarize count()` は集計を行いますが、個別のイベント詳細が失われます
- 最初の `distinct DeviceId` で既に重複は排除されているため、ここでは必要な列を選択するだけです

### 完成したクエリ:

kusto

```kusto
DeviceTvmSoftwareVulnerabilities
| where VulnerabilitySeverityLevel == 'Critical'
| distinct DeviceId
| join kind=inner DeviceInfo on DeviceId
| where Timestamp between (now(-1h)..now())
| project Timestamp, DeviceId, ReportId
```

このクエリは:

1. ✓ 重大な脆弱性を持つデバイスを識別
2. ✓ デバイスごとに1回だけ表示（重複排除）
3. ✓ 過去1時間以内にアクティブだったデバイスのみ
4. ✓ 必要な情報（Timestamp、DeviceId、ReportId）を返す

質問#57 トピック1
  
Microsoft Teams を使用する Microsoft 365 E5 サブスクリプションをご利用です。
Microsoft Purview コンプライアンス ポータルを使用して、ユーザーの Teams チャットのコンテンツ検索を実行する必要があります。ソリューションでは、検索範囲を最小限に抑える必要があります。  
  
コンテンツ検索はどのように構成すればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image221.png)

## 正解:
**Locations**: `Exchange mailboxes`
**Keywords**: `Kind`

## 詳細な解説:

### Locationsの選択:

ドキュメントによると、**Microsoft Teamsのチャットメッセージは以下の場所に保存されます**:

1. **1:1チャット**: 全チャット参加者のExchange Onlineメールボックスに保存
2. **グループチャット（1:N）**: 全チャット参加者のExchange Onlineメールボックスに保存
3. **チャネルメッセージ**: チームに関連付けられたExchange Onlineメールボックスに保存

したがって、**Teamsチャットを検索するには`Exchange mailboxes`を選択する必要があります**。

**選択肢の分析**:

- ❌ **Exchange public folders**: パブリックフォルダーはTeamsチャットを含みません
- ✅ **Exchange mailboxes**: Teamsチャットはここに保存されます
- ❌ **SharePoint sites**: SharePointにはTeamsチャネルの**ファイル**が保存されますが、チャットメッセージは保存されません

### Keywordsの選択:

ドキュメントによると、**Teamsコンテンツを特定して検索するには**:

**`Kind`プロパティを使用**:

```
kind:microsoftteams
```

これは、Teamsのチャット、会議、通話からのアイテムを返します。

**選択肢の分析**:

- ❌ **Category**: カテゴリプロパティはTeams検索には使用されません
- ❌ **ItemClass**: `itemclass:IPM.SkypeTeams.Message`も使用可能ですが、`Kind`の方が一般的で推奨されます
- ✅ **Kind**: `kind:microsoftteams`が最も適切で、公式ドキュメントで推奨されている方法です

### 検索範囲の最小化:

この構成は**検索範囲を最小限に抑える**という要件も満たします:

1. **Exchange mailboxes**のみを対象とすることで、SharePointサイトやパブリックフォルダーを除外
2. **Kind:microsoftteams**を使用することで、メールやその他のコンテンツを除外し、Teamsコンテンツのみに絞り込み

質問#58 トピック1

Microsoft 365 E5 サブスクリプションに Linux デバイス 100 台が含まれており、デバイスは Microsoft Defender 365 にオンボードされています。Microsoft 365 Defender ポータルを使用して、デバイスから調査パッケージの収集を開始する必要があります。  
  
どのような対応アクションを実行すればよいでしょうか？

- A. ウイルススキャンを実行する
- B. 自動調査を開始する
- C. 調査パッケージの収集
- D. ライブレスポンスセッションを開始する

## 正解: **D. ライブレスポンスセッションを開始する**

## 詳細な解説:

### Linuxデバイスでの調査パッケージ収集方法:

ドキュメントによると、**Linuxデバイスから調査パッケージを収集するには、ライブレスポンスの`collect`コマンドを使用する必要があります**。

### 各選択肢の分析:

**選択肢A: ウイルススキャンを実行する**

- これは`scan`コマンドまたは「Run antivirus scan」アクションです
- マルウェアの識別と修復に使用されますが、調査パッケージは収集しません
- ✗ 調査パッケージ収集には使用できません

**選択肢B: 自動調査を開始する**

- これは自動化されたインシデント調査機能です
- 調査パッケージの手動収集とは異なります
- ✗ 直接的な調査パッケージ収集方法ではありません

**選択肢C: 調査パッケージの収集**

- Windowsデバイスでは、デバイスページから直接「Collect investigation package」アクションが利用可能です
- **しかし、Linuxデバイスではこの直接的なアクションは利用できません**
- ✗ Linuxデバイスには適用できません

**選択肢D: ライブレスポンスセッションを開始する** ✓

- **これが正解です**
- Linuxデバイスでは、ライブレスポンスセッション内で`collect`コマンドを使用する必要があります

### Linuxでの調査パッケージ収集の手順:

ドキュメントによると:

1. **ライブレスポンスセッションを開始**
    - Microsoft Defender ポータル > デバイスを選択 > 「Initiate live response session」
2. **`collect`コマンドを実行**
    - ライブレスポンスコンソールで`collect`と入力
    - これは**高度なコマンド**で、適切な権限が必要です

### ライブレスポンスコマンド表（Linuxサポート）:

|コマンド|説明|Linux サポート|
|---|---|---|
|`collect`|デバイスからフォレンジックパッケージを収集|✓ Yes|
|`scan`|クイックウイルススキャンを実行|✓ Yes|
|`getfile`|ファイルをダウンロード|✓ Yes|

### Linuxでの調査パッケージに含まれる内容:

- ディスクボリューム情報
- 開いているファイルのリスト
- アクティブな接続とリスニング接続
- ARPテーブル、ファイアウォールルール
- 実行中のプロセスのリスト
- CPU詳細、ハードウェア情報
- サインイン履歴、Sudoers

質問#59 トピック1

機密ファイルが外部に共有された場合にアラートを生成し、修復アクションをトリガーするように、Microsoft Defender for Cloud Apps を構成する必要があります。Microsoft 365 Defender ポータルで実行する必要がある 2 つのアクションはどれですか？ 正解はそれぞれ解答の一部を示しています。  
  
注: 正解は 1 点です。

- A. \[設定\] から \[クラウド アプリ\] を選択し、\[Microsoft Information Protection\] を選択してから、\[このテナントからの Microsoft Information Protection の機密ラベルとコンテンツ検査警告のファイルのみをスキャンする\] を選択します。
- B. クラウド アプリから \[ファイル\] を選択し、\[ファイルの種類\] を \[ドキュメント\] にフィルターします。
- C. \[設定\] から \[クラウド アプリ\] を選択し、\[Microsoft Information Protection\] を選択して \[ファイル\] を選択し、ファイル監視を有効にします。
- D. クラウド アプリから \[ファイル\] を選択し、アプリを Office 365 にフィルターします。
- E. クラウド アプリから \[ファイル\] を選択し、検索から \[新しいポリシー\] を選択します。
- F. \[設定\] から \[クラウド アプリ\] を選択し、\[Microsoft Information Protection\] を選択して、\[新しいファイルで Microsoft Information Protection の機密ラベルとコンテンツ検査の警告を自動的にスキャンする\] を選択します。

## 正解: **C** と **F**

**C. 設定 → Information Protection → ファイル → ファイル監視を有効にする**

**F. 設定 → Information Protection → Azure Information Protection → 新しいファイルを自動的にスキャンする**

## 詳細な解説:

### 重要な注意点:

選択肢では「Azure Information Protection」と記載されていますが、現在のMicrosoft製品では「Microsoft Information Protection」または「Microsoft Purview Information Protection」という名称が使用されています。試験問題では古い名称が使われている場合がありますが、機能は同じです。

### 必要な2つのアクション:

**✓ 選択肢C: ファイル監視を有効にする**

**場所**: 設定 → Information Protection → ファイル → **Enable file monitoring**

**理由**:

- これはDefender for Cloud Appsでファイルポリシーを機能させるための**必須の前提条件**です
- ドキュメントより: _"Select Enable file monitoring and then select Save"_
- ファイル監視が有効でないと、ファイルポリシーは作成できても機能しません

**✓ 選択肢F: 新しいファイルを自動的にスキャンする**

**場所**: 設定 → Information Protection → Azure Information Protection (現在はMicrosoft Information Protection) → **Automatically scan new files for sensitivity labels and content inspection warnings**

**理由**:

- 機密ラベルが付いたファイルを検出するために必要です
- ドキュメントより: _"Automatically scan new files for Microsoft Information Protection sensitivity labels and content inspection warnings"_
- これにより、新しくアップロードされたファイルが自動的にスキャンされ、機密ラベルが識別されます

### 他の選択肢が正解でない理由:
**✗ 選択肢A: このテナントからのみスキャン**
- これはオプションの設定で、外部テナントのラベルを除外します
- 必須ではありません

**✗ 選択肢B: ファイルの種類でフィルター**
- これは単なる表示フィルターです
- ポリシー設定には影響しません

**✗ 選択肢D: アプリでフィルター**
- これも表示フィルターです
- 構成手順ではありません

**✗ 選択肢E: ファイルから新しいポリシーを選択**
- 正しいパスは「ポリシー → ポリシー管理」から作成します
- また、これは3番目のステップ（ポリシー作成）であり、最初に必要な2つの設定ではありません

### 完全な構成手順:

1. **ファイル監視を有効化**（選択肢C）
```
   設定 → Information Protection → Files → Enable file monitoring → 保存
```

2. **自動スキャンを有効化**（選択肢F）
```
   設定 → Information Protection → Microsoft Information Protection 
   → Automatically scan new files → 保存
```

3. **ファイルポリシーを作成**（次のステップ）
```
   クラウドアプリ → ポリシー → ポリシー管理 → ポリシーの作成 → ファイルポリシー
   - Access Level = External
   - Sensitivity label = Confidential
   - Alerts: Create alert for each matching file
   - Governance actions: Remove external users など
```

### 結論:
**正解: C + F**

この2つの設定により、機密ファイルの外部共有を検出し、アラートと修復アクションをトリガーする準備が整います。これらは、効果的なファイルポリシーを作成するための**必須の前提条件**です。

質問#60 トピック1

Microsoft Purview を使用する Microsoft 365 サブスクリプションをご利用です。  
  
会社には Project1 というプロジェクトがあります。  
  
件名に Project1 という単語が含まれるすべてのメールメッセージを特定する必要があります。このソリューションでは、Project1 に携わったユーザーのメールボックスのみを検索する必要があります。  
  
どうすればよいでしょうか？

- A. ユーザーデータ検索を実行します。
- B. 記録管理処分を作成します。
- C. 監査検索を実行します。
- D. コンテンツ検索を実行します。

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)  

**解説:**
件名に "Project1" を含むメールを、特定の関与ユーザーのメールボックスのみから検索するには、Microsoft Purviewの **「コンテンツ検索 (Content search)」** を使用します。
コンテンツ検索では、検索対象の場所（特定のユーザーメールボックス）を指定し、キーワードクエリ（`Subject:"Project1"`）を使用して条件に合致するアイテムを抽出できます。「ユーザーデータ検索」という特定の機能名はPurviewにはなく（DSRなどのコンテキストではありますが）、一般的なメール検索にはコンテンツ検索が標準的です。