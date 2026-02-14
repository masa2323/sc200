質問#64 トピック3

Microsoft Sentinel ワークスペースを含む Azure サブスクリプションをお持ちです。Microsoft Sentinel アラートに応じて自動的に実行されるプレイブックを作成する必要があります。  
  
まず何を作成すればよいでしょうか？

- A. Microsoft Sentinel のハンティングクエリ
- B. Azureロジックアプリ
- C. Microsoft Sentinelの自動化ルール
- D. Azure Functionsのトリガー

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)  

**解説:**
Sentinelアラートに応じて自動実行されるプレイブック（Playbook）の実体です。
**「Azure Logic App」**: Sentinelのプレイブックは、Azure Logic Appとして実装されます。まずLogic Appを作成し、それにSentinelトリガー（インシデント作成時など）を設定することで、自動化ルールから呼び出せるようになります。

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

### 完成したクエリ:
```kusto
_Im_Dns(starttime=ago(1d),responsecodename='NXDOMAIN')
| summarize count() by SrcIpAddr, bin(TimeGenerated,15m)
```

### 解説:

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

質問#66 トピック3

オンプレミスネットワークには、Windows Server を実行するサーバーが 100 台あります。Microsoft Sentinel を使用する Azure サブスクリプションを所有しています。  
  
オンプレミスサーバーから Microsoft Sentinel にカスタムログをアップロードする必要があります。  
  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image165.png)

**解説:**
1. Azure Connected Machine agent (Azure Arc) を使用する理由

現在の Azure におけるログ収集の標準は **Azure Monitor Agent (AMA)** です。オンプレミスのサーバーに AMA をインストールして Azure サービスと連携させるためには、まずそのサーバーを **Azure Arc** 対応サーバーとして登録する必要があります。 そのために必要なのが **Azure Connected Machine agent** です。

- **Log Analytics agent:** いわゆるレガシーエージェント（MMA）であり、現在は AMA への移行が推奨されています。
- **Microsoft Dependency agent:** VM Insights などでプロセス間の依存関係を可視化するためのもので、ログ収集の基盤ではありません。
    
2. Data connectors page を使用する理由

Microsoft Sentinel でカスタムログ（テキスト形式など）を取り込む設定を行うには、Sentinel ポータルの **「データ コネクタ (Data connectors)」** ページから設定を開始します。
ここで「Custom Text Log via AMA」などのコネクタを選択し、**データ収集ルール (DCR)** を作成・構成することで、どのサーバーからどのパスのファイルを収集するかを定義します。

質問#67 トピック3

Microsoft Sentinel ワークスペースを含む Azure サブスクリプションをご利用です。このワークスペースには Microsoft Defender for Cloud データコネクタが含まれています。  
  
特定のイベントのアラートを作成する際に含める詳細情報をカスタマイズする必要があります。  
  
どうすればよいでしょうか？

- A. ユーザーおよびエンティティ行動分析 (UEBA) を有効にします。
- B. データ収集ルール (DCR) を作成します。
- C. コネクタのプロパティを変更します。
- D. スケジュールされたクエリ ルールを作成します。

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)  

**解説:**
Defender for Cloudのアラート詳細（Alert properties）をカスタマイズしてSentinelアラートを作成する方法です。
**「スケジュールされたクエリ ルールを作成します (Create scheduled query rules)」**: Sentinelのアラート作成ウィザード（分析ルール作成）において、「アラートのエンリッチメント (Alert enrichment)」>「アラートの詳細 (Alert details)」セクションを使用すると、KQLクエリの結果から特定の値をアラート名や説明、深刻度などに動的にマッピングできます。これにより、Defender for Cloudからの生データよりリッチな情報を持つSentinelアラートを生成できます。

質問#68 トピック3

Workspace1 という Microsoft Sentinel ワークスペースと、DNS スキーマに基づく 200 個のカスタム Advanced Security Information Model (ASIM) パーサーがあります。  
  
この 200 個のパーサーを Workspace1 で利用できるようにする必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。  
  
まず何をすべきでしょうか？

- A. パーサーを Azure Monitor ログ ページにコピーします。
- B. DNS テンプレートに基づいて JSON ファイルを作成します。
- C. DNS テンプレートに基づいて XML ファイルを作成します。
- D. DNS テンプレートに基づいて YAML ファイルを作成します。

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)  

**解説:**
大量のカスタムASIMパーサーをデプロイする際、管理作業を最小化するアプローチです。
**「DNSテンプレートに基づいてYAMLファイルを作成します」**: ASIMパーサーの開発・管理にはYAML形式の定義ファイルが推奨されています。YAMLファイルを作成し、それを`ASIM YAML to ARM` コンバータツールなどでARMテンプレート（JSON）に変換して一括デプロイするフローが、大規模管理において効率的です。JSONを手書きするのは困難であるため、YAMLが起点となります。

質問#69 トピック3
  
Microsoft Sentinel ワークスペースをご利用の場合、  
  
Microsoft Sentinel インシデントは次の図のように生成されます。  
  
![](https://img.examtopics.com/sc-200/image167.png)  
  
図に示されている情報に基づき、ドロップダウンメニューを使用して各文を完成させる選択肢を選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image168.png)

**正解:** ![](https://img.examtopics.com/sc-200/image169.png)

**解説:**
1. Investigate (調査)

画面左下にある青い **「Investigate」** ボタンをクリックすると、インシデントに関連するエンティティ（ユーザー、IPアドレス、ホストなど）とその繋がりを視覚化した **「調査グラフ（Investigation Graph）」** が表示されます。これにより、攻撃の全容や影響範囲をマップ形式で把握できます。

- **Alerts / Entities:** これらはインシデント詳細画面内のタブであり、リスト形式で情報を表示しますが、接続関係を「マップ（グラフ）」として表示するのは「Investigate」の役割です。
    
2. Comments (コメント)

インシデント対応中に行われた操作や分析結果、メモなどのアクティビティ履歴を確認・記録するには **「Comments」** タブを使用します。調査の進捗やチーム内での共有事項がここにリストとして蓄積されます。

- **Alerts:** インシデントに含まれる個々のアラートの一覧を表示します。
- **Bookmarks:** 調査中に特定のログを「証拠」として保存したものを表示します。
- **Status:** これはタブではなく、インシデントの状態（New, Active, Closed）を示す属性です。
