---
title: getPropertyInfo メソッド (SQLServerDriver) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDriver.getPropertyInfo
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b5eaad8a-31ef-44ac-af11-d5caa13ac3e2
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: fefcbd719689879ece66fe43df7d546d315d1e5f
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80925191"
---
# <a name="getpropertyinfo-method-sqlserverdriver"></a>getPropertyInfo メソッド (SQLServerDriver)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  データベースへの接続に必要なプロパティを検出するために使用します。  
  
## <a name="syntax"></a>構文  
  
```  
  
public java.sql.DriverPropertyInfo[] getPropertyInfo(java.lang.String Url,  
                                                     java.util.Properties Info)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *Url*  
  
 データベースへの接続に使用される URL を含む **String** 値です。  
  
 *Info*  
  
 プロパティ値のペアの一覧です。初回使用時には null です。  
  
## <a name="return-value"></a>戻り値  
 DriverPropertyInfo オブジェクトの配列です。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>解説  
 この getPropertyInfo メソッドは、java.sql.Driver インターフェイスの getPropertyInfo メソッドで指定されています。  
  
## <a name="see-also"></a>参照  
 [SQLServerDriver のメソッド](../../../connect/jdbc/reference/sqlserverdriver-methods.md)   
 [SQLServerDriver のメンバー](../../../connect/jdbc/reference/sqlserverdriver-members.md)   
 [SQLServerDriver クラス](../../../connect/jdbc/reference/sqlserverdriver-class.md)  
  
  
