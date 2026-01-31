---
title: SC-200試験  ExamTopics
source: https://www.examtopics.com/exams/microsoft/sc-200/view/
author:
published:
created: 2026-01-18
description: Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    .
tags:
  - clippings
---
## トピック1 - 質問セット1

質問1 トピック1

ドラッグ＆ドロップ -  
Microsoft 365 Defender を使用してインシデントを調査しています。CFOLaptop  
、CEOLaptop、COOLaptop という 3 つのデバイスで失敗したサインイン認証をカウントする高度なハンティングクエリを作成する必要があります。  
クエリをどのように完成させるか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正しい選択肢は 1 つにつき 1 ポイントです。  
選択して配置:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0001100001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/#)   [議論   32](https://www.examtopics.com/exams/microsoft/sc-200/view/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0001200001.png)

**解説:**
1. テーブルの選択: `DeviceLogonEvents`

サインイン（ログオン）に関するイベントを調査する場合、最も適切なテーブルは **`DeviceLogonEvents`** です。`DeviceEvents` はプロセス作成やファイル変更など、より広範なデバイス操作を記録するテーブルであるため、ログオンに特化した調査では効率的ではありません。

2. フィルタリング: `where` ... `and`

特定のデバイス（CFOLaptop, CEOLaptop, COOLaptop）に絞り込むために `in` 演算子を使用したフィルタリングを行います。 また、UI 上で 2 番目のボックスと 3 番目のボックスの間に **「and」** が配置されているため、1 つの `where` 句内で複数の条件を繋ぐ形式になります。

- `| where DeviceName in (...)` **and** `ActionType == "LogonFailed"` これにより、「指定した 3 台のいずれか」かつ「ログオン失敗」という条件が完成します。
    
3. 集計処理: `summarize`

今回の目的は「カウントする（count）」ことです。

- **`summarize`**: データの集計（カウント、合計、平均など）を行う際に使用します。
    
- **`project`**: 特定の列を選択して表示するだけで、集計（計算）は行いません。 したがって、`count()` 関数を使用してデバイス名やログオンタイプごとに集計を行う `| summarize LogonFailures=count() by DeviceName, LogonType` が正解となります。

質問2 トピック1

組織内の他のユーザーがサインインに使用したことのない場所からユーザーがサインインしようとしたときに、セキュリティ アラートを受信する必要があります。  
どの異常検出ポリシーを使用する必要がありますか?  

- A. 不可能な旅行
- B. 匿名IPアドレスからのアクティビティ
- C. まれな国からの活動
- D. マルウェア検出

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/#)   [議論   37](https://www.examtopics.com/exams/microsoft/sc-200/view/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/#)  

*コミュニティ投票の配分*

C（100％）

**解説:**
「組織内の他のユーザーが使用したことのない場所」からのサインインは、通常とは異なる国や地域からのアクセスを示唆しており、**「まれな国からの活動 (Activity from infrequent country)」** ポリシーが該当します。

- **不可能な旅行 (Impossible travel)**: 短時間で物理的に移動不可能な2つの場所からのアクセスを検知します。
- **匿名IPアドレス (Anonymous IP)**: TorやVPNなどの匿名化プロキシからのアクセスを検知します。

質問3 トピック1

Microsoft 365 サブスクリプションをご利用で、Microsoft Defender for Office 365 を使用しています。Microsoft  
SharePoint Online サイトには機密文書が含まれています。これらの文書には、32 文字の英数字からなる顧客アカウント番号が含まれています。  
機密文書を保護するために、データ損失防止 (DLP) ポリシーを作成する必要があります。機密  
文書を検出するには、どのような方法を使用すればよいでしょうか。  

- A. SharePoint検索
- B. Microsoft 365 Defender のハンティングクエリ
- C. Azure 情報保護
- D. 正規表現パターンマッチング

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/#)   [議論   65](https://www.examtopics.com/exams/microsoft/sc-200/view/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/#)  

*コミュニティ投票の配分*

D（59％）

C（41％）

**解説:**
32文字の英数字という特定のパターン（顧客アカウント番号）を検出する場合、**正規表現 (Regular Expression)** を使用した「機密情報の種類 (Sensitive info type)」の作成が最適です。SharePointの検索機能や単なるハンティングクエリではDLPポリシーとしての自動保護・検出の要件を満たせません。

質問4 トピック1

