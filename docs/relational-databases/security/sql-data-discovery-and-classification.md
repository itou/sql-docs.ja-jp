---
title: SQL データの検出と分類 | Microsoft Docs
description: SQL データの検出と分類
documentationcenter: ''
ms.reviewer: vanto
ms.assetid: 89c2a155-c2fb-4b67-bc19-9b4e03c6d3bc
ms.service: sql-database
ms.prod_service: sql-database,sql
ms.custom: security
ms.topic: conceptual
ms.date: 06/10/2020
ms.author: datrigan
author: DavidTrigano
ms.openlocfilehash: 7c23b7faa93281ab34ed4b500d10dfd50e9c8c76
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85737043"
---
# <a name="sql-data-discovery-and-classification"></a>SQL データの検出と分類
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

データの検出と分類では、データベース内の機密データの**検出**、**分類**、**ラベル付け**、**レポート作成**を行うための新しいツールが導入されました。このツールは [SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) に組み込まれています。
最も機密性の高いデータ (ビジネス、財務、医療など) の検出と分類は、組織の情報保護の達成において極めて重要な役割を果たすことができます。 次のような場合にインフラストラクチャとして使用できます。
* データのプライバシー基準を満たせるようにする。
* 機密性の高いデータを含むデータベース/列へのアクセスを制御し、セキュリティを強化する。

> [!NOTE]
> データの検出と分類は、**SQL Server 2012 以降でサポートされ、[SSMS 17.5](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) 以降で使用できます**。 Azure SQL Database については、「[Azure SQL Database のデータの検出と分類](/azure/sql-database/sql-database-data-discovery-and-classification/)」を参照してください。

## <a name="overview"></a><a id="subheading-1"></a>概要
データの検出と分類では高度な一連のサービスが導入され、データベースだけでなく、データの保護を目的とした新しい SQL Information Protection パラダイムが形成されます。

* **検出および推奨事項** - 分類エンジンはデータベースをスキャンし、機密データが含まれる可能性のある列を識別します。 適切な分類の推奨事項を確認して適用するだけでなく、手動で列を分類するための簡単な方法が提供されます。
* **ラベル付け** - 列で永続的に機密分類ラベルにタグを付けることができます。
* **表示** - データベース分類状態を詳細なレポートに表示することができます。このレポートを印刷したりエクスポートしたりして、コンプライアンスと監査の目的に、またその他のニーズに合わせて使用することができます。

## <a name="discovering-classifying--labeling-sensitive-columns"></a><a id="subheading-2"></a>機微な列の検出、分類およびラベル付け
次のセクションでは、データベース内の機密データを含む列の検出、分類、およびラベル付けの手順に加え、データベースの現在の分類状態の表示とレポートのエクスポートの手順について説明します。

分類には、次の 2 つのメタデータ属性が含まれます。
* ラベル - 列に格納されるデータの機密レベルを定義するために使用される、主な分類属性です。  
* 情報の種類 - 列に格納されるデータの種類をさらに細分化します。

**SQL Server データベースを分類するには:**

1. SQL Server Management Studio (SSMS) で、SQL Server に接続します。

2. SSMS オブジェクト エクスプローラーで、分類するデータベースを右クリックして、 **[タスク]** 、 **[データの検出と分類]** 、 **[データの分類]** の順に選択します。

   ![ナビゲーション ウィンドウ][0]

3. 分類エンジンは機密データが含まれる可能性のある列についてデータベースをスキャンし、**推奨される列の分類**のリストを提供します。

    * 推奨される列の分類のリストを表示するには、上部にある推奨事項通知ボックスまたはウィンドウの下部にある推奨事項パネルをクリックします。

        ![ナビゲーション ウィンドウ][2]

        ![ナビゲーション ウィンドウ][3]

    * 推奨事項のリストを確認します。
        * 特定の列の推奨事項を承諾するには、関連する行の左側の列のチェック ボックスをオンにします。 推奨事項テーブル ヘッダーのチェック ボックスをオンにして、*すべての推奨事項* を承諾済みとしてマークすることもできます。

        * ドロップダウン ボックスを使用して、推奨される情報の種類と機密ラベルを変更することもできます。        

        ![ナビゲーション ウィンドウ][4]

    * 選択した推奨事項を適用するには、青い **[Accept selected recommendations]\(選択した推奨事項を承諾\)** ボタンをクリックします。

        ![ナビゲーション ウィンドウ][5]

