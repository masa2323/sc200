---
title: "SC-200試験 - 無料の実際のQ&A、38ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/38/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#21 トピック7

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft Copilot for Security をご利用です。Copilot  
  
for Security ワークスペースでは、以下のプラグインを使用しています。  
  
• Microsoft Entra  
• Microsoft Defender XDR  
  
Microsoft Defender ポータルから、Copilot for Security を使用して、報告されたインシデントを調査します。  
  
調査に Microsoft Entra ID Protection の情報を含めるプロンプトブックを実行する必要があります。  
  
まず何をすべきでしょうか？

- A. Microsoft Defender ポータルからインシデント レポートを作成します。
- B. Copilot for Security スタンドアロン エクスペリエンスで調査を開きます。
- C. Microsoft Sentinel で調査を開きます。
- D. Microsoft Defender ポータルから、高度な検索クエリを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)  

**解説:**
Copilot for SecurityでEntra ID Protectionの情報を含むPromptbookを実行する方法。
DefenderポータルのCopilot統合（Embedded experience）では、利用可能な機能やプラグインがコンテキストに限定される場合があります（Defenderプラグインが主）。
**「Open the investigation in the Copilot for Security standalone experience」**。
Entra ID Protectionプラグインを含む包括的な調査や、カスタムPromptbookの実行は、スタンドアロンポータル（security.microsoft.com/copilot ではなく copilot.security.microsoft.com）で行うのが最も確実です。特に「Entra ID Protection情報を含めるPromptbook」がカスタムのものである場合、スタンドアロンエクスペリエンスの方が柔軟性があります。
Defenderポータル内でもCopilotは使えますが、クロスプロダクト（Entra ID Protectionなど）の広範なデータを含むPromptbookを実行するには、スタンドアロンエクスペリエンスに切り替える（Open in standalone）のが標準的なフローです。

*コミュニティ投票の配分*

B（100％）

質問#22 トピック7

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft Copilot for Security を使用しています。Copilot  
  
for Security セッションを開始し、それぞれに応答を求める 5 つのプロンプトを入力します。  
  
プロンプトは使用しますが、応答は含めないプロンプトブックを作成する必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。  
  
どうすればよいでしょうか？

- A. 各プロンプトを選択し、\[プロンプトブックの作成\] を選択します。
- B. 新しいプロンプトブックを作成し、各プロンプトを含めます。
- C. 次の入力を持つ新しいプロンプトを入力します: セッションプロンプトからプロンプトブックを作成します。
- D. セッションを共有し、\[プロンプトブックの作成\] を選択します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)  

*コミュニティ投票の配分*

A（75％）

D（25％）

質問#23 トピック7

オンプレミスの Windows 11 Pro デバイスが 1,000 台あり、Microsoft Defender for Endpoint にオンボードされています。Microsoft  
  
Defender XDR を使用する Microsoft 365 サブスクリプションを所有しています。  
  
攻撃者がデバイス上で以下の操作を実行したことが判明しました。  
  
• レジストリベースのウイルス対策除外のファイルシステム パスを変更した  
• 悪意のあるファイルをファイルシステム パスにダウンロードした  
  
デバイスでライブ応答セッションを開始しました。  
  
レジストリの変更を元に戻す必要があります。  
  
どのコマンドを実行すればよいでしょうか？

- A. 修復する
- B. レジストリ
- C. スキャン
- D. 分析する

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)  

*コミュニティ投票の配分*

A（85％）

B（15％）

質問#24 トピック7

オンプレミス ネットワークには、contoso.com と fabrikam.com という 2 つの Active Directory ドメイン サービス (AD DS) ドメインが含まれています。Contoso.com には Group1 というグループが含まれています。Fabrikam.com には Group2 というグループが含まれています。WS1  
  
という Microsoft Sentinel ワークスペースがあり、そこには Rule1 というスケジュールされたクエリ ルールが含まれています。Rule1 は、異常な AD DS セキュリティ イベントに応答してアラートを生成します。各アラートはインシデントを作成します。  
  
次の要件を満たすインシデント トリアージ ソリューションを実装する必要があります。  
  
• contoso.com からのセキュリティ インシデントは Group1 に割り当てる必要があります。  
• fabrikam.com からのセキュリティ インシデントは Group2 に割り当てる必要があります。  
• 管理作業を最小限に抑える必要があります。  
  
このソリューションには何を含める必要がありますか。

- A. インシデントの作成によってトリガーされるプレイブック
- B. アラートの作成によってトリガーされるプレイブック
- C. ルール1に割り当てられた1つの自動化ルール
- D. ルール1に割り当てられた2つの自動化ルール

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)  

