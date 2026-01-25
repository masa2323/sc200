---
title: "SC-200試験 - 無料の実際のQ&A、41ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/41/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問1 トピック12

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Contoso Ltd. という会社には、北米各地に本社と 5 つの支社があります。本社はシアトルにあります。支社は、トロント、マイアミ、ヒューストン、ロサンゼルス、バンクーバーにあります。Contoso  
には、ニューヨークとサンフランシスコに支社がある Fabrikam, Ltd. という子会社があります。  
  
既存の環境 -  
  
エンド ユーザー環境 -  
Contoso のすべてのユーザーは、Windows 10 デバイスを使用しています。各ユーザーには、Microsoft 365 のライセンスが付与されています。また、Contoso の営業チームのメンバーには iOS デバイスが配布されています。  
  
クラウドとハイブリッド インフラストラクチャ -  
Contoso のすべてのアプリケーションは Azure にデプロイされています。Microsoft  
Cloud App Security を有効にします。Contoso  
と Fabrikam は、異なる Azure Active Directory (Azure AD) テナントを持っています。  
  
現在の問題 -  
Contoso 社のセキュリティチームは、多数のサイバーセキュリティアラートを受信して​​います。セキュリティチームは、どのサイバーセキュリティアラートが正当な脅威で、どれがそうでないかを特定するのに多くの時間を費やしています。  
Contoso の営業チームは、iOS デバイスのみを使用しています。営業チームのメンバーは、さまざまなサードパーティ ツールを使用して顧客とファイルを交換しています。過去に、営業チームはデバイスがフィッシング攻撃を受けたことがあります。Contoso  
のマーケティング チームには、外部ベンダーとのコラボレーション用に複数の Microsoft SharePoint Online サイトがあります。マーケティング チームでは、ベンダーがマルウェアを含むファイルをアップロードするインシデントが何度か発生しています。Contosoの経営陣は、セキュリティ侵害の疑いがあります。経営陣は、Microsoft Cloud App Security で保護されたアプリケーションのデータ アクセス、ダウンロード、削除など、  
過去 48 時間以内に 6 件を超えるアクティビティがあったファイルを特定するよう依頼しています。要件 -計画されている変更 - Contoso は、両社のセキュリティ操作を統合し、すべてのセキュリティ操作を一元管理する予定です。技術要件 - Contoso では、次の技術要件を特定しています。Azure仮想マシンがブルート フォース攻撃を受けている場合にアラートを受信します。Azure Sentinel を使用して、環境に対するアクティブな攻撃を迅速に修復することで、組織のリスクを軽減します。Contoso と Fabrikam の Azure AD テナント間でデータを相関させる Azure Sentinel クエリを実装します。Fabrikamの Azure Defender for Key Vault アラートを、外部攻撃者や自社の Azure AD アプリケーションへの潜在的な侵害が発生した場合に修復する手順を開発します。特定の国から初めて Azure リソースへのサインインに失敗したユーザーのケースをすべて特定します。ジュニアセキュリティ管理者から、次の不完全なクエリが提供されます。BehaviorAnalytics \- | where ActivityType == "FailedLogOn" | where \_\_\_\_\_\_\_\_ == True  
  
質問 技術要件を満たすには、失敗したサインインに関するクエリを完了する必要があります。where  
句を完了するための列名はどこで確認できますか？  

- A. Azure Security Center のセキュリティ アラート
- B. Azureのアクティビティログ
- C. Azureアドバイザー
- D. Log Analytics ワークスペースのクエリ ウィンドウ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)  

**解説:**
**Litwareケーススタディ (Topic 12 Question 1):**
**問題:** 失敗したサインインに関するクエリ（BehaviorAnalytics ... | where ActivityType == "FailedLogOn"）を完成させるために、列名を確認したい。
**解決策:**
**「The Log Analytics workspace query window (Log Analyticsワークスペースのクエリウィンドウ)」**。
Sentinel（Log Analytics）のクエリウィンドウ（Logsブレード）では、左側の「Tables」ペインでテーブルスキーマ（列名やデータ型）を確認できます。`BehaviorAnalytics` テーブルを展開して、利用可能な列を確認するのが標準的な手順です。
Azure Activity LogはAzureリソースの操作ログであり、SentinelのUEBAテーブル（BehaviorAnalytics）のスキーマ確認場所ではありません。

*コミュニティ投票の配分*

D（100％）

質問2 トピック12

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Contoso Ltd. という会社には、北米各地に本社と 5 つの支社があります。本社はシアトルにあります。支社は、トロント、マイアミ、ヒューストン、ロサンゼルス、バンクーバーにあります。Contoso  
には、ニューヨークとサンフランシスコに支社がある Fabrikam, Ltd. という子会社があります。  
  
既存の環境 -  
  
エンド ユーザー環境 -  
Contoso のすべてのユーザーは、Windows 10 デバイスを使用しています。各ユーザーには、Microsoft 365 のライセンスが付与されています。また、Contoso の営業チームのメンバーには iOS デバイスが配布されています。  
  
