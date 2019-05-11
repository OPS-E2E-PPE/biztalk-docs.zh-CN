---
title: 在 SAP 中的 EXEC 语句的语法 |Microsoft Docs
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
ms.openlocfilehash: 7a48a043eb53b4ad4d8aeddcf27245766915699c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372721"
---
# <a name="syntax-for-an-exec-statement-in-sap"></a>在 SAP 中的 EXEC 语句的语法
以下部分介绍了用于实现对 EXEC 语句的语法规范[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。 请注意，在某些情况下，该语法的 TRANSACT-SQL 语法稍有不同。  
  
```  
EXEC rfc_name {<argument_element>} [ , …n ]  {;}[0,1] [ OPTION <disabledatavalidation>, <firstresultset> ]  
```  
  
 其中：  
  
- **rfc_name**指定要执行的函数调用的名称。  
  
- **<argument_element>** ::= @param_name = [0,1] \<const\> {[ INPUT &#124; OUTPUT ]}[0,1]  
  
  -   **param_name**指定函数接口中定义的参数名称。  
  
  -   **\<const\>** ::= integer &#124; real &#124; string &#124; ? &#124; NULL &#124; xml_element  
  
- **选项**提供了在你想要显示的数据的选项。 可用选项是：  
  
  - **disabledatavalidation**选项集**EnableSafeTyping**属性中的基础绑定[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 启用安全键入 DATS、 TIMS 和 NUMC 数据类型表示为字符串。 有关此绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
  - **firstresultset**指定返回的第一个结果集[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。 ADO 提供程序源上执行任何语句，仅第一个返回的结果集时可用。 RFC EXEC 方案通常多个表参数返回，但如果只有第一个结果集是可用于客户端程序，这可能不是使用。 通过指定"firstresultset"关键字的 OPTION 子句的一部分，客户端可以指定他们想要返回的提供程序的第一个表参数。 例如：  
  
    ```  
    EXEC Z_TEST_ALL_TYPES @P_IN='TestInput' OPTION 'disabledatavalidation', firstresultset TAB_ALLTYPES'  
    ```  
  
     在此示例中，在 EXEC 语句指定返回的表的第一个参数应为 TAB_ALLTYPES。  
  
  > [!IMPORTANT]
  >  您必须始终提供值选项关键字在单引号中，例如，'*disabledatavalidation*。  
  
  在上述语法中，可以使用 xml_element 来为复杂类型提供输入。 Xml 元素结构将不同的结构和表。 为结构 xml_element 类似于以下内容：  
  
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
  
 有关示例语句，请参阅[EXEC 语句示例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)。  
  
## <a name="handling-named-parameters"></a>命名参数的处理  
 以下是用于指定命名参数在 EXEC 查询中的指导原则：  
  
- 必须指定的参数命名它们 (例如， @param_name= value)。  
  
  > [!NOTE]
  >  不支持未命名的参数  
  
- 当使用默认值定义参数时，可以不必指定参数来执行该过程。  
  
- EXEC 查询不支持使用参数具有以下属性：  
  
  - 嵌套的结构 （包含作为其字段的结构的结构）。  
  
  - 嵌套的表。  
  
  - 包含一个结构的表。  
  
  - 包含表的结构。  
  
  - 结构或表中的字段的复合字符串类型，例如`SSTRING`或`RAWSTRING`。  
  
    执行 RFC 时下, 表列出了 RFC 参数类型和参数方向之间的逻辑映射。  
  
  |RFC 参数类型|查询关键字|参数方向|  
  |--------------------|-------------------|-------------------------|  
  |导入参数|执行任何操作|Paramdirection.Input|  
  |导出参数|“输出”|Paramdirection.Output|  
  |表参数|输出/采取任何操作|InputOutput|  
  
  以下是处理参数的常规指导原则：  
  
- 为常量或通过在查询中使用占位符，可以指定参数值。  
  
- 当在查询中使用占位符，必须创建`SAPParameter`对象，并将其添加到相应的命令对象。 然后将该占位符名称传递给构造函数;方向和值取决于上下文。  
  
  -   有关`Input`参数，请执行不在查询中指定参数方向的关键字。 `value`必须设置参数对象的字段，或提供程序将引发异常。 您必须显式设置`direction`字段的参数对象，因为提供程序的默认值为`Input`。  
  
  -   对于其他参数，使用窗体`@paramname=@placeholder`并指定`Output`在查询中显式关键字。 然后必须添加`SAPParameter`的对应于该占位符并显式设置为参数方向`ParamDirection.Output`或`ParamDirection.InputOutput`，具体取决于参数类型。  
  
- 参数名称和占位符名称不区分大小写。  
  
- 不能在查询中重复参数名称，除非它们具有不同的方向。  
  
- 占位符名称不能在查询中重复。  
  
## <a name="considerations-when-calling-an-exec-statement"></a>调用 EXEC 语句时的注意事项  
 本部分列出了使用 EXEC 语句中的使用时必须牢记的点[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。  
  
- EXEC 语句[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]将返回`TIMS`字段的值作为.NET`System.DateTime`对象。  
  
  > [!NOTE]
  >  SELECT 语句[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返回`TIMS`字段的值作为.NET`System.TimeSpan`对象。 有关 SELECT 语句的详细信息，请参阅[为在 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。  
  
## <a name="see-also"></a>请参阅  
 [关于 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)