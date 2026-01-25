---
title: "SC-200試験 - 無料の実際のQ&A、21ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/21/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#74 トピック3

ケーススタディ -  
  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
  
Fabrikam, Inc. は金融サービス会社です。  
  
この会社には、ニューヨーク、ロンドン、シンガポールに支社があります。Fabrikam には、世界中にリモート ユーザーがいます。リモート ユーザーは、支社への VPN 接続を使用して、クラウド リソースを含む会社のリソースにアクセスします。  
  
既存の環境 -  
  
ID 環境 -  
  
ネットワークには、fabrikam.com という名前の Azure AD テナントと同期する fabrikam.com という名前の Active Directory ドメイン サービス (AD DS) フォレストが含まれています。フォレストを同期するために、Fabrikam は、パススルー認証が有効でパスワード ハッシュ同期が無効な Azure AD Connect を使用します。fabrikam.com  
  
フォレストには、Group1 と Group2 という 2 つのグローバル グループが含まれています。Microsoft  
  
365 環境 -  
  
Fabrikam のすべてのユーザーには、Microsoft 365 E5 ライセンスと Azure Active Directory Premium Plan 2 ライセンスが割り当てられています。  
  
Fabrikam は Microsoft Defender for Identity と Microsoft Defender for Cloud Apps を実装し、ログコレクターを有効にしています。Azure  
  
環境 -  
  
Fabrikam は、次の表に示すリソースを含む Azure サブスクリプションを保有しています。Amazon  
  
![](https://img.examtopics.com/sc-200/image172.png)  
  
Web Services (AWS) 環境  
  
Fabrikam には Account1 という名前の Amazon Web Services (AWS) アカウントがあります。Account1 には、カスタム Windows Server 2022 を実行する 100 個の Amazon Elastic Compute Cloud (EC2) インスタンスが含まれています。イメージには Microsoft SQL Server 2019 が含まれていますが、エージェントはインストールされていません。  
  
現在の問題 -  
  
ユーザーが VPN 接続を使用すると、Microsoft 365 Defender によって、誤検知であるあり得ない移動アラートが大量に生成されます。Defender  
  
for Identity によって、誤検知である DCSync 攻撃の疑いアラートが大量に生成されます。  
  
要件 -  
  
計画されている変更 -  
  
Fabrikam では、次のサービスを実装する予定です。  
  
• Microsoft Defender for Cloud  
• Microsoft Sentinel  
  
ビジネス要件 -  
  
Fabrikam では、次のビジネス要件を特定しています。  
  
• 可能な限り、最小権限の原則を使用します。  
• 管理の労力を最小限に抑えます。  
  
Microsoft Defender for Cloud Apps の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud Apps の要件を特定しています。  
  
• あり得ない移動アラート ポリシーが各ユーザーの以前のアクティビティに基づいていることを確認します。  
• 誤検知であるあり得ない移動アラートの量を減らします。  
  
Microsoft Defender for Identity の要件  
  
誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Defender for Cloud の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud の要件を特定しています。  
  
• Group2 のメンバーがセキュリティ ポリシーを変更できること  
を確認します。 • Group1 のメンバーが、Azure サブスクリプション レベルで規制コンプライアンス ポリシー イニシアチブを割り当てることができることを確認します。  
• Account1 の既存および将来のリソースへの Azure Arc 対応サーバー用の Azure Connected Machine エージェントの展開を自動化します。  
• 誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Sentinel の要件 -  
  
Fabrikam では、次の Microsoft Sentinel の要件を特定しています。 •  
  
組み込みの Advanced Security Information Model (ASIM) 統合パーサーを使用して、過去 7 日間のNXDOMAIN DNS 要求  
をクエリします。 • AWS EC2 インスタンスから、ローカル グループ メンバーシップの変更を含む Windows セキュリティ イベント ログ エントリを収集します。 •  
ユーザーおよびエンティティの動作分析 (UEBA)  
を使用して、Azure AD ユーザーの異常なアクティビティを特定します  
• App1 が Microsoft Sentinel 自動化ルールで使用できることを確認します。  
• 過去 30 日間に生成されたインシデントのトリアージにかかる平均時間を特定します。  
• 過去 30 日間に生成されたインシデントのクローズにかかる平均時間を特定します。  
• グループ1のメンバーがプレイブックを作成および実行できることを確認します。  
• グループ1のメンバーが分析ルールを管理できることを確認します。  
• Jupyterノートブックを使用して、プール1でハンティングクエリを実行します。  
• グループ2のメンバーがインシデントを管理できることを確認します。  
• データクエリのパフォーマンスを最大化します。  
• 収集されるデータの量を最小限に抑えます。Microsoft  
  
Sentinelの要件を満たすには、どの平均時間メトリックを使用するかを特定する必要があります。  
  
どのワークブックを使用すればよいでしょうか？

- A. イベントアナライザー
- B. 調査の洞察
- C. セキュリティ運用の効率
- D. 分析の効率

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)  

