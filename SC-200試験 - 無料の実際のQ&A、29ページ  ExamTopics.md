---
title: "SC-200試験 - 無料の実際のQ&A、29ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/29/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問7 トピック5

Microsoft 365 E5 サブスクリプションがあり、Device1 というデバイスが含まれています。Device1 は Microsoft Defender for Endpoint に登録されています。Device1  
  
から、証拠として File1.exe というファイルを含むインシデントが報告されました。  
  
「調査パッケージの収集」アクションを開始し、ZIP ファイルをダウンロードします。File1.exe  
  
が最初に実行された時刻と最後に実行された時刻を特定する必要があります。  
  
調査パッケージで確認すべき点は何でしょうか？

- A. プロセス
- B. 自動実行
- C. セキュリティイベントログ
- D. スケジュールされたタスク
- E. プリフェッチファイル

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)

**正解：** E [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
調査パッケージ（Investigation package）に含まれるデータから実行可能ファイルの実行時刻を特定するための情報源です。
**「Prefetch files (プリフェッチファイル)」**: Windowsのプリフェッチファイル（.pf）は、アプリケーションの起動頻度や起動速度を最適化するためのものですが、副次的に「そのアプリケーションが最後に実行された日時」や「実行回数」などの情報が含まれています。調査パッケージにはプリフェッチファイルのダンプが含まれており、これを解析することで、File1.exeの初回/最終実行時刻を特定できます。

*コミュニティ投票の配分*

E（71％）

14%

14%

質問8 トピック5

Microsoft Defender for Cloud が有効になっている Azure サブスクリプションをお持ちです。Windows  
  
Server 2022 を実行し、Amazon Web Services (AWS) でホストされている Server1 という仮想マシンがあります。Defender  
  
for Cloud を使用して Server1 のログを収集し、脆弱性を解決する必要があります。Server1  
  
に最初にインストールすべきものは何ですか？

- A. Microsoft 監視エージェント
- B. Azure Monitorエージェント
- C. Azure Connected Machine エージェント
- D. Azure Pipelinesエージェント

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
AWS上のWindows Server (Server1) をAzure (Defender for Cloud) で保護・ログ収集するための最初の手順です。
**「Azure Connected Machine agent」**: これをインストールすることで、非Azureサーバー（オンプレミスやAWS）をAzure Arc対応サーバーとして登録できます。Azure Arcに登録されると、Azure VM拡張機能（Azure Monitor Agentなど）をインストールできるようになり、Defender for Cloudによる保護やログ収集が可能になります。
※MMA (Microsoft Monitoring Agent) は廃止予定であり、現在はAzure Monitor Agent (AMA) が標準ですが、AMAを非AzureサーバーにインストールするにはAzure Arc (Connected Machine Agent) が前提条件として推奨されます。

*コミュニティ投票の配分*

C（100％）

質問9 トピック5

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをご利用です。Microsoft  
  
Graph API を攻撃ベクトルとして利用することが知られている攻撃者を調査しています。攻撃者は以下の表に示す戦術を実行します。  
  
![](https://img.examtopics.com/sc-200/image270.png)  
  
組織内で悪意のあるアクティビティを検索する必要があります。MicrosoftGraphActivityLogs  
  
テーブルを使用して分析できる戦術はどれでしょうか？

- A. Tactic2のみ
- B. 戦術1と戦術2のみ
- C. 戦術2と戦術3のみ
- D. 戦術1、戦術2、戦術3

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
MicrosoftGraphActivityLogsテーブルで検出可能な戦術（Tactic）についてです。
このテーブルには、Microsoft Graph APIへのすべてのリクエストログが含まれます。

- **Tactic 1 (Reconnaissance: 偵察)**: `User.Read.All` などのAPIを使用してディレクトリ情報を収集する行為はログに記録されます。
- **Tactic 2 (Discovery: 探索)**: `Mail.Read` などでメール内容を探索する行為もAPIコールとして記録されます。
- **Tactic 3 (Collection: 収集)**: データをダウンロードする行為もAPIコールです。
したがって、攻撃者がGraph APIを使用している限り、すべての戦術のアクティビティがログに含まれるため、分析可能です。

*コミュニティ投票の配分*

D（100％）

質問10 トピック5

ドラッグ アンド ドロップ  
\-  
  
次の Advanced Security Information Model (ASIM) パーサーを含む Microsoft Sentinel ワークスペースがあります。  
  
• \_Im\_ProcessCreate  
• imProcessCreate  
  
vimProcessCreate という新しいソース固有のパーサーを作成します。  
  
次の要件を満たすようにパーサーを変更する必要があります。  
  
• すべての ProcessCreate パーサーを呼び出します。  
• フィールドをプロセス スキーマに標準化します。  
  
各要件を満たすには、どのパーサーを変更する必要がありますか。 回答するには、適切なパーサーを正しい要件にドラッグします。  
  
各パーサーは、1 回または複数回使用することも、まったく使用しないこともできます。 コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image271.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)

**正解:** ![](https://img.examtopics.com/sc-200/image272.png)

**解説:**
ASIMパーサー（Advanced Security Information Model）のカスタマイズ（統合パーサーの作成）です。

1. **Call all ProcessCreate parsers**: **`imProcessCreate`**。これはASIMの「統合パーサー（Unifying parser）」であり、すべてのソース固有パーサー（`_Im_ProcessCreate_Windows`, `_Im_ProcessCreate_Linux` など）をまとめて呼び出します。新しいカスタムパーサー（vimProcessCreate）がすべてのProcessCreateイベントを含むようにするには、既存の統合パーサーのロジックを含めるか、統合パーサー自体を変更する必要がありますが、質問の意図は「どのパーサーがすべてのソースを呼び出しているか（それをベースにするか）」という点です。通常、カスタムソースを含める場合、統合パーサーがカスタムパーサーを呼び出すように構成しますが、ここでは要件を満たすために変更すべき対象として「統合パーサー（imProcessCreate）」が正解です。
2. **Normalize fields to the process schema**: **`_Im_ProcessCreate`**。これはASIMの「パラメータなしバージョン」または「フィルタリングなしバージョン」の基本パーサー、あるいはスキーマ定義に関連しますが、一般的にASIMでは `_Im_...` がソース固有や正規化ロジックを持つ基本的なKQL関数です。新しいソース（vimProcessCreate）を作成する場合、フィールドをスキーマにマッピング（正規化）するロジックは、その新しいパーサー内に記述しますが、選択肢から選ぶなら、正規化を行う個々のソースパーサーの命名規則（`_Im_ProcessCreate` プレフィックスなど）に従う、またはそれを参照します。
※画像の正解は、左側（Call all...）に **`imProcessCreate`**、右側（Normalize...）に **`vimProcessCreate`**（設問で作った新しいパーサー自体）または **`_Im_ProcessCreate`** を選んでいる可能性があります。通常、正規化はソース固有パーサー（ここではvimProcessCreate）の役割です。

質問11 トピック5

HOTSPOT  
\-  
  
Windows Server を実行するオンプレミス サーバーがあります。SW1  
  
という Microsoft Sentinel ワークスペースがあります。SW1 は、Azure Monitor エージェント データ コネクタを使用してサーバーから Windows セキュリティ ログ エントリを収集するように構成されています。  
  
収集するイベントの範囲をイベント 4624 と 4625 のみに制限する予定です。  
  
コネクタに適用されたフィルターの構文を検証するには、PowerShell スクリプトを使用する必要があります。  
  
スクリプトをどのように完成させる必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image273.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)

**正解:** ![](https://img.examtopics.com/sc-200/image274.png)

**解説:**
AMA用のWindows Security Log収集フィルタ（XPathクエリ）を検証するPowerShellスクリプトの完成です。

1. **Command**: **`Get-WinEvent`**。Windowsイベントログをクエリするためのコマンドレットです。
2. **Parameter**: **`-FilterXPath`**。XPathクエリを指定してフィルタリング結果を確認するために使用します。
3. **Value**: **`Security!*[System[(EventID=4624 or EventID=4625)]]`**。セキュリティログ（Security）に対して、EventIDが4624または4625であるイベントを選択するXPath構文です。`LogName!XPath` の形式はAMA設定画面（JSON/DCR）で使われますが、`Get-WinEvent` コマンドで使う場合は `-LogName Security -FilterXPath "*[System[(EventID=4624 or EventID=4625)]]"` のようになります。選択肢の形式に合わせて最も適切なものを選びます。

質問12 トピック5

Microsoft 365 サブスクリプションをご利用で、Microsoft Defender for Endpoint プラン 2 をご利用で、500 台の Windows デバイスを保有しています。Microsoft  
  
Defender XDR のカスタム デセプション ルールを作成する予定です。  
  
このルールが特定の 10 台のデバイスにのみ適用されるようにする必要があります。  
  
まず何をすべきでしょうか？

- A. ルールにカスタムルアーを追加します。
- B. 各デバイスの IP アドレスをルールのデコイ アカウントとホストのリストに追加します。
- C. デバイスをグループに追加します。
- D. デバイスにタグを割り当てます。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
Defender XDRのデセプション（Deception）ルールを特定のデバイス（10台）のみに適用する方法です。
**「Assign a tag to the devices (デバイスにタグを割り当てる)」**:
デセプションルールのスコープ設定では、**「デバイス タグ (Device Tags)」** を使用して対象をフィルタリングすることができます。デバイスグループも使えますが、特定の少数のデバイスを対象にする場合、タグ付けが柔軟で一般的です。選択肢にデバイスグループがある場合でも、タグが正解となるケースが多いです（詳細な粒度制御のため）。

*コミュニティ投票の配分*

D（81％）

A（19％）

質問13 トピック5

Microsoft Defender for Cloud を使用する Sub1 という Azure サブスクリプションがあります。Sub1  
に PCI DSS 4.0 イニシアチブを割り当て、Defender for Cloud の規制コンプライアンス ダッシュボードにそのイニシアチブを表示する必要があります。  
  
環境設定のセキュリティ ポリシーで、業界標準や規制標準を追加するオプションが利用できないことがわかりました。  
  
まず何をすべきでしょうか？

- A. Log Analytics の継続的なエクスポート設定を構成します。
- B. サブスクリプションに対して Cloud Security Posture Management (CSPM) プランを有効にします。
- C. Azure Event Hubs の連続エクスポート設定を構成します。
- D. Microsoft Cloud Security Benchmark (MCSB) の割り当てを無効にします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
規制コンプライアンスダッシュボードでPCI DSS 4.0などの基準を追加するための前提条件です。
**「Enable the Cloud Security Posture Management (CSPM) plan」**: Defender CSPMプラン（有料）を有効にすることで、デフォルトのMicrosoft Cloud Security Benchmark (MCSB) 以外の規制基準（PCI DSS, ISO 27001など）を追加・管理できるようになります。無料版（Foundational CSPM）ではカスタム基準や追加基準の利用が制限されています。

*コミュニティ投票の配分*

B（100％）

質問14 トピック5

SW1というMicrosoft Sentinelワークスペースがあります。SW1  
  
で有効になっている異常ルールを特定する必要があります。Microsoft  
  
Sentinelで確認すべき項目は何ですか？

- A. コンテンツハブ
- B. エンティティの行動
- C. 分析
- D. 設定

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
Sentinelで有効になっている「異常（Anomaly）ルール」を確認する場所です。
**「Analytics (分析)」**: 異常ルール（Anomaly rules）は、分析ルールのタブ（Active rulesまたはRule templates）の中に一覧表示されます。ここで有効/無効の状態を確認したり、編集したりできます。「Entity behavior」はUEBAのダッシュボード、「Content hub」はソリューションのインストール場所です。

*コミュニティ投票の配分*

C（100％）

質問15 トピック5

WS1 という Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。  
  
新しい攻撃ベクトルを検出するハンティングクエリを作成します。この攻撃ベクトルは、MITRE ATT&CK データベースに登録されている戦術にマッピングされます。  
  
新しい攻撃ベクトルが検出されたときに、WS1 でインシデントが作成されることを確認する必要があります。  
  
どのような設定が必要ですか？

- A. 狩猟ライブストリームセッション
- B. クエリブックマーク
- C. スケジュールされたクエリルール
- D. 融合ルール

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
新しい攻撃ベクトル（Hunting queryで見つかるものなど）に基づいて、将来的に自動でインシデントを作成するようにするための設定です。
**「Scheduled query rule (スケジュールされたクエリルール)」**: ハンティングクエリを定期的に実行し、条件に合致した場合にアラート（およびインシデント）を作成するには、そのクエリを「分析ルール（Analytics rule）」、具体的には「スケジュールされたクエリルール」に変換または作成する必要があります。

*コミュニティ投票の配分*

C（100％）

質問16 トピック5

Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
社内のセキュリティチームが、ネットワーク上のコマンドアンドコントロール (C2) エージェントのトラフィックを検出しています。エージェントは 50 時間に 1 回通信します。  
  
侵害されたデバイスを特定し、通信パターンを確立する Microsoft Defender XDR カスタム検出ルールを作成する必要があります。このソリューションは、以下の要件を満たす必要があります。  
  
• 過去 14 日間に通信したすべてのデバイスを特定する。  
• デバイスの特定にかかる時間を最小限に抑える。  
  
このルールの検出頻度はどのくらいに設定すればよいでしょうか。

- A. 12時間ごと
- B. 24時間ごと
- C. 3時間ごと
- D. 1時間ごと

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)   [議論   16](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
カスタム検出ルールで「過去14日間の通信」を特定しつつ、「特定にかかる時間を最小限に抑える（実行頻度の最適化）」設定です。
C2エージェントは「50時間に1回」通信します。
検出ルールで `Lookback time`（データを遡る期間）を長く設定（例: 14日）すれば、1回の実行で過去の通信パターンを捕捉できますが、頻度（Frequency）の設定が問われています。
選択肢の中で **「Every 24 hours (24時間ごと)」** が標準的かつリソース効率が良いです。1時間ごと（D）や3時間ごと（C）だと頻繁すぎて負荷が高く、通信が50時間に1回しかないため、空振りが多くなります。24時間ごとならば、50時間周期の通信を数回の実行で確実に捕捉でき（Lookback期間が十分あれば1回でも捕捉可能）、かつシステム負荷を抑えられます。
Lookback期間を14日（336時間）に設定しておけば、クエリ実行頻度が24時間に1回でも、毎回「過去14日分」をスキャンするため、50時間周期の通信を見落とすことはありません。

*コミュニティ投票の配分*

B（44％）

D（33％）

A（19％）

4%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/28/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 29 ページを表示しています。

410問中**281 - 290**問 を表示
