---
title: '[ジョブのプロパティ] - [新しいジョブ] ([通知] ページ)'
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql13.ag.job.notifications.f1
ms.assetid: ed393cbd-4496-4399-a177-e5baa92fb689
author: markingmyname
ms.author: maghan
ms.reviewer: ''
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 2d1bc2ec3aef699e491fdac2036352fd986fec85
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85690608"
---
# <a name="job-properties---new-job-notifications-page"></a>[ジョブのプロパティ] - [新しいジョブ] ([通知] ページ)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> [Azure SQL Database Managed Instance](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) では現在、すべてではありませんがほとんどの SQL Server エージェントの機能がサポートされています。 詳細については、「[Azure SQL Database Managed Instance と SQL Server の T-SQL の相違点](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent)」を参照してください。

このページを使用して、ジョブの完了時に [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントが実行するアクションを設定します。  
  
## <a name="options"></a>Options  
**電子メール**  
このオプションを選択すると、ジョブの完了時に電子メールが送信されます。 このオプションを選択した後、通知先のオペレーターと、次の通知をトリガーする条件を選択します。 **[ジョブ成功時]** 、 **[ジョブ失敗時]** 、または **[ジョブ完了時]** 。  
  
**ページ**  
このオプションを選択すると、ジョブの完了時にオペレーターのポケットベルに電子メールが送信されます。 このオプションを選択した後、通知先のオペレーターと、次の通知をトリガーする条件を指定します。 **[ジョブ成功時]** 、 **[ジョブ失敗時]** 、または **[ジョブ完了時]** 。  
  
**Net send**  
このオプションを選択すると、ジョブの完了時に Net Send を使用してオペレーターに通知が送られます。 このオプションを選択した後、通知先のオペレーターと、次の通知をトリガーする条件を指定します。 **[ジョブ成功時]** 、 **[ジョブ失敗時]** 、または **[ジョブ完了時]** 。  
  
**[Windows アプリケーション イベント ログに書き込む]**  
このオプションを選択すると、ジョブの完了時にアプリケーション イベント ログにエントリが書き込まれます。 このオプションを選択した後、通知先のオペレーターと、次の通知をトリガーする条件を指定します。 **[ジョブ成功時]** 、 **[ジョブ失敗時]** 、または **[ジョブ完了時]** 。  
  
**[自動的にジョブを削除]**  
このオプションを選択すると、ジョブの完了時にジョブが削除されます。 このオプションを選択した後、ジョブの削除をトリガーする条件を指定します。 **[ジョブ成功時]** 、 **[ジョブ失敗時]** 、または **[ジョブ完了時]** 。  
  
## <a name="see-also"></a>参照  
[ジョブの実装](../../ssms/agent/implement-jobs.md)  
[方法: データベース メールを使用するように SQL Server エージェント メールを構成する](https://msdn.microsoft.com/4b8b61bd-4bd1-43cd-b6e5-c6ed2e101dce)  
  
