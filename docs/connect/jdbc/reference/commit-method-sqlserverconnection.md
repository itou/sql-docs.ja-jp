---
title: commit メソッド (SQLServerConnection) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection.commit
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: c7346165-51bf-4844-b64c-29833c147236
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 50afbfa25052e0f602c486d011ce666a599372e0
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80923589"
---
# <a name="commit-method-sqlserverconnection"></a>commit メソッド (SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  前回のコミットまたはロールバック以降のすべての変更を永続的にして、[SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) オブジェクトによって現在保持されているデータベース ロックをすべて解除します。  
  
## <a name="syntax"></a>構文  
  
```  
  
public void commit()  
```  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>解説  
 この method メソッドは、java.sql.Connection インターフェイスの method メソッドで規定されています。  
  
 このメソッドは、自動コミット モードが無効になっている場合にのみ使用してください。  
  
 クライアントが手動トランザクションを開始した後、SQL Server が何らかの理由でその手動トランザクションをロールバックした場合、このメソッドは失敗して例外をスローすることに注意してください。 たとえば、クライアントが明示的に ROLLBACK TRANSACTION を呼び出すストアド プロシージャを呼び出した後で method メソッドを呼び出すと、例外がスローされます。 また、クライアントが開始した手動トランザクションのロールバック条件を満たす重大度 16 以上のエラーが SQL Server で発生した場合、それ以降の method メソッドの呼び出しでは例外がスローされます。  
  
## <a name="see-also"></a>参照  
 [SQLServerConnection のメンバー](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection クラス](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
