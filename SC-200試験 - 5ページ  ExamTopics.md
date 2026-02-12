質問#41 トピック1

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft 365 Defender をご利用いただいています。Microsoft が発見した新たな攻撃手法を確認し、サブスクリプション内の脆弱なリソースを特定する必要があります。ソリューションは管理作業を最小限に抑える必要があります。Microsoft 365 Defender ポータルではどのブレードを使用すればよいでしょうか？

- A. 高度な狩猟
- B. 脅威分析
- C. インシデントとアラート
- D. 学習ハブ

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)  

**解説:**
Microsoftが発見した新たな攻撃手法（新しい脅威、キャンペーンなど）に関する情報を確認し、自社の環境（サブスクリプション）内のどのリソースが脆弱であるか（軽減策が未適用のデバイスなど）を特定するには、**「脅威分析 (Threat Analytics)」** ブレードを使用します。
脅威分析には、アナリストレポート、関連するアラート、および影響を受ける資産や軽減策のステータスが含まれており、管理者は効率的にリスクを把握し対処できます。

質問#43 トピック1
  
Microsoft Defender 365 を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
ネットワークには、Azure AD と同期するオンプレミスの Active Directory Domain Services (AD DS) ドメインが含まれています。
デバイスと AD DS ドメイン コントローラーに記録された直近 100 件のサインイン試行を特定する必要があります。KQLクエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image183.png)

**正解:** ![](https://img.examtopics.com/sc-200/image184.png)

**解説:**
このクエリの目的は、**「デバイス」**と**「ドメインコントローラー」**の両方で記録された直近 100 件のサインイン試行を特定することです。

1. テーブルの選択: `IdentityLogonEvents`

- **DeviceLogonEvents:** Microsoft Defender for Endpoint がインストールされた**デバイス（エンドポイント）**上でのローカルログオンやネットワークログオンを記録します（すでにクエリの最初に記載されています）。
    
- **IdentityLogonEvents:** Microsoft Defender for Identity が監視している **Active Directory ドメインコントローラー (AD DS)** 上でのログオンアクティビティを記録します。問題文の「AD DS ドメイン コントローラーに記録された」という要件を満たすには、このテーブルが必要です。
    
    - _IdentityInfo_ はユーザーの属性情報（部署やタイトルなど）、_IdentityQueryEvents_ は LDAP クエリなどの情報を扱うため、サインイン試行の特定には適しません。
        

2. 演算子の選択: `union`

- **union:** 2つ以上のテーブルの結果（行）を**統合して1つのリスト**にするために使用します。今回は「デバイスのログ 100 件」と「ドメインコントローラーのログ 100 件」を合わせて表示したいため、`union` が適切です。
    
- **join:** 2つのテーブルを共通の列（AccountSid など）で結合し、1つの行に情報を横に並べるために使用します。今回の「ログを列挙する」という目的には適しません。

質問#44 トピック1
  
Microsoft Defender 365 を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
ネットワークには、Azure AD と同期するオンプレミスの Active Directory Domain Services (AD DS) ドメインが含まれています。AD DS ユーザーによる LDAP 要求を識別し、AD DS オブジェクトを列挙する必要があります。KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image185.png)

