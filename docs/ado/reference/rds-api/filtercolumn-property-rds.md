---
description: FilterColumn プロパティ (RDS)
title: FilterColumn プロパティ (RDS) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- FilterColumn property [ADO]
ms.assetid: 0a5473e8-8ce6-4518-83fb-4920b827e285
author: rothja
ms.author: jroth
ms.openlocfilehash: 1af2eb386f3d61387158a3a654ff900f6b6ad43a
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "88982203"
---
# <a name="filtercolumn-property-rds"></a>FilterColumn プロパティ (RDS)
フィルター条件を評価する列を示します。  
  
> [!IMPORTANT]
>  Windows 8 と windows Server 2012 以降では、RDS サーバーコンポーネントが Windows オペレーティングシステムに含まれなくなりました (詳細については、「Windows 8 および [Windows server 2012 の互換性に関するクックブック](https://www.microsoft.com/download/details.aspx?id=27416) 」を参照してください)。 RDS クライアントコンポーネントは、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションは、 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)に移行する必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
  
DataControl.FilterColumn = String  
```  
  
#### <a name="parameters"></a>パラメーター  
 *DataControl*  
 RDS を表すオブジェクト変数です [。DataControl](./datacontrol-object-rds.md) オブジェクト。  
  
 *String*  
 フィルター条件を評価する列を示す **文字列** 値です。 フィルター条件は、 [filtercriterion](./filtercriterion-property-rds.md) プロパティで指定します。  
  
## <a name="remarks"></a>解説  
 [Sortcolumn](./sortcolumn-property-rds.md)、 [sortcolumn](./sortdirection-property-rds.md)、 [filtervalue](./filtervalue-property-rds.md)、 [filterfilter、](./filtercriterion-property-rds.md)および**filtervalue**プロパティは、クライアント側キャッシュでの並べ替えとフィルター処理の機能を提供します。 並べ替え機能は、1つの列の値でレコードを並べ替えます。 フィルター機能では、検索条件に基づいてレコードのサブセットが表示されますが、完全な [レコードセット](../ado-api/recordset-object-ado.md) はキャッシュに保持されます。 [Reset](./reset-method-rds.md)メソッドは、条件を実行し、現在の**レコードセット**を更新可能な**レコードセット**に置き換えます。  
  
## <a name="applies-to"></a>適用対象  
 [DataControl オブジェクト (RDS)](./datacontrol-object-rds.md)  
  
## <a name="see-also"></a>参照  
 [FilterColumn、Filtercolumn、Filtercolumn、SortColumn、および Sortcolumn プロパティと Reset メソッドの例 (VBScript)](./filter-column-criterion-value-sortcolumn-sortdirection-example-vbscript.md)   
 [Filterfilterproperty (RDS)](./filtercriterion-property-rds.md)   
 [FilterValue プロパティ (RDS)](./filtervalue-property-rds.md)   
 [SortColumn プロパティ (RDS)](./sortcolumn-property-rds.md)   
 [SortDirection プロパティ (RDS)](./sortdirection-property-rds.md)