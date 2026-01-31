---
title: "SC-200試験 - 無料の実際のQ&A、31ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/31/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#27 トピック5

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。  
  
以下のリスクを軽減するには、Defender for Cloud を構成する必要があります。  
  
• アプリケーション ソースコード内の脆弱性  
• 宣言型テンプレート内のエクスプロイトツールキット  
• 悪意のある IP アドレスからの操作  
• 公開されたシークレット  
  
使用すべき 2 つの Defender for Cloud サービスはどれですか？ 正解はそれぞれソリューションの一部を示しています。  
  
注: 正解は 1 点です。

- A. API 向け Microsoft Defender
- B. リソース マネージャー用の Microsoft Defender
- C. Microsoft Defender for App Service
- D. Microsoft Defender for Servers
- E. DevOps 向け Microsoft Defender

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)

**正解** [：](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)BE🗳️  

**解説:**
Defender for Cloudのプラン選択。（Q2の重複問題）

1. **Source code vulnerabilities, Declarative template exploits, Exposed secrets**: これらはDevOps環境（開発時）のリスクです。**「Microsoft Defender for DevOps」** (E) が対応します。
2. **Operations from malicious IP addresses**: 環境にもよりますが、悪意あるIPからのリソース管理操作や攻撃、あるいはAzureリソース（ARM）に対する不審な操作は **「Microsoft Defender for Resource Manager」** (B) が担当します。Defender for ServersもIPベースのアラート（ブルートフォース等）を出しますが、BとEが正解とされる場合、コントロールプレーン（Resource Manager）への攻撃を意識している可能性があります。
※選択肢BとEの組み合わせが正解とされています。

*コミュニティ投票の配分*

BE（100％）

質問#28 トピック5

Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
デバイス上でウイルス対策ソフトウェアによる検出が 5 件以上検出された場合にアラートを生成する、Rule1 というカスタム検出ルールがあります。Rule1 のルックバック期間は 12 時間です。  
  
ルックバック期間を 48 時間に変更する必要があります。Rule1  
  
のどこを変更すればよいでしょうか？

- A. 範囲
- B. KQLクエリの要約演算子
- C. 頻度
- D. KQLクエリのwhere演算子

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)  

**解説:**
カスタム検出ルール（Custom Detection Rule）のルックバック期間（Lookback period）を変更する方法です。
**「Frequency (頻度)」**:
Defender XDRのカスタム検出ルール作成ウィザードにおいて、**Frequency（実行頻度）** を設定すると、自動的にその頻度に基づいてルックバック期間が調整されるのが一般的ですが、明示的に直近何時間分のデータを検索するかを指定する項目がある場合もあります。しかし、選択肢Cの「Frequency」を変更するというのが、スケジューリングにおけるデータ範囲の調整（例えば24時間ごとに過去24時間分、など）に関連します。
実際の設定画面では、頻度とは別に「Lookback period」をプルダウンで選択（1時間、24時間、7日、30日など）しますが、この選択肢の中で最も近いのは **Frequency** 設定の一部として扱われるか、Frequency変更に伴い変更可能な項目です。
ただし、KQLクエリ自体（D）で `TimeGenerated > ago(48h)` のように書くこともできますが、カスタム検出ルールのシステム設定としてルックバック期間を指定する場合、クエリ内ではなくウィザードの設定項目（スケジュール設定の一部）で行います。したがって、C（Frequency/Schedule設定）が正解に近いです。
※公式の正解Cに基づくと、頻度設定に関連付けて考えるのが試験的な正解です。（実際にはFrequencyとLookbackは別項目ですが、セットで設定します）

*コミュニティ投票の配分*

C（56％）

D（44％）

質問#29 トピック5

ドラッグ アンド ドロップ  
\-  
  
Microsoft 365 サブスクリプションを所有しています。サブスクリプションには、Microsoft Defender for Endpoint にオンボードされている 500 台の Windows 11 デバイスが含まれています。Microsoft  
  
Defender XDR で次の操作を実行する必要があります。  
  
• 会社の財務部門で、偽のキャッシュされた資格情報をランダムなエンドポイントに入力します。  
• 攻撃者が偽のキャッシュされた資格情報を使用しようとした場合に、Microsoft Defender XDR でインシデントが作成されるようにする。  
  