クラウドとハイブリッド インフラストラクチャ -  
Contoso のすべてのアプリケーションは Azure にデプロイされています。Microsoft  
Cloud App Security を有効にします。Contoso  
と Fabrikam は、異なる Azure Active Directory (Azure AD) テナントを持っています。  
  
現在の問題 -  
Contoso 社のセキュリティチームは、多数のサイバーセキュリティアラートを受信して​​います。セキュリティチームは、どのサイバーセキュリティアラートが正当な脅威で、どれがそうでないかを特定するのに多くの時間を費やしています。  
Contoso の営業チームは、iOS デバイスのみを使用しています。営業チームのメンバーは、さまざまなサードパーティ ツールを使用して顧客とファイルを交換しています。過去に、営業チームはデバイスがフィッシング攻撃を受けたことがあります。Contoso  
のマーケティング チームには、外部ベンダーとのコラボレーション用に複数の Microsoft SharePoint Online サイトがあります。マーケティング チームでは、ベンダーがマルウェアを含むファイルをアップロードするインシデントが何度か発生しています。Contosoの経営陣は、セキュリティ侵害の疑いがあります。経営陣は、Microsoft Cloud App Security で保護されたアプリケーションのデータ アクセス、ダウンロード、削除など、  
過去 48 時間以内に 6 件を超えるアクティビティがあったファイルを特定するよう依頼しています。要件 -計画されている変更 - Contoso は、両社のセキュリティ操作を統合し、すべてのセキュリティ操作を一元管理する予定です。技術要件 - Contoso では、次の技術要件を特定しています。Azure仮想マシンがブルート フォース攻撃を受けている場合にアラートを受信します。Azure Sentinel を使用して、環境に対するアクティブな攻撃を迅速に修復することで、組織のリスクを軽減します。Contoso と Fabrikam の Azure AD テナント間でデータを相関させる Azure Sentinel クエリを実装します。Fabrikamの Azure Defender for Key Vault アラートを、外部攻撃者や自社の Azure AD アプリケーションへの潜在的な侵害が発生した場合に修復する手順を開発します。特定の国から初めて Azure リソースへのサインインに失敗したユーザーのケースをすべて特定します。ジュニアセキュリティ管理者から、次の不完全なクエリが提供されます。BehaviorAnalytics \- | where ActivityType == "FailedLogOn" | where \_\_\_\_\_\_\_\_ == True  
  
質問 技術要件を満たすには、アクティブな攻撃を修復する必要があります。  
ソリューションには何を含めるべきですか？  

- A. Azure Automation ランブック
- B. Azure ロジック アプリ
- C. Azure 関数
- D. Azure Sentinel ライブストリーム

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)  

**解説:**
**Litwareケーススタディ (Topic 12 Question 2):**
**技術要件:** 「Azure Sentinelを使用して、環境に対するアクティブな攻撃を迅速に修復することで、組織のリスクを軽減する。」
**解決策:**
**「Azure Logic Apps (Azureロジックアプリ)」**。
Sentinelにおいて、修復（Remediation）を自動化するための主要なメカニズムは **Playbook** であり、Playbookの実体は **Azure Logic Apps** です。
インシデントトリガーやアラートトリガーでLogic Appを実行し、ユーザー無効化、IPブロックなどの修復アクションを自動化します。
Azure Functions（D）も自動化に使えますが、Sentinelの標準的なSOARコンポーネントとしてはLogic App（Playbook）が第一選択です。

*コミュニティ投票の配分*

B（80％）

D（20％）

質問3 トピック12

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Contoso Ltd. という会社には、北米各地に本社と 5 つの支社があります。本社はシアトルにあります。支社は、トロント、マイアミ、ヒューストン、ロサンゼルス、バンクーバーにあります。Contoso  
には、ニューヨークとサンフランシスコに支社がある Fabrikam, Ltd. という子会社があります。  
  
既存の環境 -  
  
エンド ユーザー環境 -  
Contoso のすべてのユーザーは、Windows 10 デバイスを使用しています。各ユーザーには、Microsoft 365 のライセンスが付与されています。また、Contoso の営業チームのメンバーには iOS デバイスが配布されています。  
  
クラウドとハイブリッド インフラストラクチャ -  
Contoso のすべてのアプリケーションは Azure にデプロイされています。Microsoft  
Cloud App Security を有効にします。Contoso  
と Fabrikam は、異なる Azure Active Directory (Azure AD) テナントを持っています。  
  
