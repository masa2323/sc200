質問#31 トピック7

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションを所有しています。このサブスクリプションには、Microsoft Defender for Endpoint にオンボードされている 500 台の Windows 11 デバイスが含まれています。  
  
これらのデバイスの Administrators グループのメンバーシップに不正な変更が加えられていることを発見しました。  
  
以下の要件を満たすソリューションを構成する必要があります。  
  
• 各エンドポイントの Administrators グループのメンバーシップを 1 時間ごとに確認する。  
• Administrators グループのメンバーシップの変更が検出されたら、Microsoft Defender XDR でインシデントを作成する。  
  
まず何を作成すればよいでしょうか？

- A. デバイスグループ
- B. 高度なハンティングクエリ
- C. アラート調整ルール
- D. 検出ルール

### 正解の理由：B. 高度なハンティングクエリ

このソリューションの核となるのは「**カスタム検出ルール (Custom detection rule)**」ですが、Microsoft Defender XDR ポータルのワークフロー上、それを設定するためには**まずクエリを作成して実行する**必要があります。

1. **ロジックの定義:** メンバーシップの変更（例：`DeviceEvents` テーブルの `LocalGroupMemberAdded` アクションなど）を特定するための KQL クエリを記述します。
2. **ルールの作成:** クエリを実行し、結果が表示された状態で初めて「**検出ルールの作成 (Create detection rule)**」ボタンがアクティブになります。
3. **スケジュールの設定:** ルールの作成画面の中で、要件にある「1時間ごと」のチェック頻度や「インシデントの作成」などのアクションを設定します。
    
つまり、クエリ（B）がなければ、ルール（D）を作成・構成すること自体ができないため、「まず（First）」作成すべきものはクエリとなります。

---
### 他の選択肢が最適ではない理由

- **A. デバイスグループ:** デバイスを論理的にグループ化（タグ付けや権限管理用）するものですが、メンバーシップの監視やインシデント作成のロジックとは直接関係ありません。
- **C. アラート調整ルール (Alert tuning rules):** 既存のアラートを抑制したり、誤検知を減らしたりするための設定です。新しい検知ロジックを作成するものではありません。
- **D. 検出ルール:** 最終的なソリューションそのものですが、前述の通り、これを作成するための「入力データ」として高度なハンティングクエリを先に用意する必要があります。

質問#32 トピック7
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
ネットワークには、Microsoft Entra テナントと同期するオンプレミスの Active Directory Domain Services (AD DS) ドメインが含まれています。デバイスと AD DS ドメイン コントローラーに記録された直近 100 件のサインイン試行を特定する必要があります。KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。

注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image448.png)

**解説:**
#### 1. `union` を選択する理由

今回の目的は、2 つの異なるソース（デバイスのログとドメインコントローラーのログ）から得られた**行を組み合わせて 1 つの結果セットにする**ことです。

- **`union`:** 複数のテーブルから行を統合するために使用されます。今回のクエリ構造のように、一方のテーブルの結果と、括弧 `( )` 内で定義されたもう一方のテーブルの結果を連結するのに最適です。
- **`join`:** 共通のキー（ユーザー名や ID など）に基づいて、2 つのテーブルの「列」を横に結合するために使用されます。今回は「サインイン試行を一覧表示する」ことが目的であり、列を増やすことではないため不適切です。
    
#### 2. `IdentityLogonEvents` を選択する理由

要件にある「AD DS ドメインコントローラーに記録されたサインイン試行」を特定するには、Microsoft Defender for Identity がキャプチャする認証イベントを保持しているテーブルが必要です。

- **`IdentityLogonEvents`:** オンプレミスの Active Directory（ドメインコントローラー経由）および Microsoft Entra ID で行われた認証アクティビティを記録します。
- **`IdentityInfo`:** ユーザーのプロファイル情報（部署、役職など）を保持するテーブルであり、個々のサインインイベントは記録されません。
- **`IdentityQueryEvents`:** Active Directory に対して行われた LDAP クエリなどの「探索」アクティビティを記録するもので、サインイン試行の特定には向きません。
    
