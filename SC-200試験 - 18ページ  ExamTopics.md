質問#44 トピック3

Azure サブスクリプションには、app1 という Azure ロジック アプリと、Azure Active Directory (Azure AD) コネクタを備えた Microsoft Sentinel ワークスペースが含まれています。Microsoft  
Sentinel が Azure AD 生成のアラートを検出したときに、app1 が起動するようにする必要があります。  
まず何を作成すればよいでしょうか？  

- A. リポジトリ接続
- B. ウォッチリスト
- C. 分析ルール
- D. 自動化ルール

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
Azure ADのアラート（Identity Protectionなど）がSentinelに取り込まれた際にLogic Appを自動実行する設定です。
**「自動化ルール (Automation rule)」**: Sentinelにて「インシデント作成時」または「アラート作成時」をトリガーとする自動化ルールを作成し、アクションとして「プレイブックの実行（Run playbook）」を選択します。これにより、特定の条件（Azure ADからのアラートなど）に合致した場合にLogic App（プレイブック）を自動起動できます。

質問#45 トピック3

Microsoft Sentinelワークスペースをご利用の場合、  2つ以上のアラートまたはアクティビティで構成される高度な多段階攻撃を検出するために使用するルールを特定する必要があります。このソリューションは、管理作業を最小限に抑える必要があります。  
どのタイプのルールをクエリすればよいでしょうか？  

- A. Fusion
- B. Microsoft Security
- C. ML Behavior Analytics
- D. Scheduled

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
複数のアラートやアクティビティを相関分析し、高度な多段階攻撃を検出するルールです。
**「Fusion」**: Sentinelの機械学習ベースの相関エンジンです。異なる製品（Defender for Cloud, Azure AD Identity Protectionなど）からのシグナルを組み合わせ、キルチェーンの各段階にまたがる攻撃キャンペーンを自動的に検出します。デフォルトで有効化されており、管理作業は最小限で済みます。

質問#46 トピック3

Microsoft Sentinel を使用する Azure サブスクリプションがあり、100 台の Linux 仮想マシンが含まれています。Microsoft  Sentinel を使用してこれらの仮想マシンを監視する必要があります。ソリューションは、以下の要件を満たす必要があります。
✑  管理作業を最小限に抑える。
✑  FOG データの読み取りに必要な解析を最小限に抑える。  
どのような構成が必要ですか？  

- A. Log Analytics データコレクター API
- B. REST API統合
- C. 共通イベントフォーマット（CEF）コネクタ
- D. Syslogコネクタ

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
100台のLinux VMを監視し、管理と解析の手間を最小限にする構成です。
**「Common Event Format (CEF) connector」**: Syslogメッセージの一種ですが、標準化されたフィールドを持つCEF形式を使用することで、Sentinel側での追加の解析作業（Parsersの作成など）を最小限に抑えられます。Syslogコネクタ（標準Syslog）では、非構造化データのParsingが必要になる場合がありますが、CEFなら`CommonSecurityLog`テーブルにきれいに格納されます。

質問#47 トピック3

Microsoft Defender for Cloud の強化されたセキュリティ機能が有効になっている Azure サブスクリプションが 100 個あります。すべてのサブスクリプションは単一の Azure Active Directory (Azure AD) テナントにリンクされています。Defender for Cloud のログを Syslog サーバーにストリーミングする必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
注: 正しい選択は 1 ポイントです。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0015200001.png)  

### 解答の根拠

ドキュメントによると、Microsoft Defender for CloudのログをSyslogサーバーにストリーミングするには:
1. **Exports logs to an (エクスポート先):**
    - Azure Event Hubを使用する必要があります
    - Syslogサーバーへの直接エクスポートはサポートされていないため、Azure Event Hub経由でストリーミングします
2. **Configure streaming by (ストリーミングの設定方法):**
    - **100個のサブスクリプション**があり、**管理作業を最小限に抑える**必要があるため、Azure Policyを使用して一括設定するのが最適です
    - ドキュメントには「テナントレベルでアラートをストリーミングするには、このAzure Policyを使用し、スコープをルート管理グループに設定する」と明記されています
    - Azure Policy「Deploy export to an event hub for Microsoft Defender for Cloud alerts and recommendations」を**ルート管理グループ(root management group)に割り当てる**ことで、すべてのサブスクリプションに自動的に適用されます