現在の問題 -  
Contoso 社のセキュリティチームは、多数のサイバーセキュリティアラートを受信して​​います。セキュリティチームは、どのサイバーセキュリティアラートが正当な脅威で、どれがそうでないかを特定するのに多くの時間を費やしています。  
Contoso の営業チームは、iOS デバイスのみを使用しています。営業チームのメンバーは、さまざまなサードパーティ ツールを使用して顧客とファイルを交換しています。過去に、営業チームはデバイスがフィッシング攻撃を受けたことがあります。Contoso  
のマーケティング チームには、外部ベンダーとのコラボレーション用に複数の Microsoft SharePoint Online サイトがあります。マーケティング チームでは、ベンダーがマルウェアを含むファイルをアップロードするインシデントが何度か発生しています。Contosoの経営陣は、セキュリティ侵害の疑いがあります。経営陣は、Microsoft Cloud App Security で保護されたアプリケーションのデータ アクセス、ダウンロード、削除など、  
過去 48 時間以内に 6 件を超えるアクティビティがあったファイルを特定するよう依頼しています。要件 -計画されている変更 - Contoso は、両社のセキュリティ操作を統合し、すべてのセキュリティ操作を一元管理する予定です。技術要件 - Contoso では、次の技術要件を特定しています。Azure仮想マシンがブルート フォース攻撃を受けている場合にアラートを受信します。Azure Sentinel を使用して、環境に対するアクティブな攻撃を迅速に修復することで、組織のリスクを軽減します。Contoso と Fabrikam の Azure AD テナント間でデータを相関させる Azure Sentinel クエリを実装します。Fabrikamの Azure Defender for Key Vault アラートを、外部攻撃者や自社の Azure AD アプリケーションへの潜在的な侵害が発生した場合に修復する手順を開発します。特定の国から初めて Azure リソースへのサインインに失敗したユーザーのケースをすべて特定します。ジュニアセキュリティ管理者から、次の不完全なクエリが提供されます。BehaviorAnalytics \- | where ActivityType == "FailedLogOn" | where \_\_\_\_\_\_\_\_ == True  
  
質問 ホットスポット -  
経営陣の問題を調査するために、高度なハンティングクエリを作成する必要があります。  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切な選択肢を選択してください。  
注: 正しい選択肢は1つにつき1ポイントです。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009300001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)   [議論   30](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)

**正解:** ![](https://img.examtopics.com/sc-200/image443.png)

**解説:**
**Litwareケーススタディ (Topic 12 Question 3):**
**経営陣の要請:** 「Microsoft Cloud App Securityで保護されたアプリケーションで、データアクセス、ダウンロード、削除などのアクティビティが過去48時間に6件以上あったファイルを特定する。」
**クエリ構築:**

1. **Source Table**: **`CloudAppEvents`**。Cloud App Security (MDA) のイベントはSentinelの `CloudAppEvents` テーブル（または `AppFileEvents` 等、コネクタ設定による）に格納されますが、ファイルアクティビティのハンティングには `CloudAppEvents` が使用されます（Rawデータ）。
   正解画像では `CloudAppEvents` が選択されているはずです。
   *補足*: ファイル名ごとの集計をするため、`summarize count() by FileName` などが続くはずですが、ここではテーブル選択が重要です。`SecurityAlert` や `SecurityIncident` ではありません。
   実際の正解画像では `CloudAppEvents` が正解として選ばれています。

質問4 トピック12

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Contoso Ltd. という会社には、北米各地に本社と 5 つの支社があります。本社はシアトルにあります。支社は、トロント、マイアミ、ヒューストン、ロサンゼルス、バンクーバーにあります。Contoso  
には、ニューヨークとサンフランシスコに支社がある Fabrikam, Ltd. という子会社があります。  
  
既存の環境 -  
  
エンド ユーザー環境 -  
Contoso のすべてのユーザーは、Windows 10 デバイスを使用しています。各ユーザーには、Microsoft 365 のライセンスが付与されています。また、Contoso の営業チームのメンバーには iOS デバイスが配布されています。  
  
クラウドとハイブリッド インフラストラクチャ -  
Contoso のすべてのアプリケーションは Azure にデプロイされています。Microsoft  
Cloud App Security を有効にします。Contoso  
と Fabrikam は、異なる Azure Active Directory (Azure AD) テナントを持っています。  
  
現在の問題 -  
Contoso 社のセキュリティチームは、多数のサイバーセキュリティアラートを受信して​​います。セキュリティチームは、どのサイバーセキュリティアラートが正当な脅威で、どれがそうでないかを特定するのに多くの時間を費やしています。  
Contoso の営業チームは、iOS デバイスのみを使用しています。営業チームのメンバーは、さまざまなサードパーティ ツールを使用して顧客とファイルを交換しています。過去に、営業チームはデバイスがフィッシング攻撃を受けたことがあります。Contoso  
のマーケティング チームには、外部ベンダーとのコラボレーション用に複数の Microsoft SharePoint Online サイトがあります。マーケティング チームでは、ベンダーがマルウェアを含むファイルをアップロードするインシデントが何度か発生しています。Contosoの経営陣は、セキュリティ侵害の疑いがあります。経営陣は、Microsoft Cloud App Security で保護されたアプリケーションのデータ アクセス、ダウンロード、削除など、  
過去 48 時間以内に 6 件を超えるアクティビティがあったファイルを特定するよう依頼しています。要件 -計画されている変更 - Contoso は、両社のセキュリティ操作を統合し、すべてのセキュリティ操作を一元管理する予定です。技術要件 - Contoso では、次の技術要件を特定しています。Azure仮想マシンがブルート フォース攻撃を受けている場合にアラートを受信します。Azure Sentinel を使用して、環境に対するアクティブな攻撃を迅速に修復することで、組織のリスクを軽減します。Contoso と Fabrikam の Azure AD テナント間でデータを相関させる Azure Sentinel クエリを実装します。Fabrikamの Azure Defender for Key Vault アラートを、外部攻撃者や自社の Azure AD アプリケーションへの潜在的な侵害が発生した場合に修復する手順を開発します。特定の国から初めて Azure リソースへのサインインに失敗したユーザーのケースをすべて特定します。ジュニアセキュリティ管理者から、次の不完全なクエリが提供されます。BehaviorAnalytics \- | where ActivityType == "FailedLogOn" | where \_\_\_\_\_\_\_\_ == True  
  
質問 ホットスポット -  
技術要件を満たすために、Contoso と Fabrikam に Azure Sentinel クエリを実装する必要があります。  
ソリューションには何を含めるべきですか？回答するには、回答エリアで適切な選択肢を選択してください。  
注: 正解は 1 点です。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009400001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0009500001.jpg)