**正解:** ![](https://img.examtopics.com/sc-200/image186.png)

**解説:**
1. テーブルの選択: `IdentityQueryEvents`

- **IdentityQueryEvents:** Active Directory に対して行われた **LDAP 要求**、DNS クエリ、Samr クエリなどの「クエリ（照会）」アクティビティを記録するテーブルです。問題文にある「LDAP 要求を識別し、AD DS オブジェクトを列挙する」という目的に直接合致するのはこのテーブルです。
    
- _IdentityDirectoryEvents:_ グループ メンバーシップの変更やパスワード変更など、ディレクトリ オブジェクトの「変更」に関連するイベントを記録します。
    
- _IdentityInfo:_ ユーザーの部署、役職、グループ所属などの「属性情報（メタデータ）」を保持するテーブルであり、アクティビティのログではありません。
    

2. 関数の選択: `isnotempty`

- **isnotempty:** 指定された列（この場合は `AccountSid`）に値が入っている（空ではない）行のみを抽出します。
    
- 構文として `| where isnotempty(AccountSid)` とすることで、「実行したユーザーの SID が記録されている（＝匿名ではない特定のユーザーによる）クエリ」に絞り込むことができます。
    
    - _contains_ や _has_ は「特定の文字列が含まれているか」を検索する**演算子**です。これらを使用する場合は `| where AccountSid contains "S-1-5-..."` のように比較対象の文字列が必要ですが、今回の構文 `| where [ ] (AccountSid)` は関数を呼び出す形式になっているため、`isnotempty` が適切です。

質問#45 トピック1

Microsoft Defender 365 を使用する Microsoft 365 E5 サブスクリプションをお持ちです。Microsoft Defender for Cloud Apps の統合監査ログのデータを使用して脅威を調査できるようにする必要があります。  
  
まず何を設定すればよいでしょうか？

- A. ユーザーエンリッチメント設定
- B. Azureコネクタ
- C. Office 365コネクタ
- D. 自動ログアップロード設定

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)  

**解説:**
Microsoft Defender for Cloud Apps (MDCA) で統合監査ログ（Unified Audit Log）のデータを使用して脅威を調査するには、Microsoft 365（Office 365）とMDCAを接続する必要があります。
これを行うには、**「Office 365コネクタ (Office 365 connector)」** を設定します（現在は「アプリコネクタ」設定でOffice 365を接続します）。これにより、Office 365のアクティビティログがMDCAに取り込まれ、調査やポリシー適用が可能になります。

質問#46 トピック1

次のKQLクエリを含むカスタム検出ルールがあります。  
  
