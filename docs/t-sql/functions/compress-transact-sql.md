---
description: COMPRESS (Transact-SQL)
title: COMPRESS (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 10/11/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: reference
f1_keywords:
- COMPRESS
- COMPRESS_TSQL
helpviewer_keywords:
- COMPRESS function
ms.assetid: c2bfe9b8-57a4-48b4-b028-e1a3ed5ece88
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 51cf2e37ae548383d7c02b3ba4028b9327857928
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88468189"
---
# <a name="compress-transact-sql"></a>COMPRESS (Transact-SQL)
[!INCLUDE [sqlserver2016-asdb-asdbmi-asa](../../includes/applies-to-version/sqlserver2016-asdb-asdbmi-asa.md)]

この関数は GZIP アルゴリズムを使用して、入力式を圧縮します。 この関数は **varbinary (max)** 型のバイト配列を返します。
  
![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>構文  
  
```sql
COMPRESS ( expression )  
```  
  
## <a name="arguments"></a>引数
*式 (expression)*  
A

* **binary(***n***)**
* **char(***n***)**
* **nchar(***n***)**
* **nvarchar(max)**
* **nvarchar(***n***)**
* **varbinary(max)**
* **varbinary(***n***)**
* **varchar(max)**

or

* **varchar(***n***)**

expression。 詳細については、「[式 &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)」を参照してください。
  
## <a name="return-types"></a>戻り値の型
圧縮された入力内容を表す **varbinary (max)**。
  
## <a name="remarks"></a>解説  
圧縮されたデータにインデックスを付けることはできません。
  
`COMPRESS` 関数は入力式のデータを圧縮します。 圧縮するデータ セクションごとに、この関数を呼び出す必要があります。 ストレージ中の行またはページ レベルでの自動データ圧縮の詳細については、「[データ圧縮](../../relational-databases/data-compression/data-compression.md)」を参照してください。
  
## <a name="examples"></a>例  
  
### <a name="a-compress-data-during-the-table-insert"></a>A. 表の挿入中にデータを圧縮する  
この例では、テーブルに挿入されるデータを圧縮する方法を示します。
  
```sql
INSERT INTO player (name, surname, info )  
VALUES (N'Ovidiu', N'Cracium',   
        COMPRESS(N'{"sport":"Tennis","age": 28,"rank":1,"points":15258, turn":17}'));  
  
INSERT INTO player (name, surname, info )  
VALUES (N'Michael', N'Raheem', compress(@info));  
```  
  
### <a name="b-archive-compressed-version-of-deleted-rows"></a>B. 削除された行の圧縮バージョンをアーカイブする  
次のステートメントは、まず `player` テーブルから古いプレーヤー レコードを削除します。 次に、領域を節約するために、レコードを圧縮形式で `inactivePlayer` テーブルに格納します。
  
```sql
DELETE FROM player  
OUTPUT deleted.id, deleted.name, deleted.surname, deleted.datemodifier, COMPRESS(deleted.info)   
INTO dbo.inactivePlayers
WHERE datemodified < @startOfYear; 
```  
  
## <a name="see-also"></a>関連項目
[文字列関数 &#40;Transact-SQL&#41;](../../t-sql/functions/string-functions-transact-sql.md)  
[DECOMPRESS &#40;Transact-SQL&#41;](../../t-sql/functions/decompress-transact-sql.md)
  
  