---
### 💡 実務・試験対策のポイント

SC-200 において、サインインの調査でよく使われるテーブルの使い分けを整理しておくと非常に有利です。

| **テーブル名**                 | **記録される内容**                                       |
| ------------------------- | ------------------------------------------------- |
| **`DeviceLogonEvents`**   | **デバイス（エンドポイント）上**でのログオンイベント                      |
| **`IdentityLogonEvents`** | **AD / Entra ID** での認証イベント（DC へのログオンなど）           |
| **`SigninLogs`**          | **Microsoft Entra ID** の純粋なサインインログ（Sentinel 等で使用） |

質問#33 トピック7

Workspace1 という Microsoft Sentinel ワークスペースがあります。Workspace1 にカスタムブックを作成する必要があります。Workspace1 には、過去 7 日間の Microsoft Entra サインインの失敗を示すタイムチャートを表示する必要があります。ソリューションでは、チャートに各日のサインイン失敗回数が含まれるようにする必要があります。KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image450.png)

**正解:**### 回答領域

- **最初のドロップダウン:** **`| make-series`**
- **2 番目のドロップダウン:** **`default=0 on TimeGenerated step 1d`**
    
---
### 技術解説

#### 1. `| make-series` を選択する理由

今回の要件は「各日のサインイン失敗回数」をタイムチャートで表示することです。

- **`make-series`:** 指定した期間（今回は 7 日間）の時系列データを生成します。最大の特徴は、**データが存在しない期間に対しても、指定したデフォルト値（0など）を補完して連続した系列を作成できる**点です。
- **`summarize`:** データを集計しますが、特定の日に失敗が 1 件もなかった場合、その日の行自体が生成されません。その結果、タイムチャートに「穴」が開いてしまい、要件である「各日の回数を含める」を正確に満たせなくなります。
    
#### 2. `default=0 on TimeGenerated step 1d` を選択する理由

`make-series` 演算子を使用する場合の標準的な構文です。

- **`default=0`:** ログが存在しない時間帯のカウントを 0 として扱います。
- **`on TimeGenerated`:** どの列を時間軸として使用するかを指定します。
- **`step 1d`:** グラフの粒度（ビン）を 1 日単位に設定します。
    
---
### 💡 試験・実務でのポイント

SC-200 の試験で **「タイムチャート (timechart)」** や **「データの欠損を 0 で埋める (Replace missing data with 0 / default=0)」** というキーワードが出てきたら、迷わず **`make-series`** を探してください。

質問#34 トピック7
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションがあります。Azure サブスクリプションには、Workspace1 という Log Analytics ワークスペースが含まれています。  
  
すべてのログを Workspace1 に転送しています。  
  
過去 24 時間以内に Microsoft Entra グループの変更を要求したすべてのアプリケーションとセキュリティ プリンシパルを特定する必要があります。KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image452.png)
### 回答領域

- **最初のドロップダウン (テーブル名):** **`MicrosoftGraphActivityLogs`**
- **2 番目のドロップダウン (RequestMethod):** **`GET`**
    
---
### 技術解説

#### 1. `MicrosoftGraphActivityLogs` を選択する理由

今回の要件は、Microsoft Entra（旧 Azure AD）グループへの「変更要求」を特定することです。

- **`MicrosoftGraphActivityLogs`**: Microsoft Graph API に対して行われたすべての HTTP リクエストの詳細（URI、メソッド、実行したアプリ、ユーザー、サービスプリンシパルなど）を記録するテーブルです。クエリ内の `RequestUri` や `RequestMethod` といった列は、このテーブルの標準的なスキーマです。
- `EnrichedMicrosoft365AuditLogs` は主に監査イベントの結果を扱いますが、API レベルの生の要求（Request）を詳細に追跡するには Graph アクティビティログが適しています。
- `SecurityEvent` は Windows のイベントログを扱うため、Entra ID の API 操作の特定には使用しません。
    
#### 2. `GET` を選択する理由

要件にある「グループの**変更**」を特定するには、参照のみの操作を除外する必要があります。