**解答:**

| 項目                      | 選択肢                                                                  |
| ----------------------- | -------------------------------------------------------------------- |
| Exports logs to an:     | **Azure event hub**                                                  |
| Configure streaming by: | **Creating an Azure Policy assignment at the root management group** |

この構成により:

- Azure Event Hubにログをエクスポート
- Event HubからAzure Functionなどを使ってSyslogサーバーに転送
- ルート管理グループレベルでAzure Policyを設定することで、100個すべてのサブスクリプションに自動適用され、管理作業が最小限になります

質問#48 トピック3

100台のLinux仮想マシンを含むAzureサブスクリプションがあります。  
仮想マシンからイベントログを収集するには、Microsoft Sentinelを構成する必要があります。
3 つのアクションのうち、どのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
選択して配置してください。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0015300001.jpg)  

### 解答の根拠
Microsoft Sentinelを使用してLinux仮想マシンからログを収集するための標準的な手順:

1. **まず、Microsoft SentinelをLog Analyticsワークスペースに追加する**
    - Microsoft Sentinelを有効化するには、Log Analyticsワークスペースに接続する必要があります
2. **次に、Syslogコネクタをワークスペースに追加する**
    - データコネクタを設定して、Syslogデータの収集を有効にします
    - これにより、どのデータを収集するかを定義します
3. **最後に、Linux仮想マシンにLog Analytics agentをインストールする**
    - エージェントをインストールすることで、実際にログの収集が開始されます
    - エージェントがSyslogデータをワークスペースに送信します

**正しい順序:**
1. **Add Microsoft Sentinel to a workspace.**
2. **Add a Syslog connector to the workspace.**
3. **Install the Log Analytics agent for Linux on the virtual machines.**

質問#49 トピック3

Microsoft Sentinel を使用する Azure サブスクリプションをご利用です。  
  
ハンティングクエリを使用して新たな脅威を検出しました。Microsoft Sentinel が脅威を自動的に検出できるようにする必要があります。ソリューションは管理の手間を最小限に抑える必要があります。  
  
どうすればよいでしょうか？

- A. 分析ルールを作成します。
- B. クエリをワークブックに追加します。
- C. ウォッチリストを作成します。
- D. プレイブックを作成します。

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
Huntingクエリで見つけた脅威を、今後は自動的に検出する（ルール化する）ための方法です。
**「分析ルールを作成します (Create an analytics rule)」**: Huntingクエリの結果画面から「新しいアラート ルール (New alert rule)」を作成することで、そのクエリロジックをスケジュールされた分析ルールとして保存できます。これにより、同様の脅威を継続的かつ自動的に検出できるようになります。

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

### 理由:

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

質問#51 トピック3

Microsoft Sentinel を使用する Azure サブスクリプションをお持ちです。  
サインイン情報を時系列で視覚化するカスタムレポートを作成する必要があります。  
まず何を作成すればよいでしょうか？

- A. 狩猟に関する質問
- B. ワ​​ークブック
- C. ノートブック
- D. プレイブック

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
データを可視化するカスタムレポートを作成する機能です。
**「ワークブック (Workbook)」**: Sentinelにおけるデータの可視化、レポート作成、ダッシュボード機能の標準ツールです。KQLクエリの結果をグラフ、チャート、グリッドとして表示し、インタラクティブなレポートを作成できます。

質問#52 トピック3

Microsoft Sentinelワークスペースを使用しています。  
  
あるアカウントへのサインイン失敗に関するアラートが複数回発生しています。  
  
これらのアラートは誤検知であることが判明しました。  
  
このアカウントに対して、今後サインイン失敗アラートが生成されないようにする必要があります。このソリューションは、以下の要件を満たす必要があります。  
  
