---
title: 次のフェッチ位置 (OLE DB ドライバー) | Microsoft Docs
description: 行のフェッチ - 次のフェッチ位置
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- fetching rows
- OLE DB rowsets, fetching
- next fetch position
- rowsets [OLE DB], fetching
author: pmasl
ms.author: pelopes
ms.openlocfilehash: d6fd65f54f0c6f6aa219595e1948ce758c50b4db
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87244203"
---
# <a name="fetching-rows---next-fetch-position-ole-db-driver"></a>行のフェッチ - 次のフェッチ位置 (OLE DB ドライバー)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  OLE DB Driver for SQL Server は次のフェッチ位置を追跡します。その結果、**GetNextRows** メソッドの一連の呼び出しでは、行をスキップしたり、同じ行を繰り返すことなく、行セット全体が読み取られます。この場合、この一連の呼び出しの間に、スキップされたり、読み取る方向が変更されたり、**FindNextRow**、**Seek**、または **RestartPosition** の各メソッドの呼び出しによって中断されることはありません。 **IRowset::GetNextRows**、**IRowset::RestartPosition**、または **IRowsetIndex::Seek** を呼び出すか、*pBookmark* 値に NULL を指定して **FindNextRow** を呼び出すことにより、次のフェッチ位置が変更されます。 *pBookmark* 値に NULL 以外の値を指定して **FindNextRow** を呼び出しても、次のフェッチ位置には影響しません。  
  
## <a name="see-also"></a>参照  
 [行のフェッチ](../../oledb/ole-db-rowsets/fetching-rows.md)  
  
  
