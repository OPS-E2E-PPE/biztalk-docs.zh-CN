---
title: "SAP 中的 EXEC 语句的语法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: EXEC statement, syntax for
ms.assetid: 406b1100-39a0-4321-89c9-ec1b8a3cfdc6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 362aa1f81158c9d9f1135c9bff25c64d7d745953
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="syntax-for-an-exec-statement-in-sap"></a><span data-ttu-id="bf0cb-102">SAP 中的 EXEC 语句的语法</span><span class="sxs-lookup"><span data-stu-id="bf0cb-102">Syntax for an EXEC Statement in SAP</span></span>
<span data-ttu-id="bf0cb-103">以下部分介绍用于实现 EXEC 语句的语法规范[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-103">The following section describes grammar specifications for implementing EXEC statements against the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="bf0cb-104">请注意，在某些情况下，语法的 TRANSACT-SQL 语法稍有不同。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-104">Notice that in several cases, the syntax is somewhat different from Transact-SQL syntax.</span></span>  
  
```  
EXEC rfc_name {<argument_element>} [ , …n ]  {;}[0,1] [ OPTION <disabledatavalidation>, <firstresultset> ]  
```  
  
 <span data-ttu-id="bf0cb-105">其中：</span><span class="sxs-lookup"><span data-stu-id="bf0cb-105">where:</span></span>  
  
-   <span data-ttu-id="bf0cb-106">**rfc_name**指定执行的函数调用的名称。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-106">**rfc_name** specifies the name of the function call to execute.</span></span>  
  
-   <span data-ttu-id="bf0cb-107">**< argument_element >** :: = @param_name = [0，1] \<const\> {[输入 &#124;输出]} [0，1]</span><span class="sxs-lookup"><span data-stu-id="bf0cb-107">**<argument_element>** ::= @param_name = [0,1] \<const\> {[ INPUT &#124; OUTPUT ]}[0,1]</span></span>  
  
    -   <span data-ttu-id="bf0cb-108">**param_name**指定函数接口中定义的参数名称。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-108">**param_name** specifies the parameter name defined in the function interface.</span></span>  
  
    -   <span data-ttu-id="bf0cb-109">**\<const\>**  :: = 整数 &#124; 实际 &#124; 字符串 &#124;？</span><span class="sxs-lookup"><span data-stu-id="bf0cb-109">**\<const\>** ::= integer &#124; real &#124; string &#124; ?</span></span> <span data-ttu-id="bf0cb-110">&#124;NULL &#124;xml_element</span><span class="sxs-lookup"><span data-stu-id="bf0cb-110">&#124; NULL &#124; xml_element</span></span>  
  
-   <span data-ttu-id="bf0cb-111">**选项**提供上要如何表示该数据的选项。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-111">**OPTION**  provides option on how you want to present the data.</span></span> <span data-ttu-id="bf0cb-112">可用选项是：</span><span class="sxs-lookup"><span data-stu-id="bf0cb-112">The available options are:</span></span>  
  
    -   <span data-ttu-id="bf0cb-113">**disabledatavalidation**选项集**EnableSafeTyping**绑定属性在基础[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-113">**disabledatavalidation** option sets the **EnableSafeTyping** binding property in the underlying [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="bf0cb-114">启用安全键入的 DAT、 TIMS 和 NUMC 数据类型表示为字符串。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-114">When safe typing is enabled the DATS, TIMS, and NUMC data types are represented as strings.</span></span> <span data-ttu-id="bf0cb-115">有关此绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-115">For more information about this binding property, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    -   <span data-ttu-id="bf0cb-116">**firstresultset**指定返回的第一个结果集[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-116">**firstresultset** specifies the first result set that is returned by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="bf0cb-117">在 ADO 提供程序源上执行任何语句，仅第一个返回的结果集时可用。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-117">When any statement is executed on an ADO Provider source, only the first result set returned is available.</span></span> <span data-ttu-id="bf0cb-118">对于 RFC EXEC 方案，通常多个表参数将返回但如果只有第一个结果集不可用于客户端程序，这可能不是使用。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-118">For RFC EXEC scenarios, usually multiple table parameters are returned but if only the first result set is available for the client program, which might not be of use.</span></span> <span data-ttu-id="bf0cb-119">通过指定的 OPTION 子句的一部分"firstresultset"关键字，客户端可以指定他们想要返回的提供程序的第一个表参数。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-119">By specifying the “firstresultset” keyword as part of the OPTION clause, clients can specify the first table parameter that they want the Provider to return.</span></span> <span data-ttu-id="bf0cb-120">例如：</span><span class="sxs-lookup"><span data-stu-id="bf0cb-120">For example:</span></span>  
  
        ```  
        EXEC Z_TEST_ALL_TYPES @P_IN='TestInput' OPTION 'disabledatavalidation', firstresultset TAB_ALLTYPES'  
        ```  
  
         <span data-ttu-id="bf0cb-121">在此示例中，EXEC 语句指定返回的第一个表参数应为 TAB_ALLTYPES。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-121">In this example, the EXEC statement specifies that the first table parameter returned should be TAB_ALLTYPES.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="bf0cb-122">你必须始终提供值选项关键字在单引号中，例如，*disabledatavalidation*。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-122">You must always provide the values for the OPTION keyword within single quotes, for example, '*disabledatavalidation*'.</span></span>  
  
 <span data-ttu-id="bf0cb-123">在前面的语法中，可以使用 xml_element 对于复杂类型提供输入。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-123">In the preceding syntax, xml_element can be used to provide input for complex types.</span></span> <span data-ttu-id="bf0cb-124">Xml 元素结构将不同的结构和表。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-124">The xml element structure will be different for structures and tables.</span></span> <span data-ttu-id="bf0cb-125">结构 xml_element 如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf0cb-125">The xml_element for structure resembles the following:</span></span>  
  
```  
<PARAM_NAME>  
    <FIELDNAME_1 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_1>  
    <FIELDNAME_2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">value</FIELDNAME_2>  
    ...  
    ...  
</ PARAM_NAME>  
```  
  
 <span data-ttu-id="bf0cb-126">为表 xml_element 如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf0cb-126">The xml_element for table resembles the following:</span></span>  
  
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
  
 <span data-ttu-id="bf0cb-127">例如，结构类型的 XML 元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf0cb-127">For example, the XML element for a structure type resembles the following:</span></span>  
  
```  
<INOUT_STRUCT>  
       <ACCPFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006</ACCPFIELD>  
       <CHARFIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">John</CHARFIELD>                 
</INOUT_STRUCT>  
```  
  
 <span data-ttu-id="bf0cb-128">同样，表类型的 XML 元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf0cb-128">Similarly, the XML element for a table type resembles the following:</span></span>  
  
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
  
 <span data-ttu-id="bf0cb-129">有关示例语句，请参阅[EXEC 语句的示例](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-129">For example statements, see [Examples for EXEC Statement](../../adapters-and-accelerators/adapter-sap/examples-for-exec-statement.md).</span></span>  
  
## <a name="handling-named-parameters"></a><span data-ttu-id="bf0cb-130">命名参数的处理</span><span class="sxs-lookup"><span data-stu-id="bf0cb-130">Handling Named Parameters</span></span>  
 <span data-ttu-id="bf0cb-131">以下是用于指定命名 EXEC 查询中的参数的准则：</span><span class="sxs-lookup"><span data-stu-id="bf0cb-131">The following are guidelines for specifying named parameters in EXEC queries:</span></span>  
  
-   <span data-ttu-id="bf0cb-132">你必须指定参数命名它们 (例如， @param_name= 值)。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-132">You must specify parameters by naming them (for example, @param_name=value).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf0cb-133">不支持未命名的参数</span><span class="sxs-lookup"><span data-stu-id="bf0cb-133">Unnamed parameters are not supported</span></span>  
  
-   <span data-ttu-id="bf0cb-134">使用默认值定义参数后，您可以执行过程未指定参数。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-134">When a parameter is defined using a default value, you can execute the procedure without specifying a parameter.</span></span>  
  
-   <span data-ttu-id="bf0cb-135">EXEC 查询不支持使用具有以下属性的参数：</span><span class="sxs-lookup"><span data-stu-id="bf0cb-135">EXEC queries do not support using parameters with the following properties:</span></span>  
  
    -   <span data-ttu-id="bf0cb-136">嵌套的结构 （包含作为其字段的结构的结构）。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-136">Nested structures (structures that contain structures as their fields).</span></span>  
  
    -   <span data-ttu-id="bf0cb-137">嵌套的表。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-137">Nested tables.</span></span>  
  
    -   <span data-ttu-id="bf0cb-138">一个包含结构的表。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-138">A table containing a structure.</span></span>  
  
    -   <span data-ttu-id="bf0cb-139">一个包含表的结构。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-139">A structure containing a table.</span></span>  
  
    -   <span data-ttu-id="bf0cb-140">结构或表中的字段的复合字符串类型，例如`SSTRING`或`RAWSTRING`。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-140">A structure or table that has fields with composite string types, for example `SSTRING` or `RAWSTRING`.</span></span>  
  
     <span data-ttu-id="bf0cb-141">下表列出 RFC 参数类型的参数方向之间的逻辑映射时执行 RFC。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-141">The following table lists logical mappings between RFC parameter types and parameter directions when executing an RFC.</span></span>  
  
    |<span data-ttu-id="bf0cb-142">RFC Param 类型</span><span class="sxs-lookup"><span data-stu-id="bf0cb-142">RFC Param Type</span></span>|<span data-ttu-id="bf0cb-143">查询关键字</span><span class="sxs-lookup"><span data-stu-id="bf0cb-143">Query Keyword</span></span>|<span data-ttu-id="bf0cb-144">参数方向</span><span class="sxs-lookup"><span data-stu-id="bf0cb-144">Parameter Direction</span></span>|  
    |--------------------|-------------------|-------------------------|  
    |<span data-ttu-id="bf0cb-145">导入参数</span><span class="sxs-lookup"><span data-stu-id="bf0cb-145">Import parameters</span></span>|<span data-ttu-id="bf0cb-146">执行任何操作</span><span class="sxs-lookup"><span data-stu-id="bf0cb-146">Nothing</span></span>|<span data-ttu-id="bf0cb-147">Paramdirection.Input</span><span class="sxs-lookup"><span data-stu-id="bf0cb-147">Paramdirection.Input</span></span>|  
    |<span data-ttu-id="bf0cb-148">导出参数</span><span class="sxs-lookup"><span data-stu-id="bf0cb-148">Export parameters</span></span>|<span data-ttu-id="bf0cb-149">“输出”</span><span class="sxs-lookup"><span data-stu-id="bf0cb-149">Output</span></span>|<span data-ttu-id="bf0cb-150">Paramdirection.Output</span><span class="sxs-lookup"><span data-stu-id="bf0cb-150">Paramdirection.Output</span></span>|  
    |<span data-ttu-id="bf0cb-151">表参数</span><span class="sxs-lookup"><span data-stu-id="bf0cb-151">Table parameters</span></span>|<span data-ttu-id="bf0cb-152">输出/采取任何操作</span><span class="sxs-lookup"><span data-stu-id="bf0cb-152">Output/Nothing</span></span>|<span data-ttu-id="bf0cb-153">InputOutput</span><span class="sxs-lookup"><span data-stu-id="bf0cb-153">InputOutput</span></span>|  
  
 <span data-ttu-id="bf0cb-154">以下是处理参数所需的常规指导原则：</span><span class="sxs-lookup"><span data-stu-id="bf0cb-154">The following are general guidelines for handling parameters:</span></span>  
  
-   <span data-ttu-id="bf0cb-155">为常量或通过在查询中使用占位符，你可以指定参数值。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-155">You can specify parameter values either as constants or by using placeholders in the query.</span></span>  
  
-   <span data-ttu-id="bf0cb-156">在查询中使用占位符，必须创建`SAPParameter`对象并将其添加到相应的命令对象。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-156">When using placeholders in the query, you must create a `SAPParameter` object and add it to the corresponding command object.</span></span> <span data-ttu-id="bf0cb-157">然后将占位符名称传递给构造函数;方向和值取决于上下文。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-157">You then pass the placeholder name to the constructor; the direction and value depend on the context.</span></span>  
  
    -   <span data-ttu-id="bf0cb-158">有关`Input`参数，不在指定查询参数方向的关键字。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-158">For `Input` parameters, do not specify in the query a keyword for the parameter direction.</span></span> <span data-ttu-id="bf0cb-159">`value`必须设置的参数对象的字段，或提供程序将引发异常。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-159">The `value` field of the parameter object must be set, or the provider will throw an exception.</span></span> <span data-ttu-id="bf0cb-160">不，必须显式设置`direction`字段的参数对象，因为提供程序将默认为`Input`。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-160">You must not explicitly set the `direction` field of the parameter object, because the provider defaults to `Input`.</span></span>  
  
    -   <span data-ttu-id="bf0cb-161">对于其他参数，使用该窗体`@paramname=@placeholder`并指定`Output`在查询中显式的关键字。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-161">For other parameters, use the form `@paramname=@placeholder` and specify the `Output` keyword explicitly in the query.</span></span> <span data-ttu-id="bf0cb-162">然后，必须添加`SAPParameter`对应占位符，显式将参数方向设置为`ParamDirection.Output`或`ParamDirection.InputOutput`，具体取决于参数类型。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-162">You must then add a `SAPParameter` that corresponds with the placeholder and explicitly set the parameter direction to either `ParamDirection.Output` or `ParamDirection.InputOutput`, depending on the parameter type.</span></span>  
  
-   <span data-ttu-id="bf0cb-163">参数名称和占位符名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-163">Parameter names and placeholder names are not case-sensitive.</span></span>  
  
-   <span data-ttu-id="bf0cb-164">参数名称不能重复在查询中，除非它们具有不同的方向。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-164">Parameter names cannot be repeated in a query unless they have different directions.</span></span>  
  
-   <span data-ttu-id="bf0cb-165">在查询中，占位符名称不能重复。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-165">Placeholder names cannot be repeated in a query.</span></span>  
  
## <a name="considerations-when-calling-an-exec-statement"></a><span data-ttu-id="bf0cb-166">调用 EXEC 语句时的注意事项</span><span class="sxs-lookup"><span data-stu-id="bf0cb-166">Considerations When Calling an EXEC Statement</span></span>  
 <span data-ttu-id="bf0cb-167">本部分列出使用 EXEC 语句使用时必须记住的点[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-167">This section lists the points that you must keep in mind when using the EXEC statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
-   <span data-ttu-id="bf0cb-168">EXEC 语句，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返回`TIMS`字段值作为.NET`System.DateTime`对象。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-168">For an EXEC statement, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns `TIMS` field values as .NET `System.DateTime` objects.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf0cb-169">对于 SELECT 语句中，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返回`TIMS`字段值作为.NET`System.TimeSpan`对象。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-169">For a SELECT statement, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] returns `TIMS` field values as .NET `System.TimeSpan` objects.</span></span> <span data-ttu-id="bf0cb-170">SELECT 语句的详细信息，请参阅[为 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="bf0cb-170">For more information about the SELECT statement, see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0cb-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf0cb-171">See Also</span></span>  
 [<span data-ttu-id="bf0cb-172">关于 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="bf0cb-172">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)