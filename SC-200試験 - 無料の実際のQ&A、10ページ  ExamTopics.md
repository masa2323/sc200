---
title: "SC-200試験 - 無料の実際のQ&A、10ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/10/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#25 トピック2

ドラッグ＆ドロップ -  
Azure サブスクリプションをお持ちです。  
以下の要件を満たすには、権限を委任する必要があります。✑  
Azure Defender を有効化および無効化する。✑  
リソースにセキュリティ推奨事項を適用する。  
ソリューションでは、最小権限の原則を適用する必要があります。  
各要件には、どの Azure Security Center ロールを使用する必要がありますか？回答するには、適切なロールを正しい要件にドラッグしてください。各ロールは、1 回使用することも、複数回使用することも、まったく使用しないこともできます。コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
注: 正しい選択ごとに 1 ポイントが付与されます。  
選択して配置:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0008200001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)   [議論   44](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)

**正解:** ![](https://img.examtopics.com/sc-200/image416.png)

**解説:**
Azure Security Center (Defender for Cloud) の権限委任に関する設定です。

1. **Azure Defenderを有効化および無効化する**: **「Security Admin」** (またはOwner)。Security Adminはセキュリティポリシーの表示・更新、推奨事項やアラートの管理が可能です。Defenderプランの有効化はポリシー設定の一部とみなされます。
2. **リソースにセキュリティ推奨事項を適用する**: **「Contributor」** (またはOwner)。推奨事項の適用（「Fix」ボタンによる修復など）は、対象リソース（VMやストレージ等）自体の設定変更を伴うため、そのリソースに対する書き込み権限（Contributor以上）が必要です。Security Adminにはリソース変更権限はありません。

質問#26 トピック2

ホットスポット -  
Azure Defender を使用する Azure サブスクリプションを所有しています。Azure  
Security Center のワークフロー自動化を使用して、Azure Defender の脅威アラートに対応する予定です。  
脅威の修復を自動的に実行する Azure ポリシーを作成する必要があります。  
ソリューションには何を含めるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正しい選択ごとに 1 ポイントが加算されます。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0008300001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)

**Correct Answer:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0008400001.jpg) Reference:  

**解説:**
Azure Policyを使用して脅威の修復を自動化する設定です。

1. **Effect (効果)**: **「DeployIfNotExist」**。修復（Remediation）を自動的に行うポリシーを作成する場合、対象リソースが準拠していない（必要な設定や拡張機能がない）場合に、自動的にデプロイを実行する `DeployIfNotExist` 効果を使用します。
2. **Category (カテゴリ)**: **「Security Center」**。Defender for Cloud (Security Center) 関連のポリシー定義は、通常このカテゴリに分類されます。

<https://docs.microsoft.com/en-us/azure/governance/policy/concepts/effects> <https://docs.microsoft.com/en-us/azure/security-center/workflow-automation>

質問#27 トピック2

ホットスポット -  
  
オンプレミスのデータセンターに、App1 というカスタム Web アプリが含まれています。App1 は Active Directory ドメイン サービス (AD DS) 認証を使用しており、Microsoft Entra アプリケーション プロキシを使用してアクセスできます。Microsoft  
  
Defender XDR を使用する Microsoft 365 E5 サブスクリプションがあります。  
  
ユーザーが機密性の高いドキュメントをダウンロードしたというアラートを受け取りました。  
  
アラートに関連するリスクに対処するために、ユーザーが App1 を使用して「Highly Confidential」の機密ラベルが適用されたドキュメントのダウンロードを開始する際には、多要素認証 (MFA) を必須にする必要があります。  
  
どうすればよいでしょうか。回答するには、回答領域から適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image311.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image312.png)

**解説:**
オンプレミスアプリ（App Proxy経由）での機密ファイルダウンロード時にMFAを強制し、ダウンロードを制御するソリューションです。

1. **Conditional Access policy**: ユーザーがアプリにアクセスする条件（アプリ、ユーザー、場所など）に基づいてアクセスを制御します。ここで、**「Microsoft Defender for Cloud Appsの条件付きアクセスアプリ制御を使用する (Use Conditional Access App Control)」** を選択し、セッションをMDCA（Defender for Cloud Apps）にプロキシします。
2. **Session policy (in Defender for Cloud Apps)**: プロキシされたセッション内で、ユーザーのアクション（ダウンロード）を監視・制御します。**「Microsoft Defender for Cloud Appsのセッションポリシー」** を作成し、ファイルに「Highly Confidential」ラベルが付いている場合にダウンロードをブロックする（またはダウンロード時にMFAを要求する）設定を行います。

