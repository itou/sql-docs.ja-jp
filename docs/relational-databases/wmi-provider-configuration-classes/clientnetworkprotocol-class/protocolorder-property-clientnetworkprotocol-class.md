---
description: ProtocolOrder プロパティ (ClientNetworkProtocol クラス)
title: ProtocolOrder プロパティ (ClientNetworkProtocol)
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
apiname:
- ProtocolOrder Property (ClientNetworkProtocol Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- ProtocolOrder property
ms.assetid: aa09b8ab-37db-4406-8973-acf503855fd2
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 51b686edb6ac9e93862c5f90f06bb7370fe47a9a
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89523048"
---
# <a name="protocolorder-property-clientnetworkprotocol-class"></a>ProtocolOrder プロパティ (ClientNetworkProtocol クラス)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  [Setordervalue メソッド (ClientNetworkProtocol クラス)](../../../relational-databases/wmi-provider-configuration-classes/clientnetworkprotocol-class/setordervalue-method-clientnetworkprotocol-class.md)メソッドによって指定された現在参照されているクライアントネットワークプロトコルの順序番号を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
object.ProtocolOrder [= value]  
```  
  
## <a name="parts"></a>指定項目  
 *object*  
 クライアントによって使用されるネットワークプロトコルを表す [Clientnetworkprotocol クラス](../../../relational-databases/wmi-provider-configuration-classes/clientnetworkprotocol-class/clientnetworkprotocol-class.md) オブジェクト [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 。  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 **Ordervalue**メソッドによって設定された、現在参照されているクライアントネットワークプロトコルの順序番号を指定する**uint32**値。 クライアント ネットワーク プロトコルが無効の場合、この値は 0 になります。  
  
## <a name="remarks"></a>解説  
  
## <a name="see-also"></a>参照  
 [クライアントプロトコルの構成](https://technet.microsoft.com/library/ms181035.aspx)   
 [クライアントのネットワーク プロトコルと Net-Library の構成](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
