---
title: "SC-200試験 - 無料の実際のQ&A、25ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/25/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問6 トピック4

次の表に示すリソースがあります。Microsoft  
  
![](https://img.examtopics.com/sc-200/image265.png)  
  
Defender for Cloud を使用する Azure サブスクリプションがあります。VM1  
  
と Server1 を保護するには、Defender for Cloud を使用する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• Advanced Threat Protection と脆弱性評価をサポートする。  
• 各 SQL Server 2022 インスタンスを SQL 仮想マシンとして登録する。  
• 実装と管理の手間を最小限に抑える。  
  
各サーバーに何を展開すればよいでしょうか。回答するには、回答領域から適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image266.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)

**正解:** ![](https://img.examtopics.com/sc-200/image267.png)

**解説:**
この問題のポイントは、**SQL Server 2022** の新機能と、管理の手間を最小限に抑えつつ「SQL 仮想マシン」として登録するという要件にあります。

1. SQL 仮想マシンとしての登録と保護

- **VM1 (Azure VM):** Azure 上の SQL Server を「SQL 仮想マシン」として登録し、脆弱性評価や Advanced Threat Protection を有効にするには、**SQL IaaS Agent 拡張機能**（SQL IaaS Agent extension）をインストールします。これは「Azure 仮想マシン拡張機能」の一種です。
    
- **Server1 (Azure Arc 対応サーバー):** Azure Arc にオンボード済みのオンプレミスサーバー上の SQL Server 2022 を管理・保護するには、**SQL Server 用 Azure 拡張機能**（Azure extension for SQL Server）を使用します。これも Azure Arc を通じてデプロイされる「Azure 仮想マシン拡張機能」です。
    

2. 「最小限の手間」とエージェントの選択

- 以前のバージョンでは Log Analytics エージェントが必要でしたが、SQL Server 2022 以降、および最新の Microsoft Defender for SQL では、**拡張機能のみ**で登録、脆弱性評価、および Advanced Threat Protection の主要機能をサポートできるようになっています。
    
- **Azure Monitor Agent (AMA)** や **Log Analytics エージェント** を追加で導入・管理することは、今回の要件である「実装と管理の手間を最小限に抑える」に反するため、拡張機能のみを選択するのが正解となります。
3. 補足

- **Advanced Threat Protection:** 拡張機能を通じて、SQL インジェクションや異常なアクセスなどの脅威を検知します。
    
- **脆弱性評価:** データベースのセキュリティ設定をスキャンし、推奨される修正策を提示します。これらも拡張機能によって構成可能です。は、VM1/Server1ともに「Defender for Servers Plan 2」を指していると考えられます。

質問7 トピック4

Microsoft Sentinel ワークスペースに、Workbook1 というカスタム ワークブックが含まれています。SecurityEvent テーブルに基づいてビジュアルを作成する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• 過去 1 週間に取り込まれたセキュリティ イベントの数を特定する。  
• 日別のイベント数をタイムチャートで表示する。

Workbook1  には何を追加すればよいでしょうか。

- A. ク​​エリ
- B. 指標
- C. グループ
- D. リンクまたはタブ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)  

**解説:**
ワークブックで過去1週間のイベント数の推移を表示するために追加すべき要素です。
**「Query (クエリ)」**: ワークブックの核となる要素です。KQLクエリ（`SecurityEvent | summarize count() by bin(TimeGenerated, 1d)` など）を記述し、その結果を「Time chart」として可視化するように設定します。チャート表示の設定自体もクエリパーツの一部（Visualization設定）で行います。


質問8 トピック4
  
50台の仮想マシンを含むAzureサブスクリプションを所有しています。Microsoft Defender for Cloudを展開する予定です。40 台の仮想マシンに対してエージェントレススキャンを有効にする必要があります。ソリューションでは、仮想マシンのディスクスナップショットを作成し、スナップショットの帯域外分析を実行する必要があります。  
  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image268.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)

**正解:** ![](https://img.examtopics.com/sc-200/image269.png)

**解説:**
40台のVMに対してエージェントレススキャン（ディスクスナップショット分析）を有効にする手順です。

1. **Turn on**: **「Defender Cloud Security Posture Management (CSPM)」**。エージェントレススキャン機能は、Defender CSPMプランの主要機能です（またはDefender for Servers Plan 2でも利用可能ですが、CSPMの文脈で語られることが多いです）。
2. **Turn off**: **「Agentless scanning for machines for the 10 virtual machines」**。質問の意図は「40台に対してのみ有効にする」ことです。全体設定でエージェントレススキャンを有効にしつつ、「除外タグ（Exclusion tags）」などを使用して、スキャンしたくない10台を除外構成にする（またはその逆）必要があります。設定画面では「特定のマシンを除外」するオプションがあります。

質問9 トピック4

Azureサブスクリプションをお持ちです。Microsoft Graphのアクティビティログをサードパーティのセキュリティ情報イベント管理（SIEM）ツールにストリーミングする必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。  
  
ログはどこにストリーミングすればよいでしょうか？

- A. Azure Event Hubs 名前空間
- B. Azureストレージアカウント
- C. Azure Event Grid 名前空間
- D. Log Analytics ワークスペース

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)  