4. 代わりに列を**手動で分類**することもできます。さらに、推奨事項ベースの分類について、次の操作を実行することもできます。

    * ウィンドウの上部のメニューで **[分類の追加]** をクリックします。

        ![ナビゲーション ウィンドウ][6]

    * 開いたコンテキスト メニューで、分類するスキーマ、テーブル、列の順に選択し、情報の種類と機密ラベルを選択します。 次に、コンテキスト ウィンドウの下部にある青い **[分類の追加]** ボタンをクリックします。

        ![ナビゲーション ウィンドウ][7]

5. 分類を完了し、新しい分類メタデータでデータベース列に永続的にラベル (タグ) を付けるには、ウィンドウの上部のメニューで **[保存]** をクリックします。

    ![ナビゲーション ウィンドウ][8]


6. データベースの分類状態の完全な要約を示すレポートを生成するには、ウィンドウの上部のメニューで **[レポートの表示]** をクリックします。 (レポートは SSMS を利用して生成することもできます。 レポートを生成するデータベースを右クリックし、 **[タスク]** 、 **[データの検出と分類]** 、 **[レポートの生成]** の順に選択します。)

    ![ナビゲーション ウィンドウ][9]

    ![ナビゲーション ウィンドウ][10]

## <a name="manage-information-protection-policy-with-ssms"></a><a id="subheading-3"></a>SSMS で情報保護ポリシーを管理する

[SSMS 18.4](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) 以降を利用し、情報保護ポリシーを管理できます。

1. SQL Server Management Studio (SSMS) で、SQL Server に接続します。

2. SSMS Object Explorer でお使いのデータベースの 1 つを右クリックし、 **[タスク]** 、 **[データの検出と分類]** の順に選択します。

   次のメニュー オプションで情報保護ポリシーを管理できます。

* **情報保護ポリシー ファイルの設定**: 選択されている JSON ファイルに定義されているとおりに情報保護ポリシーが使用されます。

* **情報保護ポリシーのエクスポート**: 情報保護ポリシーを JSON ファイルにエクスポートします。

* **情報保護ポリシーのリセット**: 既定の情報保護ポリシーに情報保護ポリシーがリセットされます。

> [!IMPORTANT]
> 情報保護ポリシー ファイルは SQL Server に保存されません。
> SSMS では既定の情報保護ポリシーが使用されます。 カスタマイズされた情報保護ポリシーでエラーが発生した場合、SSMS では既定のポリシーを使用できません。 データ分類でエラーが発生します。 解決するには、 **[情報保護ポリシーのリセット]** をクリックし、既定のポリシーを使用し、データ分類をもう一度有効にします。

## <a name="accessing-the-classification-metadata"></a><a id="subheading-4"></a>分類メタデータへのアクセス

SQL Server 2019 には [`sys.sensitivity_classifications`](../system-catalog-views/sys-sensitivity-classifications-transact-sql.md) というシステム カタログ ビューが導入されています。 このビューでは、情報の種類と機密ラベルが返されます。 

