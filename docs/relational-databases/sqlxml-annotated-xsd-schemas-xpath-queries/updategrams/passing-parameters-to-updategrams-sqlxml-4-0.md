---
title: アップデートグラムへのパラメーターの引き渡し (SQLXML)
description: SQLXML 4.0 でアップデートグラムにパラメーターを渡す方法について説明します。
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nullvalue attribute
- passing parameters [SQLXML]
- parameters [SQLXML]
- updategrams [SQLXML], passing parameters
- null values [SQLXML]
ms.assetid: 2354e6e7-1860-471f-8711-4e374c5a4ed2
author: MightyPen
ms.author: genemi
ms.custom: seo-lt-2019
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: ce7be0a6f01ac92f13f35e4410dc59601fdbdc01
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85790561"
---
# <a name="passing-parameters-to-updategrams-sqlxml-40"></a>アップデートグラムへのパラメーターの引き渡し (SQLXML 4.0)
[!INCLUDE [SQL Server Azure SQL Database](../../../includes/applies-to-version/sql-asdb.md)]
  アップデートグラムはテンプレートであり、パラメーターを渡すことができます。 テンプレートにパラメーターを渡す方法の詳細については、「[アップデートグラムのセキュリティに関する考慮事項 &#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/security/updategram-security-considerations-sqlxml-4-0.md)」を参照してください。  
  
 アップデートグラムでは、パラメーター値として NULL を渡すことができます。 NULL パラメーター値を渡すには、 **nullvalue**属性を指定します。 **Nullvalue**属性に割り当てられた値は、パラメーター値として指定されます。 アップデートグラムでは、この値は NULL として扱われます。  
  
> [!NOTE]  
>  とでは、 **\<sql:header>** **\<updg:header>** **nullvalue**を非修飾として指定する必要があります。一方、では、 **\<updg:sync>** **nullvalue**を qualified として指定します ( **updg: nullvalue**など)。  
  
## <a name="examples"></a>使用例  
 次の例を使用して実際のサンプルを作成するには、 [SQLXML の例を実行するための要件](../../../relational-databases/sqlxml/requirements-for-running-sqlxml-examples.md)を満たす必要があります。  
  
 アップデートグラムの例を使用する前に、次の点に注意してください。  
  
-   例では、アップデートグラムでマッピング スキーマを指定せず、既定のマッピングを使用します。 マッピングスキーマを使用するアップデートグラムの例については、「[アップデートグラムでの注釈付きマッピングスキーマの指定 &#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md)」を参照してください。  
  
### <a name="a-passing-parameters-to-an-updategram"></a>A: アップデートグラムにパラメーターを渡す  
 この例では、アップデートグラムで HumanResources.Shift テーブル内の従業員の姓を変更します。 アップデートグラムには、勤務時間を一意に識別する ShiftID と、Name の 2 つのパラメーターが渡されます。  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
  <updg:param name="ShiftID"/>  
  <updg:param name="Name" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="$ShiftID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="$Name" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a>アップデートグラムをテストするには  
  
1.  上のアップデートグラムをメモ帳にコピーし、UpdategramWithParameters.xml としてファイルに保存します。  
  
2.  次の行を追加して、 [ADO を使用して sqlxml 4.0 クエリを実行](../../../relational-databases/sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md)し、アップデートグラムを実行するための sqlxml 4.0 テストスクリプト (sqlxml4test.vbs) を準備し `cmd.Properties("Output Stream").Value = outStream` ます。  

    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value  
    cmd.Parameters.Append cmd.CreateParameter("@ShiftID",  2, 1,  0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@Name",   200, 1, 50, "New Name")  
    ```  
  
### <a name="b-passing-null-as-a-parameter-value-to-an-updategram"></a>B: アップデートグラムにパラメーター値として NULL を渡す  
 アップデートグラムを実行するときに、NULL に設定するパラメーターに "isnull" 値を割り当てます。 アップデートグラムでは "isnull" パラメーター値が NULL に変換され、それに従って処理が行われます。  
  
 次のアップデートグラムでは、従業員の役職を NULL に設定します。  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header nullvalue="isnull" >  
  <updg:param name="EmployeeID"/>  
  <updg:param name="ManagerID" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Employee EmployeeID="$EmployeeID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Employee ManagerID="$ManagerID" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a>アップデートグラムをテストするには  
  
1.  上のアップデートグラムをメモ帳にコピーし、UpdategramPassingNullvalues.xml としてファイルに保存します。  
  
2.  次の行を追加して、 [ADO を使用して sqlxml 4.0 クエリを実行](../../../relational-databases/sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md)し、アップデートグラムを実行するための sqlxml 4.0 テストスクリプト (sqlxml4test.vbs) を準備し `cmd.Properties("Output Stream").Value = outStream` ます。  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value   
    cmd.Parameters.Append cmd.CreateParameter("@EmployeeID", 3, 1, 0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@ManagerID",  3, 1, 0, Null)  
    ```  
  
## <a name="see-also"></a>関連項目  
 [SQLXML 4.0&#41;&#40;アップデートグラムのセキュリティに関する考慮事項](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