**解説:**
**Litwareケーススタディ (Topic 12 Question 4):**
**要件:** 「ContosoとFabrikamのAzure ADテナント間でデータを相関させるAzure Sentinelクエリを実装する。」（クロスワークスペースクエリ）
**クエリ構成:**
Sentinel（Log Analytics）で異なるワークスペースのデータをクエリするには、`workspace('<Workspace ID>').<table>` 構文または `union` 演算子を使用します。
**Solution:**
**`union`**
**`workspace('<Contoso Workspace ID>').SecurityEvent,`**
**`workspace('<Fabrikam Workspace ID>').SecurityEvent`**
**`| where ...`**
正解画像では、`union` 演算子と `workspace` 関数を使用して、両方の組織の `SecurityEvent` テーブルを結合しています。これにより、テナント（ワークスペース）を跨いだ相関分析が可能になります。

<https://docs.microsoft.com/en-us/azure/sentinel/extend-sentinel-across-workspaces-tenants>

## トピック13 - テストレット6

質問1 トピック13

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Litware Inc. は再生可能エネルギー企業です。Litware  
には、ボストンとシアトルにオフィスがあります。Litware には、米国全土にリモート ユーザーがいます。クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境 -  
  
ID 環境 -  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。Microsoft  
  
365 環境 -  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています。Microsoft Cloud  
App Security の組み込み異常検出ポリシーはすべて有効になっています。サブスクリプションには、次の表に示すように、米国東部のAzureリージョンのリソースが含まれています。ネットワーク環境 - Litwareの各オフィスはインターネットに直接接続し、Azureサブスクリプション内の仮想ネットワークへのサイト間VPN接続を備えています。オンプレミス環境 -オンプレミスネットワークには、次の表に示すコンピューターが含まれています。  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700001.png)  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700002.png)  
  
現在の問題 -  
ユーザーが両方のオフィスに同時に接続すると、Cloud App Security で誤検知アラートが頻繁に生成されます。  
計画されている変更と要件  
  
計画されている変更 -  
Litware では、次の変更を実装する予定です。  
Azure サブスクリプションで Azure Sentinel を作成して構成します。  
Azure AD テスト ユーザー アカウントを使用して、Azure Sentinel の機能を検証します。  
  
ビジネス要件 -  
Litware では、次のビジネス要件を特定しています。  
可能な限り、最小権限の原則を使用する必要があります。  
他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
Azure Information Protection の要件  
セキュリティ ラベルが付いており、Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection の「データ検出ダッシュボード」からアクセスできる必要があります。  
Microsoft Defender for Endpoint の要件  
Microsoft Defender for Endpoint を使用して、Windows 10 コンピューター上のすべての Cloud App Security 未承認アプリをブロックする必要があります。  
Microsoft Cloud App Security の要件  
Cloud App Security は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Azure Defender の要件 -  
すべてのサーバーが同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Azure Sentinel の要件 -  
Litware は、次の Azure Sentinel の要件を満たす必要があります。  
Azure Sentinel と Cloud App Security を統合します。  
admin1 というユーザーが Azure Sentinel プレイブックを構成できるようにします。  
カスタム クエリに基づいて Azure Sentinel 分析ルールを作成します。 ルールは、プレイブックの実行を自動的に開始する必要があります。  
特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
Microsoft Office 365 への受信アクセス時にアラートを生成するテスト ルールを作成します。 Azure AD テストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。 質問 Microsoft Defender for Endpoint の要件を満たすため、CLIENT1 で実行されるクラウドアプリを制限する必要があります。  
変更すべき 2 つの構成はどれですか？ 正解はそれぞれソリューションの一部です。  
注: 正解は 1 点です。  

