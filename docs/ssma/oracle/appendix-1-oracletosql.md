---
description: 付録 - 1 (OracleToSQL)
title: 付録-1 (OracleToSQL) |Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: e01f8be5-ce68-4c9f-bd13-d65e73a16470
author: nahk-ivanov
ms.author: alexiva
manager: alexiva
ms.openlocfilehash: c9e605f33615fa09b87a3c58353689db9eeecdd7
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "88463266"
---
# <a name="appendix---1-oracletosql"></a>付録 - 1 (OracleToSQL)
SSMA コンソールのコマンドラインオプションのクイックビューを次に示します。  
  
|法. いいえ。|スイッチ|必須|スイッチ引数|許可される値|  
|-----------|----------|-------------|-------------------|--------------------|  
|1|-s/スクリプト|はい|scriptfile|有効な XML ファイル名です。<br /><br />コンソールスクリプト定義ファイル。|  
|2|-v/variable|いいえ|変数 valuefile|有効な XML ファイル名です。<br /><br />スクリプトファイルで変数を使用する場合は、このファイルを指定する必要があります。|  
|3|-c/serverconnection|いいえ|serverconnectionfile|有効な XML ファイル名です。<br /><br />このファイルには、サーバーの接続情報が含まれています。|  
|4|-x/xmloutput|いいえ|xmloutputfile|このオプションは、XML 形式のコンソール出力を示します。 このオプションが指定されていない場合、既定の出力はテキスト形式です。<br /><br />Xmloutputfile が指定されていない場合、XML 出力はに送られ `STDOUT` ます。<br /><br />Xmloutputfile は、コンソール出力を XML 形式で記述するファイルの名前です。|  
|5|-l/ログ|いいえ|logfile|有効なファイル名です。|  
|6|-e/projectenvironment|いいえ|project環境フォルダー|SSMA プロジェクト環境ファイルを含む有効なフォルダー名です。|  
|7|-p/securepassword|いいえ|-a/add {<server_id> [,...n] &#124; すべて}-c&#124;microsoft.sqlserver.management.common.serverconnection> <サーバー接続-ファイル> [-v&#124;variable <variable-file>] [-o/overwrite]<br /><br />or<br /><br />-a/add {<server_id> [,...n] すべての}-s&#124;スクリプトを &#124; <スクリプトファイル> [-v&#124;variable <variable-file>] [-o/overwrite]<br /><br />-r/remove {<server_id> [,...n] &#124; すべて}<br /><br />-l/リスト<br /><br />-e/export {<サーバー id> [,...n] すべてを &#124;} <暗号化されたパスワードファイル><br /><br />-i/インポート {<サーバー id> [,...n] すべてを &#124;} <暗号化されたパスワードファイル>|このオプションを指定する場合は、他のオプションと組み合わせることはできません。<br /><br />サーバー id: サーバー {string} に対して指定された一意の ID<br /><br />サーバー-接続-ファイル: サーバー定義ファイル (serverconnectionfile または scriptfile)。<br /><br />変数-値-ファイル: 変数定義ファイルで、サーバー接続ファイルで使用されます。<br /><br />暗号化-パスワードファイル: ユーザー指定のパスフレーズを使用して暗号化されたサーバーパスワードファイルです。|  
|8|-?|いいえ|適用できません|適用できません|  
  
## <a name="see-also"></a>参照  
[SSMA コンソールの実行 (Oracle)](https://msdn.microsoft.com/7228ccba-c69f-4b4c-8664-01a2750183c5)  
  