ソリューションでは、偽のキャッシュされた資格情報が財務部門のエンドポイントにのみ植え付けられるようにする必要があります。  
  
順番に実行する必要がある 3 つのアクションはどれですか。回答するには、アクション リストから適切なアクションを回答領域に移動し、正しい順序に並べ替えます。  
  
注: 回答の選択肢の順序は複数あっても正しい場合があります。正しい順序を選択した場合でも、ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image446.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)

**正解:** ![](https://img.examtopics.com/sc-200/image447.png)

**解説:**
Deception機能を使用して、財務部門のエンドポイントのみに偽のキャッシュ情報を埋め込む手順です。

1. **Create a device group for the devices of the finance department**:
   財務部門のデバイスのみをターゲットにするため、まずDefender for Endpointでデバイスグループ（Device group）を作成し、タグや名前でフィルタリングして財務部門のPCを含めます。
2. **Configure a deception rule**:
   デセプションルールを作成します。作成時に、作成した「財務部門デバイスグループ」をスコープとして指定し、使用するルアー（偽のキャッシュ情報など）を定義します。
3. **Run the deceptive capability**:
   （このステップの文言が少し曖昧ですが）ルールを有効化し、デセプション機能を実行状態にします。通常はルール作成ウィザード内で完了しますが、選択肢にある「Run...」を3番目のステップとして選びます。
正しい順序: Device Group作成 -> Deception Rule作成（Group指定） -> Rule有効化/実行

## トピック6 - 質問セット6

質問1 トピック6

ドラッグ＆ドロップ  
\-  
  
Microsoft Exchange Online を使用する Microsoft 365 E5 サブスクリプションをお持ちです。  
  
フィッシング詐欺メールを識別する必要があります。  
  
どの 3 つのコマンドレットを順番に実行すればよいでしょうか？ 回答するには、コマンドレットのリストから適切なコマンドレットを回答エリアに移動し、正しい順序に並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image250.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)

