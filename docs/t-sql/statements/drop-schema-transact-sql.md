---
description: DROP SCHEMA (Transact-SQL)
title: DROP SCHEMA (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/11/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- DROP SCHEMA
- DROP_SCHEMA_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- deleting schemas
- schemas [SQL Server], removing
- DROP SCHEMA statement
- dropping schemas
- removing schemas
ms.assetid: 874aa29e-c8ad-41e4-a672-900fdc58f1f6
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: f70e5b4c355414a284aaf6db1d64c7ed182cd35a
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88496835"
---
# <a name="drop-schema-transact-sql"></a>DROP SCHEMA (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  データベースからスキーマを削除します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```syntaxsql  
-- Syntax for SQL Server and Azure SQL Database  
  
DROP SCHEMA  [ IF EXISTS ] schema_name  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
DROP SCHEMA schema_name  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>引数
 *IF EXISTS*  
 **適用対象**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] から[現在のバージョン](https://go.microsoft.com/fwlink/p/?LinkId=299658)まで)。  
  
 条件付きでは既に存在する場合にのみ、スキーマを削除します。  
  
 *schema_name*  
 データベースで認識されるスキーマの名前を指定します。  
  
## <a name="remarks"></a>注釈  
 削除するスキーマは、オブジェクトが含まれていないスキーマであることが必要です。 オブジェクトがスキーマに含まれている場合、DROP ステートメントは失敗します。  
  
 スキーマに関する情報は、[sys.schemas](../../relational-databases/system-catalog-views/schemas-catalog-views-sys-schemas.md) カタログ ビューで確認できます。  
  
 **注意事項** [!INCLUDE[ssCautionUserSchema](../../includes/sscautionuserschema-md.md)]  
  
## <a name="permissions"></a>アクセス許可  
 スキーマに対する CONTROL 権限、またはデータベースに対する ALTER ANY SCHEMA 権限が必要です。  
  
## <a name="examples"></a>例  
 次の例では、まず単一の `CREATE SCHEMA` ステートメントを実行し、 `Sprockets` が所有するスキーマ `Krishna` を作成します。次にテーブル `Sprockets.NineProngs` を作成した後、`SELECT` に対して `Anibal` 権限を許可し、`SELECT` に対して `Hung-Fu` 権限を拒否します。  
  
```sql  
CREATE SCHEMA Sprockets AUTHORIZATION Krishna   
    CREATE TABLE NineProngs (source INT, cost INT, partnumber INT)  
    GRANT SELECT TO Anibal   
    DENY SELECT TO [Hung-Fu];  
GO  
```  
  
 次のステートメントでは、このスキーマを削除します。 先に、スキーマに含まれるテーブルを削除する必要があることに注意してください。  
  
```sql  
DROP TABLE Sprockets.NineProngs;  
DROP SCHEMA Sprockets;  
GO  
```  
  
  
## <a name="see-also"></a>参照  
 [CREATE SCHEMA &#40;Transact-SQL&#41;](../../t-sql/statements/create-schema-transact-sql.md)   
 [ALTER SCHEMA &#40;Transact-SQL&#41;](../../t-sql/statements/alter-schema-transact-sql.md)   
 [DROP SCHEMA (Transact-SQL)](../../t-sql/statements/drop-schema-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)  
