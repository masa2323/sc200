---
title: "SC-200試験 - 無料の実際のQ&A、19ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/19/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#54 トピック3

HOTSPOT -  
  
次のKQLクエリがあります。  
  
![](https://img.examtopics.com/sc-200/image139.png)  
  
以下の各文について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注：正しい選択は1点です。  
  
![](https://img.examtopics.com/sc-200/image140.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   20](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image429.png)

**解説:**
KQLクエリ `search in (AuditLogs, SigninLogs) "User1" | summarize count() by $table` の動作に関する問題です。

1. **The query returns a count of the events in AuditLogs and SigninLogs that contain "User1": Yes**。`search` 演算子は指定されたテーブル（AuditLogs, SigninLogs）の全カラムから文字列 "User1" を検索します。
2. **The results are grouped by table name: Yes**。`summarize count() by $table` は、検索結果をテーブル名ごとにグループ化して件数をカウントします。
3. **The query supports the same Log Analytics limits as the union operator: No**。`search` はテキスト検索に特化しており、`union` とは異なる処理制限や特性を持ちます（例えば、全カラム検索のためコストが高い場合があります）。

質問#55 トピック3

HOTSPOT  
\-  
  
Microsoft Sentinelワークスペースがあります。Parser1  
  
というカスタムAdvanced Security Information Model (ASIM)パーサーを開発し、Schema1というスキーマを生成します。Schema1を  
  
検証する必要があります。  
  
コマンドをどのように完了すればよいですか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image142.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image143.png)

**解説:**
ASIMパーサーが生成するスキーマ（Schema1）を検証するためのコマンド（クエリ）です。
**「ASIMスキーマテスター（ASIM schema tester）」**: ASIMには、パーサーが標準スキーマに準拠しているか確認するための検証用クエリ（ツール）が用意されています。これは通常、Sentinelのログクエリ画面から実行します。
※画像選択肢の詳細は不明ですが、`Get-AzSentinel...` のようなPowerShellコマンドレットではなく、KQLベースの検証クエリを選択する流れとなります（あるいはValidation用の特定の関数呼び出し）。

質問#56 トピック3

HOTSPOT  
\-  
  
ユーザーおよびエンティティ行動分析 (UEBA) が有効になっている Microsoft Sentinel ワークスペースがあります。Server1  
  
というサーバー上で実行された、セキュリティ上重要なユーザー操作に関連するすべてのログエントリを特定する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• IT 部門のメンバーではないユーザーによる、セキュリティ上重要な操作のみを含める。  
• 誤検知の数を最小限に抑える。  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが加算されます。  
  
![](https://img.examtopics.com/sc-200/image144.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image145.png)

**解説:**
UEBAが有効な環境で、IT部門以外のユーザーによる重要な操作を特定するクエリです。

1. **IdentityInfo**: ユーザーの部署（Department）やグループ情報などを含むUEBAエンティティテーブルです。これとSecurityEventやAuditLogsを結合します。
2. **Department != "IT"**: `IdentityInfo` テーブルの `Department` 列を使用して、IT部門のユーザーを除外します。
3. **summarize ... by AccountName**: アカウントごとに集計します。

質問#57 トピック3

HOTSPOT  
\-  
  
Microsoft Sentinelワークスペースをお持ちです。  
  
過去3時間に複数の国から成功したサインインを識別するKQLクエリを作成する必要があります。  
  
クエリはどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image146.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image147.png)

**解説:**
過去3時間以内に複数の国から成功したサインインを検出するKQLクエリです。

1. **SigninLogs**: サインインログテーブルを使用します。
2. **where TimeGenerated > ago(3h)**: 過去3時間にフィルタリングします。
3. **where ResultType == 0**: 成功したサインイン（ResultType 0）に絞り込みます。
4. **summarize Count = dcount(Location) by UserPrincipalName**: ユーザーごとに、ロケーション（国/地域）のユニーク数（distinct count）をカウントします。
5. **where Count > 1**: ロケーション数が1より大きい（複数国）ユーザーを抽出します。

質問#58 トピック3

HOTSPOT  
\-  
  
Azureサブスクリプションを所有しています。Microsoft  
  
Sentinelワークスペースを実装する予定です。1日あたり20GBのセキュリティログデータを取り込む予定です。  
  
ワークスペースのストレージを構成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 毎日取り込むデータのコストを最小限に抑える。  
• 追加コストをかけずにデータ保持期間を最大化する。  
  
各要件に対して、どのような対策を講じるべきでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image148.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   18](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image149.png)

**解説:**
コストを最小化しつつデータを長期間保持するストレージ構成です。

1. **Minimize the cost of ingested data**: **「Basic Logs (基本ログ)」**。デバッグやトラブルシューティング目的の大量ログ（NetFlowなど）については、Basic Logsプランを使用することで取り込みコストを大幅に削減できます。
2. **Maximize data retention without incurring additional costs**: **「Create an archive (アーカイブを作成)」**（またはArchive tierへの移動）。Log Analyticsのデータ保持期間を超える場合、Archive層に移動することで、安価に長期間（最大7年）保持できます。

質問#59 トピック3

HOTSPOT -  
  
sws1 という Microsoft Sentinel ワークスペースがあります。sws1  
  
でインシデントが発生した際に、オンプレミスの IT サービス管理システムでインシデントを通知する Azure ロジック アプリを作成する予定です。  
  