質問#28 トピック2

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Amazon  
Web Services (AWS) に Linux 仮想マシンがあります。Azure  
Defender をデプロイし、自動プロビジョニングを有効にしています。Azure  
Defender を使用して仮想マシンを監視する必要があります。  
解決策: Azure Arc を有効にし、仮想マシンを Azure Arc にオンボードします。  
これは目標を達成していますか?  

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)   [議論   42](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)

**Correct Answer:** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)  

**解説:**
AWS上のLinux VMをAzure Defender (Defender for Cloud) で監視するための適切な手順です。
**「Azure Arcを有効にし、仮想マシンをAzure Arcにオンボードする」**: これが正解です。非Azureサーバー（AWS, GCP, オンプレミス）をDefender for Cloudで保護・監視するための推奨される方法は、まずAzure Arc対応サーバーとして接続することです。これにより、Azure上のリソースとして扱われ、Defenderエージェント（Log AnalyticsエージェントやMDEなど）の自動プロビジョニングやポリシー管理が可能になります。

*Community vote distribution*

A (58%)

B (42%)

質問#29 トピック2

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Amazon  
Web Services (AWS) に Linux 仮想マシンがあります。Azure  
Defender をデプロイし、自動プロビジョニングを有効にしています。Azure  
Defender を使用して仮想マシンを監視する必要があります。  
解決策: 仮想マシンに Log Analytics エージェントを手動でインストールします。  
これは目標を達成していますか?  

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)   [議論   24](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)  

**解説:**
**「仮想マシンにLog Analyticsエージェントを手動でインストールする」**: これは目標を完全には達成しません（または推奨される最善策ではありません）。
単にログを収集するだけであれば可能ですが、Azure Defenderの統合的な監視機能（自動プロビジョニング、脆弱性管理、推奨事項の完全なサポートなど）をAWS上のVMで利用するには、**Azure Arc** を介して接続するのが現在の標準的な設計です。したがって、Q28のアプローチ（Arc有効化）が正解であり、手動インストールのみでは「いいえ」となります。

*Community vote distribution*

B (81%)

A (19%)

質問#30 トピック2

オンプレミスのLinuxサーバーが5台あります。Microsoft  
Defender for Cloudを使用するAzureサブスクリプションを所有しています。Linux  
サーバーを保護するには、Defender for Cloudを使用する必要があります。  
まずサーバーに何をインストールすればよいでしょうか？  

- A. 依存エージェント
- B. Log Analyticsエージェント
- C. Azure Connected Machine エージェント
- D. ゲスト構成拡張機能

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)   [議論   44](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)  

**解説:**
オンプレミスのLinuxサーバーをDefender for Cloudで保護するために最初にインストールすべきものは、**「Azure Connected Machineエージェント (Azure Connected Machine agent)」** です。
このエージェントをインストールすることで、サーバーはAzure Arcにオンボードされ、AzureリソースIDを持ちます。その後、Defender for CloudからLog Analyticsエージェントや他の拡張機能をデプロイして保護を有効化できます。

*Community vote distribution*

C (70%)

B (30%)

質問#31 トピック2

ドラッグ＆ドロップ -  
Azureサブスクリプションをお持ちです。このサブスクリプションには、Microsoft Defender for Cloudにオンボードされている仮想マシンが10台含まれています。Defender  
for Cloudが仮想マシン上でデジタル通貨マイニング行為を検出した場合、メール通知を受信するようにする必要があります。ソリューションはテストメールを生成する必要があります。3  
つのアクションのうち、どのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序で並べ替えてください。  
選択して配置：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0008700001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)   [議論   26](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)

**Correct Answer:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0008700002.jpg) Step 1: From Logic App Designer, create a logic app.  

**解説:**
デジタル通貨マイニングの検出時にメール通知を行う自動化フローの設定とテスト手順です。