会社では、Microsoft Office VBAマクロを含む基幹業務アプリを使用しています。  
ユーザーがOffice VBAマクロから追加のペイロードをダウンロードして子プロセスとして実行することを防止する必要があります。  
この目標を達成するために実行できる2つのコマンドはどれですか？ 正解はそれぞれ完全なソリューションを示しています。  
注：正解はそれぞれ1点です。A  
.  
![](https://www.examtopics.com/assets/media/exam-media/04261/0001400001.png)  
B.  
![](https://www.examtopics.com/assets/media/exam-media/04261/0001400002.png)  
C.  
![](https://www.examtopics.com/assets/media/exam-media/04261/0001400003.png)  
D.  
![](https://www.examtopics.com/assets/media/exam-media/04261/0001400004.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/#)   [議論   49](https://www.examtopics.com/exams/microsoft/sc-200/view/#)

**解説:**
この問題の核心は、「防止 (Prevent/Block)」するために必要な設定値と、PowerShell のコマンドレットの使い分けにあります。

1. 「防止」するためのアクション設定

ユーザーが Office VBA マクロから子プロセスを実行することを **防止** するには、ASR ルールのアクションを **`Enabled`**（有効/ブロック）に設定する必要があります。

- **`Enabled`**: ルールに合致する動作をブロックします。
    
- **`AuditMode`**: 動作をログに記録しますが、実行自体はブロックしません。
    

このため、アクションに `AuditMode` を指定している **B** と **C** は、今回の要件を満たしません。

2. コマンドレットの使い分け (`Add` vs `Set`)

Microsoft Defender の設定を変更する際、以下の 2 つのコマンドレットはどちらも有効な設定方法となります。

- **`Add-MpPreference`**: 既存の設定（他の ASR ルールなど）を保持したまま、新しいルールを追加します。
    
- **`Set-MpPreference`**: 指定したプロパティの設定を上書き（または構成）します。
    

問題文に「2 つのコマンド」とあり、「それぞれが完全なソリューションを示す」とされているため、`Enabled` を指定している **A** と **D** が正解となります。

質問5 トピック1

あなたの会社ではMicrosoft Defender for Endpointを使用しています。  
マクロを含むMicrosoft Word文書が社内に存在し、経理チームのデバイスで頻繁に使用されています。  
既存のセキュリティ体制を維持しながら、アラートキュー内の誤検知を非表示にする必要があります。  
実行すべき3つのアクションはどれですか？ それぞれの正解は解決策の一部を示しています。  
注：正解は1つにつき1ポイントです。  

- A. アラートを自動的に解決します。
- B. アラートを非表示にします。
- C. 任意のデバイスを対象とする抑制ルールを作成します。
- D. デバイス グループを対象とする抑制ルールを作成します。
- E. アラートを生成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/#)   [議論   87](https://www.examtopics.com/exams/microsoft/sc-200/view/#)

**正解:** BDE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/#)  

*コミュニティ投票の配分*

BDE（82％）

**解説:**
誤検知（False Positive）を管理しつつセキュリティ体制を維持するためには、以下の対応が適切です。

- **B. アラートを非表示にする (Hide the alert)**: 既存の特定のアラートを非表示にし、キューを整理します。
- **D. 抑制ルールを作成する (Create a suppression rule)**: 特定の条件（デバイスグループなど）に一致するイベントに対して、将来的にアラートが生成されないようにします（または自動的に解決します）。
- **E. アラートを生成 (Generate alert)**: （※選択肢の意味が文脈上不明確ですが、除外設定や分類に関連する操作を指している可能性があります。一般的にはBとDが主要な管理手法です。）
推奨されるアプローチは、誤検知として分類し、類似のアラートに対して抑制ルールを作成することです。

他の

質問6 トピック1

ドラッグ＆ドロップ -  
次の図に示すように、Cloud App Security ポータルを開きます。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0001500001.jpg)  
お使いの環境では Microsoft Defender for Endpoint が有効になっていません。Launchpad  
アプリのリスクを修復する必要があります。  
どの 4 つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
選択して配置:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0001600001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/#)   [議論   20](https://www.examtopics.com/exams/microsoft/sc-200/view/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0001700001.png) 参照:  
<https://docs.microsoft.com/en-us/cloud-app-security/governance-discovery>

**解説:**
Microsoft Defender for Endpointが統合されていない環境で、Cloud App Security (Defender for Cloud Apps) を使用して特定アプリ（Launchpad）をブロックする手順は以下の通りです。

1. **アプリを選択する**: Cloud App Securityポータルで該当アプリを見つけます。
2. **「認可されていない (Unsanctioned)」としてタグ付けする**: これによりブロック対象としてマークされます。
3. **ブロック スクリプトを生成する**: エンドポイント統合がないため、ファイアウォールやプロキシ用のアプライアンス固有のスクリプトを生成する必要があります。
4. **スクリプトを実行する**: 生成したスクリプトを境界デバイス（ファイアウォール等）で実行して通信を遮断します。

質問7 トピック1

ホットスポット -  
Microsoft 365 E5 サブスクリプションをご利用です。Microsoft  
365 Defender を使用してクロスドメイン調査を実施する予定です。  
悪意のあるメール添付ファイルの影響を受けるデバイスを特定するための高度なハンティングクエリを作成する必要があります。  
クエリはどのように完成させるべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正解は1つにつき1ポイントです。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0001800001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/#)   [議論   31](https://www.examtopics.com/exams/microsoft/sc-200/view/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0001900001.png) 参照:  
<https://docs.microsoft.com/en-us/microsoft-365/security/mtp/advanced-hunting-query-emails-devices?view=o365-worldwide>

**解説:**
このクエリは、「メールのデータ」と「デバイス上のファイル操作データ」という 2 つの異なるドメインを結合して調査する、クロスドメインクエリの典型的な構成です。

1. `join`（1 番目のドロップダウン）

`EmailAttachmentInfo` テーブル（メールの添付ファイル情報）と `DeviceFileEvents` テーブル（デバイス上のファイル操作情報）を関連付けるには、共通のキー（今回は `SHA256` ハッシュ値）を使用してテーブルを結合する必要があります。そのため、**`join`** 演算子を使用します。

2. `project`（2 番目のドロップダウン）

`join` の括弧内にある `DeviceFileEvents` から、結合に必要な `SHA256` と、後で表示したい `FileName` だけを抽出しています。このように、特定の列のみを選択（投影）する演算子は **`project`** です。結合前に列を絞り込むことは、クエリのパフォーマンス向上にも繋がります。

3. `project`（3 番目のドロップダウン）

クエリの最後で、最終的に表示したい列（タイムスタンプ、デバイス名、受信者アドレスなど）をリストアップしています。ここでも、出力結果に含める列を指定するために **`project`** 演算子を使用します。

質問8 トピック1

Microsoft 365 Defender で、次のような高度なハンティングクエリがあります。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0002000001.png)  
過去 24 時間以内に、Microsoft Defender で管理されているデバイスで、何らかのプロセスによってシステムの復元が無効化された場合にアラートを受信する  
必要があります。実行すべき 2 つのアクションはどれですか？ 正解はそれぞれ、解決策の一部を示しています。  
注: 正解はそれぞれ 1 ポイントです。  

- A. 検出ルールを作成します。
- B. 抑制ルールを作成します。
- C. クエリに | order by Timestamp を追加します。
- D. DeviceProcessEventsをDeviceNetworkEventsに置き換えます。
- E. クエリの出力に DeviceId と ReportId を追加します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/#)   [議論   21](https://www.examtopics.com/exams/microsoft/sc-200/view/#)

**正解:** AE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/#)  

*コミュニティ投票の配分*

AE（88％）

12%

**解説:**
高度なハンティングクエリの結果に基づいてアラートを受信するには、**「検出ルール (Detection Rule) の作成」** (A) が必要です。
カスタム検出ルールを作成するためには、クエリの出力に特定の影響を受けるエンティティ情報が含まれている必要があります。デバイス関連のアラートであれば、**`DeviceId`** や `ReportId`、`Timestamp` などのカラムが必須となります (E)。これらを含めることで、アラートが特定のデバイスに関連付けられます。

質問9 トピック1

新たなランサムウェアの亜種を展開する潜在的な攻撃を調査しています。3  
つのカスタムデバイスグループがあり、これらのグループには機密性の高い情報が保存されているデバイスが含まれています。  
すべてのデバイスに対して自動アクションを実行する予定です。  
デバイスに対してアクションを実行するには、マシンを一時的にグループ化する必要があります。  
実行すべき3つのアクションはどれですか？ それぞれの正解は、解決策の一部を示しています。  
注：正解は1つにつき1ポイントです。  

- A. デバイス グループにタグを割り当てます。
- B. デバイス ユーザーを管理者ロールに追加します。
- C. マシンにタグを追加します。
- D. ランク 1 の新しいデバイス グループを作成します。
- E. 新しい管理者ロールを作成します。
- F. ランク 4 の新しいデバイス グループを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/#)   [議論   22](https://www.examtopics.com/exams/microsoft/sc-200/view/#)

**正解:** ACD [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/#)  

*コミュニティ投票の配分*

ACD（98％）

2%

**解説:**
ランサムウェア攻撃などへの対応として、特定のデバイス群に対して一時的に強力な制限や自動対処を適用する場合の一般的な手法です。

1. **新しいデバイスグループを作成する (D)**: 修復用の一時的なグループを作成します。このグループは既存のグループより優先度（ランク）を高く設定します（ランク1など）。
2. **タグを追加する (C)**: 対象のデバイスに特定のタグ（例: "Remediation"）を付与します。
3. **デバイスグループにタグを割り当てる (A)**: 作成したデバイスグループの条件として、そのタグを指定します。
これにより、タグ付けされたデバイスは自動的に優先度の高い「修復用グループ」に移動し、そのグループに設定された自動修復設定が適用されます。

質問10 トピック1

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
Defender for Identity と Active Directory の統合を構成しています。Microsoft  
Defender for Identity ポータルから、攻撃者が悪用できる複数のアカウントを構成する必要があります。  
解決策: エンティティタグから、アカウントをハニートークンアカウントとして追加します。  
これで目標は達成されますか?  

- A. はい
- B. いいえ

**解説:**
Defender for Identity においてハニートークンアカウント（Sensitve account / Honeytoken account）を設定する場合、個々のエンティティ（ユーザー）のタグ設定画面から行うのではなく、**Microsoft 365 Defender ポータルの「設定」→「ID (Identities)」→「エンティティタグ (Entity tags)」** メニューから、対象のアカウントをハニートークンとしてリストに追加するのが正しい手順です。したがって、提案された解決策は誤りです。
