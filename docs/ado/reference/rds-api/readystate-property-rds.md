---
description: ReadyState プロパティ (RDS)
title: ReadyState プロパティ (RDS) |Microsoft Docs
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.prod: sql
ms.prod_service: connectivity
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- ReadyState property [ADO]
ms.assetid: 5be75bc7-1171-4440-a37e-c8cc6b5cd865
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a7e27abfa2464f84e130d789db93a3d7606df21
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "88981483"
---
# <a name="readystate-property-rds"></a>ReadyState プロパティ (RDS)
[DataControl](./datacontrol-object-rds.md)オブジェクトが[レコードセット](../ado-api/recordset-object-ado.md)オブジェクトにデータを取得する際の進行状況を示します。  
  
> [!IMPORTANT]
>  Windows 8 と windows Server 2012 以降では、RDS サーバーコンポーネントが Windows オペレーティングシステムに含まれなくなりました (詳細については、「Windows 8 および [Windows server 2012 の互換性に関するクックブック](https://www.microsoft.com/download/details.aspx?id=27416) 」を参照してください)。 RDS クライアントコンポーネントは、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションは、 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)に移行する必要があります。  
  
## <a name="settings-and-return-values"></a>設定と戻り値  
 次のいずれかの値を設定または返します。  
  
|[値]|説明|  
|-----------|-----------------|  
|**adcReadyStateLoaded**|現在のクエリは実行中で、行はフェッチされていません。 **DataControl**オブジェクトの**レコードセット**は使用できません。|  
|**adcReadyStateInteractive**|現在のクエリによって取得された行の初期セットは、 **DataControl** オブジェクトの **レコードセット** に格納されており、使用することができます。 残りの行はまだフェッチされています。|  
|**adcReadyStateComplete**|現在のクエリによって取得されたすべての行が **DataControl** オブジェクトの **レコードセット** に格納され、使用できるようになります。<br /><br /> この状態は、エラーが原因で操作が中止された場合、または **レコードセット** オブジェクトが初期化されていない場合にも存在します。|  
  
> [!NOTE]
>  これらの定数を使用するクライアント側の実行可能ファイルは、それぞれの宣言を提供する必要があります。 RDS ライブラリの既定のインストールフォルダーにある Adcvbs. inc. ファイルから、必要な定数宣言を切り取って貼り付けることができます。  
  
## <a name="remarks"></a>解説  
 非同期クエリ操作中に**ReadyState**プロパティの変更を監視するには、 [onReadyStateChange](./onreadystatechange-event-rds.md)イベントを使用します。 これは、プロパティの値を定期的にチェックするよりも効率的です。  
  
 非同期操作中にエラーが発生した場合、 **ReadyState** プロパティは **adcReadyStateComplete**に変更され、 [State](../ado-api/state-property-ado.md) プロパティは **adstateexecuting** から **adStateClosed**に変更され、 **レコードセット** オブジェクトの [値](../ado-api/value-property-ado.md) プロパティは *何も*保持されません。  
  
## <a name="applies-to"></a>適用対象  
 [DataControl オブジェクト (RDS)](./datacontrol-object-rds.md)  
  
## <a name="see-also"></a>参照  
 [ReadyState プロパティの例 (VBScript)](./readystate-property-example-vbscript.md)   
 [Cancel メソッド (RDS)](./cancel-method-rds.md)   
 [ExecuteOptions プロパティ (RDS)](./executeoptions-property-rds.md)