**解説:**
Microsoft GraphアクティビティログをサードパーティSIEMにストリーミングする方法です。
**「Azure Event Hubs namespace」**: Azure Monitorの診断設定（Diagnostic settings）を使用してログをエクスポートする際、サードパーティSIEM（Splunk, QRadarなど）への転送には通常 **Event Hubs** が仲介役として使用されます。Log AnalyticsはAzure内での分析用、Storage Accountはアーカイブ用です。

質問10 トピック4
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションがあり、User1 と User2 という 2 人のユーザーが登録されています。  
  
ユーザーが Microsoft Purview ポータルを使用して検索を実行できるようにする必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• User1 が Microsoft Purview Audit サービスのログを検索し、Microsoft Purview Audit サービスの構成を確認できることを確認します。  
• User2 が Microsoft Exchange Online メールボックスを検索できることを確認します。  
• 最小権限の原則に従います。  
  
各ユーザーをどの Microsoft Purview 役割グループに追加する必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image290.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)

**正解:** ![](https://img.examtopics.com/sc-200/image291.png)

**解説:**
#### User1: Microsoft Purview Audit の検索と構成の確認

- **Audit Reader (監査閲覧者):** この役割グループのメンバーは、Microsoft Purview ポータルで監査ログの検索と表示を行うことができます。また、監査ログの保持ポリシーなどの構成を確認（表示）することも可能です。
    
- **最小権限の原則:** `Security Reader` や `Global Reader` も情報の参照は可能ですが、監査サービスに特化した `Audit Reader` を使用するのが最も権限を限定できるため適切です。
    

#### User2: Microsoft Exchange Online メールボックスの検索

- **Data Investigator (データ調査員):** この役割グループは、組織内のコンテンツ（メールボックス、SharePoint、OneDrive など）を検索し、コンテンツのプレビューやエクスポートを行う権限を持っています。eDiscovery（電子証拠開示）やコンテンツ検索を実行するために必要な役割が含まれています。
    
- **他のオプションとの比較:**
    
    - `Communication Compliance Investigators`: ポリシーによってフラグが立てられた通信のレビューに限定されます。
        
    - `Insider Risk Management Investigators`: 内部リスクのケースに関連するアクティビティの調査に限定されます。
        
    - `Privacy Management Investigators`: プライバシーリスク（Priva）の管理に特化しています。
        
    - メールボックス全体の自由な検索を行うには、`Data Investigator`（または eDiscovery Manager）が必要です。

質問11 トピック4

Microsoft 365 サブスクリプションをご利用で、Microsoft Defender for Endpoint プラン 2 を使用し、500 台の Windows デバイスを保有しています。  
  
インシデント調査の一環として、以下のマルウェアの疑いのあるファイルを特定しました。  
  
• sys  
• pdf  
• docx  
• xlsx  
  
ユーザーがこれらのファイルをデバイスにダウンロードするのをブロックするために、インジケーターハッシュを作成する必要があります。  
  
インジケーターハッシュを使用してブロックできるファイルはどれですか？

- A. File1.sysのみ
- B. File1.sysとFile3.docxのみ
- C. File1.sys、File3.docx、およびFile4.xlsxのみ
- D. File2.pdf、File3.docx、File4.xlsxのみ
- E. File1.sys、File2.pdf、File3.docx、およびFile4.xlsx

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)   [議論   28](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)  

**解説:**
インジケーターハッシュ（ファイルハッシュのブロック）機能でブロック可能なファイルの種類です。
**「File1.sys only」**: **PEファイル（Portable Executable: .exe, .dll, .sys など）** のみがハッシュによるブロック対象として公式にサポートされています（以前のドキュメントに基づく）。PDFやOfficeドキュメント（docx, xlsx）は、振る舞い検知やSafe Documentsの対象ですが、MDEの「インジケーター」機能でのハッシュブロックの主要対象は実行可能ファイルコードです。
※ただし、最新のMDEでは証明書インジケーターなどでカバー範囲が広がっていますが、試験的には「実行可能ファイル(PE)のみ」という制約が問われることが多いです。

質問12 トピック4

Microsoft Defender for Endpoint を使用する Microsoft 365 サブスクリプションがあり、User1 というユーザーと Group1 という Microsoft 365 グループが含まれています。すべてのユーザーに Defender for Endpoint Plan 1 ライセンスが割り当てられています。  
  
