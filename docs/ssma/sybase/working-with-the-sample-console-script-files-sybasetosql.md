---
description: サンプルのコンソール スクリプト ファイルの操作 (SybaseToSQL)
title: サンプルのコンソールスクリプトファイルの操作 (SybaseToSQL) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Sybase Console,Sample Console Script Files
ms.assetid: ef221118-b442-4ca6-9409-6ee1d9f8d948
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 072073fae690812ed2a51cb74073eea95552392a
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88497609"
---
# <a name="working-with-the-sample-console-script-files-sybasetosql"></a>サンプルのコンソール スクリプト ファイルの操作 (SybaseToSQL)
ユーザー参照および使用のために、いくつかのサンプルファイルが製品と共に提供されています。 このセクションでは、エンドユーザーのニーズに合わせて、これらのスクリプトを簡単にカスタマイズする方法について説明します。  
  
## <a name="sample-console-script-files"></a>サンプルコンソールスクリプトファイル  
さまざまなシナリオをカバーする次のサンプルコンソールスクリプトファイルは、ユーザー参照用に用意されています。  
  
-   ServersConnectionFileSample.xml  
  
-   VariableValueFileSample.xml  
  
-   AssessmentReportGenerationSample.xml  
  
-   SqlStatementConversionSample.xml  
  
-   ConversionAndDataMigrationSample.xml  
  
