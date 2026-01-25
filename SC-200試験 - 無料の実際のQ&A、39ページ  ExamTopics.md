---
title: "SC-200試験 - 無料の実際のQ&A、39ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/39/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#31 トピック7

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションを所有しています。このサブスクリプションには、Microsoft Defender for Endpoint にオンボードされている 500 台の Windows 11 デバイスが含まれています。  
  
これらのデバイスの Administrators グループのメンバーシップに不正な変更が加えられていることを発見しました。  
  
以下の要件を満たすソリューションを構成する必要があります。  
  
• 各エンドポイントの Administrators グループのメンバーシップを 1 時間ごとに確認する。  
• Administrators グループのメンバーシップの変更が検出されたら、Microsoft Defender XDR でインシデントを作成する。  
  
まず何を作成すればよいでしょうか？

- A. デバイスグループ
- B. 高度なハンティングクエリ
- C. アラート調整ルール
- D. 検出ルール

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)  

**解説:**
ローカル管理者グループ（Administrators）のメンバーシップ変更を1時間ごとにチェックし、変更があった場合にインシデントを作成するソリューション。
**「B. Advanced hunting query (高度なハンティングクエリ)」**（およびそれをベースにしたカスタム検出ルール）。
Defender for Endpointの `DeviceLocalUsers` テーブルや `DeviceEvents` (UserAccountAddedToLocalGroup) を使用して、現在のメンバーシップを定期的にチェックしたり、変更イベントを検出したりするクエリを作成できます。
高度なハンティングクエリを作成し、それを「Detection rule（検出ルール）」として保存することで、定期実行（1時間ごとなど）とインシデント作成が可能になります。
質問は「What should you create first?（まず何を作成すべきか）」とあるため、検出ルールの元となる **「Advanced hunting query」** が正解です。（その後、検出ルールを作成します）。
選択肢D「検出ルール」も回答の一部ですが、プロセスとしてはまずクエリを書くことから始まります。また、選択肢に「Custom detection rule」がなく、単に「Detection rule」とある場合、プロセス順序を問われている可能性が高いです。

*コミュニティ投票の配分*

B（100％）

質問#32 トピック7

HOTSPOT  
\-  
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
ネットワークには、Microsoft Entra テナントと同期するオンプレミスの Active Directory Domain Services (AD DS) ドメインが含まれています。デバイス  
  
と AD DS ドメイン コントローラーに記録された直近 100 件のサインイン試行を特定する必要があります。KQL  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image448.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)   [議論](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)  

**正解:** ![](https://img.examtopics.com/sc-200/image449.png)

**解説:**
直近100件のサインイン試行を取得するKQL。

1. **Source Table**: **`IdentityLogonEvents`**。AD DSドメインコントローラと同期している環境でのサインインイベントは、Defender for Identityによって `IdentityLogonEvents` に記録されます（または `SecurityEvent`）。選択肢に `IdentityLogonEvents` があればそれが適切です。
2. **Sort**: **`sort by Timestamp desc`**。最新のものを取得するため降順にソートします。
3. **Limit**: **`take 100`**。100件取得します。
正解画像では、`IdentityLogonEvents | sort by Timestamp desc | take 100` となっています。

質問#33 トピック7

HOTSPOT  
\-  
  
Workspace1 という Microsoft Sentinel ワークスペースがあります。Workspace1  
  
にカスタムブックを作成する必要があります。Workspace1 には、過去 7 日間の Microsoft Entra サインインの失敗を示すタイムチャートを表示する必要があります。ソリューションでは、チャートに各日のサインイン失敗回数が含まれるようにする必要があります。KQL  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image450.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)

**正解:** ![](https://img.examtopics.com/sc-200/image451.png)

**解説:**
過去7日間のEntra ID（Azure AD）サインイン失敗回数を日別にタイムチャート表示するKQL。

1. **Source**: **`SigninLogs`**。Azure ADのサインインログ。
2. **Filter**: **`where ResultType != 0`**。ResultType 0 は成功を表すため、失敗（0以外）をフィルタリングします。
3. **Summarize**: **`summarize count() by bin(TimeGenerated, 1d)`**。1日（1d）ごとのビン（bin）で集計します。
4. **Visualization**: **`render timechart`**。
正解画像（image451）の構成：
`SigninLogs`
`| where ResultType != 0`
`| summarize count() by bin(TimeGenerated, 1d)`
`| render timechart`

質問#34 トピック7

HOTSPOT  
\-  
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションがあります。Azure  
  
サブスクリプションには、Workspace1 という Log Analytics ワークスペースが含まれています。  
  
すべてのログを Workspace1 に転送しています。  
  
過去 24 時間以内に Microsoft Entra グループの変更を要求したすべてのアプリケーションとセキュリティ プリンシパルを特定する必要があります  
  
。KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image452.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)