- A. Microsoft Defender セキュリティ センターのデバイス管理からのオンボーディング設定
- B. Cloud App Security 異常検出ポリシー
- C. Microsoft Defender セキュリティ センターの設定から高度な機能を選択する
- D. Cloud App SecurityのCloud Discovery設定

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)

**正解** [：](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)CD🗳️  

**解説:**
**Litwareケーススタディ (Topic 13 Question 1):**
**要件:** 「Microsoft Defender for Endpointの要件を満たすため、CLIENT1（Windows 10）で実行されるクラウドアプリを制限（ブロック）する必要があります。」
**要件詳細:** 「Microsoft Defender for Endpointを使用して、Windows 10コンピュータ上のすべてのCloud App Security未承認アプリをブロックする必要があります。」
**解決策（2つ）:**

1. **D. Cloud App SecurityのSettings配置 (Cloud Discovery settings)**（またはCloud App Securityポータルの設定）: 「Microsoft Defender for Endpoint統合」を有効にし、「Enforce app access (アプリへのアクセスを強制/ブロック)」の設定を行う必要があります。これにより、MDAで「Unsanctioned（未承認）」に設定したアプリがDefender for Endpointのカスタムインジケータとしてブロックされます。
2. **C. Microsoft Defender Security Centerの設定から高度な機能 (Advanced features) を選択する**: Defender for Endpoint側でも「Microsoft Defender for Cloud Apps」連携（統合）をオンにする必要があります。
**A** のオンボーディング設定はデバイスを登録するものであり、アプリブロック機能の有効化そのものではありません（前提条件ではありますが）。質問は「構成」を聞いているため、機能の有効化（Advanced features）と連携設定（Cloud App Security側）が正解のペアとなります。
※選択肢B「異常検出ポリシー」は関係ありません。
**正解は C と D です。**

*コミュニティ投票の配分*

CD（91％）

9%

質問2 トピック13

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Litware Inc. は再生可能エネルギー企業です。Litware  
には、ボストンとシアトルにオフィスがあります。Litware には、米国全土にリモート ユーザーがいます。クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境 -  
  
ID 環境 -  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。Microsoft  
  
365 環境 -  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています。Microsoft Cloud  
App Security の組み込み異常検出ポリシーはすべて有効になっています。サブスクリプションには、次の表に示すように、米国東部のAzureリージョンのリソースが含まれています。ネットワーク環境 - Litwareの各オフィスはインターネットに直接接続し、Azureサブスクリプション内の仮想ネットワークへのサイト間VPN接続を備えています。オンプレミス環境 -オンプレミスネットワークには、次の表に示すコンピューターが含まれています。  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700001.png)  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700002.png)  
  
現在の問題 -  
ユーザーが両方のオフィスに同時に接続すると、Cloud App Security で誤検知アラートが頻繁に生成されます。  
計画されている変更と要件  
  
計画されている変更 -  
Litware では、次の変更を実装する予定です。  
Azure サブスクリプションで Azure Sentinel を作成して構成します。  
Azure AD テスト ユーザー アカウントを使用して、Azure Sentinel の機能を検証します。  
  
ビジネス要件 -  
Litware では、次のビジネス要件を特定しています。  
可能な限り、最小権限の原則を使用する必要があります。  
他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
Azure Information Protection の要件  
セキュリティ ラベルが付いており、Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection の「データ検出ダッシュボード」からアクセスできる必要があります。  
Microsoft Defender for Endpoint の要件  
Microsoft Defender for Endpoint を使用して、Windows 10 コンピューター上のすべての Cloud App Security 未承認アプリをブロックする必要があります。  
Microsoft Cloud App Security の要件  
Cloud App Security は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Azure Defender の要件 -  
すべてのサーバーが同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Azure Sentinel の要件 -  
Litware は、次の Azure Sentinel の要件を満たす必要があります。  
Azure Sentinel と Cloud App Security を統合します。  
admin1 というユーザーが Azure Sentinel プレイブックを構成できるようにします。  
カスタム クエリに基づいて Azure Sentinel 分析ルールを作成します。 ルールは、プレイブックの実行を自動的に開始する必要があります。  
特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
Microsoft Office 365 への受信アクセス時にアラートを生成するテスト ルールを作成します。 Azure AD テストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。 質問 ドラッグ＆ドロップ -  
Azure Sentinel の要件を満たすには、イベントにメモを追加する必要があります。  
どの 3 つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
選択して配置:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0010000001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0010100001.png)

**解説:**
**Litwareケーススタディ (Topic 13 Question 2):**
**要件:** 「特定のIPアドレスからのデータアクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときにIPアドレスを参照できるようにします。」
**手順:**
Sentinelのハンティング結果やログ検索結果に対して行うアクションです。

