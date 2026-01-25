---
title: "SC-200試験 - 無料の実際のQ&A、11ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/11/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#35 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。  
  
セキュリティ アラート ビューをフィルター処理して、以下のアラートを表示する必要があります。  
  
• 通常とは異なるユーザーによるキー コンテナーへのアクセス  
• 通常とは異なる場所からのログオン  
• あり得ない移動アクティビティ  
  
どの重大度を使用すればよいですか？

- A. 情報提供
- 吹く ​
- C. 中
- D. ハイ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
特定のアラートタイプ（通常とは異なるユーザー/場所/移動）をフィルタリングするための重大度設定です。
**「Medium (中)」**: 「Unusual user accessed a key vault（通常とは異なるユーザーによるKey Vaultへのアクセス）」や「Impossible travel activity（あり得ない移動）」といった、アノマリー（異常）検知ベースのアラートは、通常「Medium」重大度に分類されます。
High（高）はマルウェアの実行など、より確実で即時性の高い脅威に割り当てられます。

*コミュニティ投票の配分*

C（92％）

8%

質問#36 トピック2

サードパーティのセキュリティ情報イベント管理（SIEM）ソリューションを使用して、Microsoft Defender for Cloud のアラートを確認する予定です。MITRE  
  
ATT&CK の権限昇格戦術の使用を示すアラートを見つける必要があります。  
  
どの JSON キーを検索すればよいでしょうか？

- A. 説明
- B. 意図
- C. 拡張プロパティ
- D. エンティティ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)   [議論   18](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
SIEMでDefender for Cloudアラートを取り込む際、MITRE ATT&CKの戦術（Privilege Escalationなど）を識別するために使用されるJSONキーです。
**「Intent」**: Defender for CloudのアラートJSONスキーマには `Intent` というプロパティがあり、ここに攻撃の意図（Kill Chain Intent）としてMITRE ATT&CKの戦術名（例: "Privilege Escalation"）がマッピングされます。
`ExtendedProperties` にも詳細情報が含まれますが、戦術の分類として標準的に使用されるトップレベルのフィールドは `Intent` です。

*コミュニティ投票の配分*

B（93％）

4%

質問#37 トピック2

ドラッグ＆ドロップ -  
  
オンプレミスサーバーが50台あります。Microsoft  
  
Defender for Cloudを使用するAzureサブスクリプションがあります。Defender for Cloudの展開では、Microsoft Defender for Serversと自動プロビジョニングが有効になっています。  
  
オンプレミスサーバーをサポートするには、Defender for Cloudを構成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 脅威と脆弱性の管理を提供する。  
• データ収集ルールをサポートする。  
  
これらの3つのアクションのうち、順番に実行する必要があるのはどれですか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序で並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image131.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)   [議論   13](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)

**正解:** ![](https://img.examtopics.com/sc-200/image418.png)

**解説:**
オンプレミスサーバーで脅威脆弱性管理とデータ収集ルール（DCR）をサポートするための構成手順です。

1. **Azure Arc対応サーバーエージェントをインストールする**: まず、オンプレミスサーバーをAzure Arcにオンボードします。これによりAzureリソースとして管理可能になります。
2. **Azure Monitorエージェントをインストールする**: Arc対応サーバーにAMA (Azure Monitor Agent) を拡張機能としてインストールします。従来のLog Analyticsエージェントではなく、DCRをサポートするAMAが必要です。
3. **データ収集ルールを作成する**: AMAを使用して収集するデータの種類と送信先を定義するDCR (Data Collection Rule) を作成し、関連付けます。

質問#38 トピック2

HOTSPOT  
\-  
  
Microsoft Defender for Cloud を使用する Azure サブスクリプションがあり、app1 という Azure ロジック アプリが含まれています。  
  
特定の Defender for Cloud セキュリティ アラートが生成されたときに、app1 が起動するようにする必要があります。Azure  
Resource Manager (ARM) テンプレートをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image133.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)

