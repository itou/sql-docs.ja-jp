---
description: サーバー接続ファイルの作成 (の場合)
title: サーバー接続ファイルの作成 (には、Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 08/17/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 829153be-aa8e-4162-87e8-69882feecf19
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 207aa406df3f426658afa569d434ea71db5eba1e
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88480508"
---
# <a name="creating-the-server-connection-files-accesstosql"></a>サーバー接続ファイルの作成 (の場合)
サーバー情報は、スクリプトファイルの [サーバー] セクションで指定できます。 サーバー情報は、別のサーバー接続ファイルで指定することもできます。 サーバー接続ファイルのコマンドラインパラメーターが `-c <serverconnectionfile>` です。 スクリプトファイルとサーバー接続ファイルの両方に同じサーバー id が存在する場合は、スクリプトファイル内のサーバー定義が考慮されます。  
  
```xml  
<!--Sample of server connection file commands -->  
<!--Connection to SQL Server-->  
  
<sql-server name="target_3">  
  
  <sql-server-authentication>  
  
    <server value="$TargetServerName$"/>  
  
    <database value="$TargetDB$"/>  
  
    <user-id value="$TargetUserName$"/>  
  
    <password value="$TargetPassword$"/>  
  
    <encrypt value="true"/>  
  
    <trust-server-certificate value="true"/>  
  
  </sql-server-authentication>  
  
</sql-server>  
```  
  
```xml  
<!--Connection to SQL Azure-->  
  
<sql-azure name="target_azure">  
  
  <server value="$TargetAzureServerName$"/>  
  
  <database value="$TargetAzureDB$"/>  
  
  <user-id value="$TargetAzureUserName$"/>  
  
  <password value="$TargetAzurePassword$"/>  
  
</sql-azure>  
```  
  
## <a name="server-connection-file-validation"></a>サーバー接続ファイルの検証  
ユーザーは、' スキーマ ' フォルダーで使用可能なスキーマ定義ファイル **' A2SSConsoleScriptServersSchema '** に対して、サーバー接続ファイルを簡単に検証できます。  
  
## <a name="next-step"></a>次のステップ  
コンソールを操作する次の手順では、 [SSMA コンソール &#40;実行](../../ssma/access/executing-the-ssma-console-accesstosql.md)して、sql&#41;  
  
## <a name="see-also"></a>関連項目  
[SSMA コンソール (アクセス) の実行](https://msdn.microsoft.com/aa1bf665-8dc0-4259-b36f-46ae67197a43)  
  
