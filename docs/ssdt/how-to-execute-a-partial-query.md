---
title: 部分クエリを実行する
description: 複雑なクエリのセクションのデバッグに関するヘルプを表示します。 Transact-SQL エディターを使用して、特定のスクリプト セグメントを強調表示し、1 つのクエリとして実行します。
ms.prod: sql
ms.technology: ssdt
ms.topic: conceptual
ms.assetid: af04ab37-6cbb-4185-9382-e5922fa5b1df
author: markingmyname
ms.author: maghan
ms.reviewer: “”
ms.custom: seo-lt-2019
ms.date: 02/09/2017
ms.openlocfilehash: f9aaa7712726b37d03c7d7de0994bb8abe01a7d9
ms.sourcegitcommit: b860fe41b873977649dca8c1fd5619f294c37a58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2020
ms.locfileid: "85518802"
---
# <a name="how-to-execute-a-partial-query"></a>方法:部分クエリを実行する

Transact\-SQL エディターでは、スクリプトの一部を選択し、その部分を単一のクエリとして実行することができます。 これにより、複雑なクエリをセクションに分けて、セクションごとに容易にデバッグできるようになります。  
  
> [!WARNING]  
> 以下に示す手順では、「[接続されているデータベース開発](../ssdt/connected-database-development.md)」および「[プロジェクト指向のオフライン データベース開発](../ssdt/project-oriented-offline-database-development.md)」に示されているこれまでの手順で作成したエンティティを使用します。  
  
## <a name="to-partially-execute-a-query"></a>クエリを部分的に実行するには  
  
1. **SQL Server オブジェクト エクスプローラー**で、 **[ビュー]** の下にある **PerishableFruits** をダブルクリックし、Transact\-SQL エディターで開きます。  
  
2. コード内の「`SELECT p.Id, p.Name FROM dbo.Product p`」という部分を選択し、右クリックして、 **[クエリの実行]** をクリックします。  
  
3. `Products` テーブル内のすべての行の指定されたフィールドが、**結果**ペインに返されます。