**正解:** ![](https://img.examtopics.com/sc-200/image134.png)

**解説:**
ARMテンプレートでDefender for CloudのアラートをトリガーにLogic Appを実行する設定です。

1. **Resource type**: **`Microsoft.Security/automations`**。これがワークフロー自動化のリソースタイプです。
2. **Trigger**: **`Alert`** (または `StateChange` の中で `Alert` イベントを指定)。アラート生成時に発火させるため、トリガー条件としてアラートを指定します。

質問#39 トピック2

HOTSPOT -  
  
サポートされているすべてのリソースタイプに対してMicrosoft Defender for Cloudが有効になっているAzureサブスクリプションがあります。LA1  
  
というAzureロジックアプリを作成します。LA1  
  
を使用して、Defender for Cloudで検出されたセキュリティリスクを自動的に修復する予定です。Defender  
  
for CloudでLA1をテストする必要があります。  
  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正しい選択ごとに1ポイントが加算されます。  
  
![](https://img.examtopics.com/sc-200/image159.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)   [議論   20](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)

**正解:** ![](https://img.examtopics.com/sc-200/image419.png)

**解説:**
Defender for Cloudの自動修復Logic App (LA1) をテストする方法です。

1. **From Defender for Cloud, select**: **「Security alerts」**。アラート一覧ページからテスト対象のアラートを選択します（またはサンプルアラートを生成します）。
2. **Select**: **「Trigger logic app」** (または「Take action」メニュー内のロジックアプリ実行オプション)。アラートの詳細画面から、手動で特定のLogic Appをトリガーして、動作（修復アクションの実行など）を確認します。
※「Workflow automation」ページは自動化ルールの定義を行う場所であり、個別の修復ロジックの即時テスト実行はアラート画面から行うのが一般的です。

質問#40 トピック2

Microsoft Defender for Cloud が有効になっている Azure サブスクリプションをお持ちです。Windows  
  
10 を実行し、Log Analytics エージェントがインストールされた仮想マシンがあります。  
  
この仮想マシンに対して、アラートを生成する攻撃をシミュレートする必要があります。  
  
まず何をすべきでしょうか？

- A. Log Analytics トラブルシューティング ツールを実行します。
- B. 実行ファイルをコピーし、ファイル名を ASC\_AlertTest\_662jfi039N.exe に変更します。
- C. Microsoft Monitoring Agent の設定を変更します。
- D. MMASetup 実行可能ファイルを実行し、--foo 引数を指定します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
Windows VMでDefender for Cloudのアラート生成攻撃をシミュレートする標準的な方法です。
**「実行ファイルをコピーし、ファイル名を ASC_AlertTest_662jfi039N.exe に変更する」**: 正規の実行ファイル（cmd.exeやcalc.exeなど）をコピーし、この特定の名前（`ASC_AlertTest_662jfi039N.exe`）に変更して実行すると、Defender for Cloudはこれをテスト用のアクティビティとして検知し、テストアラートを生成します。

*コミュニティ投票の配分*

B（80％）

D（20％）

質問#41 トピック2

ドラッグ＆ドロップ -  
  
新しいAzureサブスクリプションを作成し、Azure Monitorのログ収集を開始します。Windows  
  
Serverを実行しているAzure仮想マシンに悪意のあるファイルが存在する場合、Microsoft Defender for Cloudがアラートをトリガーすることを検証する必要があります。  
  
どの3つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
  
注：回答の選択肢は複数選択可能です。正しい順序を選択した場合、ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image161.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)

**正解:** ![](https://img.examtopics.com/sc-200/image420.png)

**解説:**
Windows Serverを実行するAzure VMで、悪意のあるファイルに対するアラートを検証する手順です。

1. **Enable Microsoft Defender for Servers**: まず、対象のサブスクリプションまたはVMでDefender for Serversプランを有効にし、エンドポイント保護（MDEなど）が機能するようにします。
2. **Copy the EICAR string to a file**: EICARテスト文字列（無害なウイルス対策テスト用文字列）を含むテキストファイルを作成します。
3. **Run the file on the virtual machine**: 作成したファイルをVM上で保存または実行（読み込み）します。リアルタイム保護が有効であれば、ファイルがディスクに書き込まれた時点またはアクセスされた時点で検知され、アラートがトリガーされます。

質問#42 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションがあり、Windows Server を実行する仮想マシンが 100 台含まれています。  
  
これらの仮想マシンからイベントデータを収集するように Defender for Cloud を構成する必要があります。このソリューションでは、管理の手間とコストを最小限に抑える必要があります。  
  
実行すべきアクションは 2 つあります。正解はそれぞれソリューションの一部です。  
  
注: 正解は 1 つにつき 1 ポイントです。

- A. Defender for Cloud によって作成されたワークスペースから、データ収集レベルを「共通」に設定します。
- B. Microsoft Endpoint Manager 管理センターから、自動登録を有効にします。
- C. Azure ポータルから、Azure Event Grid サブスクリプションを作成します。
- D. Defender for Cloud によって作成されたワークスペースから、データ収集レベルをすべてのイベントに設定します。
- E. Azure ポータルの Defender for Cloud から、仮想マシンの自動プロビジョニングを有効にします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)   [議論   22](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)

**正解:** AE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
多数のVM (100台) からイベントデータを収集し、コストと管理の手間を抑える構成です。

1. **E. AzureポータルのDefender for Cloudから、仮想マシンの自動プロビジョニングを有効にします**: エージェント（Log AnalyticsエージェントまたはAMA）のインストールを自動化し、管理の手間を削減します。
2. **A. Defender for Cloudによって作成されたワークスペースから、データ収集レベルを「共通 (Common)」に設定します**: 「All events」はすべてのセキュリティイベントを収集するためデータ量が膨大になりコストがかかります。「Common」は監査に必要な標準的なイベントセットであり、コスト対効果の高い推奨設定です。

*コミュニティ投票の配分*

AE（80％）

BE（20％）

質問#43 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションがあり、User1 というユーザーがいます。User1  
  
が Microsoft Defender for Cloud のセキュリティポリシーを変更できるようにする必要があります。このソリューションでは、最小権限の原則を適用する必要があります。User1  
  
にはどのロールを割り当てる必要がありますか？

- A. セキュリティオペレーター
- B. セキュリティ管理者
- C. オーナー
- D. 貢献者

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
Defender for Cloudのセキュリティポリシーを変更できる最小特権のロールです。
**「セキュリティ管理者 (Security Admin)」**: セキュリティポリシーの表示と編集（更新）、アラートや推奨事項の管理が可能です。
「セキュリティ閲覧者 (Security Reader)」(A) は表示のみ。「所有者 (Owner)」(C) や「貢献者 (Contributor)」(D) も変更可能ですが、ポリシー管理以外の多くの権限（リソースの作成・削除など）を持つため、最小特権の原則に反します。

*コミュニティ投票の配分*

B（100％）

質問#44 トピック2

AzureサブスクリプションにUser1というユーザーがいます。User1に  
  
はAzure Active Directory Premium Plan 2のライセンスが割り当てられています。  
  
過去90日間にUser1のIDが侵害されたかどうかを特定する必要があります。  
  
どのようなツールを使用すればよいでしょうか？

- A. リスク検出レポート
- B. 危険なユーザーの報告
- C. アイデンティティセキュリティスコアの推奨事項
- D. 危険なサインインレポート

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)   [議論   45](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
過去90日間にIDが侵害されたかどうかを特定するツールです。
**「危険なユーザーの報告 (Risky users report)」**: このレポートは、リスクレベル（高/中/低）やリスクの状態（修復済み、無視など）を含む、リスクのあるユーザーの履歴を提供します。ユーザーが「侵害された (Compromised)」と判定された履歴を確認するのに適しています。
「リスク検出レポート (Risk detection report)」(A) も90日間のデータを提供しますが、こちらは個々のリスクイベント（「匿名のIPアドレスからのサインイン」など）のリストであり、ユーザー全体として侵害されたかどうかの判断には「危険なユーザー」レポートが集約的で適しています。

*コミュニティ投票の配分*

B（56％）

A（39％）

5%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/10/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 11 ページ目を表示しています。

410問中**101 - 110**問 目を表示
