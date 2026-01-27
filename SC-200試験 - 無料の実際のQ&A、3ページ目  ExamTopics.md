---
title: "SC-200試験 - 無料の実際のQ&A、3ページ目 | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/3/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#21 トピック1

Microsoft Cloud App Security を構成しています。  
会社の米国拠点の IP アドレス範囲に基づいたカスタム脅威検出ポリシーがあります。  
危険な IP アドレスからのあり得ない移動やサインインに関するアラートが多数届きます。  
アラートの 99% は、本社からの正当なサインインであると判断しました。  
既知の場所からの正当なサインインに関するアラートをブロックする必要があります。  
実行すべきアクションは 2 つあります。正解はそれぞれ、解決策の一部を示しています。  
注: 正解は 1 つにつき 1 ポイントです。  

- A. 自動データ拡充を構成します。
- B. IP アドレスを企業アドレス範囲カテゴリに追加します。
- C. あり得ない移動の異常検出ポリシーの感度レベルを上げます。
- D. IP アドレスを他のアドレス範囲カテゴリに追加し、タグを追加します。
- E. IP アドレスを除外するアクティビティ ポリシーを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)   [議論   61](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)

**正解：** AB [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)  

**解説:**
誤検知（False Positive）を減らし、正当な「あり得ない移動（Impossible Travel）」アラートを抑制するためには、以下の2つのアクションが有効です。

- **B. IPアドレスを企業アドレス範囲カテゴリに追加する**: 本社のIPアドレスを「企業（Corporate）」IPアドレス範囲として登録することで、信頼できる場所とみなされます。
- **A. 自動データ拡充（Automatic data enrichment）を構成する**: これにより、エンリッチメントデータ（IPアドレスの所有者情報など）を利用して、正当なVPNやプロキシからのアクセスを識別しやすくなります。（※ただし、最も直接的な解決策は企業IPの登録です。選択肢によっては、企業IPの登録とセットで「そのIPからのアラートを除外するポリシー設定」などが正解になることもありますが、ここではABが推奨されています。）

*コミュニティ投票の配分*

AB（82％）

他の

質問#22 トピック1

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
Defender for Identity と Active Directory の統合を構成しています。Microsoft  
Defender for Identity ポータルから、攻撃者が悪用できる複数のアカウントを構成する必要があります。  
解決策: 各アカウントを機密アカウントとして追加します。  
これで目標は達成されますか?  

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)   [議論   17](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)  

**解説:**
攻撃者が悪用するための「おとりアカウント」は **ハニートークンアカウント (Honeytoken account)** と呼ばれます。
解決策として提案されている「機密アカウント (Sensitive account) として追加する」という操作は、管理者などの高特権アカウントを保護・監視強化するためのものであり、ハニートークンとしての機能（おとりとしての検知機能）とは異なります。したがって、この解決策は間違いです。
ハニートークンを設定するには、Defender for Identity (Microsoft 365 Defender) の設定画面で、対象アカウントに「Honeytoken」タグを付与する必要があります。

*コミュニティ投票の配分*

B（92％）

8%

質問#23 トピック1

Microsoft Exchange Online と Microsoft Defender for Office 365 を使用する Microsoft 365 テナントがあります。  
ゼロ時間自動削除 (ZAP) によって電子メール メッセージがユーザーのメールボックスから移動されたかどうかを確認するには、何を使用すればよいですか。  

- A. Microsoft Defender for Office 365 の脅威保護ステータスレポート
- B. Exchangeのメールボックス監査ログ
- C. Microsoft Defender for Office 365 の安全な添付ファイルのファイルの種類レポート
- D. Exchangeのメールフローレポート

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)   [議論   20](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)

**Correct Answer:** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)  

**解説:**
ゼロ時間自動削除（ZAP: Zero-hour Auto Purge）によってメールが移動または削除されたかどうかを確認するには、**「脅威保護ステータスレポート (Threat protection status report)」** を使用します。
このレポートでは、検出された脅威の種類や、ZAPによってメールが配信後に削除された件数などを確認できます。Exchangeの監査ログにはZAPのアクションはシステムイベントとして記録されない場合があり、専用のレポートが最適です。

*Community vote distribution*

A (82%)

B (18%)

質問#24 トピック1

Microsoft 365 サブスクリプションをご利用で、1,000台の Windows 10 デバイスが含まれています。これらのデバイスには Microsoft Office 365 がインストールされています。  
以下のデバイス脅威を軽減する必要があります。✑  
信頼できない Web サイトからスクリプトをダウンロードする Microsoft Excel マクロ ✑  
Microsoft Outlook で実行可能添付ファイルを開くユーザー  
✑ Outlook のルールとフォームの脆弱性  
どのような対策を講じるべきでしょうか？  

- A. Microsoft Defender ウイルス対策
- B. Microsoft Defender for Endpoint の攻撃面の縮小ルール
- C. Windows Defender ファイアウォール
- D. Azure Defender の適応型アプリケーション制御

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)  

