質問7 トピック1

Microsoft 365 E5 サブスクリプションをご利用です。Microsoft 365 Defender を使用してクロスドメイン調査を実施する予定です。  
悪意のあるメール添付ファイルの影響を受けるデバイスを特定するための高度なハンティングクエリを作成する必要があります。  
クエリはどのように完成させるべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正解は1つにつき1ポイントです。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0001800001.png)  

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0001900001.png) 参照:  
<https://docs.microsoft.com/en-us/microsoft-365/security/mtp/advanced-hunting-query-emails-devices?view=o365-worldwide>

**解説:**
このクエリは、「メールのデータ」と「デバイス上のファイル操作データ」という 2 つの異なるドメインを結合して調査する、クロスドメインクエリの典型的な構成です。

1. `join`（1 番目のドロップダウン）

`EmailAttachmentInfo` テーブル（メールの添付ファイル情報）と `DeviceFileEvents` テーブル（デバイス上のファイル操作情報）を関連付けるには、共通のキー（今回は `SHA256` ハッシュ値）を使用してテーブルを結合する必要があります。そのため、**`join`** 演算子を使用します。

1. `project`（2 番目のドロップダウン）

`join` の括弧内にある `DeviceFileEvents` から、結合に必要な `SHA256` と、後で表示したい `FileName` だけを抽出しています。このように、特定の列のみを選択（投影）する演算子は **`project`** です。結合前に列を絞り込むことは、クエリのパフォーマンス向上にも繋がります。

1. `project`（3 番目のドロップダウン）

クエリの最後で、最終的に表示したい列（タイムスタンプ、デバイス名、受信者アドレスなど）をリストアップしています。ここでも、出力結果に含める列を指定するために **`project`** 演算子を使用します。

質問#38 トピック1
  
Microsoft 365 E5 サブスクリプションをお持ちです。
Document.pdf という添付ファイルを含むすべてのメールを返すハンティングクエリを作成する必要があります。クエリは以下の要件を満たす必要があります。  
  
• 過去 1 時間以内に送信されたメールのみを表示する。  
• クエリのパフォーマンスを最適化する。  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image157.png)

**正解:** ![](https://img.examtopics.com/sc-200/image158.png)

**解説:**

### クエリの論理と最適化のポイント

このクエリを最適化するための鍵は、**「データの絞り込みをできるだけ早い段階で行う」**ことと**「結合（Join）する右側のテーブルを事前にフィルタリングする」**ことです。

- **時間による早期フィルタリング (ボックス 1)**: KQL では、クエリの最初に `| where Timestamp > ago(1h)` を配置することで、処理対象となる `EmailAttachmentInfo` のレコード数を即座に最小限に抑えることができます。これにより、その後の文字列比較（Subject や FileName）の負荷が軽減されます。

- **結合の最適化 (ボックス 2)**: `DeviceFileEvents` テーブルは非常に巨大になる可能性があるため、そのまま結合するとパフォーマンスが著しく低下します。

  - `join kind=inner (...)` の中でサブクエリを使用して、結合前に `DeviceFileEvents` 側も「過去1時間」に絞り込むのが KQL のベストプラクティスです。

  - `SHA256` ハッシュ値をキーとして使用することで、メールの添付ファイルとデバイス上でのファイルイベントを正確に紐付けることができます。

質問#44 トピック1
  
Microsoft Defender 365 を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
ネットワークには、Azure AD と同期するオンプレミスの Active Directory Domain Services (AD DS) ドメインが含まれています。AD DS ユーザーによる LDAP 要求を識別し、AD DS オブジェクトを列挙する必要があります。KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image185.png)

