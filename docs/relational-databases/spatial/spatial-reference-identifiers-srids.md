---
description: SRID (Spatial Reference Identifier)
title: SRID (Spatial Reference Identifier) | Microsoft Docs
ms.date: 03/29/2019
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Spatial Reference Identifiers (SRIDs)
- geodetic spatial data [SQL Server], identifiers
- SRID
ms.assetid: 0612658a-7d1b-4178-bdc2-42b914ea31a7
author: MladjoA
ms.author: mlandzic
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 4ce3d6732b42640755f92e64244ae10c870b4666
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88447986"
---
# <a name="spatial-reference-identifiers-srids"></a>SRID (Spatial Reference Identifier)
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]
  各空間インスタンスには SRID (spatial reference identifier) があります。 SRID は、平面地球マッピングまたは球体地球マッピングに使用される特定の楕円体に基づく空間参照系に対応します。  
  
 空間列には異なる SRID を持つオブジェクトを格納できますが、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の空間データ メソッドを使用してデータの操作を実行する際に使用できるのは、同じ SRID を持つ空間インスタンスだけです。 2 つの空間データ インスタンスから引き出される空間メソッドの結果は、それらのインスタンスが同じ SRID を持つ (同じ測定単位、データ、および投影を使用してインスタンスの座標が決定されている) 場合にのみ有効になります。 SRID の最も一般的な測定単位はメートルまたは平方メートルです。  
  
 2 つの空間インスタンスの SRID が同じでない場合に、それらのインスタンスに対して **geometry** データ型や **geography** データ型のメソッドを使用すると、NULL が返されます。 たとえば、次の述語で NULL 以外の結果が返されるためには、 **および** の 2 つの `geometry1` geometry `geometry2`インスタンスの SRID が同じである必要があります。  
  
 `geometry1.STIntersects(geometry2) = 1`  
  
> [!NOTE]  
>  空間参照識別系は、地図制作、測量、および測地のデータの格納のために開発された一連の標準である [European Petroleum Survey Group (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) 標準によって定義されています。 この標準は、Oil and Gas Producers (OGP) Surveying and Positioning Committee が所有しています。  
  
## <a name="see-also"></a>関連項目  
 [空間データ型の概要](../../relational-databases/spatial/spatial-data-types-overview.md)  
  
  