エンドポイントと脆弱性管理に対して、Microsoft Defender XDR 統合ロールベース アクセス制御 (RBAC) を有効にします。User1 が Group1 にメール通知を送信するアラートを構成できるようにする必要があります。このソリューションは、最小権限の原則に従う必要があります。User1 にはどのような権限を割り当てる必要がありますか？

- A. Defenderの脆弱性管理 - 修復処理
- B. アラート調査
- C. ライブレスポンス機能: 基本
- D. セキュリティ設定を管理する

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)  

**解説:**
Group1（メール受信者）へのメール通知設定を行うために必要な最小権限です。
**「Manage security settings (セキュリティ設定を管理する)」**: Defender for Endpointの設定（通知設定含む）を変更するには、セキュリティ設定の管理権限が必要です。「Alert investigation」や「Remediation actions」はオペレーション権限であり、システム設定（通知ルール）の変更権限ではありません。

質問13 トピック4

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。Azure Resource Manager (ARM) テンプレートを使用して、Microsoft Defender for Cloud が特定のアラートを受信したときにロジック アプリをトリガーするワークフロー自動化を作成する必要があります。  
  
テンプレートはどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image292.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)

**正解:** ![](https://img.examtopics.com/sc-200/image293.png)

**解説:**
ARMテンプレートを使用してDefender for Cloudのワークフロー自動化（Workflow Automation）を作成する際の設定値です。

1. **"type":**: **"Microsoft.Security/automations"**。ワークフロー自動化のリソースタイプです。
2. **"actions":**: **"Microsoft.Logic/workflows"**。トリガーされたときに実行するアクションの種類を指定します。ロジックアプリを呼び出す場合は "LogicApp" です。

質問14 トピック4

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある固有の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
  
Defender XDR を使用する Azure サブスクリプションがあります。Microsoft  
  
Defender ポータルから監査検索を実行し、その結果を 10,000 行を含む File1.csv というファイルとしてエクスポートします。Microsoft  
  
Excel を使用してデータの取得と変換操作を実行し、File1.csv の AuditData 列を解析します。この操作では、特定の JSON プロパティの列を生成できません。Excel  
  
が監査検索結果で特定の JSON プロパティの列を生成するようにする必要があります。  
  
解決策: Excel から、File1.csv の既存の列にフィルターを適用して JSON プロパティの数を減らし、データの取得と変換操作を実行して AuditData 列を解析します。  
  
これは要件を満たしていますか?

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)  

**解説:**
Excelでの監査ログ（AuditData列のJSON）解析に関する問題です。
ExcelのPower Query（データの取得と変換）機能でJSONを解析しようとして列生成に失敗する場合、単純に列にフィルターをかけても、元のJSON構造の複雑さが解決しない限り問題は解決しません。特に「JSONプロパティの数を減らすフィルター」という操作は、インポート前のCSVに対して行うのは困難です。正解の **B (いいえ)** は、この手順だけでは解決しない、またはより適切なJSON変換機能（Power QueryのJSON解析機能の正しい使用）が必要であることを示唆しています。

質問15 トピック4

Microsoft 365 E5 サブスクリプションがあり、User1 と User2 という 2 人のユーザーが Microsoft Copilot for Security を使用しています。Copilot for Security ポータルから、User1 がセッションを開始し、以下のプロンプトを作成します。  
  
• プロンプト 1: Entra プラグインへのアクセスを提供します  。
• プロンプト 2: Intune プラグインへのアクセスを提供します。  
• プロンプト 3: Entra プラグインへのアクセスを提供します  
  
。User1 は User2 とセッションを共有します。User2 は Microsoft Intune にアクセスできません。  
  
共有セッション中、User2 はどのプロンプトの結果を表示できますか？

- A. プロンプト1のみ
- B. プロンプト1とプロンプト2のみ
- C. Prompt3のみ
- D. プロンプト1とプロンプト3のみ
- E. プロンプト1、プロンプト2、およびプロンプト3

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)

**正解：** E [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/25/#)  

**解説:**
Copilot for Securityの共有セッションにおける可視性の問題です。
User1（権限あり）がセッションを作成し、User2（権限なし：Intuneアクセス権限なし）に共有しました。
共有セッションでは、**プロンプトの結果（回答）は、そのセッション内ですでに生成されたテキストとしてUser2にも表示されます**。User2が自分で新たにIntuneデータを取得するアクションを実行しようとすると権限エラーになりますが、User1が既に実行して生成した回答（結果）を見ることは可能です。したがって、User1が実行したすべてのプロンプトの結果（1, 2, 3）が表示されます。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/24/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 25 ページを表示しています。

410問中**241 - 250**問 を表示