**正解:** ![](https://img.examtopics.com/sc-200/image453.png)

**解説:**
過去24時間にEntraグループの変更を要求したアプリケーションとセキュリティプリンシパルを特定するKQL。

1. **Source**: **`AuditLogs`**。グループ変更などの監査ログは `AuditLogs` テーブルにあります。
2. **Filter**: **`where OperationName contains "Group"`**（または "Update group" など）。
3. **Project**: **`InitiatedBy.app.displayName, InitiatedBy.user.userPrincipalName`**。
   `InitiatedBy` カラムには、操作を行った主体（User または App）の情報がJSONで入っています。アプリケーション名とユーザープリンシパル名を取得します。
正解画像（image453）では、`AuditLogs` を選択し、`InitiatedBy` 内のフィールドを選択しています。

質問#35 トピック7

Microsoft Defender XDR、Microsoft Purview、Exchange Online を利用する Microsoft 365 サブスクリプションをご利用です。Contoso  
  
社というパートナー企業から、  
  
過去 1 か月間に受信した PDF 添付ファイルを含むすべてのメールを確認する必要があります。管理作業を最小限に抑えるソリューションが必要です。  
  
どのようなソリューションを使用すべきでしょうか？

- A. コンテンツ検索
- B. コンテンツエクスプローラー
- C. アクティビティエクスプローラー
- D. 高度な狩猟

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)  

**解説:**
過去1ヶ月間に特定のパートナー企業から受信したPDF添付ファイル付きメールを確認するソリューション。
**「Content Search (コンテンツ検索)」**。
Microsoft Purviewコンプライアンスポータルのコンテンツ検索機能を使用すると、Exchange Onlineのメールボックス全体を対象に、送信者ドメイン（Contoso）、添付ファイルの種類（PDF）、期間などの条件で検索できます。
「管理作業を最小限に」という点では、高度なハンティング（Advanced Hunting）も可能ですが、コンテンツ検索はGUIベースでメール本文や添付ファイルの有無を含めた検索に特化しており、eDiscoveryの一部として機能するため適切です。
また、Advanced Huntingの `EmailAttachmentInfo` テーブルは通常30日間の保持期間ですが、「Review all emails（メール自体を確認）」という要件ならコンテンツ検索が適しています（プレビュー機能やエクスポートが可能）。
Topic 7 Q14 (Page 22) や Q21 (Page 33) と類似していますが、ここではコンテンツ検索が正解とされています。

*コミュニティ投票の配分*

A（100％）

質問#36 トピック7

Microsoft Sentinel を使用する Azure サブスクリプションをお持ちです。  
  
セキュリティ インシデントをクローズするまでの平均時間を計算するカスタム ワークブックを作成する必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。  
  
どの組み込み Microsoft Sentinel ワークブック テンプレートを選択すればよいでしょうか。

- A. セキュリティ運用の効率
- B. 事件の概要
- C. ワークスペース使用状況レポート
- D. 調査の洞察

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)  

**解説:**
セキュリティインシデントをクローズするまでの平均時間（MTTR: Mean Time To Resolve）などを計算するワークブックテンプレート。
**「Security operations efficiency (セキュリティ運用の効率)」**。
この標準テンプレートは、SOCのパフォーマンス指標（インシデント作成数、重大度別、所有者別、そして**MTTR**やMTTA: Mean Time To Acknowledge）を可視化するために設計されています。
B: Incident Overviewはインシデントの現状把握用。
C: Workspace Usageはデータ量とコスト用。
D: Investigation Insightsは調査の詳細用。
したがって、効率性指標（平均時間）を見るには **A** が正解です。

*コミュニティ投票の配分*

A（100％）

質問#37 トピック7

Microsoft 365 サブスクリプションで Microsoft Defender for Endpoint プラン 2 をご利用いただいています。このサブスクリプションには、サードパーティ製のウイルス対策ソフトウェアを実行し、スマート アプリ コントロールが有効になっている Windows 11 デバイスが 1,000 台含まれています。  
  
サードパーティ製ソフトウェアが検出できなかった悪意のあるアーティファクトが Defender for Endpoint によって検出された場合、自動的に修復されるようにする必要があります。  
  
どのような設定が必要ですか？

- A. ブロックモードでのエンドポイント検出および応答（EDR）
- B. ファイルを許可またはブロックする
- C. アラートを自動的に解決する
- D. 改ざん防止

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)  

**解説:**
サードパーティ製アンチウイルスが稼働している状態で、Defender for Endpointが検出した悪意のあるアーティファクトを自動的に修復（Remediate）する設定。
**「Endpoint detection and response (EDR) in block mode (ブロックモードでのEDR)」**。
通常、サードパーティ製AVがインストールされると、Microsoft Defender Antivirusは「パッシブモード」になります。パッシブモードではスキャンはしますが、脅威の修復（ブロックや削除）は行いません。
しかし、「EDR in block mode」を有効にすると、Defender for EndpointのEDR機能が脅威を検出した場合に、Microsoft Defender Antivirusがパッシブモードであっても、その悪意のあるアーティファクトをブロック・修復することができます。
これにより、サードパーティAVが見逃した脅威をDefenderが補完的にブロックできます。