• 他のアカウントに対してもサインイン失敗アラートが生成されるようにする。  
• 管理作業を最小限に抑える。  
  
どうすればよいでしょうか？

- A. 分析ルールを変更します。
- B. ウォッチリストを作成します。
- C. エンティティ動作にアクティビティ テンプレートを追加します。
- D. 自動化ルールを作成します。

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
特定のアカウントに対する誤検知アラート（サインイン失敗）を停止し、他のアカウントは監視を継続する、かつ管理負荷を低くする方法です。
**「分析ルールを変更します」**: KQLクエリに特定のアカウントを除外する条件（例: `and UserPrincipalName != "user@example.com"`）を追加するのが最も確実で処理負荷も低い方法です。
※Automation rule（D）でもクローズは可能ですが、アラート自体は生成されてしまうため「生成されないようにする」という要件には分析ルールの修正が適しています。頻繁な変更がある場合はWatchlistの使用も検討されますが、選択肢の中ではAが基本です。

質問#53 トピック3
  
Microsoft 365 E5 サブスクリプションがあり、User1 と User2 という 2 人のユーザーがいます。  
次の図に示すようなハンティングクエリがあります。  
  
![](https://img.examtopics.com/sc-200/image136.png)  
  
ユーザーは以下のアクションを実行します。  
  
• User1 が User2 にグローバル管理者ロールを割り当てます。  
• User1 が User3 という新しいユーザーを作成し、そのユーザーに Microsoft Teams ライセンスを割り当てます。  
• User2 が User4 という新しいユーザーを作成し、そのユーザーにセキュリティ閲覧者ロールを割り当てます。  
• User2 が User5 という新しいユーザーを作成し、そのユーザーにセキュリティオペレーターロールを割り当てます。  
  
以下の各ステートメントについて、該当する場合は「はい」を選択します。それ以外の場合は「いいえ」を選択します。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image137.png)

1. **AuditLogsテーブル**から「Add user」操作を取得
2. 作成されたユーザーの情報を抽出
3. **AzureActivityテーブル**と結合して「Create role assignment」操作を検索
4. **結合条件**: 同じユーザー(user)が「ユーザーを作成」AND「ロール割り当てを作成」の両方を実行した場合のみマッチ

**重要なポイント:**

- このクエリは、**同一人物**が「ユーザー作成」と「ロール割り当て」の両方を行った場合のみ結果を返します
- `on user`での結合により、作成されたユーザー名ではなく、**操作を実行したユーザー**でマッチングします

**各アクションの分析:**

1. **User1がUser2にグローバル管理者ロールを割り当て**
    - 操作者: User1
    - User1はロール割り当てのみ実行(ユーザー作成なし)
    - **マッチしない**
2. **User1がUser3を作成してライセンス割り当て**
    - 操作者: User1
    - User1はユーザー作成のみ(ロール割り当てなし)
    - **マッチしない**
3. **User2がUser4を作成してセキュリティ閲覧者ロールを割り当て**
    - 操作者: User2
    - User2が「User4を作成」AND「ロール割り当てを作成」
    - 両方の操作をUser2が実行
    - **マッチする** ✓
4. **User2がUser5を作成してセキュリティオペレーターロールを割り当て**
    - 操作者: User2
    - User2が「User5を作成」AND「ロール割り当てを作成」
    - 両方の操作をUser2が実行
    - **マッチする** ✓

解答:**

|ステートメント|Yes|No|
|---|---|---|
|The query will identify the role assignment of User2.||○|
|The query will identify the creation of User3.||○|
|The query will identify the creation of User5.|○||

**正しい理由:**
1. **User2のロール割り当て - NO**: User1がUser2にロールを割り当てたが、このクエリはUser2が**受けた**ロール割り当てではなく、User2が**実行した**ロール割り当てを検出する
2. **User3の作成 - NO**: User1がUser3を作成したが、User1はロール割り当ても行っていない(User2へのロール割り当ては別の時系列)ため、結合条件を満たさない
3. **User5の作成 - YES**: User2がUser5を作成し、同時にロールも割り当てたため、結合条件を満たす