1. **Logic App Designerから、ロジックアプリを作成する (From Logic App Designer, create a logic app)**: まず、アラート受信時にメールを送信するLogic Appを作成します。
2. **Logic App Designerから、トリガーを実行する (From Logic App Designer, run a trigger)**: 作成したLogic Appが正しく動作するか（テストメールが送信されるか）、手動でトリガーを実行してテストします。設問に「ソリューションはテストメールを生成する必要がある」とあるため、このテストステップが重要です。
3. **Defender for Cloudのワークフロー自動化から、ワークフロー自動化を追加する**: テスト済みのLogic Appを、特定のアラート（デジタル通貨マイニング）が発生した際に自動実行されるように、Defender for Cloudの設定で紐付けます。
Create a logic app and define when it should automatically run  
1\. From Defender for Cloud's sidebar, select Workflow automation.  
2\. To define a new workflow, click Add workflow automation. The options pane for your new automation opens.  
![](https://www.examtopics.com/assets/media/exam-media/04261/0008800001.png)  
Here you can enter:  
A name and description for the automation.  
The triggers that will initiate this automatic workflow. For example, you might want your Logic App to run when a security alert that contains "SQL" is generated.  
The Logic App that will run when your trigger conditions are met.  
3\. From the Actions section, select visit the Logic Apps page to begin the Logic App creation process.  
4\. Etc.  
Step 2: From Logic App Designer, run a trigger.  
  
Manually trigger a Logic App -  
You can also run Logic Apps manually when viewing any security alert or recommendation.  
Step 3: From Workflow automation in Defender for cloud, add a workflow automation.  
Configure workflow automation at scale using the supplied policies  
Automating your organization's monitoring and incident response processes can greatly improve the time it takes to investigate and mitigate security incidents.  
![](https://www.examtopics.com/assets/media/exam-media/04261/0008900001.png)  
Reference:  
<https://docs.microsoft.com/en-us/azure/defender-for-cloud/workflow-automation>

質問#32 トピック2

ドラッグ＆ドロップ -  
  
Microsoft Defender for Cloud が有効になっている Microsoft サブスクリプションをお持ちです。  
  
次の表に示す Azure ロジック アプリを構成します。  
  
![](https://img.examtopics.com/sc-200/image128.png)  
  
「不審なプロセスが実行されました」というアラートがトリガーされたときに実行される自動アクションを構成する必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。3  
  
つのアクションのうち、順番に実行する必要があるのはどれですか？ 回答するには、アクションの一覧から適切なアクションを回答領域に移動し、正しい順序で並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image129.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)   [議論   15](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image417.png)

**解説:**
「不審なプロセス」アラートに対する修復アクションの自動化設定順序です。

1. **Create a logic app that has an HTTP trigger (HTTPトリガーを持つロジックアプリを作成する)**: 自動化の本体となるLogic Appを作成します。Defender for Cloudからの呼び出しを受け取るため、通常はDefenderコネクタのトリガーを使用しますが、選択肢にある中ではHTTPトリガー（Webhook的な呼び出し）が最も汎用的、あるいは特定のテンプレート構成を指しています。
2. **Create a workflow automation (ワークフロー自動化を作成する)**: Defender for Cloud上で、特定のアラート条件とLogic Appを紐付ける設定を行います。
3. **Select the Suspicious process executed alert (「不審なプロセスが実行されました」アラートを選択する)**: ワークフロー自動化のトリガー条件として、対象のアラートタイプを指定します。

質問#33 トピック2

Microsoft Defender for Cloud が有効になっている Azure サブスクリプションをお持ちです。Windows  
  
Server 2022 を実行し、Amazon Web Services (AWS) でホストされている Server1 という仮想マシンがあります。Defender  
  
for Cloud を使用して Server1 のログを収集し、脆弱性を解決する必要があります。Server1  
  
に最初にインストールすべきものは何ですか？

- A. Microsoft 監視エージェント
- B. Azure Monitorエージェント
- C. Azure Arcエージェント
- D. Azure Pipelinesエージェント

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)   [議論   25](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)  

**解説:**
AWS上のWindows Server 2022からログを収集し、脆弱性を解決するための最初のステップです。
**「Azure Arcエージェント (Azure Arc agent)」** (正しくはAzure Connected Machine agentですが、選択肢ではこれに相当) を最初にインストールします。これにより、AWS上のサーバーがAzureの管理下に置かれ（Arc対応サーバー）、その後のログ収集エージェント（AMA/MMA）の配布や脆弱性スキャン機能の適用が可能になります。

*Community vote distribution*

C (81%)

Other

質問#34 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションがあり、storage1 というストレージ アカウントが含まれています。storage1  
  
内の BLOB に対して、異常に多くの削除操作が発生したというアラートを受け取りました。  
  
どの BLOB が削除されたのかを特定する必要があります。  
  
確認すべき点は何でしょうか。

- A. ストレージ1のアクティビティログ
- B. Azure Storage Analytics ログ
- C. アラートの詳細
- D. アラートの関連エンティティ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)   [議論   27](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)  

**解説:**
Blobが削除されたことを特定し、誰がいつ削除したかなどの詳細を確認するにはログが必要です。
**「Azure Storage Analytics logs」** (またはAzure MonitorのStorage logs) を確認する必要があります。アクティビティログ (A) には、ストレージアカウントの作成やキーの変更などの管理操作（コントロールプレーン）のみが記録され、Blobの読み書き・削除といったデータプレーンの操作は記録されません。
アラートの詳細 (C) や関連エンティティ (D) も手がかりにはなりますが、具体的な操作ログ（どのBlobが削除されたか）を直接確認する一次情報源はストレージログです。

*Community vote distribution*

B (52%)

D (27%)

A (15%)

6%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/9/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 10 ページ目を表示しています。

410問中**91 - 100**問 を表示
