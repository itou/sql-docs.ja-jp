---
description: pdw_materialized_view_column_distribution_properties (Transact-sql)
title: pdw_materialized_view_column_distribution_properties (Transact-sql)
ms.custom: seo-dt-2019
ms.date: 07/03/2019
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: jrasnick
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: d62b0e25-3226-4f87-a10a-b3a0d9555e19
author: XiaoyuMSFT
ms.author: xiaoyul
monikerRange: = azure-sqldw-latest || = sqlallproducts-allversions
ms.openlocfilehash: 2e881f982f3fba0e2af1ea977c2b18531fbad88f
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88400288"
---
# <a name="syspdw_materialized_view_column_distribution_properties-transact-sql"></a>pdw_materialized_view_column_distribution_properties (Transact-sql) 

[!INCLUDE [asa](../../includes/applies-to-version/asa.md)]

具体化されたビューの列の分布情報を表示します。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|object_id|**int**|列が所属するオブジェクトの ID。 |  
|column_id|**int**|列の ID。|  
|distribution_ordinal|**tinyint**|0 = ディストリビューション列ではありません。</br> 1 = SQL Data Warehouse は、この列を使用して具体化されたビューを分散しています。|
 
## <a name="permissions"></a>アクセス許可 

VIEW DATABASE STATE 権限が必要です。

## <a name="see-also"></a>関連項目

[具体化されるビューを使用したパフォーマンスチューニング](/azure/sql-data-warehouse/performance-tuning-materialized-views)   
[CREATE MATERIALIZED VIEW AS SELECT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-materialized-view-as-select-transact-sql?view=azure-sqldw-latest)   
[ALTER MATERIALIZED VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-materialized-view-transact-sql?view=azure-sqldw-latest)   
[Transact-sql&#41;について説明 &#40;](/sql/t-sql/queries/explain-transact-sql?view=azure-sqldw-latest)   
[sys.pdw_materialized_view_distribution_properties &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-pdw-materialized-view-distribution-properties-transact-sql?view=azure-sqldw-latest)   
[sys.pdw_materialized_view_mappings &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-pdw-materialized-view-mappings-transact-sql?view=azure-sqldw-latest)   
[DBCC PDW_SHOWMATERIALIZEDVIEWOVERHEAD &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-pdw-showmaterializedviewoverhead-transact-sql?view=azure-sqldw-latest)   
[SQL Data Warehouse and Parallel Data Warehouse Catalog Views (SQL Data Warehouse および Parallel Data Warehouse のカタログ ビュー)](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)   
[System views supported in Azure SQL Data Warehouse (Azure SQL Data Warehouse でサポートされるシステム ビュー)](/azure/sql-data-warehouse/sql-data-warehouse-reference-tsql-system-views)   
[T-SQL statements supported in Azure SQL Data Warehouse (Azure SQL Data Warehouse でサポートされる T-SQL ステートメント)](/azure/sql-data-warehouse/sql-data-warehouse-reference-tsql-statements)