**正解:** ![](https://img.examtopics.com/sc-200/image186.png)

**解説:**

1. テーブルの選択: `IdentityQueryEvents`

- **IdentityQueryEvents:** Active Directory に対して行われた **LDAP 要求**、DNS クエリ、Samr クエリなどの「クエリ（照会）」アクティビティを記録するテーブルです。問題文にある「LDAP 要求を識別し、AD DS オブジェクトを列挙する」という目的に直接合致するのはこのテーブルです。

- _IdentityDirectoryEvents:_ グループ メンバーシップの変更やパスワード変更など、ディレクトリ オブジェクトの「変更」に関連するイベントを記録します。

- _IdentityInfo:_ ユーザーの部署、役職、グループ所属などの「属性情報（メタデータ）」を保持するテーブルであり、アクティビティのログではありません。

1. 関数の選択: `isnotempty`

- **isnotempty:** 指定された列（この場合は `AccountSid`）に値が入っている（空ではない）行のみを抽出します。

- 構文として `| where isnotempty(AccountSid)` とすることで、「実行したユーザーの SID が記録されている（＝匿名ではない特定のユーザーによる）クエリ」に絞り込むことができます。

  - _contains_ や _has_ は「特定の文字列が含まれているか」を検索する**演算子**です。これらを使用する場合は `| where AccountSid contains "S-1-5-..."` のように比較対象の文字列が必要ですが、今回の構文 `| where [ ] (AccountSid)` は関数を呼び出す形式になっているため、`isnotempty` が適切です。
質問#46 トピック1

次のKQLクエリを含むカスタム検出ルールがあります。  
  
![](https://img.examtopics.com/sc-200/image187.png)  
  
以下の各文について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注：正しい選択ごとに1ポイント獲得できます。  
  
![](https://img.examtopics.com/sc-200/image188.png)

**正解:** ![](https://img.examtopics.com/sc-200/image413.png)

**解説:**
Microsoft Defender 365 のカスタム検出ルールで自動応答アクション（ファイルの削除やデバイスの隔離など）を有効にするには、クエリの結果に**特定のアクションごとに定義された必須の列**が含まれている必要があります。

1. 電子メールの削除について（いいえ）

電子メールに対するアクション（削除や移動など）を自動化するには、クエリの結果に以下の **2 つの列が両方とも**含まれている必要があります。

- `NetworkMessageId`
- `RecipientEmailAddress`

提示されたクエリの最後の `summarize` 文を見ると、`RecipientEmailAddtess`（スペルミスがありますが、受信者アドレス用の列と見なせます）は含まれていますが、**`NetworkMessageId` が含まれていない**ため、メールの削除アクションを自動化することはできません。

1. アプリ実行の制限について（はい）

デバイス（エンドポイント）に対するアクションである「アプリ実行の制限」や「デバイスの隔離」を行うには、以下の列が必要です。

- `DeviceId`

クエリの投影（`summarize`）には **`DeviceId` 列が含まれている**ため、このルールを使用して特定のデバイス上でのアプリ実行を自動的に制限することが可能です。

1. ファイルの削除について（はい）

ファイルに対するアクション（ファイルの削除やクリーンアップ）を行うには、以下の **2 つの列が両方とも**含まれている必要があります。

- `SHA256`
- `DeviceId`（どのデバイスから削除するかを特定するため）

クエリの結果には **`SHA256` と `DeviceId` の両方が含まれている**ため、このルールに基づいて一致したファイルを自動的に削除するように設定できます。

質問#54 トピック1

Microsoft Defender for Endpoint を使用する Microsoft 365 E5 サブスクリプションをお持ちです。AlertInfo、AlertEvidence、DeviceLogonEvents テーブルをリンクするクエリを作成する必要があります。ソリューションは、テーブル内のすべての行を返す必要があります。  
  
どの演算子を使用すればよいでしょうか？

- A. search *
- B. union kind = inner
- C. join kind = inner
- D. evaluate hint.remote =

### 正解: **該当なし（正確には `join kind=fullouter` ですが、選択肢にはありません）**

ただし、**選択肢の中で最も問題の要件に近いのは C. join kind = inner** ですが、これは正解ではありません。

### 詳細な解説

問題の要件は「**テーブル内のすべての行を返す必要があります**」です。

#### 各Join演算子の動作

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

質問#56 トピック1

Microsoft Defender for Endpoint を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
以下の要件を満たす検出ルールを作成する必要があります。  
  
• 重大なソフトウェア脆弱性を持つデバイスが過去 1 時間以内にアクティブだった場合にトリガーされる  
• 重複する結果の数を制限する  
  
KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択肢は 1 つにつき 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image219.png)

## 正解

**第1のドロップダウン**: `| distinct DeviceId`
**第2のドロップダウン**: `| project Timestamp, DeviceId, ReportId`

## 詳細な解説

### クエリの構造分析

kusto

```kusto
DeviceTvmSoftwareVulnerabilities
| where VulnerabilitySeverityLevel == 'Critical'
```

この部分は、重大な脆弱性を持つデバイスをフィルタリングします。

### 第1のドロップダウン（重複削減）

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

### 中間のjoin処理

kusto

```kusto
| join kind=inner DeviceInfo on DeviceId
| where Timestamp between (now(-1h)..now())
```

この部分は、DeviceInfoテーブルと結合し、過去1時間以内にアクティブだったデバイスをフィルタリングします。

### 第2のドロップダウン（最終出力）

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

### 完成したクエリ

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

質問15 トピック3

Azure Sentinel を使用して、Azure の不規則なアクティビティを監視します。  
次の図に示すように、脅威を検出するためのカスタム分析ルールを作成します。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0012100001.jpg)  
ルール定義の一部としてインシデント設定は定義しません。  
図に示されている情報に基づき、ドロップダウンメニューを使用して各文を完成させる選択肢を選択してください。  
注: 正解は1つにつき1点です。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0012200001.png)  

**解説:**
提供された Azure Sentinel（Microsoft Sentinel）の分析ルール設定に基づくと、正解は以下の通りです。

### 1つ目の文の回答

**文:** 「If a user deploys three Azure virtual machines simultaneously, how many times will you receive **[0 alerts]** in the next five hours.」 （1人のユーザーが3台の仮想マシンを同時にデプロイした場合、今後5時間以内にアラートを**0回**受信します。）

- **理由:** クエリ内に `| make-series ... by Caller` という句があります。これは、アクティビティを**実行者（Caller）ごと**にグループ化して1行にまとめることを意味します。1人のユーザーが何台デプロイしても、クエリ結果として返されるのは**1行（1つの結果）**のみです。

- アラートのしきい値（Alert threshold）が「Generate alert when number of query results **Is greater than 2**（クエリ結果の数が2より大きい場合）」に設定されているため、結果が1行だけでは条件を満たさず、アラートは発生しません。

---

### 2つ目の文の回答

**文:** 「If three separate users deploy one Azure virtual machine each within five minutes of each other, you will receive **[1 alert]** .」 （3人の別々のユーザーがそれぞれ1台の仮想マシンを5分以内にデプロイした場合、アラートを**1回**受信します。）

- **理由:** 3人の異なるユーザー（Callers）が操作を行うため、クエリ結果にはユーザーごとの行が計**3行**生成されます。

- 3行の結果はしきい値の「2より大きい」という条件を満たすため、アラートがトリガーされます。

- ただし、設定の下部にある抑制（Suppression）が **On** になっており、「Stop running query for **5 Hours**（5時間停止）」と設定されています。そのため、一度アラートが出るとその後5時間はクエリが実行されず、追加のアラートは送信されません。

質問18 トピック3
悪意のある IP アドレスからの Azure 仮想マシンへのサインインが検出された場合、Azure Sentinel でインシデントを作成する必要があります。  
解決策: データコネクタのスケジュールされたクエリ ルールを作成します。  
これは目標を達成していますか?  

- A. はい
- B. いいえ

### 正解: **B. いいえ**

### 理由

質問文には「**データコネクタ**のスケジュールされたクエリルールを作成する」と記載されていますが、これは正しいアプローチではありません。

**正しいアプローチ:**
悪意のあるIPアドレスからのサインインを検出してインシデントを作成するには、以下を行う必要があります:

1. **データコネクタを設定** - まずデータソース(Azure仮想マシンのログなど)をSentinelに接続
2. **分析ルール(Analytics Rule)でスケジュールされたクエリルールを作成** - データコネクタではなく、**Analyticsセクション**でスケジュールされたクエリルールを作成

### 正しい手順

Microsoft Learn のドキュメントによると:

```
1. Microsoft Sentinel で「Analytics」を選択
2. 「+Create」> 「Scheduled query rule」を選択
3. クエリを作成(例: 悪意のあるIPアドレスからのサインインを検出)
4. 「Incident settings」タブで「Create incidents from alerts triggered by this analytics rule」を有効化
```

### 重要なポイント

- **データコネクタ**: データソースをSentinelに接続するためのもの(ログの収集)
- **スケジュールされたクエリルール**: **Analyticsルール**として作成し、検出されたイベントからアラートとインシデントを生成

Azure Security Center によって生成されたセキュリティアラートを視覚的に表示するカスタム Azure Sentinel クエリを作成する予定です。  
棒グラフを表示するためのクエリを作成する必要があります。  
クエリには何を含めるべきですか？  

- A. 延長する
- B. ビン
- C. カウント
- D. ワークスペース

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)  

