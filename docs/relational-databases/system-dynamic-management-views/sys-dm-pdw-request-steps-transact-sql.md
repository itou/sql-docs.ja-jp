---
description: dm_pdw_request_steps (Transact-sql)
title: dm_pdw_request_steps (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 05/19/2020
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: cc563e88-0d34-436e-b914-b60d6ee0d50b
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: 4144e068354d43e2e8a5f9ea5bd6af7ad40a0e6d
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88489752"
---
# <a name="sysdm_pdw_request_steps-transact-sql"></a>dm_pdw_request_steps (Transact-sql)
[!INCLUDE[applies-to-version/asa-pdw](../../includes/applies-to-version/asa-pdw.md)]

  指定された要求またはクエリを作成するすべてのステップに関する情報を保持 [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] します。 クエリステップごとに1行が表示されます。  
  
|列名|データ型|説明|Range|  
|-----------------|---------------|-----------------|-----------|  
|request_id|**nvarchar(32)**|request_id と step_index このビューのキーを構成します。<br /><br /> 要求に関連付けられている一意の数値 id。|『 [Transact-sql&#41;&#40;dm_pdw_exec_requests ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md)の request_id を参照してください。|  
|step_index|**int**|request_id と step_index このビューのキーを構成します。<br /><br /> 要求を構成する一連の手順におけるこのステップの位置。|n 個の手順を含む要求の場合は 0 ~ (n-1)。|  
|operation_type|**nvarchar(35)**|このステップで表される操作の種類。|**DMS クエリプランの操作:** ' Returnoperation) '、' PartitionMoveOperation '、' MoveOperation '、' BroadcastMoveOperation '、' ShuffleMoveOperation '、' TrimMoveOperation '、' CopyOperation '、' DistributeReplicatedTableMoveOperation '<br /><br /> **SQL クエリプランの操作:** ' OnOperation '、' RemoteOperation '<br /><br /> **その他のクエリプランの操作:** ' MetaDataCreateOperation '、' RandomIDOperation '<br /><br /> **読み取りの外部操作:** 'HadoopShuffleOperation', 'HadoopRoundRobinOperation', 'HadoopBroadcastOperation'<br /><br /> **MapReduce の外部操作:** ' HadoopJobOperation '、' HdfsDeleteOperation '<br /><br /> **書き込みの外部操作:** 'ExternalExportDistributedOperation', 'ExternalExportReplicatedOperation', 'ExternalExportControlOperation'<br /><br /> 詳細については、「」の「クエリプランについて」を参照してください [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)] 。 <br /><br />  クエリプランは、データベースの設定によっても影響を受ける可能性があります。  詳細については、 [ALTER DATABASE SET オプション](https://docs.microsoft.com/sql/t-sql/statements/alter-database-transact-sql-set-options?toc=/azure/sql-data-warehouse/toc.json&bc=/azure/sql-data-warehouse/breadcrumb/toc.json&view=azure-sqldw-latest) を確認してください。|  
|distribution_type|**nvarchar(32)**|このステップが実行されるディストリビューションの種類。|' AllNodes '、' Allnodes '、' AllComputeNodes '、' CompuSubsetNodes '、' Distribution '、' '、' SubsetDistributions '、' 未指定 '|  
|location_type|**nvarchar(32)**|ステップが実行されている場所。|' Compute '、' Control '、' DMS '|  
|status|**nvarchar(32)**|このステップの状態です。|保留中、実行中、完了、失敗、UndoFailed、PendingCancel、取り消し、取り消し済み、中止|  
|error_id|**nvarchar (36)**|このステップに関連付けられているエラーの一意の id (存在する場合)。|[Transact-sql&#41;&#40;dm_pdw_errors](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-errors-transact-sql.md)の error_id を参照してください。 エラーが発生しなかった場合は NULL です。|  
|start_time|**datetime**|ステップが実行を開始した時刻。|小さいまたは現在の時刻に等しいが、このステップが属するクエリの end_compile_time 以上です。 クエリの詳細については、「 [sys. dm_pdw_exec_requests &#40;transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md)」を参照してください。|  
|end_time|**datetime**|このステップの実行が完了した時刻。が取り消されたか、失敗しました。|小さいまたは現在の時刻に等しいが start_time 以上。 現在実行中またはキューに登録されているステップの場合は、NULL に設定します。|  
|total_elapsed_time|**int**|クエリステップが実行されていた合計時間 (ミリ秒単位)。|0 ~ end_time と start_time の差。 キューに登録されたステップの場合は0。<br /><br /> Total_elapsed_time が整数の最大値を超えた場合、total_elapsed_time は引き続き最大値になります。 この条件により、"最大値を超えました。" という警告が生成されます。<br /><br /> ミリ秒単位の最大値は24.8 日に相当します。|  
|row_count|**bigint**|この要求によって変更または返された行の合計数。|ステップの影響を受けた行の数。  データ操作手順の場合は0以上。  データを操作しないステップの場合は-1。|  
|command|**nvarchar (4000)**|このステップのコマンドの完全なテキストを保持します。|ステップの任意の有効な要求文字列。 操作が MetaDataCreateOperation 型である場合は NULL です。 4000文字を超える場合は切り捨てられます。|  
  
 このビューで保持される最大行数の詳細については、「」の「最小値と最大値」の「システムビューの最大値」セクションを参照してください [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)] 。  
  
## <a name="see-also"></a>関連項目  
 [SQL Data Warehouse および並列データウェアハウスの動的管理ビュー &#40;Transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
