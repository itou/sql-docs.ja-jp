---
title: '[スケジュールの管理]'
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql13.ag.job.manageschedules.f1
ms.assetid: f56c0736-dccc-41d2-afcf-71344aff143a
author: markingmyname
ms.author: maghan
ms.reviewer: ''
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: cc4923611fd9f90bffd5ff58d11c79da8d920122
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85726960"
---
# <a name="manage-schedules"></a>[スケジュールの管理]
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> [Azure SQL Database Managed Instance](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) では現在、すべてではありませんがほとんどの SQL Server エージェントの機能がサポートされています。 詳細については、「[Azure SQL Database Managed Instance と SQL Server の T-SQL の相違点](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent)」を参照してください。

[!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントのジョブ スケジュールのプロパティを表示および変更できます。  
  
## <a name="options"></a>オプション  
**[利用可能なスケジュール]**  
このユーザーが利用可能なスケジュールの一覧を表示します。 ジョブの所有者とスケジュールの所有者は同じである必要があります。 したがって、この一覧には、このジョブの所有者によって所有されているスケジュールだけが表示されます。  
  
**Name**  
スケジュールの名前を表示します。  
  
**有効**  
スケジュールを有効にするには、このオプションを選択します。  
  
**説明**  
ジョブを実行するスケジュールの条件を説明します。  
  
**[スケジュール済みのジョブ]**  
スケジュールにアタッチされているジョブの番号を表示します。 番号をクリックすると、ジョブのプロパティが表示されます。  
  
**[新規作成]**  
新しいスケジュールを作成するには、このボタンをクリックします。  
  
**削除**  
選択されているスケジュールを削除するには、このボタンをクリックします。  
  
**Properties**  
選択されているスケジュールのプロパティを変更するには、このボタンをクリックします。  
  
## <a name="see-also"></a>参照  
[スケジュールの作成とジョブへのアタッチ](../../ssms/agent/create-and-attach-schedules-to-jobs.md)  
  
