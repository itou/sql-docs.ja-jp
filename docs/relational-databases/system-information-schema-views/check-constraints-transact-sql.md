---
description: CHECK_CONSTRAINTS (Transact-sql)
title: CHECK_CONSTRAINTS (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- CHECK_CONSTRAINTS
- CHECK_CONSTRAINTS_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- CHECK_CONSTRAINTS view
- INFORMATION_SCHEMA.CHECK_CONSTRAINTS view
ms.assetid: e9577fd2-c349-4dff-874c-9e57d2e5a3ec
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 93226ed2c3136276f20512b2fd280fcbf2571ff2
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89550183"
---
# <a name="check_constraints-transact-sql"></a>CHECK_CONSTRAINTS (Transact-sql)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  現在のデータベースの CHECK 制約ごとに1行のデータを返します。 この情報スキーマビューでは、現在のユーザーがアクセス許可を持っているオブジェクトに関する情報が返されます。  
  
 これらのビューから情報を取得するには、INFORMATION_SCHEMA の完全修飾名を指定し **ます。**_view_name_。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**CONSTRAINT_CATALOG**|**nvarchar (** 128 **)**|制約修飾子。|  
|**CONSTRAINT_SCHEMA**|**nvarchar (** 128 **)**|制約が属するスキーマの名前。<br /><br /> &#42;&#42; 重要 &#42;&#42; では、オブジェクトのスキーマを決定するために INFORMATION_SCHEMA ビューを使用しないでください。 INFORMATION_SCHEMA ビューは、オブジェクトのメタデータのサブセットのみを表します。 オブジェクトのスキーマを調べる唯一の信頼性のある方法は、sys.objects カタログ ビューに対するクエリを実行する方法です。|  
|**CONSTRAINT_NAME**|**sysname**|制約名。|  
|**CHECK_CLAUSE**|**nvarchar (** 4000 **)**|[!INCLUDE[tsql](../../includes/tsql-md.md)] 定義ステートメントの実際のテキスト|  
  
## <a name="see-also"></a>参照  
 [システムビュー &#40;Transact-sql&#41;](https://msdn.microsoft.com/library/35a6161d-7f43-4e00-bcd3-3091f2015e90)   
 [情報スキーマビュー &#40;Transact-sql&#41;](~/relational-databases/system-information-schema-views/system-information-schema-views-transact-sql.md)   
 [check_constraints &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-check-constraints-transact-sql.md)   
 [sys.objects &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)  
  
  
