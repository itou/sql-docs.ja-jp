---
description: '&lt;ソースデータクエリ &gt; -OPENQUERY'
title: OPENQUERY (DMX) |Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: fd654bf63cfbb961b6aaa3c6369358db25371846
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88500878"
---
# <a name="ltsource-data-querygt---openquery"></a>&lt;ソースデータクエリ &gt; -OPENQUERY
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  クエリを使用してソースデータクエリを既存のデータソースに置き換えます。 INSERT、SELECT FROM 予測結合、および SELECT FROM ナチュラル予測結合ステートメントでは、 **OPENQUERY**がサポートされています。  
  
## <a name="syntax"></a>構文  
  
```  
  
OPENQUERY(<named datasource>, <query syntax>)  
```  
  
## <a name="arguments"></a>引数  
 *名前付きデータソース*  
 データベースに存在するデータソース [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 。  
  
 *クエリ構文*  
 行セットを返すクエリ構文です。  
  
## <a name="remarks"></a>解説  
 **OPENQUERY** は、データソースのアクセス許可をサポートすることにより、外部データにアクセスするより安全な方法を提供します。 接続文字列はデータソースに格納されるため、管理者はデータソースのプロパティを使用してデータへのアクセスを管理できます。 データソースの詳細については、「 [サポートされるデータソース &#40;SSAS-多次元&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional)」を参照してください。  
  
 サーバーで使用できるデータソースの一覧を取得するには、 **MDSCHEMA_INPUT_DATASOURCES** スキーマ行セットに対してクエリを実行します。 **MDSCHEMA_INPUT_DATASOURCES**の使用方法の詳細については、「 [MDSCHEMA_INPUT_DATASOURCES 行セット](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/ms126243(v=sql.110))」を参照してください。  
  
 次の DMX クエリを使用して、現在の Analysis Services データベースのデータソースの一覧を返すこともできます。  
  
 `SELECT * FROM $system.MDSCHEMA_INPUT_DATASOURCES`  
  
## <a name="examples"></a>例  
 次の例では、データベースに既に定義されている MyDS データソースを使用して、 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] データベースへの接続を作成 [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] し、 **vtargetmail** ビューに対してクエリを実行します。  
  
```  
OPENQUERY (MyDS,'SELECT TOP 1000 * FROM vTargetMail')  
```  
  
## <a name="see-also"></a>参照  
 [&#60;ソースデータクエリ&#62;](../dmx/source-data-query.md)   
 [DMX&#41; データ操作ステートメントを &#40;データマイニング拡張機能](../dmx/dmx-statements-data-manipulation.md)   
 [データ マイニング拡張機能 &#40;DMX&#41; ステートメント リファレンス](../dmx/data-mining-extensions-dmx-statements.md)  
  
  
