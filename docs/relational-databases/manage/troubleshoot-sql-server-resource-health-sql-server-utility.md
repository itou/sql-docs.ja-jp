---
title: SQL Server のリソース正常性のトラブルシューティング (SQL Server ユーティリティ) | Microsoft Docs
description: SQL Server UCP によって特定されるリソース正常性の問題のトラブルシューティングについて説明します。これには、CPU の過大使用、ファイル領域、割り当てられたディスク領域などがあります。
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 614f07b5-f221-4013-9f8d-22964cf42270
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cb188aa5a71ef9631aa61ead08cfc33ed1210c7f
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85786451"
---
# <a name="troubleshoot-sql-server-resource-health-sql-server-utility"></a>SQL Server のリソース正常性のトラブルシューティング (SQL Server ユーティリティ)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP によって特定されるリソース正常性の問題のトラブルシューティングでは、コンピューターや [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]のインスタンスでの CPU の過大使用を緩和したり、データ層アプリケーションの CPU の過大使用を緩和したりします。 この他にも、データベース ファイルのファイル領域の過大使用や記憶域ボリュームに割り当てられたディスク領域の過大使用の解決も行われます。  
  
 データベースが "緊急" 状態になっている場合、正常性状態は過大使用になっているログ ファイル領域を示します。  
  
 データ収集の失敗 (UCP のマネージド インスタンスのリスト ビューに灰色の状態アイコンで示されます) の詳細については、「 [SQL Server ユーティリティのトラブルシューティング](https://msdn.microsoft.com/library/f5f47c2a-38ea-40f8-9767-9bc138d14453)」を参照してください。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティの概要の詳細については、「 [SQL Server ユーティリティの機能とタスク](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)」を参照してください。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP で検出された特定のリソースの正常性に関する問題を緩和する方法の詳細については、以下のトピックを参照してください。  
  
-   [SQL Server のバージョンとエディションを識別する方法](https://go.microsoft.com/fwlink/?LinkID=178504)  
  
-   [SQL Server 2008 のパフォーマンスに関する問題のトラブルシューティング](https://go.microsoft.com/fwlink/?LinkId=151354)  
  
  