**解説:**
ドメイン（contoso.com vs fabrikam.com）に基づいてインシデントの所有者グループを割り当てるトリアージソリューション。
管理作業を最小限にする。
**「Two automation rules assigned to Rule1」**。
オートメーションルール（Automation rules）は、インシデント作成時に条件に基づいてアクション（所有者の割り当て、タグ付けなど）を自動実行します。

1. **Automation Rule A**:
   - Condition: `Domain` contain `contoso.com` (またはEntity条件)
   - Action: Assign to `Group1`
2. **Automation Rule B**:
   - Condition: `Domain` contain `fabrikam.com`
   - Action: Assign to `Group2`
これらをスケジュールされたルール（Rule1）に関連付けます。Automation ruleはインシデントトリガーで動作し、Playbook（Logic Apps）よりも軽量でコストがかからず、設定も簡単（Sentinel内だけで完結）です。管理作業・コストの観点でPlaybookよりAutomation ruleが推奨されます。
※「1つのルールで分岐」も可能かもしれませんが（If-else的な）、Automation rulesは条件ごとに作成するのが基本です。したがって「2つのオートメーションルール」を作成し、それぞれに条件を設定するのが正解です。

*コミュニティ投票の配分*

D（60％）

C（40％）

質問#25 トピック7

Microsoft 365 サブスクリプションをお持ちです。  
  
以下の KQL クエリがあります。  
  
![](https://img.examtopics.com/sc-200/image339.png)  
  
このクエリを使用して Microsoft Defender XDR カスタム検出ルールを作成できることを確認する必要があります。  
  
クエリに何を追加すればよいでしょうか？

- A. | 集計 (タイムスタンプ、レポート ID) = arg\_max (タイムスタンプ、レポート ID)、デバイス ID による count()
- B. | 集計 (ReportId) = make\_set(ReportId)、デバイスIDによるcount()
- C. | 集計 (Timestamp, DeviceName)=arg\_min(Timestamp, DeviceName)、DeviceId による count()
- D. | 集計 (タイムスタンプ) = 範囲 (タイムスタンプ)、デバイス ID による count()

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)  

*コミュニティ投票の配分*

A（100％）

質問#26 トピック7

HOTSPOT  
\-  
  
Microsoft Defender for Office 365 を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
検出はされたものの、配信後にメールボックスから正常に削除されなかった、潜在的に悪意のあるメールに関するイベントを一覧表示するハンティングクエリを作成する必要があります。このソリューションでは、イベントがメール受信者のサインインイベントと相関関係にあることを確認する必要があります。  
  
クエリはどのように完成させるべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正しい選択肢は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image355.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)

**正解:** ![](https://img.examtopics.com/sc-200/image356.png)

**解説:**
Defender for Office 365のイベント（ZAP失敗など）とユーザーサインインを相関させるKQL。

1. **Event table**: **`EmailPostDeliveryEvents`**。配信後（Post Delivery）のイベント、例えばZAP（Zero-hour Auto Purge）の成功・失敗などはこのテーブルに記録されます。
2. **Filter**: **`where ActionType == 'ZAP' and ActionResult == 'Error'`**（またはNotDeleted）。削除されなかった（Failed to delete）イベントを探します。
3. **Join**: **`join SignInLogs`**。サインインログと結合します。
4. **Join condition**: **`on $left.RecipientEmailAddress == $right.UserPrincipalName`**（またはAccount）。メールの受信者アドレスとサインインユーザーのUPNで結合します。
正解画像（image356）では、**`EmailPostDeliveryEvents`**、**`join SignInLogs`**、**`on $left.RecipientEmailAddress == $right.UserPrincipalName`** が選択されています。

質問#27 トピック7

HOTSPOT  
\-  
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションを所有しています。Device1  
  
というデバイス上で、File1.exe というファイルによって開始された悪意のあるプロセスを発見しました。File1.exe  
  
がいつ作成されたかを特定する KQL クエリを作成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• FileName、InitiatingProcessFileName、および InitiatingProcessCommandLine 列を返す。  
• 返されるデータの量を最小限に抑える。  
  
クエリはどのように完成させるべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image401.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)

