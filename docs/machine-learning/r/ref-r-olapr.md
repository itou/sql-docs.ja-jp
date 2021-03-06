---
title: olapR R パッケージ
description: olapR は、Microsoft が提供する R パッケージであり、SQL Server Analysis Services OLAP キューブに対する MDX クエリに使用されます。 関数はすべての MDX 操作をサポートするわけではありませんが、ディメンションに対してスライス、ダイス、ドリルダウン、ロールアップ、およびピボットを行うクエリを作成できます。 このパッケージは、SQL Server Machine Learning Services と SQL Server 2016 R Services に含まれています。
ms.prod: sql
ms.technology: machine-learning-services
ms.date: 07/14/2020
ms.topic: how-to
author: dphansen
ms.author: davidph
monikerRange: '>=sql-server-2016||>=sql-server-linux-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: 844489b4c9f3e0e92848ebb1c9cb3b725ac5fedd
ms.sourcegitcommit: d1535944bff3f2580070cc036ece30f1d43ee2ce
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86406165"
---
# <a name="olapr-r-package-in-sql-server-machine-learning-services"></a>olapR (SQL Server Machine Learning Services の R パッケージ)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

**olapR** は、Microsoft が提供する R パッケージであり、SQL Server Analysis Services OLAP キューブに対する MDX クエリに使用されます。 関数はすべての MDX 操作をサポートするわけではありませんが、ディメンションに対してスライス、ダイス、ドリルダウン、ロールアップ、およびピボットを行うクエリを作成できます。 このパッケージは、[SQL Server Machine Learning Services](../sql-server-machine-learning-services.md) と [SQL Server 2016 R Services](sql-server-r-services.md) に含まれています。

このパッケージは、サポートされているすべてのバージョンの SQL Server で Analysis Services OLAP キューブへの接続に使用できます。 現時点では、表形式モデルへの接続はサポートされていません。

## <a name="load-package"></a>パッケージの読み込み

**olapR** パッケージは、R セッションに事前に読み込まれません。 次のコマンドを実行してパッケージを読み込みます。

```R
library(olapR)
```

## <a name="package-version"></a>パッケージ バージョン

すべての Windows 限定の製品、およびパッケージを提供するダウンロードにおける現行バージョンは 1.0.0 です。

## <a name="full-reference-documentation"></a>完全なリファレンス ドキュメント

**olapr** パッケージは、複数の Microsoft 製品で配布されていますが、このパッケージを SQL Server または別の製品のどちらで取得しても、使用方法は同じです。 これらの関数は同じであるため、[個々の sqlrutils 関数のドキュメント](https://docs.microsoft.com/machine-learning-server/r-reference/olapr/olapr)は Microsoft Machine Learning Server の [R リファレンス](https://docs.microsoft.com/machine-learning-server/r-reference/introducing-r-server-r-package-reference)の下でのみ公開されています。 製品固有の動作が存在する場合、関数のヘルプ ページにその相違点が示されます。

## <a name="availability-and-location"></a>可用性と場所

このパッケージは、Azure 上の複数の仮想マシン イメージの他に、次の製品にも用意されています。 パッケージの場所はそれに応じて異なります。

Product | 場所 |
--------|----------|
SQL Server Machine Learning Services (R 統合あり) | C:\Program Files\Microsoft SQL Server\MSSQL14.MSSQLSERVER\R_SERVICES\library | 
SQL Server 2016 R Services | C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\R_SERVICES\library
Microsoft Machine Learning Server (R Server) | C:\Program Files\Microsoft\R_SERVER\library |
Microsoft R Client | C:\Program Files\Microsoft\R Client\R_SERVER\library |
Data Science Virtual Machine (Azure 上) | C:\Program Files\Microsoft\R Client\R_SERVER\library |
SQL Server Virtual Machine (Azure 上) <sup>1</sup> | C:\Program Files\Microsoft SQL Server\MSSQL14.MSSQLSERVER\R_SERVICES\library |

<sup>1</sup> R 統合は SQL Server では省略可能です。 olapR パッケージは、VM の構成中に Machine Learning または R 機能を追加するとインストールされます。


## <a name="see-also"></a>関連項目

[olapR を使って MDX クエリを作成する方法](how-to-create-mdx-queries-using-olapr.md)