**解説:**
Fabrikamの要件「過去30日間に生成されたインシデントのトリアージ/クローズにかかる平均時間を特定する」を満たすためのワークブックです。
**「Security operations efficiency (セキュリティ運用の効率)」**: この組み込みワークブックは、SOCのパフォーマンス指標（KPI）を可視化するために設計されています。インシデントの作成からトリアージまでの平均時間（MTTT）、解決までの平均時間（MTTR）、インシデントの発生傾向などを追跡できます。

*コミュニティ投票の配分*

C（100％）

質問#75 トピック3

HOTSPOT  
\-  
  
ケーススタディ  
\-  
  
これはケーススタディです。ケーススタディは個別に時間制限がありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディとセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する展示資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
  
このケーススタディの最後に、確認画面が表示されます。この画面では、試験の次のセクションに進む前に回答を確認し、変更を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには  
\-  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。 ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同じであることに注意してください。 質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要  
\-  
  
Fabrikam, Inc. は金融サービス会社です。  
  
この会社には、ニューヨーク、ロンドン、シンガポールに支社があります。 Fabrikam には、世界中にリモート ユーザーがいます。リモート ユーザーは、支社への VPN 接続を使用して、クラウド リソースなどの会社のリソースにアクセスします。  
  
既存の環境  
\-  
  
ID 環境  
\-  
  
ネットワークには、fabrikam.com という名前の Azure AD テナントと同期する fabrikam.com という名前の Active Directory ドメイン サービス (AD DS) フォレストが含まれています。 フォレストを同期するために、Fabrikam は、パススルー認証が有効でパスワード ハッシュ同期が無効な Azure AD Connect を使用します。  
  
fabrikam.com フォレストには、Group1 と Group2 という 2 つのグローバル グループが含まれています。  
  
Microsoft 365 環境  
\-  
  
Fabrikam の全ユーザーには、Microsoft 365 E5 ライセンスと Azure Active Directory Premium Plan 2 ライセンスが割り当てられています。Fabrikam  
  
は Microsoft Defender for Identity と Microsoft Defender for Cloud Apps を実装し、ログコレクターを有効にしています。Azure  
  
環境  
\-  
  
Fabrikam には、次の表に示すリソースが含まれる Azure サブスクリプションがあります。  
  
