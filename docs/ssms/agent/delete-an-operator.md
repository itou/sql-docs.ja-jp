---
title: Delete an Operator
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- removing operators
- deleting operators
- dropping operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], deleting with Management Studio
ms.assetid: 2b7b8627-082d-4189-8584-abd3a9b604cf
author: markingmyname
ms.author: maghan
ms.reviewer: ''
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 60c114db56faf39eeffc92b99fa8545b872d7e17
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85775061"
---
# <a name="delete-an-operator"></a>Delete an Operator
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> [Azure SQL Database Managed Instance](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) では現在、すべてではありませんがほとんどの SQL Server エージェントの機能がサポートされています。 詳細については、「[Azure SQL Database Managed Instance と SQL Server の T-SQL の相違点](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent)」を参照してください。

このトピックでは、[!INCLUDE[msCoName](../../includes/msconame_md.md)] または [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] を使用して、[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] で [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] エージェントの警告通知を受信しないように、オペレーターを削除する方法について説明します。  
  
## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a>はじめに  
  
### <a name="limitations-and-restrictions"></a><a name="Restrictions"></a>制限事項と制約事項 
オペレーターを削除すると、そのオペレーターと関連するすべての通知も削除されます。  
  
### <a name="security"></a><a name="Security"></a>セキュリティ  
  
#### <a name="permissions"></a><a name="Permissions"></a>アクセス許可  
オペレーターを削除できるのは、 **sysadmin** 固定サーバー ロールのメンバーです。  
  
## <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a>SQL Server Management Studio の使用  
  
#### <a name="to-delete-an-operator"></a>オペレーターを削除するには  
  
1.  **オブジェクト エクスプローラー**で、削除するオペレーターを含むサーバーをプラス記号をクリックして展開します。  
  
2.  プラス記号をクリックして **[SQL Server エージェント]** を展開します。  
  
3.  プラス記号をクリックして **[オペレーター]** フォルダーを展開します。  
  
4.  削除するオペレーターを右クリックして、 **[削除]** をクリックします。  
  
5.  **[オブジェクトの削除]** ダイアログ ボックスで、正しいオペレーターが選択されていることを確認し、 **[OK]** をクリックします。 削除したオペレーターに送信されていた警告およびジョブが別のオペレーターに送信されるようにする場合は、 **[再割り当てするオペレーター]** をオンにし、一覧からオペレーターを選択します。  
  
## <a name="using-transact-sql"></a><a name="TsqlProcedure"></a>Transact-SQL の使用  
  
#### <a name="to-delete-an-operator"></a>オペレーターを削除するには  
  
1.  **オブジェクト エクスプローラー**で、 [!INCLUDE[ssDE](../../includes/ssde_md.md)]のインスタンスに接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。  
  
    ```  
    -- deletes operator 'Test Operator' and reassigns all alerts and jobs
    --  sent to that operator to 'François Ajenstat'  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_operator @name = 'Test Operator',  
        @reassign_to_operator = 'François Ajenstat';  
    GO  
    ```  
  
詳細については、「 [sp_delete_operator (Transact-SQL)](https://msdn.microsoft.com/ff6c2c4b-e9fe-4d0c-bbc2-a2ddcc1acb95)」を参照してください。  
  