-   **ServersConnectionFileSample.xml:**  
  
    -   このサンプルでは、ソースとターゲットのデータベースで使用できるさまざまなモードの接続を提供し、ユーザーは要件に従って任意のモードを選択できます。 このサンプルには、サーバー定義が含まれています。  
  
    -   ユーザーは、必要なソースとターゲットのサーバー定義に値を変更するだけで、必要なデータベースに接続できます。 この例では、すべての値は、 **VariableValueFileSample.xml**で使用できる変数値として提供されています。  その他のすべての接続パラメーターは、ユーザーの作業サーバー接続ファイルから削除できます。  
  
    -   ソースサーバーとターゲットサーバーへの接続の詳細については、「 [SybaseToSQL&#41;&#40;サーバー接続ファイルを作成する ](../../ssma/sybase/creating-the-server-connection-files-sybasetosql.md)」を参照してください。  
  
-   **VariableValueFileSample.xml:**  
    サンプルコンソールスクリプトファイルで使用されており、 `ServersConnectionFileSample.xml` このファイルで照合されているすべての変数。 サンプルのコンソールスクリプトを実行するには、ユーザーがサンプル変数の値をユーザー定義の変数に置き換えるだけで、このファイルを追加のコマンドライン引数としてスクリプトファイルと共に渡す必要があります。  
  
    変数値ファイルの詳細については、「 [&#40;SybaseToSQL&#41;の変数値ファイルの作成 ](../../ssma/sybase/creating-variable-value-files-sybasetosql.md)」を参照してください。  
  
-   **AssessmentReportGenerationSample.xml:**  
    このサンプルを使用すると、データの変換と移行を開始する前にユーザーが分析に使用できる xml 評価レポートを生成できます。  
  
    このコマンドでは、 `generate-assessment-report` 属性の変数値 (参照 **VariableValueFileSample.xml**) を、 `object-name` ユーザーが使用しているデータベース名に変更する必要があります。 指定されたオブジェクトの種類によっては、 `object-type` 値も変更する必要があります。  
  
    ユーザーが複数のオブジェクトまたはデータベースを評価する必要がある場合は、 `metabase-object` サンプルの `generate-assessment-report` コンソールスクリプトファイルの例4に示すように、複数のノードを指定できます。  
  
    レポートの生成の詳細については、「 [SybaseToSQL&#41;&#40;レポートの生成 ](../../ssma/sybase/generating-reports-sybasetosql.md)」を参照してください。  
  
    > [!NOTE]  
    > -   変数値 file コマンドライン引数がコンソールアプリケーションに渡され、ユーザーが指定した値を使用して VariableValueFileSample.xml が更新されていることを確認します。  
    > -   サーバー接続ファイルのコマンドライン引数がコンソールアプリケーションに渡され、ServersConnectionFileSample.xml が正しいサーバーパラメーター値で更新されていることを確認します。  
  
-   **SqlStatementConversionSample.xml:**  
    このサンプルを使用する `t-sql` `sql` と、入力として指定されたソースデータベースコマンドの対応するスクリプトをユーザーが生成できます。  
  
    このコマンドでは、 `convert-sql-statement` 属性の変数値 (参照 **VariableValueFileSample.xml**) `context` をユーザーが使用しているデータベース名に変更する必要があります。 ユーザーは、 `sql` 変換する必要があるソースデータベースコマンドに属性値を変更する必要もあり `sql` ます。  
  
    ユーザーは、変換する sql ファイルを指定することもできます。 これについては、 `convert-sql-statement` サンプルのコンソールスクリプトファイルのコマンド例4で説明しました。  
  
    > [!NOTE]  
    > 変数値 file コマンドライン引数がコンソールアプリケーションに渡され、ユーザーが指定した値を使用して VariableValueFileSample.xml が更新されていることを確認します。  
  
-   **ConversionAndDataMigrationSample.xml:**  
     このサンプルを使用すると、ユーザーはデータ移行への変換からエンドツーエンドの移行を実行できます。 変更する必要がある必須の属性値の一覧を次に示します。  
  
    **コマンド名**  
  
    `map-schema`  
  
    転送元データベースから送信先スキーマへのスキーママッピング。  
  
    **属性**  
  
    -   `source-schema:` を変換する必要があるソースデータベースを指定します。  
  
    -   `sql-server-schema`: 移行先のターゲットデータベースを指定します。  
  
    **コマンド名**  
  
    `convert-schema`  
  
    -   送信元スキーマから送信先スキーマへのスキーマ変換を実行します。  
  
    -   ユーザーが複数のオブジェクトまたはデータベースを評価する必要がある場合は、 `metabase-object` サンプルの `convert-schema` コンソールスクリプトファイルの例4に示すように、複数のノードを指定できます。  
  
    **属性**  
  
    `object-name`: 変換する必要があるソースデータベースまたはオブジェクトの名前を指定します。 に指定されている `object-type` オブジェクトの型に基づいて、対応するが変更されていることを確認します。 `object-name`  
  
    **コマンド名**  
  
    `synchronize-target`  
  
    -   ターゲットデータベースとターゲットオブジェクトを同期します。  
  
    -   ユーザーが複数のオブジェクトまたはデータベースを評価する必要がある場合は、 `metabase-object` `synchronize-target` サンプルコンソールスクリプトファイルのコマンド例3に示すように、複数のノードを指定できます。  
  
    **属性**  
  
    `object-name:` を作成する必要がある sql server データベースまたはオブジェクトの名前を指定します。 に指定されている `object-type` オブジェクトの型に基づいて、対応するが変更されていることを確認します。 `object-name`  
  
    **コマンド名**  
  
    `migrate-data`  
  
    -   ソースデータをターゲットに移行します。  
  
    -   ユーザーが複数のオブジェクトまたはデータベースを評価する必要がある場合は、 `metabase-object` サンプルの `migrate-data` コンソールスクリプトファイルの例2に示すように、複数のノードを指定できます。  
  
    **属性**  
  
    `object-name:` 移行する必要があるソースデータベースまたはテーブルの名前を指定します。 に指定されている `object-type` オブジェクトの型に基づいて、対応するが変更されていることを確認します。 `object-name`  
  
## <a name="see-also"></a>参照  
[&#40;SybaseToSQL&#41;の変数値ファイルを作成する ](../../ssma/sybase/creating-variable-value-files-sybasetosql.md)  
[サーバー接続ファイルの作成 &#40;SybaseToSQL&#41;](../../ssma/sybase/creating-the-server-connection-files-sybasetosql.md)  
[SybaseToSQL&#41;&#40;レポートを生成しています ](../../ssma/sybase/generating-reports-sybasetosql.md)  
  