1. **Select the event(s) in the investigation graph or query results**: イベントを選択します。
2. **Select Add bookmark (ブックマークを追加)**: ログの結果をブックマークとして保存する際に、メモやタグを追加できます。
   *補足*: 要件に「調査グラフ内を移動するときに...」とあるため、ブックマーク機能（Bookmarks）を使用するのが正解です。ブックマークにはエンティティマッピングとともにメモ（Notes）を追加でき、調査グラフ（Investigation Graph）で使用できます。
   **Action順序**:
   1. クエリを実行してイベントを選択。
   2. 「Add bookmark」を選択。
   3. ブックマークの詳細（エンティティマッピング、メモなど）を入力して保存。
   正解画像の順序を確認する必要がありますが、「Add bookmark」が含まれる手順が正解です。

<https://docs.microsoft.com/en-us/azure/sentinel/bookmarks>

質問3 トピック13

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Litware Inc. は再生可能エネルギー企業です。Litware  
には、ボストンとシアトルにオフィスがあります。Litware には、米国全土にリモート ユーザーがいます。クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境 -  
  
ID 環境 -  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。Microsoft  
  
365 環境 -  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています。Microsoft Cloud  
App Security の組み込み異常検出ポリシーはすべて有効になっています。サブスクリプションには、次の表に示すように、米国東部のAzureリージョンのリソースが含まれています。ネットワーク環境 - Litwareの各オフィスはインターネットに直接接続し、Azureサブスクリプション内の仮想ネットワークへのサイト間VPN接続を備えています。オンプレミス環境 -オンプレミスネットワークには、次の表に示すコンピューターが含まれています。  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700001.png)  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700002.png)  
  
現在の問題 -  
ユーザーが両方のオフィスに同時に接続すると、Cloud App Security で誤検知アラートが頻繁に生成されます。  
計画されている変更と要件  
  
計画されている変更 -  
Litware では、次の変更を実装する予定です。  
Azure サブスクリプションで Azure Sentinel を作成して構成します。  
Azure AD テスト ユーザー アカウントを使用して、Azure Sentinel の機能を検証します。  
  
ビジネス要件 -  
Litware では、次のビジネス要件を特定しています。  
可能な限り、最小権限の原則を使用する必要があります。  
他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
Azure Information Protection の要件  
セキュリティ ラベルが付いており、Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection の「データ検出ダッシュボード」からアクセスできる必要があります。  
Microsoft Defender for Endpoint の要件  
Microsoft Defender for Endpoint を使用して、Windows 10 コンピューター上のすべての Cloud App Security 未承認アプリをブロックする必要があります。  
Microsoft Cloud App Security の要件  
Cloud App Security は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Azure Defender の要件 -  
すべてのサーバーが同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Azure Sentinel の要件 -  
Litware は、次の Azure Sentinel の要件を満たす必要があります。  
Azure Sentinel と Cloud App Security を統合します。  
admin1 というユーザーが Azure Sentinel プレイブックを構成できるようにします。  
カスタム クエリに基づいて Azure Sentinel 分析ルールを作成します。 ルールは、プレイブックの実行を自動的に開始する必要があります。  
特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
Microsoft Office 365 への受信アクセス時にアラートを生成するテスト ルールを作成します。 Azure AD テストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。 質問 ホットスポット -  
Azure Sentinel の要件を満たすには、Azure Sentinel 統合を構成する必要があります。  
どうすればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正しい選択ごとに 1 ポイントが加算されます。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0010200001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0010200002.jpg)

**解説:**
**Litwareケーススタディ (Topic 13 Question 3):**
**要件:** 「Azure SentinelとCloud App Securityを統合します。」
**構成:**
**Data Connectors (データコネクタ)** ページに移動し、**Microsoft Cloud App Security (MCAS)** コネクタを選択して、「Open connector page」→「Connect」をクリックします。
Configuration steps:

1. **From the Navigation pane, select Data connectors**.
2. **Select Microsoft Cloud App Security**.
3. **Select Open connector page and click Connect**.
Sentinelにデータを取り込むための標準的な手順です。

<https://docs.microsoft.com/en-us/cloud-app-security/siem-sentinel>

質問4 トピック13

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Litware Inc. は再生可能エネルギー企業です。Litware  
には、ボストンとシアトルにオフィスがあります。Litware には、米国全土にリモート ユーザーがいます。クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境 -  
  
ID 環境 -  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。Microsoft  
  
365 環境 -  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています。Microsoft Cloud  
App Security の組み込み異常検出ポリシーはすべて有効になっています。サブスクリプションには、次の表に示すように、米国東部のAzureリージョンのリソースが含まれています。ネットワーク環境 - Litwareの各オフィスはインターネットに直接接続し、Azureサブスクリプション内の仮想ネットワークへのサイト間VPN接続を備えています。オンプレミス環境 -オンプレミスネットワークには、次の表に示すコンピューターが含まれています。  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700001.png)  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700002.png)  
  
