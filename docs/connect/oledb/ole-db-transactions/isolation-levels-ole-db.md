---
title: 分離レベル (OLE DB ドライバー) | Microsoft Docs
description: 分離レベル (OLE DB)
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- isolation levels [OLE DB]
- transactions [OLE DB]
- OLE DB Driver for SQL Server, transactions
author: pmasl
ms.author: pelopes
ms.openlocfilehash: 60fce8b96ff116f1c1e92a75e1335a33207d36d3
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87244103"
---
# <a name="isolation-levels-ole-db"></a>分離レベル (OLE DB)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] クライアントは、接続のトランザクション分離レベルを制御できます。 OLE DB Driver for SQL Server のコンシューマーは、次の方法を使用してトランザクション分離レベルを制御します。  
  
-   OLE DB Driver for SQL Server の既定の自動コミット モードには、DBPROPSET_SESSION プロパティの DBPROP_SESS_AUTOCOMMITISOLEVELS。  
  
     OLE DB Driver for SQL Server の既定のレベルは、DBPROPVAL_TI_READCOMMITTED です。  
  
-   ローカルの手動コミット トランザクションには、**ITransactionLocal::StartTransaction** メソッドの *isoLevel* パラメーター。  
  
-   MS DTC でコーディネートされる分散トランザクションには、**ITransactionDispenser::BeginTransaction** メソッドの *isoLevel* パラメーター。  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] では、ダーティ リード分離レベルでの読み取り専用アクセスを許可します。 他のすべてのレベルでは、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] オブジェクトにロックをかけることによってコンカレンシーを制限します。 クライアントがより高度なコンカレンシー レベルを要求すると、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] はデータへのコンカレント アクセスに対してより厳密な制限を適用します。 データへの最高レベルのコンカレント アクセスを維持するには、OLE DB Driver for SQL Server のコンシューマーで、特定のコンカレンシー レベルの要求を適切に制御する必要があります。  
  
> [!NOTE]  
>  [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] ではスナップショット分離レベルが導入されました。 詳細については、「[スナップショット分離を使用した作業](../../oledb/features/working-with-snapshot-isolation.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [トランザクション](../../oledb/ole-db-transactions/transactions.md)  
  
  