**解説:**
棒グラフ（Bar chart）を表示するためにデータを集計する際に使用する演算子です。
**「count (カウント)」**: 棒グラフの各バーの高さ（件数）を計算するために `count()` 関数（通常は `summarize count() by ...` の形式で）を使用します。
※時系列の棒グラフであれば `bin` も必要になりますが、単にカテゴリごとの分布（例：アラート重大度ごとの件数）を表示する場合など、`count` が主要な集計要素となります。設問が時系列に限定していないため、集計の基本となるCが正解とされています。

質問#36 トピック3

次の表に示すリソースがあります。
![](https://www.examtopics.com/assets/media/exam-media/04261/0013900002.png)  
SW1  で重複したイベントが発生しないようにする必要があります。  
各アクションには何を使用すればよいでしょうか？ 適切なリソースを正しいアクションにドラッグして答えてください。各リソースは1回、複数回、または全く使用されない場合があります。コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
注：正しい選択ごとに1ポイント獲得できます。  
選択して配置：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0014000001.jpg)  

ドキュメントによると、重複イベントを防止するための2つの方法があります:

1. **Syslog設定からCEFメッセージを送信するファシリティを削除する** (ソースマシン側で設定)
2. **Log Analytics AgentでSyslog同期を無効にする** (より直接的な方法)

設定内容を整理すると:

- **Server2** はSyslogログをCEF1に送信
- **Server1** はCEFログをCEF1に送信
- **CEF1** はログをSW1(Azure Sentinel)に転送

重複を防ぐためには:

1. **Syslog設定から、CEFメッセージを送信するファシリティを削除** → **Server1**で実行
2. **Log Analytics AgentでSyslog同期を無効にする** → **CEF1**で実行(Log Analytics AgentはCEF1に配置されているため)