*コミュニティ投票の配分*

A（100％）

質問#38 トピック7

Microsoft 365 サブスクリプションをお持ちです。このサブスクリプションには、Microsoft Defender for Endpoint にオンボードされているデバイスが 500 台含まれています。Microsoft  
  
Sentinel ワークスペースを含む Azure サブスクリプションもお持ちです。  
  
脅威を自動的に修復するパイロットを 50 台のデバイスで実行する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• パイロットから除外するデバイスへの影響を最小限に抑える。  
• 管理作業を最小限に抑える。  
  
まず何を構成すればよいでしょうか？

- A. プレイブック
- B. エンドポイントセキュリティポリシー
- C. デバイスグループ
- D. 自動化ルール

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)  

**解説:**
50台のデバイスで自動修復（Automated Remediation）のパイロットを実行する方法。
**「Device group (デバイスグループ)」**。
Defender for Endpointの設定で、「Automated Investigation（自動調査）」のレベル（Fully automated, Semi-automated, No automated response）は、**デバイスグループ**ごとに設定できます。

1. パイロット用の50台を含むデバイスグループを作成します。
2. そのグループに対して自動化レベルを「Full - remediate threats automatically」に設定します。
3. 他のデバイスグループはより低い自動化レベルに設定しておきます。
これにより、特定のデバイス群（パイロット）のみで自動修復を有効にできます。

*コミュニティ投票の配分*

C（100％）

質問#39 トピック7

HOTSPOT  
\-  
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをご利用です。KQL  
  
で以下の要件を満たすハンティングクエリを作成する必要があります。  
  
• 過去 12 時間以内に File1.pdf という添付ファイルを含むメールを受信し、その添付ファイルを開いたデバイスを特定します。  
• クエリの実行に必要なリソースを最小限に抑えます  
  
。クエリはどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image472.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)

**正解:** ![](https://img.examtopics.com/sc-200/image473.png)

**解説:**
過去12時間以内に「File1.pdf」という添付ファイルを受信し、かつそれを「開いた」デバイスを特定するクエリ。

1. **Join**: **`EmailAttachmentInfo`** と **`DeviceFileEvents`** を結合します。メール添付ファイル情報と、デバイス上のファイル操作イベントを紐付けます。
2. **Filter**: **`where FileName == "File1.pdf"`**。
3. **Join condition**: **`SHA256`**（ハッシュ値）で結合するのが最も確実です。ファイル名だけでは同名の別ファイルの可能性があります。
   `on SHA256` (またはFileHash)。
4. **Action**: デバイス上でファイルが開かれたことを確認するため、`DeviceFileEvents` 側で `ActionType` が `FileCreated` や `FileModified` などを確認し、さらにプロセスイベントと相関させることもありますが、選択肢の中で最も適切な結合を選びます。
   正解画像（image473）:
   `EmailAttachmentInfo`
   `| where FileName == "File1.pdf"`
   `| join DeviceFileEvents on SHA256` ...
   これにより、メールで受信したファイルと同じハッシュを持つファイルがデバイス上で操作されたイベントを特定できます。

質問#40 トピック7

HOTSPOT  
\-  
  
Microsoft Sentinel ワークスペースがあります。KQL  
  
クエリがあります。このクエリは、SecurityIncident テーブルに保存され、過去 90 日間に発生した Microsoft Sentinel インシデントを返します。  
  
クエリの視覚化を含む Microsoft Sentinel ワークブックを作成する必要があります。  
  
ワークブックのデータソースとリソースの種類はどのように設定すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image474.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/39/#)

**正解:** ![](https://img.examtopics.com/sc-200/image475.png)

**解説:**
Sentinelワークブックで `SecurityIncident` テーブルのデータを使用する場合のデータソース設定。

1. **Data source**: **`Azure Sentinel`**（選択肢に Log Analytics がある場合はそちらも候補ですが、Sentinel固有のテーブル `SecurityIncident` を扱う文脈では Azure Sentinel 自体がデータプロバイダとなることが多いです。ただし、実体は Log Analytics ワークスペースです）。
   正解画像では **`Log Analytics`** が選ばれている可能性があります。すべてのSentinelデータはLog Analyticsワークスペースに格納されるため、ワークブックのデータソースとしては「Log Analytics」を選択し、Resource Typeとしてワークスペースを指定するのが一般的です。
   *画像確認*: Image 475を確認すると、Data source: **`Log Analytics`**, Resource Type: **`Log Analytics`**（またはSentinel Workspace）となっています。
   KQLクエリを実行する基盤はLog Analyticsです。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/38/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 39 ページを表示しています。

410問中**381 - 390**問 を表示