> [!NOTE]
> このビューには **VIEW ANY SENSITIVITY CLASSIFICATION** 権限が必要です。 詳細については、「 [Metadata Visibility Configuration](https://docs.microsoft.com/sql/relational-databases/security/metadata-visibility-configuration?view=sql-server-ver15)」を参照してください。

SQL Server 2019 インスタンスで、`sys.sensitivity_classifications` を問い合わせ、分類されているすべての列とそれらに対応する分類を確認します。 次に例を示します。 

```sql
SELECT 
    schema_name(O.schema_id) AS schema_name,
    O.NAME AS table_name,
    C.NAME AS column_name,
    information_type,
    label,
    rank,
    rank_desc
FROM sys.sensitivity_classifications sc
    JOIN sys.objects O
    ON  sc.major_id = O.object_id
    JOIN sys.columns C 
    ON  sc.major_id = C.object_id  AND sc.minor_id = C.column_id
```

SQL Server 2019 より前の場合、情報の種類と機密ラベルの分類メタデータは次の拡張プロパティにあります。 

* `sys_information_type_name`
* `sys_sensitivity_label_name`

メタデータには、拡張プロパティ カタログ ビュー [`sys.extended_properties`](../system-catalog-views/extended-properties-catalog-views-sys-extended-properties.md) を使用してアクセスすることができます。

SQL Server 2017 以前のインスタンスの場合、次の例からは、分類されているすべての列とそれらに対応する分類が返されます。

```sql
SELECT
    schema_name(O.schema_id) AS schema_name,
    O.NAME AS table_name,
    C.NAME AS column_name,
    information_type,
    sensitivity_label 
FROM
    (
        SELECT
            IT.major_id,
            IT.minor_id,
            IT.information_type,
            L.sensitivity_label 
        FROM
        (
            SELECT
                major_id,
                minor_id,
                value AS information_type 
            FROM sys.extended_properties 
            WHERE NAME = 'sys_information_type_name'
        ) IT 
        FULL OUTER JOIN
        (
            SELECT
                major_id,
                minor_id,
                value AS sensitivity_label 
            FROM sys.extended_properties 
            WHERE NAME = 'sys_sensitivity_label_name'
        ) L 
        ON IT.major_id = L.major_id AND IT.minor_id = L.minor_id
    ) EP
    JOIN sys.objects O
    ON  EP.major_id = O.object_id 
    JOIN sys.columns C 
    ON  EP.major_id = C.object_id AND EP.minor_id = C.column_id
```

## <a name="manage-classifications"></a><a id="subheading-5"></a>分類の管理

# <a name="t-sql"></a>[T-SQL](#tab/t-sql)
T-SQL を使って、列の分類を追加/削除し、データベース全体のすべての分類を取得することができます。

- 1 つ以上の列の分類の追加/更新:[ADD SENSITIVITY CLASSIFICATION](https://docs.microsoft.com/sql/t-sql/statements/add-sensitivity-classification-transact-sql)
- 1 つ以上の列の分類の削除:[DROP SENSITIVITY CLASSIFICATION](https://docs.microsoft.com/sql/t-sql/statements/drop-sensitivity-classification-transact-sql)

# <a name="powershell-cmdlet"></a>[PowerShell コマンドレット](#tab/sql-powelshell)
PowerShell コマンドレットを使用して列の分類を追加/削除し、すべての分類を取得し、データベース全体の推奨事項を取得できます。

- [Get-SqlSensitivityClassification](https://docs.microsoft.com/powershell/module/sqlserver/Get-SqlSensitivityClassification?view=sqlserver-ps)
- [Get-SqlSensitivityRecommendations](https://docs.microsoft.com/powershell/module/sqlserver/Get-SqlSensitivityRecommendations?view=sqlserver-ps)
- [Set-SqlSensitivityClassification](https://docs.microsoft.com/powershell/module/sqlserver/Set-SqlSensitivityClassification?view=sqlserver-ps)
- [Remove-SqlSensitivityClassification](https://docs.microsoft.com/powershell/module/sqlserver/Remove-SqlSensitivityClassification?view=sqlserver-ps)

---

## <a name="next-steps"></a><a id="subheading-6"></a>次のステップ

Azure SQL Database については、「[Azure SQL Database のデータの検出と分類](https://go.microsoft.com/fwlink/?linkid=866265)」を参照してください。

次の列レベルのセキュリティ メカニズムを適用して、機微な列の保護を検討してください。

* [動的データ マスク](https://docs.microsoft.com/sql/relational-databases/security/dynamic-data-masking): 使用中の機微な列を難読化します。
* [Always Encrypted](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine): 保存中の機微な列を暗号化します。

<!--Anchors-->
[SQL Data Discovery & Classification overview]: #subheading-1
[Discovering, classifying & labeling sensitive columns]: #subheading-2
[Manage information protection policy with SSMS]: #subheading-3
[Accessing the classification metadata]: #subheading-4
[Manage classifications]: #subheading-5
[Next Steps]: #subheading-6

<!--Image references-->

[0]: ./media/sql-data-discovery-and-classification/0-data-classification-explorer.png
[2]: ./media/sql-data-discovery-and-classification/2-recommendations-notification-box.png
[3]: ./media/sql-data-discovery-and-classification/3-recommendations-panel.png
[4]: ./media/sql-data-discovery-and-classification/4-recommendations.png
[5]: ./media/sql-data-discovery-and-classification/5-accept-recommendations-button.png
[6]: ./media/sql-data-discovery-and-classification/6-add-classification-button.png
[7]: ./media/sql-data-discovery-and-classification/7-manual-classification.png
[8]: ./media/sql-data-discovery-and-classification/8-save.png
[9]: ./media/sql-data-discovery-and-classification/9-view-report.png
[10]: ./media/sql-data-discovery-and-classification/10-report.png