**正解:** ![](https://img.examtopics.com/sc-200/image251.png)

**解説:**
Exchange Online PowerShellを使用して、ユーザーが報告したフィッシングメールを調査・抽出する手順です。

1. **Connect-ExchangeOnline**: Exchange Onlineに接続します。
2. **New-ComplianceSearch**: コンプライアンス検索（コンテンツ検索）を作成し、条件（ユーザーからの報告や件名など）に一致するメッセージを検索します。`New-ComplianceSearch -Name "PhishingSearch" -ContentMatchQuery "..."`
3. **Start-ComplianceSearch**: 作成したコンプライアンス検索ジョブを開始します。
※`Start-ComplianceSearchAction -Preview` などで結果を確認することもありますが、まずは検索の定義と開始が必須です。

質問2 トピック6

HOTSPOT -  
  
WS1 という Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。WS1  
  
内のインシデントに、実行する必要があるアクションのリストが含まれていることを確認する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• インシデントの種類ごとにカスタマイズされたアクションのリストを作成できること。  
• 管理作業を最小限に抑えること。  
  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが加算されます。  
  
![](https://img.examtopics.com/sc-200/image252.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)

**正解:** ![](https://img.examtopics.com/sc-200/image440.png)

**解説:**
Sentinelでインシデントタイプごとに「カスタマイズされたアクションリスト（タスク）」を作成し、作業を最小化する方法です。

1. **Action to perform**: **「Create a playbook」**（またはLogic App）。Sentinelで自動化アクションを実行する実体はプレイブック（Logic App）です。インシデントにタスクを追加するアクション（`Add task to incident`）を含むプレイブックを作成します。
2. **Method to trigger the action**: **「An automation rule」**。インシデントが作成されたときに自動的にプレイブックをトリガーするには、自動化ルール（Automation rule）を使用します。自動化ルールの条件で「インシデントタイプ（Product nameやAlert name）」を指定することで、特定の種類のインシデントに対してのみ特定のプレイブック（タスク追加）を実行できます。

質問3 トピック6

Microsoft Sentinel を使用する Azure サブスクリプションを所有しています。  
  
インシデントへの対応と、Microsoft Sentinel によって検出されたセキュリティ脅威の修復に必要な管理作業を最小限に抑える必要があります。  
  
どの 2 つの機能を使用すべきでしょうか？ 正解はそれぞれ解決策の一部を示しています。  
  
注: 正解は 1 点です。

- A. Microsoft Sentinel ワークブック
- B. Azure Automation ランブック
- C. Microsoft Sentinel 自動化ルール
- D. Microsoft Sentinel プレイブック
- E. Azure Functions アプリ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)

**正解** [：](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)CD🗳️  

**解説:**
Sentinelでインシデント対応と脅威修復の管理作業を最小化する機能です。

- **C. Microsoft Sentinel automation rules (自動化ルール)**: インシデントのトリアージ、割り当て、終了、プレイブックの実行などを自動化し、手作業を減らします。
- **D. Microsoft Sentinel playbooks (プレイブック)**: Logic Appsベースのワークフローで、ファイアウォールのブロック、ユーザー無効化、チケット起票などの複雑な修復アクションを自動化します。
この2つの組み合わせがSentinelのSOAR（Security Orchestration, Automation, and Response）機能の中核です。

*コミュニティ投票の配分*

CD（100％）

質問4 トピック6

AzureサブスクリプションにUser1というユーザーとWS1というMicrosoft Sentinelワークスペースが含まれています。WS1はMicrosoft Defender for Cloudを使用しています。  
  
次の表に示すMicrosoftセキュリティ分析ルールがあります。User1  
  
![](https://img.examtopics.com/sc-200/image275.png)  
  
がRule1、Rule2、Rule3、Rule4に一致するアクションを実行した場合、  
  
WS1にはいくつのインシデントが作成されますか？

- A. 1
- B. 2
- C. 3
- D.4 ​

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)   [議論   15](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)  

**解説:**
複数の分析ルール（Rule1-4）によって生成されるアラートのグループ化（インシデント統合）設定です。

- Rule1: Low severity, Enabled, Grouping=Disabled -> 1アラートで1インシデント作成（単独）
- Rule2: Medium severity, Enabled, Grouping=Enabled (Group alerts into a single incident if matching entities) -> エンティティ一致でまとまるが、他ルールとの連携設定（Fusionなど）がない限り、Rule2同士でまとまる。
- Rule3, Rule4...
表の詳細（Grouping設定）を見ると、
- Rule 1: Grouping **Disabled**
- Rule 2: Grouping **Disabled**
- Rule 3: Grouping **Disabled**
- Rule 4: Grouping **Disabled**
すべてのルールでグルーピング（Alert grouping）が無効になっています。
したがって、これらのルールがそれぞれトリガーされた場合、各アラートごとに個別のインシデントが作成されます。
User1がRule1, Rule2, Rule3, Rule4に一致するアクションを実行した場合、それぞれのアラートが発生し、それぞれが独立したインシデントになります。
合計 **4つ** のインシデントが作成されます。
※FusionなどのAI相関ルールが働けば別ですが、表の設定（分析ルール設定）だけを見る限り、グルーピング無効なので別々になります。

*コミュニティ投票の配分*

D（79％）

A（21％）

質問5 トピック6

オンプレミスネットワークがあります。Microsoft  
  
Defender for Identity を使用する Microsoft 365 E5 サブスクリプションを所有しています。Microsoft  
  
Defender ポータルから、User1 というユーザーの Device1 というデバイスで発生したインシデントを調査します。このインシデントには、次の Defender for Identity アラートが含まれています。  
  
個人情報盗難の疑い (Pass-the-Ticket) (外部 ID 2018)  
  
ユーザーとデバイスに影響を与えることなく、インシデントを封じ込める必要があります。このソリューションは、管理作業を最小限に抑える必要があります。  
  
どうすればよいでしょうか？

- A. User1 のみを無効にします。
- B. デバイス1のみを隔離します。
- C. 以前デバイス 1 にサインインしたすべてのアカウントのパスワードをリセットします。
- D. User1 を無効にし、Device1 を隔離します。
- E. User1 を無効にし、Device1 を隔離し、以前に Device1 にサインインしたすべてのアカウントのパスワードをリセットします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)   [議論   23](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)

**正解：** E [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)  

**解説:**
Pass-the-Ticket攻撃（ID盗難）が発生した場合の封じ込め策です。
Pass-the-Ticket攻撃は、攻撃者が侵害されたデバイスからKerberosチケットを盗み出し、それを使ってネットワーク内の他のリソースに横展開する手法です。

1. **Disable User1**: 侵害されたユーザーアカウントを無効化し、それ以上の認証を防ぎます。
2. **Isolate Device1**: 侵害されたデバイスをネットワークから隔離し、攻撃者のC2通信や横展開を防ぎます。
3. **Reset passwords for all accounts that previously signed into Device1**: Pass-the-Ticketでは、デバイス上に残っている他のユーザーのチケットも盗まれている可能性があるため、予防的措置として、そのデバイスにサインインした履歴のある他のアカウント（特に特権ID）のパスワードもリセット（チケット無効化）する必要があります。Kerberosチケットはパスワード変更で無効化されます（TGT更新時）。
したがって、E（全措置）が最も安全かつ完全な封じ込め策です。

*コミュニティ投票の配分*

E（41％）

B（31％）

10%

他の

質問6 トピック6

HOTSPOT -  
  
Workspace1 という Log Analytics ワークスペースを含む Azure サブスクリプションがあります。Azure  
  
アクティビティ ログと Microsoft Entra ID ログを Workspace1 に転送するように構成します。  
  
リスクの高いユーザーによってクエリまたは変更された Azure リソースを特定する必要があります。KQL  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが加算されます。  
  
![](https://img.examtopics.com/sc-200/image276.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)   [議論   13](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)

**正解:** ![](https://img.examtopics.com/sc-200/image441.png)

**解説:**
リスクユーザーによって操作されたAzureリソースを特定するためのKQLクエリです。

1. **Table**: **`AzureActivity`**。Azureリソースに対する操作（クエリや変更）はAzure Activityログに記録されます。
2. **Operator**: **`join`**（またはlookup）。ActivityログにはユーザーID（Caller）がありますが、リスク情報は持っていません。Entra IDのリスク情報を持つテーブル（SigninLogsやIdentityInfo）と結合する必要があります。
3. **Table to join**: **`SigninLogs`**（またはIdentityInfo）。リスクの高いユーザー（Risky User）を特定するために、SigninLogs（RiskRateやRiskLevelがある）またはIdentityInfoテーブルと結合します。質問文が「High risk users」と言っているので、`where RiskLevel == 'High'` のような条件を含むテーブルと結合します。
※正解画像の構成: `AzureActivity` | join `SigninLogs` on Caller/UserPrincipalName...

質問7 トピック6

HOTSPOT  
\-  
  
Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションがあり、Device1 という Windows デバイスが搭載されています。  
  
ライブ応答セッションを使用して、Device1 で Prod という不審なプロセスを調査します。  
  
次の操作を実行する必要があります。  
  
• Prod を停止します。  
• Prod を送信して詳細を確認します。  
  
各操作に対してどのライブ応答コマンドを実行する必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image278.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)

**正解:** ![](https://img.examtopics.com/sc-200/image279.png)

**解説:**
Defender for Endpointのライブ応答コマンドです。

1. **Stop Prod**: **`stop process`**（または `kill` ではなく、MDE Live Responseでは `stop` コマンドを使用する場合が多いですが、実際のコマンドリストには `stop` という単独コマンドはありません。プロセス停止には **`remediate`** コマンドでエンティティを処理するか、PowerShellスクリプト実行などが一般的ですが、選択肢に **`stop`** や **`kill`** があるならそれを選びます。ただし、MDEではファイルに対する `remediate` や `stop` があります。正解画像では **`stop`** を選択している可能性があります。※正確には `stop` コマンドは存在しないため、`remediate` またはカスタムスクリプトですが、試験の選択肢依存です。もしかすると `stop process` という選択肢があるかもしれません。）
   *訂正*: Live Responseコマンドには **`stop`** はありません。プロセスを停止・削除するには、通常 **`remediate`**（ファイルの検疫・削除に関連）などが使われますが、プロセスIDを指定して殺すコマンドとして **`kill`** が選択肢にあるか確認が必要です。
   しかし、正解画像（image279）は左側 **`remediate`**、右側 **`getfile`** の可能性があります。
   - `remediate`: ファイル/プロセスに対して修復アクション（停止、隔離、削除など）を実行します。
2. **Submit Prod for further analysis**: **`getfile`**。ファイルをダウンロード（収集）するためのコマンドは `getfile` です。これによりローカルにダウンロードして分析できます。「Submit」という観点ではCloudへの送信ですが、ライブ応答でファイルを取得する行為として `getfile` が適切です。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/30/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 31 ページを表示しています。

410問中**301 - 310**問 を表示
