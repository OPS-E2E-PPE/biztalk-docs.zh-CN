---
title: SAP 中的 EXEC 语句的语法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
ms.assetid: 406b1100-39a0-4321-89c9-ec1b8a3cfdc6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 362aa1f81158c9d9f1135c9bff25c64d7d745953
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="syntax-for-an-exec-statement-in-sap"></a>SAP 中的 EXEC 语句的语法
以下部分介绍用于实现 EXEC 语句的语法规范[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。 请注意，在某些情况下，语法的 TRANSACT-SQL 语法稍有不同。  
  
```  
EXEC rfc_name {<argument_element>} [ , …n ]  {;}[0,1] [ OPTION <disabledatavalidation>, <firstresultset> ]  
```  
  
 其中：  
  
-   **rfc_name**指定执行的函数调用的名称。  
  
-   **< argument_element >** :: = @param_name = [0，1] \<const\> {[输入 &#124;输出]} [0，1]  
  
    -   **param_name**指定函数接口中定义的参数名称。  
  
    -   **\<const\>**  :: = 整数 &#124; 实际 &#124; 字符串 &#124;？ &#124;NULL &#124;xml_element  
  
-   **选项**提供上要如何表示该数据的选项。 可用选项是：  
  
    -   **disabledatavalidation**选项集**EnableSafeTyping**绑定属性在基础[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 启用安全键入的 DAT、 TIMS 和 NUMC 数据类型表示为字符串。 有关此绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
    -   **firstresultset**指定返回的第一个结果集[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。 在 ADO 提供程序源上执行任何语句，仅第一个返回的结果集时可用。 对于 RFC EXEC 方案，通常多个表参数将返回但如果只有第一个结果集不可用于客户端程序，这可能不是使用。 通过指定的 OPTION 子句的一部分"firstresultset"关键字，客户端可以指定他们想要返回的提供程序的第一个表参数。 例如：  
  
        ```  
        EXEC Z_TEST_ALL_TYPES @P_IN='TestInput' OPTION 'disabledatavalidation', firstresultset TAB_ALLTYPES'  
        ```  
  
         在此示例中，EXEC 语句指定返回的第一个表参数应为 TAB_ALLTYPES。  
  
    > [!IMPORTANT]
    >  你必须始终提供值选项关键字在单引号中，例如，*disabledatavalidation*。  
  
 在前面的语法中，可以使用 xml_element 对于复杂类型提供输入。 Xml 元素结构将不同的结构和表。 结构 xml_element 如下所示：  
  
```  
<PARAM_NAME>  
    <FIELDNAME_1 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_1>  
    <FIELDNAME_2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_2>  
    ...  
    ...  
</ PARAM_NAME>  
```  
  
 为表 xml_element 如下所示：  
  
```  
<PARAM_NAME>  
    <STRUCT_NAME  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
        <FIELDNAME_1>value</FIELDNAME_1>  
    <STRUCT_NAME/>  
    <STRUCT_NAME  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
        <FIELDNAME_1>value</FIELDNAME_1>  
    <STRUCT_NAME/>  
    ...  
    ...  
</ PARAM_NAME>  
```  
  
 例如，结构类型的 XML 元素如下所示：  
  
```  
<INOUT_STRUCT>  
       <ACCPFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006</ACCPFIELD>  
       <CHARFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">John</CHARFIELD>                 
</INOUT_STRUCT>  
```  
  
 同样，表类型的 XML 元素如下所示：  
  
```  
<TAB_ALLTYPES>   
<ZZSTRUCTALLTYPES_RFC xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
       <ACCPFIELD>2006</ACCPFIELD>  
       <CHARFIELD>John</CHARFIELD>                          
</ZZSTRUCTALLTYPES_RFC>  
<ZZSTRUCTALLTYPES_RFC xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
       <ACCPFIELD>2007</ACCPFIELD>  
       <CHARFIELD>James</CHARFIELD>                          
</ZZSTRUCTALLTYPES_RFC>  
</TAB_ALLTYPES>  
```  
  
 有关示例语句，请参阅[EXEC 语句的示例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)。  
  
## <a name="handling-named-parameters"></a>命名参数的处理  
 以下是用于指定命名 EXEC 查询中的参数的准则：  
  
-   你必须指定参数命名它们 (例如， @param_name= 值)。  
  
    > [!NOTE]
    >  不支持未命名的参数  
  
-   使用默认值定义参数后，您可以执行过程未指定参数。  
  
-   EXEC 查询不支持使用具有以下属性的参数：  
  
    -   嵌套的结构 （包含作为其字段的结构的结构）。  
  
    -   嵌套的表。  
  
    -   一个包含结构的表。  
  
    -   一个包含表的结构。  
  
    -   结构或表中的字段的复合字符串类型，例如`SSTRING`或`RAWSTRING`。  
  
     下表列出 RFC 参数类型的参数方向之间的逻辑映射时执行 RFC。  
  
    |RFC Param 类型|查询关键字|参数方向|  
    |--------------------|-------------------|-------------------------|  
    |导入参数|执行任何操作|Paramdirection.Input|  
    |导出参数|“输出”|Paramdirection.Output|  
    |表参数|输出/采取任何操作|InputOutput|  
  
 以下是处理参数所需的常规指导原则：  
  
-   为常量或通过在查询中使用占位符，你可以指定参数值。  
  
-   在查询中使用占位符，必须创建`SAPParameter`对象并将其添加到相应的命令对象。 然后将占位符名称传递给构造函数;方向和值取决于上下文。  
  
    -   有关`Input`参数，不在指定查询参数方向的关键字。 `value`必须设置的参数对象的字段，或提供程序将引发异常。 不，必须显式设置`direction`字段的参数对象，因为提供程序将默认为`Input`。  
  
    -   对于其他参数，使用该窗体`@paramname=@placeholder`并指定`Output`在查询中显式的关键字。 然后，必须添加`SAPParameter`对应占位符，显式将参数方向设置为`ParamDirection.Output`或`ParamDirection.InputOutput`，具体取决于参数类型。  
  
-   参数名称和占位符名称不区分大小写。  
  
-   参数名称不能重复在查询中，除非它们具有不同的方向。  
  
-   在查询中，占位符名称不能重复。  
  
## <a name="considerations-when-calling-an-exec-statement"></a>调用 EXEC 语句时的注意事项  
 本部分列出使用 EXEC 语句使用时必须记住的点[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
-   EXEC 语句，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返回`TIMS`字段值作为.NET`System.DateTime`对象。  
  
    > [!NOTE]
    >  对于 SELECT 语句中，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返回`TIMS`字段值作为.NET`System.TimeSpan`对象。 SELECT 语句的详细信息，请参阅[为 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。  
  
## <a name="see-also"></a>另请参阅  
 [关于 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)