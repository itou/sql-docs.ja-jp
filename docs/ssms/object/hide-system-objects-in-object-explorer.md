---
title: '[オブジェクト エクスプローラーのシステム オブジェクトを非表示にする]'
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- hiding system objects
- system objects [SQL Server]
- objects [SQL Server], hiding
- Object Explorer, hiding objects
ms.assetid: c01d8804-838c-4f75-b78c-80e41e4fffdc
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 05864efb35ecd5fcd49e8f8b90cd8093984a9f78
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "86001951"
---
# <a name="hide-system-objects-in-object-explorer"></a>[オブジェクト エクスプローラーのシステム オブジェクトを非表示にする]
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
このトピックでは、 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] で [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]を使用して、オブジェクト エクスプローラーのシステム オブジェクトを非表示にする方法について説明します。 オブジェクト エクスプローラーの **[データベース]** ノードには、システム データベースなどのシステム オブジェクトが含まれています。 システム オブジェクトを非表示にするには、 **[ツール]** / **[オプション]** ページを使用します。 システム関数やシステム データ型など、システム オブジェクトの中にはこの設定で非表示にならないものもあります。  
  
## <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a>SQL Server Management Studio の使用  
  
#### <a name="to-hide-system-objects-in-object-explorer"></a>オブジェクト エクスプローラーでシステム オブジェクトを非表示にするには  
  
1.  **[ツール]** メニューの **[オプション]** をクリックします。  
  
2.  **[環境/スタートアップ]** ページで、 **[オブジェクト エクスプローラーのシステム オブジェクトを非表示にする]** を選択し、 **[OK]** をクリックします。  
  
3.  この変更を有効にするには SQL Server Management Studio の再起動が必要であることを示すメッセージが表示されたら、 **[SQL Server Management Studio]** ダイアログ ボックスで **[OK]** をクリックします。  
  
4.  SQL Server Management Studio を閉じ、再度開きます。  
  