- **`GET`**: データの取得（読み取り）に使用されるメソッドです。これを除外（`!=`）することで、`POST`（作成）、`PUT` / `PATCH`（更新）、`DELETE`（削除）といった、リソースに対して**何らかの変更を加える操作**だけを抽出できます。
- `POST` や `PUT` を除外してしまうと、肝心の変更操作そのものが結果から消えてしまうため不適切です。
    
---
### 💡 実務・試験対策のポイント
Microsoft Sentinel や Defender XDR において、**Microsoft Graph アクティビティログ**は「どのアカウント（またはアプリ）が、機密性の高いグループ（Global Admins など）に対して不審な変更を試みたか」を調査する際の非常に強力な武器になります。

質問#35 トピック7

Microsoft Defender XDR、Microsoft Purview、Exchange Online を利用する Microsoft 365 サブスクリプションをご利用です。Contoso 社というパートナー企業から、過去 1 か月間に受信した PDF 添付ファイルを含むすべてのメールを確認する必要があります。管理作業を最小限に抑えるソリューションが必要です。  
  
どのようなソリューションを使用すべきでしょうか？

- A. コンテンツ検索
- B. コンテンツエクスプローラー
- C. アクティビティエクスプローラー
- D. 高度な狩猟

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)  

**解説:**
過去1ヶ月間に特定のパートナー企業から受信したPDF添付ファイル付きメールを確認するソリューション。
**「Content Search (コンテンツ検索)」**。
Microsoft Purviewコンプライアンスポータルのコンテンツ検索機能を使用すると、Exchange Onlineのメールボックス全体を対象に、送信者ドメイン（Contoso）、添付ファイルの種類（PDF）、期間などの条件で検索できます。
「管理作業を最小限に」という点では、高度なハンティング（Advanced Hunting）も可能ですが、コンテンツ検索はGUIベースでメール本文や添付ファイルの有無を含めた検索に特化しており、eDiscoveryの一部として機能するため適切です。
また、Advanced Huntingの `EmailAttachmentInfo` テーブルは通常30日間の保持期間ですが、「Review all emails（メール自体を確認）」という要件ならコンテンツ検索が適しています（プレビュー機能やエクスポートが可能）。
Topic 7 Q14 (Page 22) や Q21 (Page 33) と類似していますが、ここではコンテンツ検索が正解とされています。

質問#36 トピック7

Microsoft Sentinel を使用する Azure サブスクリプションをお持ちです。  
  
セキュリティ インシデントをクローズするまでの平均時間を計算するカスタム ワークブックを作成する必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。  
  
どの組み込み Microsoft Sentinel ワークブック テンプレートを選択すればよいでしょうか。

- A. セキュリティ運用の効率
- B. 事件の概要
- C. ワークスペース使用状況レポート
- D. 調査の洞察

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)  

**解説:**
セキュリティインシデントをクローズするまでの平均時間（MTTR: Mean Time To Resolve）などを計算するワークブックテンプレート。
**「Security operations efficiency (セキュリティ運用の効率)」**。
この標準テンプレートは、SOCのパフォーマンス指標（インシデント作成数、重大度別、所有者別、そして**MTTR**やMTTA: Mean Time To Acknowledge）を可視化するために設計されています。
B: Incident Overviewはインシデントの現状把握用。
C: Workspace Usageはデータ量とコスト用。
D: Investigation Insightsは調査の詳細用。
したがって、効率性指標（平均時間）を見るには **A** が正解です。

質問#37 トピック7

Microsoft 365 サブスクリプションで Microsoft Defender for Endpoint プラン 2 をご利用いただいています。このサブスクリプションには、サードパーティ製のウイルス対策ソフトウェアを実行し、スマート アプリ コントロールが有効になっている Windows 11 デバイスが 1,000 台含まれています。  
  
サードパーティ製ソフトウェアが検出できなかった悪意のあるアーティファクトが Defender for Endpoint によって検出された場合、自動的に修復されるようにする必要があります。  
  
どのような設定が必要ですか？