現在の問題 -  
ユーザーが両方のオフィスに同時に接続すると、Cloud App Security で誤検知アラートが頻繁に生成されます。  
計画されている変更と要件  
  
計画されている変更 -  
Litware では、次の変更を実装する予定です。  
Azure サブスクリプションで Azure Sentinel を作成して構成します。  
Azure AD テスト ユーザー アカウントを使用して、Azure Sentinel の機能を検証します。  
  
ビジネス要件 -  
Litware では、次のビジネス要件を特定しています。  
可能な限り、最小権限の原則を使用する必要があります。  
他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
Azure Information Protection の要件  
セキュリティ ラベルが付いており、Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection の「データ検出ダッシュボード」からアクセスできる必要があります。  
Microsoft Defender for Endpoint の要件  
Microsoft Defender for Endpoint を使用して、Windows 10 コンピューター上のすべての Cloud App Security 未承認アプリをブロックする必要があります。  
Microsoft Cloud App Security の要件  
Cloud App Security は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Azure Defender の要件 -  
すべてのサーバーが同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Azure Sentinel の要件 -  
Litware は、次の Azure Sentinel の要件を満たす必要があります。  
Azure Sentinel と Cloud App Security を統合します。  
admin1 というユーザーが Azure Sentinel プレイブックを構成できるようにします。  
カスタム クエリに基づいて Azure Sentinel 分析ルールを作成します。 ルールは、プレイブックの実行を自動的に開始する必要があります。  
特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
Microsoft Office 365 への受信アクセス時にアラートを生成するテスト ルールを作成します。 Azure AD テストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。 質問 Azure Sentinel の要件とビジネス要件を満たすために、admin1 にロールベースのアクセス制御 (RBAC) ロールを割り当てる必要があります。  
どのロールを割り当てるべきですか？  

- A. 自動化オペレーター
- B. 自動化ランブックオペレーター
- C. Azure Sentinel コントリビューター
- D. Azure Sentinel Responder

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)  

*コミュニティ投票の配分*

C（100％）

質問5 トピック13

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Litware Inc. は再生可能エネルギー企業です。Litware  
には、ボストンとシアトルにオフィスがあります。Litware には、米国全土にリモート ユーザーがいます。クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境 -  
  
ID 環境 -  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。Microsoft  
  
365 環境 -  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています。Microsoft Cloud  
App Security の組み込み異常検出ポリシーはすべて有効になっています。サブスクリプションには、次の表に示すように、米国東部のAzureリージョンのリソースが含まれています。ネットワーク環境 - Litwareの各オフィスはインターネットに直接接続し、Azureサブスクリプション内の仮想ネットワークへのサイト間VPN接続を備えています。オンプレミス環境 -オンプレミスネットワークには、次の表に示すコンピューターが含まれています。  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700001.png)  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700002.png)  
  
現在の問題 -  
ユーザーが両方のオフィスに同時に接続すると、Cloud App Security で誤検知アラートが頻繁に生成されます。  
計画されている変更と要件  
  
計画されている変更 -  
Litware では、次の変更を実装する予定です。  
Azure サブスクリプションで Azure Sentinel を作成して構成します。  
Azure AD テスト ユーザー アカウントを使用して、Azure Sentinel の機能を検証します。  
  
ビジネス要件 -  
Litware では、次のビジネス要件を特定しています。  
可能な限り、最小権限の原則を使用する必要があります。  
他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
Azure Information Protection の要件  
セキュリティ ラベルが付いており、Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection の「データ検出ダッシュボード」からアクセスできる必要があります。  
Microsoft Defender for Endpoint の要件  
Microsoft Defender for Endpoint を使用して、Windows 10 コンピューター上のすべての Cloud App Security 未承認アプリをブロックする必要があります。  
Microsoft Cloud App Security の要件  
Cloud App Security は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Azure Defender の要件 -  
すべてのサーバーが同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Azure Sentinel の要件 -  
Litware は、次の Azure Sentinel の要件を満たす必要があります。  
Azure Sentinel と Cloud App Security を統合します。  
admin1 というユーザーが Azure Sentinel プレイブックを構成できるようにします。  
カスタム クエリに基づいて Azure Sentinel 分析ルールを作成します。 ルールは、プレイブックの実行を自動的に開始する必要があります。  
特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
Microsoft Office 365 への受信アクセス時にアラートを生成するテスト ルールを作成します。 Azure AD テストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。 質問 Azure Sentinel の要件を満たすには、どのルール設定を構成する必要がありますか?  

- A. ルールロジックの設定から、抑制をオフにします。
- B. Analytics ルールの詳細から、戦術を構成します。
- C. ルールロジックの設定から、エンティティをマップします。
- D. 分析ルールの詳細から、重大度を構成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)  