このロジック アプリ用に Microsoft Sentinel コネクタの資格情報を構成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 管理作業を最小限に抑える。  
• 最小権限の原則を適用する。  
  
資格情報はどのように構成すればよいでしょうか？ 回答するには、回答領域から適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image150.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   18](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image430.png)

**解説:**
Logic AppのSentinelコネクタ用資格情報を、最小権限かつ管理負荷最小で構成する方法です。

1. **Authentication type**: **「Managed Identity (マネージドID)」**。Logic Appのシステム割り当てマネージドIDを使用することで、パスワード管理が不要になり、安全かつ管理が容易になります。
2. **Role**: **「Microsoft Sentinel Responder」**。インシデントの更新（クローズやコメント追加）を行うには、Responderロールが必要です。Contributorは過剰権限、Readerでは更新ができません。

質問#60 トピック3

Microsoft Sentinelワークスペースを使用しています。  
  
組み込みのAdvanced Security Information Model（ASIM）パーサーが自動更新されないようにする必要があります。  
  
この目標を達成するための2つの方法は何ですか？ 正解はそれぞれ完全な解決策を示しています。  
  
注：正解は1つにつき1ポイントです。

- A. 組み込みパーサーを参照するハンティング クエリを作成します。
- B. カスタムの統合パーサーを構築し、組み込みパーサー バージョンを含めます。
- C. 組み込みパーサーを再デプロイし、CallerContext パラメータに Any を指定し、SourceSpecificParser パラメータに Any を指定します。
- D. 組み込みパーサーを再デプロイし、Built-in の CallerContext パラメータを指定します。
- E. 組み込みパーサーを含む分析ルールを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   20](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** BC [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)  

**解説:**
組み込みのASIMパーサーが自動更新されないように制御する方法です。
**「B. カスタムの統合パーサーを構築し、特定のバージョンを含める」**: デフォルトの統合パーサー（Unifying parser）は常に最新のパーサーを呼び出します。これを防ぐには、独自のカスタム統合パーサーを作成し、その中で使用するソース特定パーサーのバージョン（例: `vimNetworkSessionMicrosoftWindowsEventFirewallV02`）を明示的に指定します。
**「C. (またはWatchlistを使用)」**: もう一つの方法は、`ASim Disabled Parsers` ウォッチリストを使用して、特定の組み込みパーサーを統合パーサーの対象から除外（無効化）することです。

*コミュニティ投票の配分*

紀元前（53％）

BE（44％）

4%

質問#61 トピック3

Workbook1 というカスタム Microsoft Sentinel ワークブックがあります。Workbook1  
  
にグリッドを追加する必要があります。ソリューションでは、グリッドに最大 100 行が含まれるようにする必要があります。  
  
どうすればよいでしょうか？

- A. グリッド クエリに take 演算子を含めます。
- B. グリッド クエリにプロジェクト演算子を含めます。
- C. クエリ エディター インターフェイスで、設定を構成します。
- D. クエリ エディター インターフェイスで、\[詳細エディター\] を選択します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   13](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)  

**解説:**
Workbookのグリッド表示を最大100行に制限する方法です。
**「グリッド クエリに take 演算子を含めます」**: KQLクエリの末尾に `| take 100` （または `limit 100`）を追加することで、クエリ結果自体を100行に制限するのが最も確実かつ一般的な方法です。
※UI上の「Advanced Settings」でも表示行数を設定できますが、クエリレベルでの制御（A）が正解とされることが多いです。

*コミュニティ投票の配分*

A（86％）

14%

質問#62 トピック3

HOTSPOT  
\-  
  
SW1というMicrosoft Sentinelワークスペースがあります。  
  
タイムチャートを含むカスタムブックを作成する予定です。  
  
プロバイダーごとに1日あたりのセキュリティアラート数を特定するクエリを作成する必要があります。  
  
クエリはどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正しい選択肢は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image152.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image153.png)

**解説:**
プロバイダーごとに1日あたりのセキュリティアラート数を特定する、タイムチャート用クエリです。
`SecurityAlert | summarize count() by ProviderName, bin(TimeGenerated, 1d) | render timechart`

1. **summarize count()**: アラート数をカウントします。
2. **by ProviderName, bin(TimeGenerated, 1d)**: プロバイダー名と、1日（1d）ごとの時間枠（bin）でグループ化します。
3. **render timechart**: 結果をタイムチャートとして描画します。

質問#63 トピック3

Workspace1 という Microsoft Sentinel ワークスペースがあります。  
  
組み込みの統合型 ASIM パーサーから、組み込みのソース固有の Advanced Security Information Model (ASIM) パーサーを除外する必要があります。Workspace1  
  
には何を作成すればよいでしょうか？

- A. 解析規則
- B. ウォッチリスト
- C. ワークブック
- D. 狩猟に関する質問

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)  

**解説:**
組み込みの統合ASIMパーサーから、特定のソース固有パーサーを除外するために作成するものです。
**「ウォッチリスト (Watchlist)」**: ASIMフレームワークでは、`ASim Disabled Parsers` という名前のウォッチリストを使用して、統合パーサーから除外したいパーサーを管理します。このリストに除外したいパーサー名とCallerContextを追加することで、クエリ変更なしに動作を制御できます。

*コミュニティ投票の配分*

B（94％）

6%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/18/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 19 ページを表示しています。

410問中**181 - 190**問 を表示