![](https://img.examtopics.com/sc-200/image187.png)  
  
以下の各文について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注：正しい選択ごとに1ポイント獲得できます。  
  
![](https://img.examtopics.com/sc-200/image188.png)

**正解:** ![](https://img.examtopics.com/sc-200/image413.png)

**解説:**
Microsoft Defender 365 のカスタム検出ルールで自動応答アクション（ファイルの削除やデバイスの隔離など）を有効にするには、クエリの結果に**特定のアクションごとに定義された必須の列**が含まれている必要があります。

1. 電子メールの削除について（いいえ）

電子メールに対するアクション（削除や移動など）を自動化するには、クエリの結果に以下の **2 つの列が両方とも**含まれている必要があります。

- `NetworkMessageId`
- `RecipientEmailAddress`

提示されたクエリの最後の `summarize` 文を見ると、`RecipientEmailAddtess`（スペルミスがありますが、受信者アドレス用の列と見なせます）は含まれていますが、**`NetworkMessageId` が含まれていない**ため、メールの削除アクションを自動化することはできません。

2. アプリ実行の制限について（はい）

デバイス（エンドポイント）に対するアクションである「アプリ実行の制限」や「デバイスの隔離」を行うには、以下の列が必要です。

- `DeviceId`

クエリの投影（`summarize`）には **`DeviceId` 列が含まれている**ため、このルールを使用して特定のデバイス上でのアプリ実行を自動的に制限することが可能です。

3. ファイルの削除について（はい）

ファイルに対するアクション（ファイルの削除やクリーンアップ）を行うには、以下の **2 つの列が両方とも**含まれている必要があります。

- `SHA256`
- `DeviceId`（どのデバイスから削除するかを特定するため）

クエリの結果には **`SHA256` と `DeviceId` の両方が含まれている**ため、このルールに基づいて一致したファイルを自動的に削除するように設定できます。

質問#47 トピック1

Microsoft Defender for Servers プラン 1 を使用する Azure サブスクリプションがあり、Server1 というサーバーが含まれています。  
  
エージェントレス スキャンを有効にしています。Server1 がスキャンされないようにする必要があります。このソリューションでは、管理の手間を最小限に抑える必要があります。  
  
どうすればよいでしょうか？

- A. 除外タグを作成します。
- B. サブスクリプションを Defender for Servers プラン 2 にアップグレードします。
- C. ガバナンス ルールを作成します。
- D. 排他グループを作成します。

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)  

**解説:**
Defender for Servers Plan 2（またはCSPM）の機能である「エージェントレススキャン (Agentless scanning)」から特定のサーバーを除外するには、**「除外タグ (Exclusion tag)」** を使用します。
スキャン設定画面で、除外したいマシンに付与されているタグとその値を指定することで、そのタグを持つマシンをスキャンの対象外にすることができます。これは管理の手間が少ない方法です。

質問#48 トピック1

機密ファイルが外部に共有された場合にアラートを生成し、修復アクションをトリガーするように、Microsoft Defender for Cloud Apps を構成する必要があります。Microsoft 365 Defender ポータルで実行する必要がある 2 つのアクションはどれですか？ 正解はそれぞれ解答の一部を示しています。  
  
注: 正解は 1 点です。

- A. \[設定\] から \[Information Protection\] を選択し、\[Azure Information Protection\] を選択してから、\[このテナントからの Azure Information Protection 分類ラベルとコンテンツ検査警告のファイルのみをスキャンする\] を選択します。
- B. クラウドアプリから「ファイル」を選択し、「ファイルの種類」を「ドキュメント」にフィルターします。
- C. 「設定」から「情報保護」を選択し、「ファイル」を選択して、ファイル監視を有効にします。
- D. クラウド アプリから \[ファイル\] を選択し、アプリを Office 365 にフィルターします。
- E. クラウド アプリから \[ファイル\] を選択し、検索から \[新しいポリシー\] を選択します。
- F. \[設定\] から \[Information Protection\] を選択し、\[Azure Information Protection\] を選択してから、\[Azure Information Protection 分類ラベルとコンテンツ検査の警告について新しいファイルを自動的にスキャンする\] を選択します。

## 正解: **C** と **F**

**C. 設定 → Information Protection → ファイル → ファイル監視を有効にする**
**F. 設定 → Information Protection → Azure Information Protection → 新しいファイルを自動的にスキャンする**

## 詳細な解説:

### 必要な2つのアクション:

**✓ 選択肢C: ファイル監視を有効にする**

**場所**: 設定 → Information Protection → ファイル → **Enable file monitoring**

**理由**:

- これはDefender for Cloud Appsでファイルポリシーを機能させるための**必須の前提条件**です
- ドキュメントより: _"Select Enable file monitoring and then select Save"_
- ファイル監視が有効でないと、ファイルポリシーは作成できても機能しません

**✓ 選択肢F: 新しいファイルを自動的にスキャンする**

**場所**: 設定 → Information Protection → Azure Information Protection (現在はMicrosoft Information Protection) → **Automatically scan new files for sensitivity labels and content inspection warnings**

**理由**:

- 機密ラベルが付いたファイルを検出するために必要です
- ドキュメントより: _"Automatically scan new files for Microsoft Information Protection sensitivity labels and content inspection warnings"_
- これにより、新しくアップロードされたファイルが自動的にスキャンされ、機密ラベルが識別されます

### 他の選択肢が正解でない理由:

**✗ 選択肢A: このテナントからのみスキャン**

- これはオプションの設定で、外部テナントのラベルを除外します
- 必須ではありません

**✗ 選択肢B: ファイルの種類でフィルター**

- これは単なる表示フィルターです
- ポリシー設定には影響しません

**✗ 選択肢D: アプリでフィルター**

- これも表示フィルターです
- 構成手順ではありません

**✗ 選択肢E: ファイルから新しいポリシーを選択**

- 正しいパスは「ポリシー → ポリシー管理」から作成します
- また、これは3番目のステップ（ポリシー作成）であり、最初に必要な2つの設定ではありません

### 完全な構成手順:

1. **ファイル監視を有効化**（選択肢C）

```
   設定 → Information Protection → Files → Enable file monitoring → 保存
```

2. **自動スキャンを有効化**（選択肢F）

```
   設定 → Information Protection → Microsoft Information Protection 
   → Automatically scan new files → 保存
```

3. **ファイルポリシーを作成**（次のステップ）

```
   クラウドアプリ → ポリシー → ポリシー管理 → ポリシーの作成 → ファイルポリシー
   - Access Level = External
   - Sensitivity label = Confidential
   - Alerts: Create alert for each matching file
   - Governance actions: Remove external users など
```

### 結論:

**正解: C + F**

この2つの設定により、機密ファイルの外部共有を検出し、アラートと修復アクションをトリガーする準備が整います。これらは、効果的なファイルポリシーを作成するための**必須の前提条件**です。

質問#49 トピック1

ネットワークには、Azure AD と同期するオンプレミスの Active Directory Domain Services (AD DS) ドメインが含まれています。Microsoft Defender 365 を使用する Microsoft 365 E5 サブスクリプションを所有しています。  

会社の財務部門のユーザーによる対話型認証の試行をすべて特定する必要があります。KQL クエリをどのように完了すればよいでしょうか？回答するには、回答領域で適切なオプションを選択してください。  

注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image190.png)

**正解:** ![](https://img.examtopics.com/sc-200/image191.png)

**解説:**
財務部門（Finance）のユーザーによる対話型認証（Interactive authentication）を特定するクエリです。

1. **`IdentityLogonEvents`**: IDログオンイベントテーブルを使用します。
2. **`where Application == 'Active Directory'`**: オンプレミスADのイベントを対象とする場合、このフィルタが入ることがあります（または`IdentityDirectoryEvents`を使うケースもありますが、ログオンタイプと部門で絞るならこちら）。
3. **`where LogonType == 'Interactive'`**: 対話型ログオンに絞り込みます。
4. **`where Department == 'Finance'`**: ユーザーの部門属性が'Finance'であるログに絞り込みます。（※`Department`情報はエンリッチメントデータとして利用可能な場合があります。）

質問#50 トピック1

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft Defender for Endpoint をご利用いただいています。  
  
マルウェアアラートをトリガーしたデバイスを特定し、アラートに関連する証拠を収集する必要があります。このソリューションでは、結果に基づいて影響を受けたデバイスのデバイス分離を開始できるようにする必要があります。Microsoft 365 Defender ポータルでは何を使用すればよいでしょうか？

- A. 事件
- B. 修復
- C. 調査
- D. 高度な狩猟

**正解: A. 事件（インシデント）**

**理由:**

**インシデント（事件）**は、Microsoft 365 Defenderにおいて、関連するアラートとその証拠を自動的に集約し、包括的な調査と対応を可能にする機能です。

インシデントを使用することで:

1. **関連アラートの集約**: マルウェアアラートをトリガーしたデバイスに関連するすべてのアラートが1つのインシデントにまとめられます
2. **証拠の自動収集**: デバイス、ユーザー、メールボックス、ファイルなど、アラートに関連するすべての証拠が自動的に収集され、インシデント内で確認できます
3. **修復アクションの実行**: インシデント画面から直接、**デバイス分離**などの修復アクションを開始できます。影響を受けたデバイスを特定し、右クリックまたはアクションメニューから「デバイスの分離」を選択できます
4. **統合された調査体験**: すべての関連情報が1か所に集約されており、効率的な調査と対応が可能です

**なぜ他の選択肢は不適切か:**

- **B. 修復**: アクションセンターでの修復は、承認待ちや完了した修復アクションを確認する場所であり、初期調査には適していません
- **C. 調査**: 自動調査は有用ですが、デバイス分離などの手動修復アクションを直接開始する包括的なインターフェースとしては、インシデントの方が適しています
- **D. 高度な狩猟**: KQLクエリを使用した能動的な脅威ハンティングツールであり、既に発生したアラートへの対応には適していません