**解説:**
**Litwareケーススタディ (Topic 13 Question 5):**
**要件:** 「Azure ADテストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに1つのインシデントとして、個別のインシデントにグループ化する必要があります。」
**設定:**
**「Map entities in the rule logic settings (ルールロジックの設定から、エンティティをマップします)」**。
Sentinelの分析ルールで「Alert grouping（アラートのグループ化）」を正しく機能させるには、まずルールがエンティティ（この場合はAccount/User）を認識している必要があります。Entities Mappingを設定しないと、Sentinelはどのアカウントに関するアラートかを識別できず、ユーザーごとのグループ化ができません。
「Group related alerts into incidents」の設定で「Grouping by entities」を選択するためには、その前提として **Entity Mapping** が必須です。
したがって、まず行うべき重要な設定はエンティティのマッピングです。

*コミュニティ投票の配分*

C（100％）

質問6 トピック13

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Litware Inc. は再生可能エネルギー企業です。Litware  
には、ボストンとシアトルにオフィスがあります。Litware には、米国全土にリモート ユーザーがいます。クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境 -  
  
ID 環境 -  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。Microsoft  
  
365 環境 -  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています。Microsoft Cloud  
App Security の組み込み異常検出ポリシーはすべて有効になっています。サブスクリプションには、次の表に示すように、米国東部のAzureリージョンのリソースが含まれています。ネットワーク環境 - Litwareの各オフィスはインターネットに直接接続し、Azureサブスクリプション内の仮想ネットワークへのサイト間VPN接続を備えています。オンプレミス環境 -オンプレミスネットワークには、次の表に示すコンピューターが含まれています。  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700001.png)  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0009700002.png)  
  
現在の問題 -  
ユーザーが両方のオフィスに同時に接続すると、Cloud App Security で誤検知アラートが頻繁に生成されます。  
計画されている変更と要件  
  
計画されている変更 -  
Litware では、次の変更を実装する予定です。  
Azure サブスクリプションで Azure Sentinel を作成して構成します。  
Azure AD テスト ユーザー アカウントを使用して、Azure Sentinel の機能を検証します。  
  
ビジネス要件 -  
Litware では、次のビジネス要件を特定しています。  
可能な限り、最小権限の原則を使用する必要があります。  
他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
Azure Information Protection の要件  
セキュリティ ラベルが付いており、Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection の「データ検出ダッシュボード」からアクセスできる必要があります。  
Microsoft Defender for Endpoint の要件  
Microsoft Defender for Endpoint を使用して、Windows 10 コンピューター上のすべての Cloud App Security 未承認アプリをブロックする必要があります。  
Microsoft Cloud App Security の要件  
Cloud App Security は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Azure Defender の要件 -  
すべてのサーバーが同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Azure Sentinel の要件 -  
Litware は、次の Azure Sentinel の要件を満たす必要があります。  
Azure Sentinel と Cloud App Security を統合します。  
admin1 というユーザーが Azure Sentinel プレイブックを構成できるようにします。  
カスタム クエリに基づいて Azure Sentinel 分析ルールを作成します。 ルールは、プレイブックの実行を自動的に開始する必要があります。  
特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
Microsoft Office 365 への受信アクセス時にアラートを生成するテスト ルールを作成します。 Azure AD テストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。 質問 ホットスポット -  
Azure Sentinel の要件を満たす分析ルールを作成する必要があります。  
どうすればよいでしょうか？回答するには、回答エリアで適切な選択肢を選択してください。  
注: 正解は 1 点です。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0010500001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/41/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0010600001.jpg)

**解説:**
**Litwareケーススタディ (Topic 13 Question 6):**
**要件:** 「カスタムクエリに基づいてAzure Sentinel分析ルールを作成します。ルールは、プレイブックの実行を自動的に開始する必要があります。」
**構成:**
分析ルールウィザード（Analytics rule wizard）の中で、オートメーションを設定する場所を選択します。

1. **Automated response (自動応答) tab**: 分析ルールの作成ウィザードには「Automated response」タブがあります（新しいバージョンでは「Automation rules」を呼び出す形になっていますが、問題の画像がClassicウィザードの場合、このタブでPlaybookを選択します）。
2. **Select the playbook**: 実行したいPlaybookにチェックを入れます。
正解画像では、**Automated response** タブ（またはそのセクション）でPlaybookを選択している画面が示されているはずです。
（※最新のSentinelでは「Automation rules」を作成してPlaybookを紐付けますが、古い試験画面ではAnalytics Rule内で直接Playbookを指定していました。画像に従ってください）。

<https://docs.microsoft.com/en-us/azure/sentinel/tutorial-detect-threats-custom#set-automated-responses-and-create-the-rule> <https://docs.microsoft.com/en-us/azure/sentinel/tutorial-respond-threats-playbook>

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/40/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 41 ページ目を表示しています。

410件中**401 - 410**件 目を表示