![](https://img.examtopics.com/sc-200/image172.png)  
  
アマゾン ウェブ サービス (AWS) 環境  
  
Fabrikam には、Account1 という名前のアマゾン ウェブ サービス (AWS) アカウントがあります。Account1 には、カスタム Windows Server 2022 を実行する 100 個の Amazon Elastic Compute Cloud (EC2) インスタンスが含まれています。イメージには Microsoft SQL Server 2019 が含まれていますが、エージェントはインストールされていません。  
  
現在の問題  
\-  
  
ユーザーが VPN 接続を使用すると、Microsoft 365 Defender によって、誤検知であるあり得ない移動アラートが大量に生成されます。  
  
Defender for Identity によって、誤検知である DCSync 攻撃の疑いアラートが大量に生成されます。  
  
要件  
\-  
  
計画されている変更  
\-  
  
Fabrikam では、次のサービスを実装する予定です。  
  
• Microsoft Defender for Cloud  
• Microsoft Sentinel  
  
ビジネス要件  
\-  
  
Fabrikam では、次のビジネス要件が特定されています。  
  
• 可能な限り、最小権限の原則を使用します。  
• 管理の労力を最小限に抑えます。  
  
Microsoft Defender for Cloud Apps の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud Apps の要件を特定しています。  
  
• あり得ない移動アラート ポリシーが各ユーザーの以前のアクティビティに基づいていることを確認します。  
• 誤検知であるあり得ない移動アラートの量を減らします。  
  
Microsoft Defender for Identity の要件  
  
誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Defender for Cloud の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud の要件を特定しています。  
  
• Group2 のメンバーが、セキュリティ ポリシーを変更できることを確認  
します。 • Group1 のメンバーが、Azure サブスクリプション レベルで規制コンプライアンス ポリシー イニシアチブを割り当てることができることを確認します。  
• Account1 の既存および将来のリソースへの Azure Arc 対応サーバーの Azure Connected Machine エージェントの展開を自動化します。  
• 誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Sentinel の要件  
  
Fabrikam では、次の Microsoft Sentinel の要件を特定しています。  
  
• 組み込みの Advanced Security Information Model (ASIM) 統合パーサーを使用して、過去 7 日間の NXDOMAIN DNS 要求を照会します。  
• AWS EC2 インスタンスから、ローカルグループメンバーシップの変更を含む Windows セキュリティイベントログエントリを収集します。  
• ユーザーおよびエンティティ行動分析 (UEBA) を使用して、Azure AD ユーザーの異常なアクティビティを特定します。  
• UEBA を使用して、侵害された Azure AD ユーザー資格情報の潜在的な影響を評価します。  
• App1 が Microsoft Sentinel 自動化ルールで使用できることを確認します。  
• 過去 30 日間に生成されたインシデントの平均トリアージ時間を特定します。  
• 過去 30 日間に生成されたインシデントのクローズにかかる平均時間を特定します。  
• Group1 のメンバーがプレイブックを作成して実行できることを確認します。  
• Group1 のメンバーが分析ルールを管理できることを確認します。  
• Jupyter ノートブックを使用して、Pool1 でハンティング クエリを実行します。  
• Group2 のメンバーがインシデントを管理できることを確認します。  
• データ クエリのパフォーマンスを最大化します。  
• 収集されるデータの量を最小限に抑えます。  
  
DNS 関連のアクティビティを調査するためのクエリを作成する必要があります。ソリューションは、Microsoft Sentinel の要件を満たしている必要があります。  
  
どのようにクエリを完了する必要がありますか? 回答するには、回答領域で適切なオプションを選択します。  
  
注: 正しい選択ごとに 1 ポイントの価値があります。  
  
![](https://img.examtopics.com/sc-200/image179.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)

**正解:** ![](https://img.examtopics.com/sc-200/image180.png)

**解説:**
ASIM (Advanced Security Information Model) 統合パーサーを使用して、過去7日間のNXDOMAIN応答を検索するクエリです。
**`_Im_Dns(starttime=ago(7d), response_code_name='NXDOMAIN')`**: ASIMパーサーは、KQL関数として実装されています（`_Im_Dns`など）。パフォーマンスを最適化するために、フィルタ条件（時間範囲や応答コードなど）を関数のパラメータとして渡すことが推奨されています。これにより、バックグラウンドでのデータ取得が最適化されます。`where`句で後からフィルタするよりも効率的です。

質問#76 トピック3

HOTSPOT  
\-  
  
ケーススタディ  
\-  
  
これはケーススタディです。ケーススタディは個別に時間制限がありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディとセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する展示資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
  
このケーススタディの最後に、確認画面が表示されます。この画面では、試験の次のセクションに進む前に回答を確認し、変更を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには  
\-  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。 ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同じであることに注意してください。 質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要  
\-  
  
Fabrikam, Inc. は金融サービス会社です。  
  
この会社には、ニューヨーク、ロンドン、シンガポールに支社があります。 Fabrikam には、世界中にリモート ユーザーがいます。リモート ユーザーは、支社への VPN 接続を使用して、クラウド リソースなどの会社のリソースにアクセスします。  
  
既存の環境  
\-  
  
ID 環境  
\-  
  
ネットワークには、fabrikam.com という名前の Azure AD テナントと同期する fabrikam.com という名前の Active Directory ドメイン サービス (AD DS) フォレストが含まれています。 フォレストを同期するために、Fabrikam は、パススルー認証が有効でパスワード ハッシュ同期が無効な Azure AD Connect を使用します。  
  
fabrikam.com フォレストには、Group1 と Group2 という 2 つのグローバル グループが含まれています。  
  
Microsoft 365 環境  
\-  
  
Fabrikam の全ユーザーには、Microsoft 365 E5 ライセンスと Azure Active Directory Premium Plan 2 ライセンスが割り当てられています。Fabrikam  
  
は Microsoft Defender for Identity と Microsoft Defender for Cloud Apps を実装し、ログコレクターを有効にしています。Azure  
  
環境  
\-  
  
Fabrikam には、次の表に示すリソースが含まれる Azure サブスクリプションがあります。  
  
![](https://img.examtopics.com/sc-200/image172.png)  
  
アマゾン ウェブ サービス (AWS) 環境  
  
Fabrikam には、Account1 という名前のアマゾン ウェブ サービス (AWS) アカウントがあります。Account1 には、カスタム Windows Server 2022 を実行する 100 個の Amazon Elastic Compute Cloud (EC2) インスタンスが含まれています。イメージには Microsoft SQL Server 2019 が含まれていますが、エージェントはインストールされていません。  
  
現在の問題  
\-  
  
ユーザーが VPN 接続を使用すると、Microsoft 365 Defender によって、誤検知であるあり得ない移動アラートが大量に生成されます。  
  
Defender for Identity によって、誤検知である DCSync 攻撃の疑いアラートが大量に生成されます。  
  
要件  
\-  
  
計画されている変更  
\-  
  
Fabrikam では、次のサービスを実装する予定です。  
  
• Microsoft Defender for Cloud  
• Microsoft Sentinel  
  
ビジネス要件  
\-  
  
Fabrikam では、次のビジネス要件が特定されています。  
  
• 可能な限り、最小権限の原則を使用します。  
• 管理の労力を最小限に抑えます。  
  
Microsoft Defender for Cloud Apps の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud Apps の要件を特定しています。  
  
• あり得ない移動アラート ポリシーが各ユーザーの以前のアクティビティに基づいていることを確認します。  
• 誤検知であるあり得ない移動アラートの量を減らします。  
  
Microsoft Defender for Identity の要件  
  
誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Defender for Cloud の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud の要件を特定しています。  
  
• Group2 のメンバーが、セキュリティ ポリシーを変更できることを確認  
します。 • Group1 のメンバーが、Azure サブスクリプション レベルで規制コンプライアンス ポリシー イニシアチブを割り当てることができることを確認します。  
• Account1 の既存および将来のリソースへの Azure Arc 対応サーバーの Azure Connected Machine エージェントの展開を自動化します。  
• 誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Sentinel の要件  
  
Fabrikam では、次の Microsoft Sentinel の要件を特定しています。  
  
• 組み込みの Advanced Security Information Model (ASIM) 統合パーサーを使用して、過去 7 日間の NXDOMAIN DNS 要求を照会します。  
• AWS EC2 インスタンスから、ローカルグループメンバーシップの変更を含む Windows セキュリティイベントログエントリを収集します。  
• ユーザーおよびエンティティ行動分析 (UEBA) を使用して、Azure AD ユーザーの異常なアクティビティを特定します。  
• UEBA を使用して、侵害された Azure AD ユーザー資格情報の潜在的な影響を評価します。  
• App1 が Microsoft Sentinel 自動化ルールで使用できることを確認します。  
• 過去 30 日間に生成されたインシデントの平均トリアージ時間を特定します。  
• 過去 30 日間に生成されたインシデントのクローズにかかる平均時間を特定します。  
• Group1 のメンバーがプレイブックを作成して実行できることを確認します。  
• Group1 のメンバーが分析ルールを管理できることを確認します。  
• Jupyter ノートブックを使用して、Pool1 でハンティング クエリを実行します。  
• Group2 のメンバーがインシデントを管理できることを確認します。  
• データ クエリのパフォーマンスを最大化します。  
• 収集されるデータの量を最小限に抑えます。  
  
Windows セキュリティ イベント ログを収集するには、Microsoft Sentinel の要件を満たす必要があります。  
  
何をすればよいですか。 回答するには、回答領域で適切なオプションを選択します。  
  
注: 正しい選択ごとに 1 ポイントの価値があります。  
  
![](https://img.examtopics.com/sc-200/image181.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)   [議論   15](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)

**正解:** ![](https://img.examtopics.com/sc-200/image182.png)

**解説:**
AWS EC2インスタンスからWindowsセキュリティイベントログを収集し、かつ「データ収集量を最小限に抑える（変更イベントのみなど）」という要件を満たす構成です。

1. **Connector type**: **「Windows Security Events via AMA」**。従来のMMAエージェントは廃止予定であり、AWS EC2などの非AzureサーバーにはAzure Arc経由でAMA (Azure Monitor Agent) を使用するのが現在の標準です。
2. **Install the agent on**: **「The EC2 instances」**。各EC2インスタンスにAzure Arcエージェントをインストールし、Azure Monitor Agent拡張機能を展開します。
3. **Define which events to collect by using**: **「A data collection rule (DCR)」**。AMAではDCRを使用して、収集するイベントレベル（Error, Auditなど）や特定のイベントIDを細かく制御できます。これにより不要なログ収集を抑え、コストとパフォーマンスを最適化できます。

質問#77 トピック3

HOTSPOT -  
  
sws1 という Microsoft Sentinel ワークスペースがあります。  
  
ユーザーが異常に多くの Azure AD ユーザーアカウントを作成したことを検出するクエリを作成する必要があります。  
  
クエリはどのように完成させるべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image197.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)   [議論   24](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)

**正解:** ![](https://img.examtopics.com/sc-200/image431.png)

**解説:**
異常に多くのユーザー作成を検出するためのクエリです。

1. **Table**: **「AuditLogs」**。Azure ADのユーザー作成イベントは `AuditLogs` テーブルに記録されます。
2. **Filter**: **`where OperationName == "Add user"`**。ユーザー追加操作をフィルタリングします。
3. **Aggregation**: **`summarize count() by InitiatedBy`**（またはActor）。誰がユーザーを作成したかごとに件数を集計し、しきい値を超えるものを検出します。

質問#78 トピック3

Azure Activity コネクタを使用してトリガーされる Microsoft Sentinel プレイブックがあります。  
  
このプレイブックを使用する新しいニアリア​​ルタイム (NRT) 分析ルールを作成する必要があります。  
  
このルールにはどのような設定が必要ですか？

- A. インシデント自動化設定
- B. クエリルール
- C. エンティティマッピング
- D. アラート自動化設定

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)   [議論   15](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)  

**解説:**
Azure Activityコネクタからのイベントに応じてプレイブックをトリガーする「ニアリアルタイム (NRT) 分析ルール」の作成に関する質問です。
**「Query rule (クエリルール)」**: NRT分析ルールは、実質的には頻繁（1分間隔）に実行されるスケジュールされたクエリールールの一種です。ルール作成画面でKQLクエリを定義し、条件に一致した場合にアラート/インシデントを生成します。プレイブックを自動実行するには、このルールの「自動化 (Automation)」設定で自動化ルールを関連付けるか、レガシーな方法では直接プレイブックを指定します。選択肢の中では、NRTルールの核心部分である「クエリルール」が設定対象として最も適切です（あるいは「インシデント自動化設定」とも取れますが、ルール自体の定義としてはクエリが必須です）。
※試験的な文脈では、NRTルールを作成すること自体（クエリ定義）を指している可能性が高いです。

*コミュニティ投票の配分*

B（40％）

D（36％）

A（24％）

質問#79 トピック3

Microsoft Sentinel データを視覚化し、サードパーティのデータソースを使用してデータを拡充し、侵害の兆候 (IoC) を特定する必要があります。  
  
何を使用すればよいでしょうか？

- A. Microsoft Sentinelのノートブック
- B. クラウドアプリ向け Microsoft Defender
- C. Azure モニター

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)  

**解説:**
データの可視化、サードパーティデータによる拡充、IoC特定を行うための高度なツールです。
**「Microsoft Sentinel Notebooks」**: Jupyter Notebooksを使用することで、MSTICPyなどのライブラリを活用し、複数のデータソース（VirusTotalなどのサードパーティ脅威インテリジェンス）からのデータ取得・結合・可視化を柔軟に行うことができます。標準のダッシュボード（Workbook）では難しい複雑な分析や外部API連携に適しています。

*コミュニティ投票の配分*

A（100％）

質問#80 トピック3

ドラッグ＆ドロップ -  
  
Azure AD データコネクタを含む Microsoft Sentinel ワークスペースがあります。Azure  
  
AD 関連のインシデントにブックマークを関連付ける必要があります。  
  
どうすればよいでしょうか？ 回答するには、適切なブレードを正しいタスクにドラッグしてください。各ブレードは 1 回使用することも、複数回使用することも、まったく使用しないこともできます。コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
  
注: 正解を選択するごとに 1 ポイント獲得できます。  
  
![](https://img.examtopics.com/sc-200/image199.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)   [議論   23](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)

**正解:** ![](https://img.examtopics.com/sc-200/image432.png)

**解説:**
Azure AD関連のインシデントにブックマークを関連付ける手順です。

1. **From the Logs blade**: まず「ログ (Logs)」ブレードでクエリを実行し、対象のイベント（Azure ADログなど）を見つけます。
2. **Create a bookmark**: クエリ結果の行を選択し、「ブックマークの追加 (Add bookmark)」を実行します。
3. **From the Hunting blade**: 作成したブックマークは「ハンティング (Hunting)」ブレードの「Bookmarks」タブに表示されます。
4. **Add to existing incident**: ブックマークを選択し、「インシデントアクション (Incident actions)」から「既存のインシデントに追加 (Add to existing incident)」を選択して関連付けます。

質問#81 トピック3

HOTSPOT  
\-  
  
Azureサブスクリプションに、User1というゲストユーザーとworkspace1というMicrosoft Sentinelワークスペースが含まれています。User1  
  
がworkspace1でMicrosoft Sentinelインシデントをトリアージできるようにする必要があります。このソリューションでは、最小権限の原則を適用する必要があります。User1  
  
にはどのロールを割り当てるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1点です。  
  
![](https://img.examtopics.com/sc-200/image201.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)

**正解:** ![](https://img.examtopics.com/sc-200/image202.png)

**解説:**
User1（ゲストユーザー）がインシデントのトリアージ（ステータス変更、割り当て変更など）を行うために必要な最小権限です。
**「Microsoft Sentinel Responder」**: このロールは、インシデントの表示、ステータスの更新、割り当て、重大度の変更、コメントの追加などが可能です。分析ルールの作成やワークスペース設定の変更（Contributor権限）はできません。トリアージ業務には最適かつ最小権限です。

質問#82 トピック3

HOTSPOT  
\-  
  
Microsoft Sentinel を使用する Azure サブスクリプションがあり、User1 というユーザーが登録されています。User1  
  
が Azure AD のエンティティの行動分析にユーザーおよびエンティティ行動分析 (UEBA) を有効にできるようにする必要があります。このソリューションでは、最小権限の原則を適用する必要があります。User1  
  
にはどのロールを割り当てるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image203.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)

**正解:** ![](https://img.examtopics.com/sc-200/image204.png)

**解説:**
ユーザーがSentinelでUEBA（User and Entity Behavior Analytics）を有効にするために必要な最小権限です。
**「Microsoft Sentinel Contributor」**: UEBAの有効化はワークスペースの設定変更にあたるため、Contributor権限が必要です。
**「Global Administrator」** (in Azure AD): UEBAを有効にするプロセスで、Azure AD (Entra ID) からのディレクトリデータの読み取り権限などを付与するための承諾が必要になる場合があり、テナントレベルの管理者権限（Global AdminまたはSecurity Admin）が要求されることがあります。
※解説画像や試験の頻出パターンでは、**Sentinel Contributor** と **Global Administrator** (またはSecurity Admin) の組み合わせが正解となるケースが多いです。

質問#83 トピック3

HOTSPOT  
\-  
  
次のリソースを含む Azure サブスクリプションがあります。  
  
• Windows Server を実行する VM1 という名前の仮想マシン  
• ユーザーおよびエンティティ行動分析 (UEBA) が有効になっている Sentinel1 という名前の Microsoft Sentinel ワークスペース  
  
VM1 へのサインイン試行を追跡する Rule1 という名前のスケジュールされたクエリ ルールがあります。  
  
会社の IT 部門外のユーザーが VM1 にサインインしたことを検出するには、Rule1 を更新する必要があります。ソリューションは、次の要件を満たしている必要があります。  
  
• UEBA の結果を利用する。  
• クエリのパフォーマンスを最大化する。  
• 誤検知の数を最小限に抑える。  
  
ルール定義をどのように完了する必要がありますか。 回答するには、回答領域で適切なオプションを選択します。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image205.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/21/#)

**正解:** ![](https://img.examtopics.com/sc-200/image206.png)

**解説:**
IT部門外のユーザーによるVMサインインを検出し、UEBA情報を利用して誤検知を減らすクエリです。

1. **`BehaviorAnalytics`**: UEBAによって生成された行動分析データが含まれるテーブルです。ユーザーごとの通常のアクティビティパターンや異常スコアが格納されています。
2. **`| where UsersInsights.Department != "IT"`**: `BehaviorAnalytics` テーブル（またはエンティティ拡充情報）に含まれるユーザーの属性情報（UsersInsights）を使用して、部署が "IT" でないユーザーをフィルタリングします。これにより、IT部門以外のユーザーのみを対象にできます。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/20/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 21 ページを表示しています。

410問中**201 - 210**問 目を表示
