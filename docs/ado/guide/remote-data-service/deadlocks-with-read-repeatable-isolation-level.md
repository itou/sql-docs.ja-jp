---
description: Read Repeatable 分離レベルでのデッドロック
title: 反復可能な Read 分離レベルを使用したデッドロック |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- deadlocks in RDS [ADO]
- read repeatable in RDS [ADO]
ms.assetid: 29f3683f-12f3-4304-8a54-fe133c25a423
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d404533b950aea7549a64b7863d2c1623118594
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "88978153"
---
# <a name="deadlocks-with-read-repeatable-isolation-level"></a>Read Repeatable 分離レベルでのデッドロック
カスタムビジネスオブジェクトが分離レベルを使用して SQL Server にアクセスし、同じトランザクション内でクエリと更新を送信する2つのクライアントによってビジネスオブジェクトが同時に呼び出される場合、デッドロックが発生する可能性があります。 リモートデータサービスは、プロセスの1つがタイムアウトしてデッドロックを解除できるように設計されていますが、そのクライアントの更新は失敗します。  
  
 タイムアウトの長さを変更するには、 [Cursor Service](../appendixes/microsoft-cursor-service-for-ole-db-ado-service-component.md) **コマンドの [タイムアウト]** 動的プロパティを使用します。  
  
> [!IMPORTANT]
>  Windows 8 と windows Server 2012 以降では、RDS サーバーコンポーネントが Windows オペレーティングシステムに含まれなくなりました (詳細については、「Windows 8 および [Windows server 2012 の互換性に関するクックブック](https://www.microsoft.com/download/details.aspx?id=27416) 」を参照してください)。 RDS クライアントコンポーネントは、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションは、 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)に移行する必要があります。  
  
## <a name="see-also"></a>参照  
 [RDS の基礎](./rds-fundamentals.md)