- A. ブロックモードでのエンドポイント検出および応答（EDR）
- B. ファイルを許可またはブロックする
- C. アラートを自動的に解決する
- D. 改ざん防止
- 
**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)  

**解説:**
サードパーティ製アンチウイルスが稼働している状態で、Defender for Endpointが検出した悪意のあるアーティファクトを自動的に修復（Remediate）する設定。
**「Endpoint detection and response (EDR) in block mode (ブロックモードでのEDR)」**。
通常、サードパーティ製AVがインストールされると、Microsoft Defender Antivirusは「パッシブモード」になります。パッシブモードではスキャンはしますが、脅威の修復（ブロックや削除）は行いません。
しかし、「EDR in block mode」を有効にすると、Defender for EndpointのEDR機能が脅威を検出した場合に、Microsoft Defender Antivirusがパッシブモードであっても、その悪意のあるアーティファクトをブロック・修復することができます。
これにより、サードパーティAVが見逃した脅威をDefenderが補完的にブロックできます。

質問#38 トピック7

Microsoft 365 サブスクリプションをお持ちです。このサブスクリプションには、Microsoft Defender for Endpoint にオンボードされているデバイスが 500 台含まれています。Microsoft Sentinel ワークスペースを含む Azure サブスクリプションもお持ちです。  
  
脅威を自動的に修復するパイロットを 50 台のデバイスで実行する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• パイロットから除外するデバイスへの影響を最小限に抑える。  
• 管理作業を最小限に抑える。  
  
まず何を構成すればよいでしょうか？

- A. プレイブック
- B. エンドポイントセキュリティポリシー
- C. デバイスグループ
- D. 自動化ルール

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)  

**解説:**
50台のデバイスで自動修復（Automated Remediation）のパイロットを実行する方法。
**「Device group (デバイスグループ)」**。
Defender for Endpointの設定で、「Automated Investigation（自動調査）」のレベル（Fully automated, Semi-automated, No automated response）は、**デバイスグループ**ごとに設定できます。

1. パイロット用の50台を含むデバイスグループを作成します。
2. そのグループに対して自動化レベルを「Full - remediate threats automatically」に設定します。
3. 他のデバイスグループはより低い自動化レベルに設定しておきます。
これにより、特定のデバイス群（パイロット）のみで自動修復を有効にできます。

質問#39 トピック7
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをご利用です。KQL で以下の要件を満たすハンティングクエリを作成する必要があります。  
  
• 過去 12 時間以内に File1.pdf という添付ファイルを含むメールを受信し、その添付ファイルを開いたデバイスを特定します。  
• クエリの実行に必要なリソースを最小限に抑えます。

クエリはどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image472.png)
### 回答領域

1. **最初のドロップダウン (join kind):** **`innerunique`**
2. **2 番目のドロップダウン (join key):** **`SHA256`**
    
---
### 技術解説

#### 1. `innerunique` を選択する理由

要件にある「**クエリの実行に必要なリソースを最小限に抑える**」を満たすために最適な結合の種類です。

- **パフォーマンスの最適化:** KQL において `innerunique` は結合操作のデフォルトであり、左側のテーブル（`EmailAttachmentInfo`）のキーを重複排除してから結合します。これにより、メモリ消費と処理時間を削減できるため、リソースを最小限に抑えることができます。
- **要件の充足:** 今回の目的は「デバイスを特定する」ことであり、1 つの悪意のあるファイルに対してデバイスごとの一致が確認できればよいため、重複排除を行う `innerunique` が効率的です。
    
#### 2. `SHA256` を選択する理由

メールの添付ファイルと、デバイス上で開かれたファイルを正確に紐付けるための唯一かつ最も信頼性の高いキーです。

- **正確な相関:** `EmailAttachmentInfo`（メール側）と `DeviceFileEvents`（デバイス側）の両方のテーブルに存在する共通の列であり、ファイルの内容を一意に識別するハッシュ値です。
    