**解答:**

| アクション                                                                        | リソース        |
| ---------------------------------------------------------------------------- | ----------- |
| From the Syslog configuration, remove the facilities that send CEF messages. | **Server1** |
| From the Log Analytics agent, disable Syslog synchronization.                | **CEF1**    |

質問#50 トピック3

Microsoft Sentinel ワークスペースがあります。  
  
次の図に示すように、Query1 というクエリがあります。Parser1 というカスタム パーサーを作成する予定です。Parser1  で Query1 を使用する必要があります。  
まず何をすべきでしょうか。
  
![](https://img.examtopics.com/sc-200/image135.png)  

- A. 5行目を削除します。
- B. 2行目を削除します。
- C. 3 行目で、!contains 演算子を !has 演算子に置き換えます。
- D. 4 行目で、TimeGenerated 述語を削除します。

KQL関数(パーサー)では、以下の制限があります:

- **`sort`や`order`演算子は、関数の戻り値として使用できません**
- 関数本体の最後の式はそのまま返されるため、`sort`を含めることはできません

したがって、Query1をパーサーとして使用するには、**5行目の`sort`演算子を削除する必要があります**。

**解答: A. 5行目を削除します。**

### 理由

1. **KQL関数(パーサー)では`sort`演算子を使用できない**
    - KQL関数の本体では、結果を返す最後の式に`sort`や`order`演算子を含めることができません
    - これはKQL関数の制限事項です
2. **パーサーは呼び出し元でソートすべき**
    - パーサー(関数)は正規化されたデータを返し、ソートは呼び出し元のクエリで行うべきです
    - これにより、パーサーの再利用性が向上します
3. **その他の選択肢が正しくない理由:**
    - **B**: 2行目(`where TimeGenerated > ago(7h)`)は時間フィルタで、パーサーでは問題ありません
    - **C**: 3行目の`!contains`演算子は正常に機能します
    - **D**: 4行目の`TimeGenerated`は`project`句で必要なフィールドです

質問#54 トピック3
  
次のKQLクエリがあります。  
  
![](https://img.examtopics.com/sc-200/image139.png)  
  
以下の各文について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注：正しい選択は1点です。  
  
![](https://img.examtopics.com/sc-200/image140.png)

**正解:** ![](https://img.examtopics.com/sc-200/image429.png)

**解説:**

1. The `UserName` field is set as the account entity. (**はい**)
クエリの最終行に `AccountCustomEntity = UserName` という記述があります。これは、Microsoft Sentinel の分析ルールにおいて、`UserName` フィールドの値を「アカウント」エンティティとしてマッピングしていることを示しています。

2. The watchlist cannot be updated after it is created. (**いいえ**)
Microsoft Sentinel のウォッチリスト（このクエリでは `_GetWatchlist('Bad_IPs')` で呼び出されているもの）は、作成後も内容を更新、削除、または新しいデータの追加が可能です。クエリ内で呼び出されているからといって、そのデータが固定（イミュータブル）されるわけではありません。

3. The `IPList` variable is set as the IP address entity. (**いいえ**)
`IPList` は、クエリの冒頭で `let IPList = _GetWatchlist('Bad_IPs');` と定義されており、ウォッチリスト内の**IPアドレスのリスト全体**を保持する変数です。 一方で、IPアドレスエンティティとしてマッピングされているのは、クエリ末尾の `IPCustomEntity = case(...)` の部分であり、そこでは個別の `SourceIP` または `DestinationIP` が代入されています。`IPList` 変数そのものがエンティティとして設定されているわけではありません。

質問#55 トピック3
  
Microsoft Sentinelワークスペースがあります。Parser1  というカスタムAdvanced Security Information Model (ASIM)パーサーを開発し、Schema1というスキーマを生成します。Schema1 を検証する必要があります。  
  
コマンドをどのように完了すればよいですか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image142.png)

## 回答

ASIMスキーマを検証するには、以下のコマンドを使用します：

```kusto
Parser1 | getschema | invoke ASimSchemaTester('Schema1')
```

**回答エリアの選択:**

- 最初のドロップダウン: **getschema**
- 2番目のドロップダウン: **invoke**

### 解説

このコマンドの動作：

1. **Parser1** - カスタムASIMパーサーを実行
2. **| getschema** - パーサーの出力スキーマを取得
3. **| invoke ASimSchemaTester('Schema1')** - Schema1に対してスキーマ検証を実行

ASimSchemaTesterは、以下をチェックします：

- 必須フィールドの存在
- フィールドの型の正確性
- 必須エイリアスの存在
- 推奨フィールドとオプションフィールドの状態

検証結果により、エラー（必須フィールドの欠落や型の不一致など）や警告（推奨フィールドの欠落など）が表示され、パーサーの修正に役立ちます。

質問#56 トピック3
  
ユーザーおよびエンティティ行動分析 (UEBA) が有効になっている Microsoft Sentinel ワークスペースがあります。Server1  というサーバー上で実行された、セキュリティ上重要なユーザー操作に関連するすべてのログエントリを特定する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• IT 部門のメンバーではないユーザーによる、セキュリティ上重要な操作のみを含める。  
• 誤検知の数を最小限に抑える。  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  

注: 正しい選択ごとに 1 ポイントが加算されます。  
  
![](https://img.examtopics.com/sc-200/image144.png)

### 回答

クエリを完成させるには、以下のように選択します：

**最初のドロップダウン（join kind）:**

- **| join kind=inner (**

**2番目のドロップダウン（テーブル）:**

- **IdentityInfo**

### 完成したクエリ

kusto

```kusto
SecurityEvent
| where EventID in ("4624","4672")
| where Computer == "SERVER1"
| join kind=inner (
    IdentityInfo
    | summarize arg_max(TimeGenerated, *) by AccountObjectId) on $left.SubjectUserSid == $right.AccountSID
| where Department != "IT"
```

### 解説

1. **join kind=inner** - 内部結合を使用して、SecurityEventとIdentityInfoの両方に存在するレコードのみを取得（誤検知を最小限に抑える）
2. **IdentityInfo** - UEBAが有効な場合に使用可能なテーブルで、ユーザーのプロファイル情報（部署、グループメンバーシップなど）を含む
3. *_summarize arg_max(TimeGenerated, _)__ - 各ユーザーの最新の情報を取得
4. **on $left.SubjectUserSid == $right.AccountSID** - SecurityEventのSubjectUserSidとIdentityInfoのAccountSIDで結合
5. **where Department != "IT"** - IT部門ではないユーザーのみをフィルタリング

このクエリにより、Server1でセキュリティ上重要な操作（EventID 4624: ログオン、4672: 特権でのログオン）を実行したIT部門以外のユーザーを特定できます。

質問#65 トピック3

Workspace1 という Microsoft Sentinel ワークスペースがあります。Workspace1 を構成して DNS イベントを収集し、DNS スキーマ用の Advanced Security Information Model (ASIM) 統合パーサーを展開します。ASIM DNS スキーマに対してクエリを実行し、過去 24 時間以内に送信元 IP アドレス別に 15 分間隔で集計された、応答コードが「NXDOMAIN」であるすべての DNS イベントを一覧表示する必要があります。このソリューションでは、クエリのパフォーマンスを最大化する必要があります。  
  
クエリをどのように完了すればよいでしょうか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image163.png)

### 回答

クエリを以下のように完成させてください:

**最初のドロップダウン（パーサー名）:**

- **_Im_Dns**

**2番目のドロップダウン（クエリ構文）:**

- **(starttime=ago(1d),responsecodename='NXDOMAIN')**

### 完成したクエリ

```kusto
_Im_Dns(starttime=ago(1d),responsecodename='NXDOMAIN')
| summarize count() by SrcIpAddr, bin(TimeGenerated,15m)
```

### 解説

#### 1. **`_Im_Dns`を使用する理由:**

- **組み込みの統合パーサー**: すべてのDNSソースを正規化された形式で統合
- **パフォーマンス**: `imDns`はワークスペースデプロイ版で、開発用途向け
- **推奨事項**: Microsoft Docsでは「ASIMコンテンツを開発する際は組み込みパーサーの使用を推奨」と明記

**不正解の選択肢:**

- `Dns`: 生のテーブル名で、正規化されていない
- `imDns`: ワークスペースデプロイ版のパーサー（開発/カスタマイズ用）

#### 2. **フィルタリングパラメータを使用する理由:**

**パフォーマンスの最大化:**

Microsoft Learn Docsには、**まったく同じ例**が記載されています:

```kusto
// フィルタリングパラメータあり（推奨）
_Im_Dns(starttime=ago(1d), responsecodename='NXDOMAIN')
  | summarize count() by SrcIpAddr, bin(TimeGenerated,15m)

// フィルタリングパラメータなし（非推奨）
_Im_Dns
  | where TimeGenerated > ago(1d)
  | where ResponseCodeName =~ "NXDOMAIN"
  | summarize count() by SrcIpAddr, bin(TimeGenerated,15m)
```

**フィルタリングパラメータの利点:**

- **パース前にフィルタリング**: データ量を削減してからパース
- **クエリ最適化**: パーサー内部で効率的な事前フィルタリング
- **パフォーマンス向上**: whereを後から使うより大幅に高速

**不正解の選択肢:**

- `where`句を使う方法: パース後のフィルタリングのためパフォーマンスが低下

質問#77 トピック3

sws1 という Microsoft Sentinel ワークスペースがあります。  
  
ユーザーが異常に多くの Azure AD ユーザーアカウントを作成したことを検出するクエリを作成する必要があります。  
  
クエリはどのように完成させるべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image197.png)

**正解:** ![](https://img.examtopics.com/sc-200/image431.png)

**解説:**
このクエリの目的は、「異常な行動」と「具体的なアクション（ユーザー作成）」を紐づけることです。

- **BehaviorAnalytics (上段):** このテーブルは Microsoft Sentinel の **UEBA (User and Entity Behavior Analytics)** 機能によって生成されます。`ActivityInsights` という列を保持しており、ユーザーの行動が通常と異なるかどうかのインサイト（例：過去と比較して作成数が多いなど）が含まれています。そのため、最初のフィルター条件に適合します。

- **AuditLogs (下段):** Azure AD（現在の Microsoft Entra ID）におけるユーザーの追加、削除、変更などのアクティビティは **AuditLogs** テーブルに記録されます。`ActionType == "Add user"` という条件や、後の工程で `mv-expand TargetResources`（操作対象のリソース情報の展開）を行うため、詳細な監査ログを持つこのテーブルを `join` する必要があります。

質問#87 トピック3
  
Microsoft Sentinel ワークスペースがあります。  
  
カスタムブックのレポートビジュアルを構成する必要があります。ソリューションは以下の要件を満たす必要があります。  
• AppDisplayName のカウントと使用状況の傾向が含まれている必要があります。  
• TrendList 列がスパークラインビジュアルで使用可能である必要があります。

KQL クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image211.png)

**正解:** ![](https://img.examtopics.com/sc-200/image212.png)

**解説:**
要件である「カウント」と「使用状況の傾向（トレンド）」を一つのテーブルにまとめ、スパークラインで表示するためには以下の処理が必要です。

1. なぜ `join` なのか？

- **データの統合:** クエリの前半部分で `summarize count()` により各アプリの合計サインイン数を算出しています。

- **結合の必要性:** 後半部分で生成するトレンドリスト（時間経過による変化）と、前半の合計カウントを `AppDisplayName` をキーにして結合する必要があります。KQL で異なる集計結果を結合するには **`join`** 演算子を使用します。

1. なぜ `make-series` なのか？

- **トレンドの生成:** 要件にある「TrendList 列がスパークラインビジュアルで使用可能であること」を満たすには、時間軸に沿った数値の配列を作成する必要があります。

- **時系列データの作成:** **`make-series`** は、指定した時間範囲（`range`）と間隔（`4h`）に基づいて、欠損値を補完しながら数値の動向を配列として生成します。この配列形式こそが、Azure ブックのスパークライン表示に不可欠なデータ形式です。

  - `make_bag()` はプロパティバッグ（JSON）の作成、`mv-expand` は配列の展開、`render` はグラフ描画に使用するため、ここでは不適切です。

質問3 トピック4
  
デフォルトのデータ保持期間が30日間であるMicrosoft Sentinelワークスペースがあります。このワークスペースには、次の表に示すように2つのカスタムテーブルが含まれています。  
  
![](https://img.examtopics.com/sc-200/image258.png)  
  
各テーブルには、過去365日間、1日あたり2件のレコードが取り込まれました。  
  
分析ルールで使用するKQLステートメントを、次の表に示すように作成します。  
  
![](https://img.examtopics.com/sc-200/image259.png)  
  
以下の各ステートメントについて、該当する場合は「はい」を選択してください。それ以外の場合は「いいえ」を選択してください。  
  
注：正しい選択は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image260.png)

**解説:**
この問題のポイントは、Microsoft Sentinel（Log Analytics）における**テーブルプラン（Basic vs Analytics）**と**保持期間（インタラクティブ保持 vs 合計保持）**の仕様の違いにあります。

#### **前提条件の整理**

- **データ量:** 1日あたり2件のレコード（過去365日間）。
- **ワークスペースのデフォルト保持期間:** 30日間。

---

1. Query1 について: はい**

- **現状:** `Table1` は **Basic** プランです。

- **制限:** 1. **保持期間:** Basic ログのインタラクティブ保持（クエリ可能な期間）は **8日間** に固定されており、変更できません。15日分のデータ（30件）をクエリすることは不可能です。 2. **KQLの制限:** Basic ログは `summarize` オペレーターを**サポートしていません**。そのため、このクエリ自体がエラーになります。

- **結論:** 30件の結果（15日分）を得るには、プランを **Analytics** に変更して `summarize` を実行可能にし、かつ保持期間を15日以上に確保する必要があります。

1. Query2 について: いいえ**

- **現状:** `Table2` は **Analytics** プランで、合計保持期間は **365日** です。インタラクティブ保持は「Default」（30日）に設定されています。

- **課題:** `ago(120)` で120日分のデータ（240件）を取得しようとしていますが、通常のKQLクエリは**インタラクティブ保持期間内**のデータしか参照できません。

- **結論:** 240件を取得するために必要なのは「合計保持期間の変更」ではなく、**「インタラクティブ保持期間」を120日に増やすこと**です。現在の合計保持期間は既に365日あるため、120日に「変更（短縮）」する必要はありません。

1. Query3 について: いいえ**

- **現状:** `Table1` は **Basic** プランです。

- **制限:** 前述の通り、Basic ログのクエリ可能な期間は **8日間** 固定です。

- **結論:** 「合計保持期間」を45日に設定したとしても、それはアーカイブ（長期保存）としての設定であり、通常のクエリ（KQL）で 45日分（90行）の結果を直接出すことはできません。これを実現するにはプランを **Analytics** に変更する必要があります。

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

1. Property (プロパティ) の選択

JSON の構造と、後続のデータ（`"cron"`, `"daemon"`）から判断します。

- **facilityNames: [:** これが正解です。Syslog 設定において、収集対象とするファシリティ（`cron`, `daemon`, `auth` など）をリスト形式で指定するためのプロパティです。
- **outputStream: [:** これは DCR 内の `destinations` セクションに関連するものであり、`dataSources` 内の `syslog` 構成の中で個別のファシリティを指定するために使うプロパティではありません。
- **type: [:** ここでは適切なプロパティではありません。

---

#### DCR 構成のポイント

この構成により、200 台の Linux サーバーから送られる CEF ログのうち、指定したファシリティ（cron, daemon）かつ、指定したログレベル（Error, Critical, Alert, Emergency）に合致するものだけが Microsoft Sentinel (Workspace1) の `CommonSecurityLog` テーブルへ取り込まれるようになります。

質問#42トピック4

複数の Microsoft Sentinel ワークスペースを含む複数の Azure サブスクリプションがあります。AzureActivity テーブルへの参照を含む Microsoft Sentinel ブックを作成しています。  
  
次のアクションを実行する KQL クエリを作成する必要があります。  
  
• 各ワークスペースに AzureActivity テーブルが存在するかどうかを確認します。  
• テーブルが存在する場合は、isMissing 列が 0 に設定された単一の行を返します。
• テーブルが存在しない場合は、isMissing 列が 1 に設定された単一の行を返します。  
  
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

1. `isfuzzy=true` の選択

`union` 演算子における **`isfuzzy=true`** は、結合対象のテーブル（この場合は `AzureActivity`）が**存在しない場合にエラーを出さず、そのテーブルを無視して処理を続行させる**ための非常に重要なパラメータです。

- **なぜこれか:** `AzureActivity` テーブルが存在しないワークスペースでこのクエリを実行すると、通常は「テーブルが見つからない」というエラーで停止してしまいます。`isfuzzy=true` を指定することで、テーブルがない場合は空の結果として扱い、エラーを回避して `mTable`（isMissing=1）側の結果を出力できるようになります。
- **kind=outer / withsource:** これらは結合の方法やソースの特定を指定するものですが、テーブル自体の「欠落」によるエラーを防ぐ機能はありません。

---

### クエリの動作ロジック

1. まず、`isMissing` が `1` の `mTable` を作成します。

2. 次に、実際の `AzureActivity` テーブルを確認し、存在すれば `isMissing` を `0` に変換した行を生成します。

3. `union isfuzzy=true` で両者を結合します。

4. テーブルが存在すれば `0` と `1` の行が混ざりますが、`top 1`（ソート順によりますが、このロジックでは存在確認が優先されます）により、最終的なステータスを判定します。

質問#45トピック4

50 個のサブスクリプションが含まれる Azure 環境があり、その中には Sub1 というサブスクリプションもあります。Sub1 には、他のサブスクリプションからログを収集する Workspace1 という Microsoft Sentinel ワークスペースが含まれています。Workspace1 には WB1 というブックが含まれています。WB1 に、Item1 というパラメーター項目を追加します。Item1 に、Parameter1 というパラメーターを追加します。  
  
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

1. Select Allow multiple selections. (複数選択を許可する) の選択

- **「1つ以上」の要件:** ユーザーが複数のサブスクリプションを選択できるようにするためには、この設定を有効にする必要があります。

- **「単一のオプションで全クエリ」の要件:** `Subscription picker` の設定で `Allow multiple selections` を有効にすると、その詳細設定の中に **「Include All（すべてを含む）」** というチェックボックスが表示されます。これをオンにすることで、ドロップダウン内に「All」という単一の選択肢が追加され、要件を満たすことができます。

質問11 トピック5
  
Windows Server を実行するオンプレミス サーバーがあります。SW1 という Microsoft Sentinel ワークスペースがあります。SW1 は、Azure Monitor エージェント データ コネクタを使用してサーバーから Windows セキュリティ ログ エントリを収集するように構成されています。  
  
収集するイベントの範囲をイベント 4624 と 4625 のみに制限する予定です。  
  
コネクタに適用されたフィルターの構文を検証するには、PowerShell スクリプトを使用する必要があります。  

スクリプトをどのように完成させる必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image273.png)

### 正解

powershell

```powershell
$events = '*[System[(EventID=4624 or EventID=4625)]]'
Get-WinEvent -LogName 'Security' $events -FilterXPath
```

### 各空欄の正しい選択肢

1. **最初の空欄（$eventsの値）**:
    - `'*[System[(EventID=4624 or EventID=4625)]]'`
2. **第二の空欄（Get-WinEventのパラメータ）**:
    - `-FilterXPath`

### 根拠（公式ドキュメントより）

#### 1. XPath構文について

公式ドキュメント "[Collect Windows events from virtual machine with Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/vm/data-collection-windows-events)" より：

> **XPath entries are written in the form `LogName!XPathQuery`**
>
> 例: `Security!*[System[EventID=1035]]`

ただし、**PowerShellの`Get-WinEvent`コマンドレットでは、LogNameは`-LogName`パラメータで別途指定**するため、XPath部分のみを指定します。

#### 2. 複数のイベントIDをフィルターする構文

同ドキュメントのサンプルより：

|説明|XPath|
|---|---|
|System events with Event ID = 4648のみ|`System!*[System[EventID=4648]]`|
|Success and failure Security events **except** for Event ID 4624|`Security!*[System[(band(Keywords,13510798882111488)) and (EventID != 4624)]]`|

また、"[Use the data ingestion benefit](https://learn.microsoft.com/en-us/azure/defender-for-cloud/data-ingestion-benefit)" より、**複数のイベントIDを含める場合の正しい構文**:

xpath

```xpath
*[System[(EventID=4624 or EventID=4625 or EventID=4688)]]
```

#### 3. Get-WinEventコマンドレットの使い方

公式ドキュメント "[Connect Microsoft Sentinel to other Microsoft services with a Windows agent-based data connector](https://learn.microsoft.com/en-us/azure/sentinel/connect-services-windows-based)" より：

> To test the validity of an XPath query, use the PowerShell cmdlet **Get-WinEvent** with the _**-FilterXPath**_ parameter. For example:
>
> powershell
>
> ```powershell
> $XPath = '*[System[EventID=1035]]'
> Get-WinEvent -LogName 'Application' -FilterXPath $XPath
> ```

### 正しいスクリプト構文

powershell

```powershell
$events = '*[System[(EventID=4624 or EventID=4625)]]'
Get-WinEvent -LogName 'Security' -FilterXPath $events
```

**重要なポイント**:

- XPath式はSystem要素内で複数のEventIDを`or`で結合
- `Get-WinEvent`では`-FilterXPath`パラメータを使用
- `-LogName 'Security'`でSecurityログを指定
- Azure Monitor AgentのDCRで使用する際は、`Security!`プレフィックスが必要になりますが、PowerShellでローカルテストする際は不要です

この構文により、イベント4624（成功したログオン）と4625（失敗したログオン）のみが返されます。

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

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)  

**解説:**
カスタム検出ルールでデバイスに対するレスポンスアクション（Isolate deviceなど）を実行できるようにするための要件です。
**「Add the DeviceId and Timestamp columns to the project operator」**:
カスタム検出ルールが特定のアクション（デバイス分離、ウイルススキャン、調査パッケージ収集など）をエンティティに対して実行するためには、クエリの結果セットに、そのエンティティを識別する識別子（**DeviceId**）と、イベントの時間（**Timestamp**）が含まれている必要があります。これらがマッピングされていないと、システムはどのデバイスに対していつのアクションを実行すればよいかわかりません。
ユーザー（Account）に対するアクションならAccountUpnなどが必要です。

質問#36 トピック6
  
contoso.com という Microsoft Entra テナントにリンクされた Azure サブスクリプション Sub1 があります。Sub1 には、Workspace1 という Log Analytics ワークスペースが含まれています。contoso.com からのすべてのログは Workspace1 にストリーミングされます。Microsoft 365 E5 サブスクリプションがあります。Workspace1 に対して、以下のクエリを実行する必要があります。  
  
• contoso.com の Microsoft Graph サービスへの HTTP 要求  
• 証明書またはシークレットを使用するサードパーティ アプリのサインイン アクティビティ  
  
KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image395.png)

### 正解の組み合わせ

1. **上のドロップダウン (Table):** `AADServicePrincipalSignInLogs`
2. **下のドロップダウン (Join Key):** `CorrelationId`

このクエリは、Microsoft Graph API へのリクエストとその実行主体（アプリケーション）の認証イベントを紐付けるためのものです。

- **AADServicePrincipalSignInLogs:** 要件である「証明書またはシークレットを使用するサードパーティ アプリのサインイン アクティビティ」を調査するために使用するテーブルです。サービス プリンシパル（アプリの ID）による認証イベントがここに記録されます。

  - `SigninLogs` は主にユーザーのインタラクティブなサインインを記録します。
  - `AADNonInteractiveUserSignInLogs` はユーザーの非インタラクティブな（バックグラウンドでの）サインインを記録します。

- **CorrelationId:** `MicrosoftGraphActivityLogs` テーブルの `SignInActivityId` フィールドは、サインイン ログ側の **`CorrelationId`** と一致するように設計されています。 これを結合キーとして使用することで、特定の Graph 操作がどの認証セッションに基づいて行われたかを特定できます。
