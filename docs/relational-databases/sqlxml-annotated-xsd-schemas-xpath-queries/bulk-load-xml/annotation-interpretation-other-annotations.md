---
title: その他の注釈 (SQLXML)
description: SQLXML 注釈の一覧を、XML 一括読み込みによってどのように解釈されるかについての説明と共に表示します。
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- url-encode annotation
- sql:key-fields
- use-cdata annotation
- sql:is-mapping-schema
- sql:url-encode
- sql:id-prefix
- sql:use-cdata
- key-fields annotation
- id-prefix annotation [SQLXML]
- is-mapping-schema annotation
ms.assetid: f7b4d37b-d6d3-4ac3-b2fd-a0b534a924e4
author: MightyPen
ms.author: genemi
ms.custom: seo-lt-2019
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 6780a99b5bca826a9e92890ebe317f32c93300fc
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85724730"
---
# <a name="annotation-interpretation---other-annotations"></a>注釈の解釈 - 他の注釈
[!INCLUDE [SQL Server Azure SQL Database](../../../includes/applies-to-version/sql-asdb.md)]
  前のトピックで説明した注釈に加えて、XML 一括読み込みでは、その他の注釈が次のように解釈されます。  
  
 **sql:id-prefix**  
 スキーマで XML データのプレフィックスを指定した場合、XML 一括読み込みでは Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] へのデータの送信前にプレフィックスが削除されます。  
  
 **sql:use-cdata**  
 XML 一括読み込みでは、CDATA セクションに格納されているテキストが読み取られ、それが [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] に送信されます。  
  
 **sql:url-encode**  
 XML 一括読み込みでは、この注釈はサポートされません。 たとえば、XML データ入力に URL を指定することはできません。また、XML 一括読み込みで、指定した場所からデータを読み込んでデータベースに格納することはできません。  
  
 **sql:is-mapping-schema**  
 XML 一括読み込みでは、この注釈はサポートされません。また、 **sql: id**もサポートされません。  
  
> [!NOTE]  
>  XML 一括読み込みでは、インライン マッピング スキーマはサポートされません。  
  
 **sql:key-fields**  
 XML 一括読み込みでは、この注釈は常に無視されます。  
  
## <a name="see-also"></a>関連項目  
 [SQLXML 4.0 &#40;の注釈の解釈&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sqlxml-4-0.md)  
  
  