**正解:** ![](https://img.examtopics.com/sc-200/image402.png)

**解説:**
File1.exe（親プロセス）が「いつ作成されたか」を特定しつつ、関連するプロセス情報も取得するKQL。

1. **Table**: **`DeviceProcessEvents`**。プロセスの作成イベント。
2. **Filter**: **`where InitiatingProcessFileName == 'File1.exe'`**。File1.exeによって開始されたプロセスを探します。
3. **Join**: **`join kind=inner (DeviceFileEvents | ...)`**。File1.exeの作成日時を知るために、ファイル作成イベント（DeviceFileEvents）と結合します。
4. **Join query**: `DeviceFileEvents | where FileName == 'File1.exe' | project FileName, DeviceId, FileCreationTime=Timestamp`
5. **On**: `on DeviceId, $left.InitiatingProcessFileName == $right.FileName`。
正解画像（image402）では、**`DeviceProcessEvents`** からスタートし、**`join DeviceFileEvents`** を行い、必要な列（FileName, InitiatingProcess...）を射影しています。
File1.exeの作成日時（Timestamp）を取得するには `DeviceFileEvents` が必要です。

質問#28 トピック7

ドラッグ＆ドロップ  
\-  
  
Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。Microsoft  
  
Entra ID 監査ログ用のワークブックを作成してカスタマイズする必要があります。  
  
どの 3 つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答領域に移動し、正しい順序に並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image403.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)

**正解:** ![](https://img.examtopics.com/sc-200/image404.png)

**解説:**
SentinelでEntra ID監査ログ用のワークブックを作成する手順。

1. **Connect the Microsoft Entra ID connector**: まず、Entra IDのログをSentinelに取り込むためにコネクタを接続・設定します。
2. **Enable the AuditLogs and SignInLogs**: コネクタの設定で、監査ログとサインインログの取り込みを有効にします。
3. **Add the Microsoft Entra Audit workbook to the workspace**: コンテンツハブまたはテンプレートギャラリーから、標準の「Microsoft Entra Audit」ワークブックテンプレートをインストール（追加）し、ワークスペースに保存します。その後カスタマイズします。
※データを取り込まないとワークブックは空です。テンプレートを追加する前にコネクタ設定が必要です。

質問#29 トピック7

HOTSPOT  
\-  
  
Sub1 という Azure サブスクリプションがあり、そこには WS1 という Microsoft Sentinel ワークスペースが含まれています。WS1  
  
に、以下の要件を満たすハンティング クエリを作成する必要があります。  
  
• 7 日間に各 Microsoft Entra セキュリティ プリンシパルによって毎日実行された変更の数を返す  
• Sub1 内のリソースへの成功した変更をすべて特定する  
• 不足しているデータ ポイントを 0 に置き換える  
  
KQL クエリをどのように完成させるべきですか？ 回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択肢は 1 つにつき 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image405.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)

**正解:** ![](https://img.examtopics.com/sc-200/image406.png)

**解説:**
Entra IDの変更履歴を時系列（7日間、日別）で可視化するハンティングクエリ。欠損値を0埋めする。

1. **Source**: **`AuditLogs`**。Entra IDの変更操作ログ。
2. **Time range**: `where TimeGenerated > ago(7d)`。
3. **Summarize**: **`summarize count() by InitiatedBy.user.userPrincipalName, bin(TimeGenerated, 1d)`**。ユーザーごと、1日ごとの件数を集計。
4. **Fill gaps**: **`make-series count() default=0 ...`**。
   `make-series` 演算子は、時系列データの欠損部分をデフォルト値（0）で埋める機能を提供します。`summarize` の代わりにこれを使います。
   正解画像（image406）では **`make-series`** を使用しています。
   Query: `AuditLogs | make-series DailyChanges = count() default=0 on TimeGenerated in range(ago(7d), now(), 1d) by InitiatedBy.user.userPrincipalName`

質問#30 トピック7

HOTSPOT  
\-  
  
次のKQLクエリを含むMicrosoft Sentinelワークブックがあります。  
  
![](https://img.examtopics.com/sc-200/image407.png)  
  
返された値に基づいてerrCount列の色を変更するビジュアルを作成する必要があります。  
  
ビジュアルはどのように設定すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image408.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)

**正解:** ![](https://img.examtopics.com/sc-200/image409.png)

**解説:**
Sentinelワークブックで、クエリ結果の値（errCount）に基づいて列の色を変更するビジュアル設定。

1. **Visualization**: **`Grid`**。テーブル形式（グリッド）で表示し、列の設定を行います。
2. **Column settings**: `errCount` 列の設定を開きます。
3. **Column renderer**: **`Thresholds`**（しきい値）。値の範囲に基づいて色（赤、黄、緑など）を変えるには「Thresholds」レンダラーを使用します。「Heatmap」も色を使いますが、特定の値の範囲でアイコンや色を変えるならThresholdsが一般的です。
   正解画像では **`Thresholds`** が選択されています。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/37/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 38 ページを表示しています。

410問中**371 - 380**問 を表示