**解説:**
Excelマクロによるスクリプトのダウンロードや、Outlookでの実行可能添付ファイルの実行など、アプリの特定の危険な動作をブロックするには、**「攻撃面の縮小 (Attack Surface Reduction: ASR) ルール」** が最適です。
ASRルールには以下のような特定のルールが含まれており、要件を直接満たします：

- Office アプリケーションによる子プロセスの作成をブロックする
- Office マクロが Win32 API を呼び出すのをブロックする
- Office アプリケーションから実行可能コンテンツを作成することをブロックする
Azure Defenderの適応型アプリケーション制御は、許可されたアプリのリストを作成するもので、マクロの詳細な挙動制御とは異なります。

*Community vote distribution*

B (100%)

質問#25 トピック1

サードパーティ製のセキュリティ情報イベント管理（SIEM）ソリューションをご利用中です。SIEM  
ソリューションが Azure Active Directory (Azure AD) の署名イベントに関するアラートをほぼリアルタイムで生成できるようにする必要があります。  
イベントを SIEM ソリューションにルーティングするにはどうすればよいでしょうか？  

- A. セキュリティ イベント コネクタを持つ Azure Sentinel ワークスペースを作成します。
- B. Azure AD の診断設定を構成して、イベント ハブにストリーミングします。
- C. Azure Active Directory コネクタを持つ Azure Sentinel ワークスペースを作成します。
- D. Azure AD の診断設定を構成して、ストレージ アカウントにアーカイブします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)  

**解説:**
Azure ADのサインインイベントを「ほぼリアルタイム（near real-time）」でサードパーティのSIEMにルーティングするには、**Azure Event Hubs** を使用するのが標準的な方法です。
Azure AD（Entra ID）の診断設定（Diagnostic settings）を構成し、ログのストリーミング先としてイベントハブを選択します。SIEMツールはイベントハブからログを収集します。ストレージアカウントへのアーカイブ（選択肢D）は長期保存向けであり、リアルタイム性には欠けます。

*Community vote distribution*

B (100%)

質問#26 トピック1

ドラッグ＆ドロップ -  
Azure Active Directory (Azure AD) テナントにリンクされた Azure サブスクリプションがあります。テナントには、User1 と User2 という 2 人のユーザーがいます。Azure  
Defender をデプロイする予定です。  
次の表に示すように、User1 と User2 がサブスクリプション レベルでタスクを実行できるようにする必要があります。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0003500001.png)  
このソリューションでは、最小権限の原則を適用する必要があります。  
各ユーザーにはどのロールを割り当てるべきでしょうか？ 適切なロールを適切なユーザーにドラッグして答えてください。各ロールは、1 回使用することも、複数回使用することも、まったく使用しないことも可能です。  
コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
選択して配置:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0003600001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)   [議論   38](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)

**Correct Answer:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0003700001.png) Box 1: Owner -  
Only the Owner can assign initiatives.  
  
Box 2: Contributor -  
Only the Contributor or the Owner can apply security recommendations.  
Reference:  
<https://docs.microsoft.com/en-us/azure/defender-for-cloud/permissions>

**解説:**
この問題のポイントは、Microsoft Defender for Cloud における **Security Administrator（セキュリティ管理者）** ロールの具体的な権限範囲を理解しているかどうかにあります。

### User1 への割り当て理由

User1 が実行する必要のある以下のタスクは、すべて **Security Administrator** ロールで許可されています。

- **イニシアチブの割り当て（Assign initiatives）**: セキュリティポリシーの管理権限が必要です。
    
- **セキュリティポリシーの編集（Edit security policies）**: Security Administrator はポリシーの表示および編集が可能です。
    
- **自動プロビジョニングの有効化（Enable automatic provisioning）**: エージェントの自動インストール設定などの管理には、Security Administrator または Owner ロールが必要です。
    

### User2 への割り当て理由

User2 のタスクにおいて決定的なのは「アラートの却下」です。

- **推奨事項の適用（Apply security recommendations）**: リソースの修正には書き込み権限が必要ですが、セキュリティ管理の文脈では Security Administrator がこれを担います。
    
- **アラートの却下（Dismiss alerts）**: **Security Administrator** ロールの重要な権限の一つです。Security Reader（セキュリティ閲覧者）は表示のみが可能で、却下はできません。また、通常の Contributor（共同作成者）ロールにはセキュリティアラートを管理する特定の権限が含まれていないため、最小権限の原則に照らすと Security Administrator が最適です。

質問#27 トピック1

ホットスポット -  
Microsoft 365 E5 サブスクリプションがあり、Microsoft Defender for Endpoint に登録されている Windows 10 デバイスが 200 台あります。  
ユーザーが Microsoft 365 Defender ポータルから直接リモートシェル接続を使用してデバイスにアクセスできるようにする必要があります。このソリューションでは、最小権限の原則を適用する必要があります。Microsoft  
365 Defender ポータルで何をすべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正しい選択ごとに 1 ポイントが付与されます。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0003800001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)   [議論   19](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image411.png)

