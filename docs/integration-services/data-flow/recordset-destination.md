---
description: レコードセット変換先
title: レコードセット変換先 | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.recordsetdest.f1
helpviewer_keywords:
- Recordset destination
- ADO recordsets [Integration Services]
- destinations [Integration Services], Recordset
- in-memory ADO recordsets [Integration Services]
ms.assetid: be973cf1-c4ff-49f8-987e-314c08ef98e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75027180045921b52377567bd90c0fa10c5fed1a
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88484581"
---
# <a name="recordset-destination"></a>レコードセット変換先

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  レコードセット変換先は、インメモリ ADO レコードセットを作成して設定します。 レコードセットの形態は、レコードセット変換先への入力によってデザイン時に定義されます。  
  
## <a name="configuration-of-the-recordset-destination"></a>レコードセット変換先の構成  
 レコードセット変換先を構成するには、ADO レコードセットを格納する変数を指定します。  
  
 実行時に、ADO レコードセットは、レコードセット変換先の VariableName プロパティで指定されたオブジェクト型の変数に書き込まれます。 その後、この変数はスクリプトおよび他のパッケージ要素で使用できるため、レコードセットはデータ フローの外部で利用可能になります。  
  
 この変換先は 1 つの入力をとります。 エラー出力はサポートされていません。  
  
 プロパティを設定するには [!INCLUDE[ssIS](../../includes/ssis-md.md)] デザイナーから行うか、またはプログラムによって設定します。  
  
 **[詳細エディター]** ダイアログ ボックスには、プログラムによって設定できるプロパティが反映されます。 **[詳細エディター]** ダイアログ ボックスまたはプログラムで設定できるプロパティの詳細については、次のトピックのいずれかを参照してください。  
  
-   [Common Properties](https://msdn.microsoft.com/library/51973502-5cc6-4125-9fce-e60fa1b7b796)  
  
-   [レコードセット変換先のカスタム プロパティ](../../integration-services/data-flow/recordset-destination-custom-properties.md)  
  
 データ フロー コンポーネントのプロパティの設定方法については、「 [データ フロー コンポーネントのプロパティを設定する](../../integration-services/data-flow/set-the-properties-of-a-data-flow-component.md)」を参照してください。  
  
## <a name="related-tasks"></a>Related Tasks  
 [レコードセット変換先を使用する](../../integration-services/data-flow/use-a-recordset-destination.md)  
  
  
