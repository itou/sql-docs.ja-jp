---
title: マップ レポートの計画 (レポート ビルダー) | Microsoft Docs
description: アクションを起こさせたり、分析情報を与えることができるよう、レポート ビルダーの自分のページ分割されたレポートにマップを使用し、分析データを地図に表示できます。
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-design
ms.topic: conceptual
ms.assetid: dc0c27a4-7e31-4a15-a0bc-3a02479d5b02
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a064351ef75698958b3f46e989eb1945625c5066
ms.sourcegitcommit: 5c7634b007f6808c87094174b80376cb20545d5f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "84881854"
---
# <a name="plan-a-map-report-report-builder-and-ssrs"></a>マップ レポートの計画 (レポート ビルダーおよび SSRS)
優れたレポートは、具体的な行動や洞察につながる情報をもたらします。 地理的背景上に売上合計や人口統計などの分析データを表現するには、 [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] のページ分割されたレポートにマップを追加します。 マップには、複数のレイヤーを含めることができます。各レイヤーには、特定の種類の空間データ (場所を表すポイント、ルートを表す線、または領域を表す多角形) によって定義されたマップ要素が表示されます。 各レイヤー上でマップ要素に分析データを関連付けることができます。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="specify-the-purpose-of-the-map"></a><a name="MapPurpose"></a> マップの目的を決める  
 優れたレポート デザインによって表現された情報は、ユーザーを問題解決に向けた行動へと導きます。 便利で見やすいマップ表示を作成するには、具体的にどのような疑問点をマップで解消しようとしているのかをはっきりさせる必要があります。 たとえば、次のようなデータをマップ上に視覚化して市場機会を特定することができます。  
  
-   店舗ごとの相対的売上  
  
-   顧客区分 (店舗の所在地と顧客の居住地との位置関係に基づく) ごとの売上  
  
-   売上やその他財務データの販売地域ごとの比較  
  
-   複数の店舗を対象に実施された各種ディスカウント戦略の売上比較  
  
 マップ表示の目的がはっきりしたら、必要なデータを分析する必要があります。 分析データのソースはレポート データセットです。 位置データのソースは空間データ ソースであり、空間データ ソースは必ず指定する必要があります。  
  
##  <a name="specify-the-spatial-and-analytical-data"></a><a name="Data"></a> 空間データと分析データを指定する  
 必要な空間データと分析データを指定する必要があります。  
  
 分析データは、レポート データセット、マップ ギャラリーからのマップに含まれるサンプル データ、ESRI シェープファイルの空間データに含まれる分析データから取得できます。  
  
 空間データには、ポイント、線、および多角形の 3 つの形態があります。  
  
-   **ポイント :** 店舗、レストラン、コンベンション センターの住所や市区町村などの場所を指定します。 マップ上に表示するすべての場所には、それに対応する空間データを指定する必要があります。 マップにポイントを追加した後で、そのポイントの位置にマーカーを表示したり、マーカーの種類、サイズ、色を変えることができます。  
  
-   **線 :** パス (飛行経路など) またはルート (配達ルートなど) を指定します。 マップに線を追加した後、線の色や線の幅を変更できます。  
  
-   **多角形 :** 地域、区域、国、都道府県、郡、市区町村などの領域や、市区町村、郵便番号、電話局、国勢調査区域などで区分される領域を指定します。 マップに多角形を追加した後、その輪郭を表示することに加え、多角形領域の中心点にマーカーを表示することができます。  
  
 必要な空間データが明らかになったら、そのソースを探す必要があります。  
  
### <a name="find-a-source-for-spatial-data"></a>空間データのソースを探す  
 マップに使用する空間データを探すには、次のソースを利用できます。  
  
-   ESRI シェープファイル (インターネットで一般公開されているシェープファイルなど)。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 空間データ ソースの空間データ。  
  
-   マップ ギャラリーのレポートからのマップ。  
  
