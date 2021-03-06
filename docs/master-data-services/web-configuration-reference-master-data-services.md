---
description: Web 設定リファレンス (Master Data Services)
title: Web 設定リファレンス
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- web configuration file [Master Data Services]
ms.assetid: b8cc9a35-97ab-4fe0-ab4b-c07f13d9793a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 34e3e849a86cb23c3974b32b9d3d8c0721601274
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88456765"
---
# <a name="web-configuration-reference-master-data-services"></a>Web 設定リファレンス (Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] では Web.config ファイルを使用することで、インターネット インフォメーション サービス (IIS) を有効にして [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Web アプリケーションおよび Web サービスをホストできるようにする構成設定を取り込みます。 この Web.config ファイルは、 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] インストール パスの WebApplication フォルダーにあります。 パスと権限の詳細については、「[フォルダーとファイルの権限 (マスター データ サービス)](../master-data-services/folder-and-file-permissions-master-data-services.md)」を参照してください。  
  
## <a name="webconfig-elements"></a>Web.Config 要素  
 Web.config ファイルには、 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] **\<masterDataServices>** 標準の IIS、.NET Framework、ASP.NET、および WINDOWS COMMUNICATION FOUNDATION (WCF) 構成要素に加えて、カスタム要素が含まれています。 次の表では、Web.config ファイルに含まれている要素について説明します。  
  
|Configuration 要素|説明|  
|---------------------------|-----------------|  
|**masterDataServices**|Custom 要素。 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web サービスを [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] データベースに接続します。|  
|**connectionStrings**|ASP.NET 要素。 詳細については、MSDN ライブラリの「 [connectionStrings 要素 (ASP.NET 設定スキーマ)](https://go.microsoft.com/fwlink/?LinkId=178347) 」を参照してください。|  
|**system.web**|ASP.NET 要素。 詳細については、MSDN ライブラリの「 [system.web 要素 (ASP.NET 設定スキーマ)](https://go.microsoft.com/fwlink/?LinkId=178348) 」を参照してください。|  
|**代替**|.NET Framework 要素。 詳細については、MSDN ライブラリの「 [ \<startup> Element](https://go.microsoft.com/fwlink/?LinkId=178349) 」を参照してください。|  
|**ランタイム**|.NET Framework 要素。 詳細については、MSDN ライブラリの「 [ \<runtime> Element](https://go.microsoft.com/fwlink/?LinkId=178350) 」を参照してください。|  
|**system.codedom**|.NET Framework 要素。 詳細については、MSDN ライブラリの「 [ \<system.codedom> Element](https://go.microsoft.com/fwlink/?LinkId=178351) 」を参照してください。|  
|**system.web. 拡張子**|ASP.NET 要素。 詳細については、MSDN ライブラリの「 [system.web.extensions 要素 (ASP.NET 設定スキーマ)](https://go.microsoft.com/fwlink/?LinkId=178352) 」を参照してください。|  
|**system.webServer**|IIS 要素を含んだセクション グループ。 詳細については、MSDN ライブラリの「[system.webServer セクション グループ \[IIS 7 設定スキーマ\]](https://go.microsoft.com/fwlink/?LinkId=178353)」を参照してください。|  
|**system.serviceModel**|WCF 要素。 詳細については、MSDN ライブラリの「」を参照してください [\<system.serviceModel>](https://go.microsoft.com/fwlink/?LinkId=178354) 。|  
|**system.diagnostics**|.NET Framework 要素。 詳細については、MSDN ライブラリの「 [ \<system.diagnostics> Element](https://go.microsoft.com/fwlink/?LinkId=178355) 」を参照してください。|  
|**appSettings**|ASP.NET 要素。 詳細については、MSDN ライブラリの「 [appSettings 要素 (全般設定スキーマ)](https://go.microsoft.com/fwlink/?LinkId=178356) 」を参照してください。|  
  
## <a name="masterdataservices-element"></a>masterDataServices 要素  
 要素は、 **\<masterDataServices>** [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web サービスをデータベースに接続するために使用されるカスタム要素です [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 。  
  
### <a name="syntax"></a>構文  
  
```  
<masterDataServices>  
   <instance virtualPath="path" siteName="name" connectionName="name" serviceName="name" />  
</masterDataServices>  
```  
  
### <a name="elements-and-attributes"></a>要素と属性  
  
|項目|説明|  
|----------|-----------------|  
|**instance**|子要素。 Web サービスとデータベース接続文字列の情報を指定する属性を含みます。|  
|**virtualPath**|Attribute。 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Web アプリケーションとサービスの仮想パスを指定します。 これは、IIS ApplicationHost.config ファイルの要素の下にある要素の **パス** 属性に対応し **\<application>** **\<site>** ます。|  
|**siteName**|Attribute。 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Web アプリケーションとサービスをホストするサイトの名前を指定します。 これは、IIS ApplicationHost.config ファイルのの下の要素の **name** 属性に対応して **\<site>** **\<sites>** います。|  
|**connectionName**|Attribute。 使用する接続の名前を指定します。 これは Web.config の要素の下にある要素の **name** 属性に対応して **\<add>** **\<connectionStrings>** います。|  
|**serviceName**|Attribute。 Web サービスの名前を指定します。 これは Web.config の要素の下にある要素の **name** 属性に対応して **\<service>** **\<services>** います。|  
  
### <a name="example"></a>例  
 次の例は、Contoso サイト上の MDS1 という名前のサービスと、MDSDB によって指定された接続文字列を使用した /MDS パスを示しています。  
  
```  
<masterDataServices>  
   <instance virtualPath="/MDS" siteName="Contoso" connectionName="MDSDB" serviceName="MDS1" />  
</masterDataServices>  
```  
  
  
