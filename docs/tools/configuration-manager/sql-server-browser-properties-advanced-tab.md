---
title: '[SQL Server Browser のプロパティ] ダイアログ ボックス ([詳細設定] タブ)'
description: ダンプ ディレクトリやインスタンス ID など、[SQL Server Browser のプロパティ] ダイアログ ボックスの [詳細設定] タブのオプションについて説明します。
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ba79137a-cb72-4bf3-a650-e11d02cfce10
author: markingmyname
ms.author: maghan
monikerRange: '>=sql-server-2016||=sqlallproducts-allversions'
ms.openlocfilehash: fa4bcec5a702b604212a465d8f3b115348e8cc87
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85880341"
---
# <a name="sql-server-browser-properties-advanced-tab"></a>[SQL Server Browser のプロパティ] ダイアログ ボックス ([詳細設定] タブ)
[!INCLUDE [SQL Server Windows Only - ASDBMI ](../../includes/applies-to-version/sql-windows-only-asdbmi.md)]
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser プログラムはサーバー上のサービスとして実行されます。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser では、[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の各種リソースに関する着信要求を受信し、このコンピューター上にインストールされている [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスに関する情報を提供します。  
  
## <a name="options"></a>Options  
 **クラスター化インデックス**  
 このサービスがクラスター サーバーのリソースとしてインストールされているかどうかが表示されます。  
  
 **[カスタマー フィードバック レポート]**  
 サービス品質の監視がこのサービスで有効になっているかどうかを示します。 カスタマー フィードバック報告の詳細については、オンライン ブックの「エラー レポートと使用状況レポートの設定」を検索してください。  
  
 **[ダンプ ディレクトリ]**  
 エラー発生時にメモリ ダンプが配置される場所です。  
  
 **[エラー報告]**  
 **[はい]** に設定した場合、重大な障害が発生したときに、ワトソン博士プログラムによって [!INCLUDE[msCoName](../../includes/msconame-md.md)] またはエラー サーバーに情報が転送されます。 エラー報告の詳細については、オンライン ブックの「エラー レポートと使用状況レポートの設定」を検索してください。  
  
 **インスタンス ID**  
 この [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント インスタンスを使用した [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスが表示されます。 既定のインスタンスは **MSSQL10_50.MSSQLSERVER**です。  
  
## <a name="see-also"></a>参照  
 [SQL Server Browser サービス](../../tools/configuration-manager/sql-server-browser-service.md)  
  
  
