---
title: Transact-SQL ブレークポイント
description: デバッグ時に、必要に応じてブレークポイントを使用して実行を一時停止できます。 ブレークポイント タスクについて説明する記事へのリンクを含むブレークポイント タスクの一覧については、こちらを参照してください。
titleSuffix: T-SQL debugger
ms.prod: sql
ms.technology: scripting
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoints
ms.assetid: c234430f-bd94-4d0d-9e74-2bf11681fa50
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: seo-lt-2019
ms.date: 12/04/2019
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 4013fea38f42ff997ebf07e74d3adee2c4896b45
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87246184"
---
# <a name="transact-sql-breakpoints"></a>Transact-SQL ブレークポイント

 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

ブレークポイントは、特定の [!INCLUDE[tsql](../../includes/tsql-md.md)] ステートメントで [!INCLUDE[tsql](../../includes/tsql-md.md)] デバッガーの実行の一時停止を指定し、その時点のコード要素の状態を確認できます。

[!INCLUDE[ssms-old-versions](../../includes/ssms-old-versions.md)]

## <a name="breakpoints"></a>ブレークポイント

[!INCLUDE[tsql](../../includes/tsql-md.md)] デバッガーの実行時に、特定のステートメントでブレークポイントを切り替えることができます。 ブレークポイントが含まれているステートメントに到達すると、デバッガーの実行は一時停止され、変数やパラメーターに存在する値などの情報を表示できます。

ブレークポイントの管理は、個別にエディター ウィンドウで、またはまとめて **[ブレークポイント]** ウィンドウで行うことができます。 ブレークポイントを編集することにより、実行を一時停止する条件や、ブレークポイント実行時の動作を指定できます。

## <a name="breakpoint-tasks"></a>ブレークポイントのタスク  
  
|タスクの説明|トピック|  
|----------------------|-----------|  
|デバッガーを一時停止する [!INCLUDE[tsql](../../includes/tsql-md.md)] ステートメントを指定する方法について説明します。|[ブレークポイントの切り替え](../../relational-databases/scripting/toggle-a-breakpoint.md)|  
|ブレークポイントを一時的に非アクティブ化し、後で再アクティブ化する方法について説明します。 ブレークポイントを削除する方法についても説明します。|[ブレークポイントの有効化、無効化、削除](../../relational-databases/scripting/enable-disable-and-delete-breakpoints.md)|  
|指定した Transact-SQL 式の評価に基づいてブレークポイントがブレークするかどうかを決定する条件を指定する方法について説明します。|[ブレークポイント条件の指定](../../relational-databases/scripting/specify-a-breakpoint-condition.md)|  
|ブレークポイントを含むステートメントが指定の回数実行されたときにのみ、ブレークポイントがブレークするように、ヒット カウントを指定する方法について説明します。|[ヒット カウントの指定](../../relational-databases/scripting/specify-a-hit-count.md)|  
|指定されたプロセスまたはスレッドでのみブレークポイントがブレークするように、フィルターを指定する方法について説明します。|[ブレークポイント フィルターの指定](../../relational-databases/scripting/specify-a-breakpoint-filter.md)|  
|ブレークポイント ステートメントが実行されるときに行われるカスタム操作である、 **ヒット時** アクションを指定する方法について説明します。 例としては、メッセージの出力などが考えられます。|[ブレークポイント アクションの指定](../../relational-databases/scripting/specify-a-breakpoint-action.md)|  
|ブレークポイントの場所を編集する方法について説明します。|[ブレークポイントの位置の編集](../../relational-databases/scripting/edit-a-breakpoint-location.md)|  
  
## <a name="see-also"></a>参照  
 [Transact-SQL デバッガー情報](../../relational-databases/scripting/transact-sql-debugger-information.md)  
  
  