- **他の列が不適切な理由:**
    
    - `FilePath`: メール添付時のテンポラリパスと、デバイスで保存・展開されたパスは通常異なるため、結合には向きません。
    - `FileOriginUrl`: メールからのダウンロード時に必ずしも一貫して記録されるわけではなく、相関キーとしては不十分です。
        
---
### 💡 試験・実務でのポイント

SC-200 などの試験対策として、**「パフォーマンス最適化」** や **「リソースの最小化」** という言葉とセットで **`innerunique`** と **「両方のテーブルへのタイムスタンプフィルタの適用（`ago(12h)`）」** を覚えておくと非常に役立ちます。

質問#40 トピック7

Microsoft Sentinel ワークスペースがあります。KQL クエリがあります。このクエリは、SecurityIncident テーブルに保存され、過去 90 日間に発生した Microsoft Sentinel インシデントを返します。  
  
クエリの視覚化を含む Microsoft Sentinel ワークブックを作成する必要があります。  
  
ワークブックのデータソースとリソースの種類はどのように設定すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image474.png)

### **正解：**
**Data source（データソース）:** **Logs (Analytics)**
**Resource type（リソースの種類）:** **Log Analytics**

## 理由
公式ドキュメントの「Visualize and monitor your data by using workbooks in Microsoft Sentinel」セクションに明確に記載されています。

### **ワークブック作成時の設定**

> "When building a query, set the **Data source** to **Logs** and **Resource type** to **Log Analytics**, and then choose one or more workspaces."

### **SecurityIncidentテーブルについて**

公式ドキュメント「Manage your SOC better with incident metrics」より：

> "The **SecurityIncident** table is built into Microsoft Sentinel. You'll find it with the other tables in the **SecurityInsights** collection under **Logs**. You can query it like any other table in **Log Analytics**."

## 選択肢の分析

### **Data source（データソース）の選択肢**

#### ❌ **Azure Data Explorer**
- 独立したデータ分析サービス
- Microsoft SentinelのSecurityIncidentテーブルには使用しない

#### ❌ **Azure Resource Graph**
- Azureリソースのメタデータをクエリするサービス
- セキュリティインシデントデータには使用しない

#### ❌ **Azure Resource Manager**
- Azureリソースのデプロイと管理のサービス
- ログデータのクエリには使用しない

#### ✅ **Logs (Analytics)**
- Log Analyticsワークスペースのログデータにアクセス
- SecurityIncidentテーブルはLog Analyticsにある
- KQLクエリを実行するための正しいデータソース

#### ❌ **Logs (Basic)**
- Basic Logsは低コストのログ取り込み層
- SecurityIncidentテーブルは通常のAnalytics層にある

### **Resource type（リソースの種類）の選択肢**
#### ❌ **Application Insights**
- アプリケーションパフォーマンス監視サービス
- Microsoft Sentinelインシデントには使用しない

#### ✅ **Log Analytics**
- Microsoft SentinelはLog Analyticsワークスペース上に構築される
- SecurityIncidentテーブルはLog Analyticsワークスペースに格納される
- KQLクエリはLog Analyticsで実行される

#### ❌ **Microsoft Sentinel**
- これはリソースタイプの選択肢として表示されるが、実際のワークブックでは「Log Analytics」を選択する
- Microsoft SentinelはLog Analyticsの上位レイヤー

#### ❌ **Security Alert**
- これはテーブル名であり、リソースタイプではない

#### ❌ **Workspace**
- 一般的な用語だが、正しいリソースタイプは「Log Analytics」

## SecurityIncidentテーブルとLog Analyticsの関係

```
Microsoft Sentinel
    ↓
Log Analytics Workspace
    ↓
SecurityInsights Collection
    ↓
SecurityIncident Table
```

### **重要なポイント：**
1. **SecurityIncidentテーブルの場所**
    - Log Analyticsワークスペース内
    - SecurityInsightsコレクション
2. **クエリの実行**
    - KQLクエリはLog Analyticsで実行される
    - データソースは「Logs (Analytics)」
3. **ワークブックの設定**
    - Data source: Logs (Analytics)
    - Resource type: Log Analytics
    - Workspace: Microsoft Sentinelワークスペースを選択
