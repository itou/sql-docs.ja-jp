---
title: OLE DB テーブル値パラメーター向けに変更されたスキーマ行セット | Microsoft Docs
description: OLE DB テーブル値パラメーター向けに変更されたスキーマ行セット
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- schema rowsets [OLE DB]
- table-valued parameters (OLE DB), schema rowsets changed for (OLE DB)
author: pmasl
ms.author: pelopes
ms.openlocfilehash: 3140a882c29a0cc319f85a861d3f341370f1a93a
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "86008712"
---
# <a name="schema-rowsets-changed-for-ole-db-table-valued-parameters"></a>OLE DB テーブル値パラメーター向けに変更されたスキーマ行セット
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  テーブル値パラメーターをサポートするために変更または追加されたスキーマ行セットは次のとおりです。  
  
|スキーマ行セット|説明|  
|-------------------|-----------------|  
|DBSCHEMA_PROCEDURE_PARAMETERS|SS_TYPE_CATALOG_NAME および SS_TYPE_SCHEMANAME という名前の 2 つの新しい列が、行セットの末尾に追加されました。 これらの列は、今後の型に再利用できます。 TYPE_NAME 列および LOCAL_TYPE_NAME 列には、テーブル値パラメーター TABLE 型の名前が含まれます。 DATA_TYPE 列には、テーブル値パラメーターの値 DBTYPE_TABLE = 143 が含まれます。|  
|DBSCHEMA_TABLE_TYPES|この行セットは、テーブル値パラメーターをサポートするために追加されました。 これは、DBSCHEMA_TABLES と似ていますが、テーブル、ビュー、またはシノニムではなく、テーブル型のメタデータのみを返す点が異なります。 TABLE_TYPE 列の値は、'TABLE TYPE' になります。|  
|DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS|この行セットは、テーブル値パラメーターをサポートするために追加されました。 これは、DBSCHEMA_PRIMARY_KEYS と似ていますが、テーブルではなく、テーブル型の主キーのメタデータのみを返す点が異なります。|  
|DBSCHEMA_TABLE_TYPE_COLUMNS|この行セットは、テーブル値パラメーターをサポートするために追加されました。 これは、DBSCHEMA_COLUMNS と似ていますが、テーブル、ビュー、またはシノニムではなく、テーブル型の列のメタデータのみを返す点が異なります。|  
  
## <a name="see-also"></a>参照  
 [テーブル値パラメーター &#40;OLE DB&#41;](../../oledb/ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)   
 [テーブル値パラメーターの使用 &#40;OLE DB&#41;](../../oledb/ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
