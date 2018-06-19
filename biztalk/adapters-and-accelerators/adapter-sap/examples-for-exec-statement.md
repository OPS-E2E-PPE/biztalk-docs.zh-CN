---
title: EXEC 语句中 BizTalk mySAP 适配器中的示例 |Microsoft 文档
description: EXEC 示例和样本使用 BizTalk 适配器包 (BAP) 中的 mySAP 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad2691f4-34bb-423c-9b3e-4abe2d55ddac
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eaae930d7d94d24bac9d484957ccf02718af60f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22216365"
---
# <a name="examples-for-exec-statement"></a>EXEC 语句的示例
本主题演示各种 EXEC 语句的示例语法。

## <a name="sample-statements"></a>示例语句 
  
-   若要执行不使用输入参数 BAPI，使用以下语法;通过返回数据**DataReader**对象：  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST  
    ```  
  
-   若要执行的 RFC 都采用输入的参数，请使用以下语法：  
  
    ```  
    EXEC RFC_CUSTOMER_GET @NAME1='Contoso'  
    ```  
  
-   若要执行的 RFC 都采用为变量指定的输入的参数，请使用以下语法：  
  
    ```  
    EXEC RFC_CUSTOMER_GET @var=@var  
    ```  
  
     在此示例中，你必须创建一个名为参数`@var`和显式设置值 （例如，到 1001)，因为 RFC_CUSTOMER_GET 的第一个参数对应于 KUNNR （客户编号）  
  
-   若要执行的输入的参数名称中使用变量 RFC，使用以下语法：  
  
    ```  
    EXEC RFC_CUSTOMER_GET @KUNNR=@var1, @NAME1='Contoso'  
    ```  
  
     你必须创建一个名为参数`@var1`，指定值，然后将其绑定到相应的命令对象。 新创建的参数对象的默认方向是`input`。  
  
-   若要作为参数执行 BAPI 和返回的表，请使用以下语法：  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST @COMPANYCODE_LIST=@var1 OUTPUT  
    ```  
  
     你必须创建一个名为参数`@var1`、 指定的值，并将其绑定到相应的命令对象。 应为新创建的参数对象的方向`InputOutput`或`Output`。  
  
-   下面的 EXEC 示例使用表复杂类型参数。 在示例中，@fields是表参数。  
  
    ```  
    exec rfc_read_table @query_table='BNKA', @fields='<FIELDS xmlns='http://Microsoft.LobServices.Sap/2007/03/Rfc/'>  
                <RFC_DB_FLD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                  <FIELDNAME>BANKL</FIELDNAME>  
                </RFC_DB_FLD>  
                <RFC_DB_FLD  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                    <FIELDNAME>BANKS</FIELDNAME>  
                </RFC_DB_FLD>  
              </FIELDS>', @fields=@flds output  
    ```  
  
-   下面的 EXEC 示例使用结构复杂类型。 在示例中，@equimaster是结构参数。  
  
    ```  
    exec BAPI_EQMT_MODIFY @equipment='000000000000000637', @equimaster='<EQUIMASTER>           
                <EQUIPMENT xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">equip</EQUIPMENT>  
                <EQUICATGRY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">E</EQUICATGRY>  
                <MATERIAL xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">mat</MATERIAL>  
              </EQUIMASTER >', @equimaster=@em output  
    ```  
  
## <a name="support-for-complex-parameter-types"></a>对复杂的参数类型的支持  
 有两种方法，以支持复杂的 RFC 参数 （表和结构） 时使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:  
  
-   复杂类型的提供内联的 XML 值。 此示例演示如何将 XML 传递给复杂的参数类型*字段*。 在下面的示例中， *@fields*是表参数。  
  
    ```  
    exec rfc_read_table @query_table='BNKA', @fields='<FIELDS xmlns='http://Microsoft.LobServices.Sap/2007/03/Rfc/'>  
                <RFC_DB_FLD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                  <FIELDNAME>BANKL</FIELDNAME>  
                </RFC_DB_FLD>  
                <RFC_DB_FLD  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                    <FIELDNAME>BANKS</FIELDNAME>  
                </RFC_DB_FLD>  
              </FIELDS>', @fields=@flds output  
    ```  
  
-   创建**DataTable**参数中的复杂类型和 SAP 参数值的集的字段的列**DataTable**。 此示例演示如何设置@fields使用复杂类型**DataTable**。  
  
    ```  
    cmd.CommandText = "exec rfc_read_table @query_table='BNKA', @fields = @p_fields";  
    DataTable dt = new DataTable();  
    dt.Columns.Add("FIELDNAME");  
    SAPParameter p = new SAPParameter("@p_fields");  
    p.Value = dt;  
    ```  
  
## <a name="limitations"></a>限制  
 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]具有以下限制为复杂类型。  
  
-   传递时，复杂类型参数中使用**DataTable**，必须包括所有字段 （列） 中的复杂类型**DataTable**。  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]不支持**DbNull**。 无法设置**DbNull**作为参数的值。  
  
