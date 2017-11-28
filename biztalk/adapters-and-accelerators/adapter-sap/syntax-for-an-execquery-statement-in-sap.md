---
title: "SAP 中 EXECQUERY 语句语法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bd7fbb-64f2-4327-a8ae-ccb574e56150
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f1eb41d07ef6a6ac3577bf0ef6d3f5bffb874f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="syntax-for-an-execquery-statement-in-sap"></a><span data-ttu-id="b4684-102">SAP 中 EXECQUERY 语句语法</span><span class="sxs-lookup"><span data-stu-id="b4684-102">Syntax for an EXECQUERY Statement in SAP</span></span>
<span data-ttu-id="b4684-103">SAP GUI 可用于通过以图形方式中选择你想要查询，列和排序的顺序要包括在结果集等中的表创建查询。[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用户能够通过提供用户可用于执行查询在 SAP 系统中定义的 EXECQUERY 操作从 ADO.NET 应用程序执行此类查询。</span><span class="sxs-lookup"><span data-stu-id="b4684-103">You can use the SAP GUI to create queries by graphically selecting the tables you want to query, the columns and sort order you want included in the result set, etc. The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] enables users to execute such queries from an ADO.NET application by providing an EXECQUERY operation that users can use to execute a query defined in the SAP system.</span></span>  
  
 <span data-ttu-id="b4684-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用自定义的 RFC Z_EXECUTE_SAP_QUERY SAP 系统中执行的预定义的查询。</span><span class="sxs-lookup"><span data-stu-id="b4684-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC Z_EXECUTE_SAP_QUERY to execute the pre-defined queries in the SAP system.</span></span> <span data-ttu-id="b4684-105">自定义的 RFC 反过来执行 RSAQ_REMOTE_QUERY_CALL，这是 SAP 系统中定义的 RFC 标准。</span><span class="sxs-lookup"><span data-stu-id="b4684-105">The custom RFC in turn executes the RSAQ_REMOTE_QUERY_CALL, which is a standard RFC defined in the SAP system.</span></span> <span data-ttu-id="b4684-106">因此，你可以使用 EXECQUERY 操作之前，必须在你将运行您的查询针对 SAP 系统中安装自定义的 RFC。</span><span class="sxs-lookup"><span data-stu-id="b4684-106">Hence, before you can use the EXECQUERY operation, you must install the custom RFC in the SAP system you will be running your queries against.</span></span> <span data-ttu-id="b4684-107">有关如何安装自定义的 RFC 的说明，请参阅[安装适用于 SAP 的数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="b4684-107">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="b4684-108">本主题提供有关 EXECQUERY 操作中和其他与 EXECQUERY 操作相关的有用信息的语法的信息。</span><span class="sxs-lookup"><span data-stu-id="b4684-108">This topic provides information on the syntax of the EXECQUERY operation, and other useful information related to the EXECQUERY operation.</span></span>  
  
## <a name="syntax-for-an-execquery-statement"></a><span data-ttu-id="b4684-109">EXECQUERY 语句语法</span><span class="sxs-lookup"><span data-stu-id="b4684-109">Syntax for an EXECQUERY Statement</span></span>  
 <span data-ttu-id="b4684-110">以下部分介绍的使用针对 EXECQUERY 操作的语法规范[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b4684-110">The following section describes the grammar specifications for using the EXECQUERY operation against the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='\<value 1>’] [, @P2='\<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='\<value 3>'] [, @P1 > '\<value 4>'] [, @P1 <= '\<value 2>']   
[, NOT @P1 = '\<value 2>'] [, NOT @P1 != '\<value 2>'] [, NOT @P1 > '\<value 2>']   
[, @P1 BETWEEN '\<value 1>' AND '\<value 2>'] [, NOT @P1 BETWEEN '\<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 <span data-ttu-id="b4684-111">其中：</span><span class="sxs-lookup"><span data-stu-id="b4684-111">where:</span></span>  
  
-   <span data-ttu-id="b4684-112">**\<QueryName >**是 SAP 系统中定义的查询的名称。</span><span class="sxs-lookup"><span data-stu-id="b4684-112">**\<QueryName>** is the name of the query defined in the SAP system.</span></span>  
  
-   <span data-ttu-id="b4684-113">**USERGROUP**指在其中定义该查询的用户组。</span><span class="sxs-lookup"><span data-stu-id="b4684-113">**USERGROUP** refers to the user group in which the query is defined.</span></span> <span data-ttu-id="b4684-114">这是必需的参数。</span><span class="sxs-lookup"><span data-stu-id="b4684-114">This is a mandatory parameter.</span></span>  
  
-   <span data-ttu-id="b4684-115">**工作区**指在其中定义该查询的工作区。</span><span class="sxs-lookup"><span data-stu-id="b4684-115">**WORKSPACE** refers to the workspace in which the query is defined.</span></span> <span data-ttu-id="b4684-116">在 SAP，有两个工作区-标准版和全局。</span><span class="sxs-lookup"><span data-stu-id="b4684-116">In SAP, there are two workspaces—Standard and Global.</span></span> <span data-ttu-id="b4684-117">提供指定标准的工作区中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="b4684-117">Provide an empty space to specify the Standard workspace.</span></span> <span data-ttu-id="b4684-118">提供`X`指定全局工作区。</span><span class="sxs-lookup"><span data-stu-id="b4684-118">Provide `X` to specify the Global workspace.</span></span> <span data-ttu-id="b4684-119">默认值为空的空间。</span><span class="sxs-lookup"><span data-stu-id="b4684-119">Default is empty space.</span></span>  
  
-   <span data-ttu-id="b4684-120">**VARIANT**引用为已保存的一组可以执行的 SAP 查询时指定的选择条件。</span><span class="sxs-lookup"><span data-stu-id="b4684-120">**VARIANT** refers to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="b4684-121">例如，可以使用变体指定查询的默认值。</span><span class="sxs-lookup"><span data-stu-id="b4684-121">For example, you can use variants to specify default values for queries.</span></span>  
  
-   <span data-ttu-id="b4684-122">**@Pn**n 是指<sup>th</sup> SAP 查询定义中的选择字段。</span><span class="sxs-lookup"><span data-stu-id="b4684-122">**@Pn** refers to the n<sup>th</sup> selection field in the SAP query definition.</span></span>  
  
-   <span data-ttu-id="b4684-123">**USEORIGINALCOLUMNNAMES**指定提供程序是否在数据集中，使用原始列名，因为它们存在于 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="b4684-123">**USEORIGINALCOLUMNNAMES** specifies whether the provider uses the original column names in the DataSet, as they exist in the SAP system.</span></span> <span data-ttu-id="b4684-124">默认情况下，提供程序使用 SAP 查询中定义的友好名称。</span><span class="sxs-lookup"><span data-stu-id="b4684-124">By default, the provider uses the friendly names defined in the SAP query.</span></span> <span data-ttu-id="b4684-125">但是，如果在查询中的友好名称不是唯一的则 ADO.NET 客户端将从数据集读取数据时引发错误。</span><span class="sxs-lookup"><span data-stu-id="b4684-125">However, if the friendly names within the query are not unique, the ADO.NET client will throw an error while reading the data from the DataSet.</span></span> <span data-ttu-id="b4684-126">在这种情况下，你必须指定 USEORIGINALCOLUMNNAMES 选项，，该值指示提供程序在数据集中使用原始列名。</span><span class="sxs-lookup"><span data-stu-id="b4684-126">In such scenarios, you must specify the USEORIGINALCOLUMNNAMES option, indicating that the provider uses the original column names in the DataSet.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b4684-127">你必须始终提供的值选项关键字在单引号中，例如，*USEORIGINALCOLUMNNAMES*。</span><span class="sxs-lookup"><span data-stu-id="b4684-127">You must always provide the value for the OPTION keyword within single quotes, for example, '*USEORIGINALCOLUMNNAMES*'.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4684-128">有关如何将 SAP 查询的参数转换为 EXECQUERY 语法的信息，请参阅[转换 SAP 查询参数转换 EXECQUERY 命令](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)。</span><span class="sxs-lookup"><span data-stu-id="b4684-128">For information about how the parameters of an SAP Query translate into an EXECQUERY syntax, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="framing-an-execquery-syntax"></a><span data-ttu-id="b4684-129">组帧 EXECQUERY 语法</span><span class="sxs-lookup"><span data-stu-id="b4684-129">Framing an EXECQUERY Syntax</span></span>  
 <span data-ttu-id="b4684-130">组帧 EXECQUERY 操作来执行 SAP 查询的语法取决于如何在 SAP 系统中，包括在 SAP 中定义每个参数值定义该查询。</span><span class="sxs-lookup"><span data-stu-id="b4684-130">Framing syntax for an EXECQUERY operation to execute an SAP query depends on how the query is defined in the SAP system, including each parameter value defined in SAP.</span></span> <span data-ttu-id="b4684-131">有关如何帧 EXECQUERY 语法来执行 SAP 查询的信息，请参阅[转换 SAP 查询参数转换 EXECQUERY 命令](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)。</span><span class="sxs-lookup"><span data-stu-id="b4684-131">For information about how to frame EXECQUERY syntax to execute an SAP query, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a><span data-ttu-id="b4684-132">其他注意事项时使用 EXECQUERY 操作</span><span class="sxs-lookup"><span data-stu-id="b4684-132">Additional Considerations While Using the EXECQUERY operation</span></span>  
 <span data-ttu-id="b4684-133">本部分列出你必须使用与 EXECQUERY 语句时需要牢记的点[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b4684-133">This section lists the points that you must keep in mind when using the EXECQUERY statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
-   <span data-ttu-id="b4684-134">指定用户组、 工作区中，和变体的值作为传递根据的是标准 SAP RFC RSAQ_REMOTE_QUERY_CALL。</span><span class="sxs-lookup"><span data-stu-id="b4684-134">The values specified for USERGROUP, WORKSPACE, and VARIANT are passed on as-is to the standard SAP RFC, RSAQ_REMOTE_QUERY_CALL.</span></span> <span data-ttu-id="b4684-135">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不会验证指定为这些参数的值。</span><span class="sxs-lookup"><span data-stu-id="b4684-135">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not validate the values specified for these parameters.</span></span>  
  
-   <span data-ttu-id="b4684-136">EXECQUERY 操作返回的所有值都是字符串类型。</span><span class="sxs-lookup"><span data-stu-id="b4684-136">All values returned by the EXECQUERY operation are of string type.</span></span>  
  
-   <span data-ttu-id="b4684-137">查询名称、 用户组、 工作区中，和变体的关键字不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b4684-137">Keywords for query names, user group, workspace, and variants are not case sensitive.</span></span> <span data-ttu-id="b4684-138">但是，参数名称必须始终是在上部 caseP 如@P1， @P2，等等。例如：</span><span class="sxs-lookup"><span data-stu-id="b4684-138">However, the parameter names must always be in upper caseP such as @P1, @P2, etc. For example:</span></span>  
  
    ```  
    EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
     <span data-ttu-id="b4684-139">与相同</span><span class="sxs-lookup"><span data-stu-id="b4684-139">is the same as</span></span>  
  
    ```  
    EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
    ```  
  
-   <span data-ttu-id="b4684-140">EXECQUERY 所支持的运算符是 >， \<，> =、 < =、 ！ =，，和 BETWEEN。</span><span class="sxs-lookup"><span data-stu-id="b4684-140">The operators supported by the EXECQUERY are >, \<, >=, <=, !=, NOT, and BETWEEN.</span></span>  
  
-   <span data-ttu-id="b4684-141">EXECQUERY 操作不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="b4684-141">Wildcard characters are not supported by the EXECQUERY operation.</span></span> <span data-ttu-id="b4684-142">例如，以下语句会提供预期的输出：</span><span class="sxs-lookup"><span data-stu-id="b4684-142">For example, the following statement gives the expected output:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
     <span data-ttu-id="b4684-143">但是，相同的查询执行带有通配符时将会出错。</span><span class="sxs-lookup"><span data-stu-id="b4684-143">However, the same query when executed with a wildcard character gives an error.</span></span> <span data-ttu-id="b4684-144">请注意，使用通配符字符 **@P2** 。</span><span class="sxs-lookup"><span data-stu-id="b4684-144">Notice the use of wildcard characters for **@P2**.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
    ```  
  
     <span data-ttu-id="b4684-145">在此示例中，你可能会收到一个错误，指出未找到任何数据。</span><span class="sxs-lookup"><span data-stu-id="b4684-145">In this example, you might get an error stating that no data was found.</span></span> <span data-ttu-id="b4684-146">这是因为查询搜索**\*&\***作为字符串，而不考虑星号 （*） 作为通配符。</span><span class="sxs-lookup"><span data-stu-id="b4684-146">This is because the query searches for **'\*&\*'** as a string and does not consider asterisk (*) as a wildcard character.</span></span>  
  
-   <span data-ttu-id="b4684-147">你始终必须采用 YYYYMMDD 格式指定日期值。</span><span class="sxs-lookup"><span data-stu-id="b4684-147">You must always specify a date values in YYYYMMDD format.</span></span>  
  
-   <span data-ttu-id="b4684-148">如果执行具有 variant 类型在 SAP 系统中定义的查询，你可以作为命令的一部分指定变量的名称。</span><span class="sxs-lookup"><span data-stu-id="b4684-148">If you are executing a query that has a variant defined in the SAP system, you can specify the name of the variant as part of the command.</span></span> <span data-ttu-id="b4684-149">例如：</span><span class="sxs-lookup"><span data-stu-id="b4684-149">For example:</span></span>  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b4684-150">不需要指定变量的名称，如果在 SAP 系统中情况下，定义查询的默认变体。</span><span class="sxs-lookup"><span data-stu-id="b4684-150">You do not need to specify a variant name if a default variant is defined for the query in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4684-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4684-151">See Also</span></span>  
 [<span data-ttu-id="b4684-152">使用.NET Framework 数据提供程序为 mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="b4684-152">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)