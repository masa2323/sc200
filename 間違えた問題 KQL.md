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