-   空間データを ESRI シェープファイルまたは [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 空間データとして提供しているサードパーティのサイト。  
  
-   Bing マップのタイル。マップ ビューの背景を提供します。 マップにタイルを表示するには、Bing Maps Web サービスをサポートするようにレポート サーバーが構成されている必要があります。  
  
 詳細については、「ESRI シェープファイルを取得できる場所」 ([マップ ウィザードおよびマップ レイヤー ウィザードのページ &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md)) を参照してください。  
  
 空間データは、政治的に慎重な扱いが要求される場合や、著作権で保護されている場合があります。 レポートに空間データを使用する場合は、空間データ ソースの使用条件やプライバシーに関する声明を十分確認してください。  
  
 必要なデータが見つかったら、そのデータをレポート定義に埋め込むか、レポートの処理時にデータを動的に取得することができます。 詳細については、このトピックの後半にある「 [レポート定義のサイズとレポート処理にかかる時間のバランスを考える](#Embedding) 」を参照してください。  
  
### <a name="determine-the-spatial-data-and-the-spatial-data-match-fields"></a>空間データとその対応フィールドを決める  
 マップ上に分析データを表示したり、サイズ、色、マーカーの種類などを変更したりするには、空間データと分析データとを関連付けるフィールドを指定する必要があります。  
  
 空間データには、次のフィールドが存在する必要があります。  
  
-   **Spatial data.** 空間データ フィールドには、ポイント、線、または多角形をそれぞれ定義する座標セットが格納されます。  
  
-   **対応フィールド :** 個々の空間データ フィールドを一意に識別する 1 つまたは複数のフィールドです。 たとえば、店舗所在地を表すポイントの場合は、その店舗の名前を使用します。 その空間データに重複する店舗名が存在する場合は、店舗名に市区町村の名前も含めるなどして対処します。  
  
 対応フィールドは、空間データと分析データを関連付けるために使用します。  
  
### <a name="determine-the-analytical-data-and-the-analytical-data-match-fields"></a>分析データとその対応フィールドを決める  
 空間データを指定したら、分析データを指定する必要があります。 分析データのソースには、次のようなものがあります。  
  
-   既存のレポート データセット。 フィールドは、[Sales]、=Fields!Sales.Value など、単純なフィールド式として指定されます。  
  
-   空間データ ソースによって提供されるデータ フィールド。 フィールドは、"シャープ記号 (#) + 空間データのソースに基づくフィールド名" 形式のキーワードとして指定されます。  
  
 次に、対応フィールドの名前を決める必要があります。  
  
-   対応フィールド : 空間データの対応フィールドと同じ情報を指定する 1 つまたは複数のフィールドを決めることによって、空間データと分析データの関係を構築します。 対応フィールドは、データ型だけでなく形式も一致している必要があります。  
  
 空間データ ソース、空間データ、分析データ ソース、分析データ、および対応フィールドが決まったら、レポートに追加するマップの種類を決めます。  
  
##  <a name="choose-a-map-type"></a><a name="MapType"></a> マップの種類を選択する  
 マップ ウィザードを実行する際は、マップと、最初のマップ レイヤーをレポートに追加します。 ウィザードの指示に従って、次のいずれかの種類のマップをレポートに追加できます。  
  
-   場所を表示するだけで、分析データが関連付けられていない基本マップ。  
  
-   それぞれのマップ要素に単一の分析値 (店舗所在地ごとの売上合計など) が関連付けられているマップ。  
  
-   それぞれのマップ要素に複数の分析値 (店舗所在地ごとの顧客数と売上合計など) が関連付けられているマップ。  
  
 次の表では、各マップの種類について説明します。 マップでは、その種類に関係なく、パレット、罫線のスタイル、フォントを制御するテーマを選択したり、ラベルを表示したりできます。  
  
|ウィザード アイコン|レイヤー スタイル|レイヤーの種類|説明およびオプション|  
|-----------------|-----------------|----------------|-----------------------------|  
|![rs_MapType_Polygon_Basic](../../reporting-services/report-design/media/rs-maptype-polygon-basic.gif "rs_MapType_Polygon_Basic")|基本マップ|多角形|領域のみ (販売地域など) を表示するマップ。<br /><br /> オプション:パレットで色を使い分けるか、単色を使用する。 パレットには、一連の色があらかじめ定義されています。 パレットのすべての色を割り当てた場合、色の濃淡が割り当てられます。|  
|![rs_MapType_Polygon_ColorAnalytical](../../reporting-services/report-design/media/rs-maptype-polygon-coloranalytical.gif "rs_MapType_Polygon_ColorAnalytical")|色分析マップ|多角形|分析データを地域ごとの売上データなどで色分けして表示するマップ。|  
|![rs_MapType_Polygon_Bubble](../../reporting-services/report-design/media/rs-maptype-polygon-bubble.gif "rs_MapType_Polygon_Bubble")|バブル マップ|多角形|領域に中央揃えで表示されるバブルのサイズを、地域ごとの売上データなどに基づいて変化させながら分析データを表示するマップ。<br /><br /> オプション:第 2 分析フィールドに基づいて領域の色を変え、色ルールを指定する。|  
|![rs_MapType_Line_Basic](../../reporting-services/report-design/media/rs-maptype-line-basic.gif "rs_MapType_Line_Basic")|基本線マップ|Line|線のみ (配達ルートなど) を表示するマップ。<br /><br /> オプション:パレットで色を使い分けるか、単色を使用する。|  
|![rs_MapType_Line_Analytical](../../reporting-services/report-design/media/rs-maptype-line-analytical.gif "rs_MapType_Line_Analytical")|分析線マップ|Line|配達済みの荷物の数や、ルートごとの時間指定の達成率などに基づいて、線の色や幅を変化させるマップ。<br /><br /> オプション:一方の分析フィールドでは線の幅を変化させ、別の分析フィールドでは線の色を変化させて、色ルールを指定する。|  
|![rs_MapType_Marker_Basic](../../reporting-services/report-design/media/rs-maptype-marker-basic.gif "rs_MapType_Marker_Basic")|基本マーカー マップ|ポイント|それぞれの場所 (市区町村など) にマーカーを表示するマップ。<br /><br /> オプション:パレットで色を使い分けるか、単色を使用して、マーカーのスタイルを変更する。|  
|![rs_MapType_Marker_Bubble](../../reporting-services/report-design/media/rs-maptype-marker-bubble.gif "rs_MapType_Marker_Bubble")|バブル マーカー マップ|ポイント|場所ごとにバブルを表示するマップ。市区町村ごとの売上データなど、特定の分析データ フィールドによってバブルのサイズが変化します。<br /><br /> オプション:第 2 分析フィールドに基づいてバブルの色を変え、色ルールを指定する。|  
|![rs_MapType_Marker_Analytical](../../reporting-services/report-design/media/rs-maptype-marker-analytical.gif "rs_MapType_Marker_Analytical")|分析マーカー マップ|ポイント|場所ごとにマーカーを表示するマップ。分析データ (販売が好調な製品、利益率、ディスカウント戦略など) に基づいて、マーカーの色、サイズ、種類などが変化します。<br /><br /> オプション : マーカーの種類を第 1 の分析フィールドで変化させ、マーカーのサイズを第 2 分析フィールドで変化させ、マーカーの色を第 3 の分析フィールドで変化させて、色ルールを指定する。|  
  
 マップ ウィザードでマップを追加した後、レイヤー ウィザードを使用して、追加レイヤーを作成したり、レイヤーのオプションを変更したりできます。 ウィザードの詳細については、「[マップ ウィザードおよびマップ レイヤー ウィザード &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md)」を参照してください。  
  
 表示オプションまたはデータ オプションはレイヤーごとにカスタマイズできます。 ウィザードの実行後にマップをカスタマイズする方法の詳細については、「 [マップまたはマップ レイヤーのデータと表示のカスタマイズ &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md)) を参照してください。  
  
##  <a name="plan-for-legends"></a><a name="Legend"></a> 凡例について検討する  
 見やすいマップにするために、各種の凡例、カラー スケール、距離スケールなどを追加することができます。 マップをデザインする際は、凡例の表示位置を検討します。 それぞれの凡例には、次の情報を指定できます。  
  
-   **凡例の場所 :** たとえば、凡例は、ビューポートの内側または外側に表示できるほか、ビューポートを基準とする 12 の相対位置に表示することができます。  
  
-   **凡例のスタイル :** たとえば、フォント スタイル、罫線のスタイル、区切り線、塗りつぶしなどのプロパティを指定できます。  
  
-   **凡例のタイトル :** たとえば、タイトル テキストを指定し、そのタイトルをマップの凡例またはカラー スケールに対して表示するかどうかを別々に制御できます。  
  
-   **マップの凡例のレイアウト :** たとえば、マップの凡例を縦長に表示したり横長に表示したりできます。  
  
 凡例の内容は、それぞれのレイヤーに対して設定されたルール オプションに従い、レポート処理時に自動的に作成されます。  
  
 既定では、すべてのレイヤーのルールの結果がマップの最初の凡例に表示されます。 複数の凡例を作成し、ルールごとに結果の表示先として使用する凡例を割り当てます。  
  
 詳細については、「[ルールおよび分析データを使用した多角形、線、およびポイントの表示の変更 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)」および「[マップの凡例、カラー スケール、および関連付けられているルールの変更 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md)」をご覧ください。  
  
##  <a name="balance-report-definition-size-and-report-processing-time"></a><a name="Embedding"></a> レポート定義のサイズとレポート処理にかかる時間のバランスを考える  
 マップ用のレポートをデザインする際に重要なことは、レポートのパフォーマンスを制御するオプションと、レポート定義のサイズを制御するオプションのバランスです。 空間データを使用したマップ要素や Bing マップのタイルは、静的なデータとしてレポート定義に埋め込むか、動的データとしてレポート処理時にその都度作成することができます。 静的なマップ データまたは動的なマップ データのトレードオフを評価し、環境に合わせてバランスを調整する必要があります。 次の点を考慮して判断してください。  
  
-   マップ要素が埋め込まれるとレポート定義のサイズが著しく増加しますが、レポート内でマップを表示するのに要する時間が短縮されます。 レポート サーバーによってサイズが制限されている場合は、それに対処する必要があります。  
  
-   レポート定義では、処理できる空間データ ポイント数の上限が指定されるほか、レポート定義に含めることのできるマップ要素の数を規定する別個の値が指定されます。  
  
-   動的なマップ要素の場合はレポート定義のサイズが小さくなりますが、マップを処理して表示するのに要する時間が増加します。  
  
-   空間データのソースがローカル コンピューター上に置かれている場合、マップ要素は常にレポート定義に埋め込まれます。 これには、ローカルにインストールされた ESRI シェープファイルまたはマップ ギャラリーからの空間データも含まれます。  
  
 動的な空間データを使用するには、空間データ ソースをレポート サーバーに置く必要があります。 レポートのデザインに [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]を使用する場合、空間データ ソースをプロジェクトに追加し、レポート定義と併せてレポート サーバーにパブリッシュすることができます。 レポート ビルダーを使用してレポートをデザインする場合は、まず空間データをレポート サーバーにアップロードし、その後、ウィザードまたはレイヤーのプロパティで、そのマップ レイヤーに使用する空間データのソースを指定する必要があります。  
  
## <a name="see-also"></a>参照  
 [マップまたはマップ レイヤーのデータと表示のカスタマイズ &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md)   
 [チュートリアル:マップ レポート &#40;レポート ビルダー&#41;](../../reporting-services/tutorial-map-report-report-builder.md)   
 [マップ &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/maps-report-builder-and-ssrs.md)   
 [レポートのトラブルシューティング: マップ レポート &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/troubleshoot-reports-map-reports-report-builder-and-ssrs.md)  
  
  
