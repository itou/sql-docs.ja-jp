---
title: 使用状況データ コレクションとクラッシュ レポートを有効または無効にする
description: この記事では、使用状況とクラッシュ レポートのデータが収集されて Microsoft に送信されるかどうかを制御する方法について説明します。
ms.prod: azure-data-studio
ms.technology: azure-data-studio
ms.topic: conceptual
author: markingmyname
ms.author: maghan
ms.reviewer: alayu, maghan, sstein
ms.custom: seodec18; seo-lt-2019
ms.date: 09/24/2018
ms.openlocfilehash: 5d65a1333f3fc0f41bdcb5b7ac1f5284f32a03cc
ms.sourcegitcommit: dc8a30a4a27e15fc6671ca2674da9b7c637ec255
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "88745542"
---
# <a name="enable-or-disable-usage-data-collection-for-azure-data-studio"></a>Azure Data Studio のデータ コレクションを有効または無効にする

## <a name="how-to-disable-telemetry-reporting"></a>テレメトリ レポートを無効にする方法

Azure Data Studio では、使用状況データが収集されて Microsoft に送信され、製品やサービスの改善に役立てられます。 詳細については、[プライバシーに関する声明](https://go.microsoft.com/fwlink/?LinkID=528096&clcid=0x409)をお読みください。

使用状況データを Microsoft に送信したくない場合は、*telemetry.enableTelemetry* 設定を *false* に設定できます。

Azure Data Studio からのすべてのテレメトリ イベントをサイレント状態にするには、 **[ファイル]**  >  **[基本設定]**  >  **[設定]** で、次のオプションを追加します。

```json
    "telemetry.enableTelemetry": false
```

**重要な注意**: このオプションを有効にするには、Azure Data Studio の再起動が必要です。 

## <a name="how-to-disable-crash-reporting"></a>クラッシュ レポートを無効にする方法

クラッシュ レポートを無効にするには、 **[ファイル]**  >  **[基本設定]**  >  **[設定]** で、次のオプションを追加します。

```json
    "telemetry.enableCrashReporter": false
```

**重要な注意**: このオプションを有効にするには、Azure Data Studio の再起動が必要です。

## <a name="additional-resources"></a>その他のリソース
- [ワークスペースとユーザー設定](settings.md)