**解説:**
Microsoft 365 Defender ポータル（Defender for Endpoint）からデバイスへのリモートシェル接続を行う機能は **「ライブ応答 (Live Response)」** です。
この機能を使用するには、まず Defender for Endpoint の設定（Settings）にある **「高度な機能 (Advanced features)」** メニューで、「ライブ応答 (Live Response)」をオンにする必要があります。

質問#28 トピック1

ホットスポット -  
Microsoft 365 Defender を使用する Microsoft 365 サブスクリプションを所有しており、User1 というユーザーが登録されています。User1  
のアカウントが侵害されたという通知を受け取りました。User1  
がサインインしたデバイスでトリガーされたアラートを確認する必要があります。  
このクエリをどのように完了すればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正しい選択肢は 1 つにつき 1 ポイントです。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0004000001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)

**Correct Answer:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0004100001.jpg) Box 1: join -  
An inner join.  
This query uses kind=inner to specify an inner-join, which prevents deduplication of left side values for DeviceId.  
This query uses the DeviceInfo table to check if a potentially compromised user (<account-name>) has logged on to any devices and then lists the alerts that have been triggered on those devices.  
  
DeviceInfo -  
//Query for devices that the potentially compromised account has logged onto  
| where LoggedOnUsers contains '<account-name>'  
| distinct DeviceId  
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables  
| join kind=inner AlertEvidence on DeviceId  
| project AlertId  
//List all alerts on devices that user has logged on to  
| join AlertInfo on AlertId  
| project AlertId, Timestamp, Title, Severity, Category  
DeviceInfo LoggedOnUsers AlertEvidence "project AlertID"  
  
Box 2: project -  
Reference:  
<https://docs.microsoft.com/en-us/microsoft-365/security/defender/advanced-hunting-query-emails-devices?view=o365-worldwide>

**解説:**
侵害されたユーザー (`<account-name>`) がログインしたデバイス上のすべてのアラートを一覧表示するクエリです。

1. **Box 1: `join`**: `AlertEvidence` テーブル（アラートに関連するデバイスやファイルの情報を持つ）と `DeviceInfo`（ログインデバイス情報）を結合するために `join` を使用します。ここでは `kind=inner`（内部結合）を使用し、両方のテーブルに存在する（つまり、侵害されたユーザーがログインし、かつアラートがある）レコードのみを抽出します。
2. **Box 2: `project`**: 最終的な出力結果として表示したい列（AlertId, Timestamp, Titleなど）を指定するために `project` 演算子を使用します。

質問#29 トピック1

Microsoft SharePoint Online を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
このサブスクリプションからユーザーを削除します。  
削除されたユーザーが、アカウントが削除される前の月に SharePoint Online サイトから多数のドキュメントをダウンロードしていた場合、通知を受け取る必要があります。どのような通知方法を  
使用すればよいでしょうか？  

- A. Microsoft Defender for Cloud Apps のファイルポリシー
- B. アクセスレビューポリシー
- C. Microsoft Defender for Office 365 のアラートポリシー
- D. インサイダーリスクポリシー

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)   [議論   60](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)

**Correct Answer:** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)  

**解説:**
削除されたユーザー、あるいは退職予定のユーザーによるデータの大量ダウンロード（Mass download）などのリスクを検知するには、**インサイダーリスク管理（Insider Risk Management）** ポリシーが最適です。
「退職するユーザーによるデータ盗難（Data theft by departing users）」というテンプレートを使用することで、ユーザーアカウントが削除される前の不審なアクティビティを遡って検知・通知することができます。DLPポリシーもダウンロード制限には使えますが、「削除されたユーザーの過去の行動」に焦点を当てたリスク分析にはインサイダーリスク管理が特化しています。

*Community vote distribution*

D (80%)

11%

9%

質問#30 トピック1

Microsoft 365 サブスクリプションをお持ちで、Microsoft 365 Defender が有効になっています。  
過去7日間に機密ラベルに加えられたすべての変更を特定する必要があります。  
どのようなツールを使用すればよいでしょうか？  

- A. Microsoft 365 Defender ポータルのインシデント ブレード
- B. Microsoft 365 コンプライアンス センターのデータ損失防止ブレードのアラート設定
- C. Microsoft 365 コンプライアンス センターのアクティビティ エクスプローラー
- D. Microsoft 365 Defender ポータルのメールとコラボレーション ブレードのエクスプローラー設定

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/3/#)

**Correct Answer:** C

**解説:**
過去7日間の機密ラベル（Sensitivity labels）の変更履歴（適用、変更、削除など）を確認するには、Microsoft 365 コンプライアンスセンター（現在のMicrosoft Purview コンプライアンスポータル）の **「アクティビティエクスプローラー (Activity explorer)」** を使用します。
アクティビティエクスプローラーでは、ラベル付けアクティビティをフィルタリングして、特定の期間（過去7日間など）や特定のアクション（ラベル変更など）を詳細に調査することができます。
