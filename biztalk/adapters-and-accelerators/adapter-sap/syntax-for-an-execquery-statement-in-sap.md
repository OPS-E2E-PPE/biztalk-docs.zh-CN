---
title: 在 SAP 中的 EXECQUERY 语句的语法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99bd7fbb-64f2-4327-a8ae-ccb574e56150
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf479438a5b0960a66b35ef7946df63d088284b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982014"
---
# <a name="syntax-for-an-execquery-statement-in-sap"></a><span data-ttu-id="0b806-102">在 SAP 中的 EXECQUERY 语句的语法</span><span class="sxs-lookup"><span data-stu-id="0b806-102">Syntax for an EXECQUERY Statement in SAP</span></span>
<span data-ttu-id="0b806-103">可以使用 SAP GUI 以图形方式选择想要查询的列和排序的顺序您要包括在结果集，等等的表创建查询。[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用户能够通过提供用户可用于执行 SAP 系统中定义的查询的 EXECQUERY 操作从 ADO.NET 应用程序执行此类查询。</span><span class="sxs-lookup"><span data-stu-id="0b806-103">You can use the SAP GUI to create queries by graphically selecting the tables you want to query, the columns and sort order you want included in the result set, etc. The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] enables users to execute such queries from an ADO.NET application by providing an EXECQUERY operation that users can use to execute a query defined in the SAP system.</span></span>  
  
 <span data-ttu-id="0b806-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]使用自定义的 RFC Z_EXECUTE_SAP_QUERY SAP 系统中执行预定义的查询。</span><span class="sxs-lookup"><span data-stu-id="0b806-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses a custom RFC Z_EXECUTE_SAP_QUERY to execute the pre-defined queries in the SAP system.</span></span> <span data-ttu-id="0b806-105">自定义 RFC 依次执行 RSAQ_REMOTE_QUERY_CALL，这是在 SAP 系统中定义的 RFC 标准。</span><span class="sxs-lookup"><span data-stu-id="0b806-105">The custom RFC in turn executes the RSAQ_REMOTE_QUERY_CALL, which is a standard RFC defined in the SAP system.</span></span> <span data-ttu-id="0b806-106">因此，您可以使用 EXECQUERY 操作之前，必须将运行针对查询 SAP 系统中安装自定义 RFC。</span><span class="sxs-lookup"><span data-stu-id="0b806-106">Hence, before you can use the EXECQUERY operation, you must install the custom RFC in the SAP system you will be running your queries against.</span></span> <span data-ttu-id="0b806-107">有关如何安装自定义 RFC 的说明，请参阅[安装适用于 SAP 数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="0b806-107">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="0b806-108">本主题提供有关 EXECQUERY 操作和其他有用的信息与 EXECQUERY 操作相关的语法信息。</span><span class="sxs-lookup"><span data-stu-id="0b806-108">This topic provides information on the syntax of the EXECQUERY operation, and other useful information related to the EXECQUERY operation.</span></span>  
  
## <a name="syntax-for-an-execquery-statement"></a><span data-ttu-id="0b806-109">EXECQUERY 语句语法</span><span class="sxs-lookup"><span data-stu-id="0b806-109">Syntax for an EXECQUERY Statement</span></span>  
 <span data-ttu-id="0b806-110">以下部分介绍了使用 EXECQUERY 操作针对的语法规范[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0b806-110">The following section describes the grammar specifications for using the EXECQUERY operation against the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
```  
EXECQUERY <QueryName> @USERGROUP='usergroup' [, @WORKSPACE='X'] [, @VARIANT='variant']   
[, @P1='<value 1>’] [, @P2='<value 2>'] ... [, @Pn = '<value n>'] [, @P1!='<value 3>'] [, @P1 > '<value 4>'] [, @P1 <= '<value 2>']   
[, NOT @P1 = '<value 2>'] [, NOT @P1 != '<value 2>'] [, NOT @P1 > '<value 2>']   
[, @P1 BETWEEN '<value 1>' AND '<value 2>'] [, NOT @P1 BETWEEN '<value 1>' AND '<value2>’]  
[OPTION 'USEORIGINALCOLUMNNAMES']  
  
```  
  
 <span data-ttu-id="0b806-111">其中：</span><span class="sxs-lookup"><span data-stu-id="0b806-111">where:</span></span>  
  
- <span data-ttu-id="0b806-112">**\<QueryName\>** 是 SAP 系统中定义的查询的名称。</span><span class="sxs-lookup"><span data-stu-id="0b806-112">**\<QueryName\>** is the name of the query defined in the SAP system.</span></span>  
  
- <span data-ttu-id="0b806-113">**用户组**指在其中定义查询的用户组。</span><span class="sxs-lookup"><span data-stu-id="0b806-113">**USERGROUP** refers to the user group in which the query is defined.</span></span> <span data-ttu-id="0b806-114">这是必需的参数。</span><span class="sxs-lookup"><span data-stu-id="0b806-114">This is a mandatory parameter.</span></span>  
  
- <span data-ttu-id="0b806-115">**工作区**指的是在其中定义查询的工作区。</span><span class="sxs-lookup"><span data-stu-id="0b806-115">**WORKSPACE** refers to the workspace in which the query is defined.</span></span> <span data-ttu-id="0b806-116">在 SAP 中，有两个工作区-标准版和全局。</span><span class="sxs-lookup"><span data-stu-id="0b806-116">In SAP, there are two workspaces—Standard and Global.</span></span> <span data-ttu-id="0b806-117">提供的空白空间，以指定的标准工作区。</span><span class="sxs-lookup"><span data-stu-id="0b806-117">Provide an empty space to specify the Standard workspace.</span></span> <span data-ttu-id="0b806-118">提供`X`以指定的全局工作区。</span><span class="sxs-lookup"><span data-stu-id="0b806-118">Provide `X` to specify the Global workspace.</span></span> <span data-ttu-id="0b806-119">默认值为空的空间。</span><span class="sxs-lookup"><span data-stu-id="0b806-119">Default is empty space.</span></span>  
  
- <span data-ttu-id="0b806-120">**变体**是指可以执行 SAP 查询时指定的选择条件的已保存组。</span><span class="sxs-lookup"><span data-stu-id="0b806-120">**VARIANT** refers to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="0b806-121">例如，变体可用于指定查询的默认值。</span><span class="sxs-lookup"><span data-stu-id="0b806-121">For example, you can use variants to specify default values for queries.</span></span>  
  
- <span data-ttu-id="0b806-122"><strong>@Pn</strong> n 是指<sup>th</sup> SAP 查询定义中的选择字段。</span><span class="sxs-lookup"><span data-stu-id="0b806-122"><strong>@Pn</strong> refers to the n<sup>th</sup> selection field in the SAP query definition.</span></span>  
  
- <span data-ttu-id="0b806-123">**USEORIGINALCOLUMNNAMES**指定提供程序是否使用原始列名称在数据集中，因为它们存在于 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="0b806-123">**USEORIGINALCOLUMNNAMES** specifies whether the provider uses the original column names in the DataSet, as they exist in the SAP system.</span></span> <span data-ttu-id="0b806-124">默认情况下，该提供程序使用 SAP 查询中定义的友好名称。</span><span class="sxs-lookup"><span data-stu-id="0b806-124">By default, the provider uses the friendly names defined in the SAP query.</span></span> <span data-ttu-id="0b806-125">但是，如果在查询中的友好名称不唯一，则 ADO.NET 客户端将从数据集中读取数据时引发错误。</span><span class="sxs-lookup"><span data-stu-id="0b806-125">However, if the friendly names within the query are not unique, the ADO.NET client will throw an error while reading the data from the DataSet.</span></span> <span data-ttu-id="0b806-126">在这种情况下，必须指定 USEORIGINALCOLUMNNAMES 选项，指示提供程序在数据集中使用的原始列名称。</span><span class="sxs-lookup"><span data-stu-id="0b806-126">In such scenarios, you must specify the USEORIGINALCOLUMNNAMES option, indicating that the provider uses the original column names in the DataSet.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="0b806-127">您必须始终提供的值选项关键字在单引号中，例如，'*USEORIGINALCOLUMNNAMES*。</span><span class="sxs-lookup"><span data-stu-id="0b806-127">You must always provide the value for the OPTION keyword within single quotes, for example, '*USEORIGINALCOLUMNNAMES*'.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b806-128">有关如何将 SAP 查询的参数转换为 EXECQUERY 语法的信息，请参阅[写入 EXECQUERY 命令转换 SAP 查询参数](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)。</span><span class="sxs-lookup"><span data-stu-id="0b806-128">For information about how the parameters of an SAP Query translate into an EXECQUERY syntax, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="framing-an-execquery-syntax"></a><span data-ttu-id="0b806-129">组帧 EXECQUERY 语法</span><span class="sxs-lookup"><span data-stu-id="0b806-129">Framing an EXECQUERY Syntax</span></span>  
 <span data-ttu-id="0b806-130">组帧 EXECQUERY 操作来执行 SAP 查询的语法取决于如何中 SAP 系统，包括在 SAP 中定义的每个参数值定义的查询。</span><span class="sxs-lookup"><span data-stu-id="0b806-130">Framing syntax for an EXECQUERY operation to execute an SAP query depends on how the query is defined in the SAP system, including each parameter value defined in SAP.</span></span> <span data-ttu-id="0b806-131">说明如何明确 EXECQUERY 语法来执行 SAP 查询的信息，请参阅[写入 EXECQUERY 命令转换 SAP 查询参数](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md)。</span><span class="sxs-lookup"><span data-stu-id="0b806-131">For information about how to frame EXECQUERY syntax to execute an SAP query, see [Translate SAP query parameters into EXECQUERY command](../../adapters-and-accelerators/adapter-sap/translate-sap-query-parameters-into-execquery-command.md).</span></span>  
  
### <a name="additional-considerations-while-using-the-execquery-operation"></a><span data-ttu-id="0b806-132">其他注意事项虽然在使用 EXECQUERY 操作</span><span class="sxs-lookup"><span data-stu-id="0b806-132">Additional Considerations While Using the EXECQUERY operation</span></span>  
 <span data-ttu-id="0b806-133">本部分列出了使用 EXECQUERY 语句使用时必须牢记的点[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0b806-133">This section lists the points that you must keep in mind when using the EXECQUERY statement with [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
- <span data-ttu-id="0b806-134">指定用户组、 工作区中，和变体的值以的方式传递的是标准 SAP RFC RSAQ_REMOTE_QUERY_CALL。</span><span class="sxs-lookup"><span data-stu-id="0b806-134">The values specified for USERGROUP, WORKSPACE, and VARIANT are passed on as-is to the standard SAP RFC, RSAQ_REMOTE_QUERY_CALL.</span></span> <span data-ttu-id="0b806-135">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不会验证为这些参数指定的值。</span><span class="sxs-lookup"><span data-stu-id="0b806-135">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not validate the values specified for these parameters.</span></span>  
  
- <span data-ttu-id="0b806-136">EXECQUERY 操作返回的所有值都是字符串类型。</span><span class="sxs-lookup"><span data-stu-id="0b806-136">All values returned by the EXECQUERY operation are of string type.</span></span>  
  
- <span data-ttu-id="0b806-137">查询名称、 用户组、 工作区中，和变体的关键字不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0b806-137">Keywords for query names, user group, workspace, and variants are not case sensitive.</span></span> <span data-ttu-id="0b806-138">但是，参数名称必须始终是在上部 caseP 如@P1， @P2，等等。例如：</span><span class="sxs-lookup"><span data-stu-id="0b806-138">However, the parameter names must always be in upper caseP such as @P1, @P2, etc. For example:</span></span>  
  
  ```  
  EXECQUERY xyz USERGROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
   <span data-ttu-id="0b806-139">与相同</span><span class="sxs-lookup"><span data-stu-id="0b806-139">is the same as</span></span>  
  
  ```  
  EXECQUERY xyz uSERgROUP=’mygrp’, NOT @P1= 'somevalue'  
  ```  
  
- <span data-ttu-id="0b806-140">EXECQUERY 所支持的运算符包括 >，<>、 =、 < =、 ！ =、 NOT、 BETWEEN 和。</span><span class="sxs-lookup"><span data-stu-id="0b806-140">The operators supported by the EXECQUERY are >, <, >=, <=, !=, NOT, and BETWEEN.</span></span>  
  
- <span data-ttu-id="0b806-141">EXECQUERY 操作不支持通配符字符。</span><span class="sxs-lookup"><span data-stu-id="0b806-141">Wildcard characters are not supported by the EXECQUERY operation.</span></span> <span data-ttu-id="0b806-142">例如，以下语句，为提供的预期的输出：</span><span class="sxs-lookup"><span data-stu-id="0b806-142">For example, the following statement gives the expected output:</span></span>  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
  ```  
  
   <span data-ttu-id="0b806-143">但是，相同的查询时使用的通配符字符执行时出现错误。</span><span class="sxs-lookup"><span data-stu-id="0b806-143">However, the same query when executed with a wildcard character gives an error.</span></span> <span data-ttu-id="0b806-144">请注意，使用的通配符字符<strong>@P2</strong>。</span><span class="sxs-lookup"><span data-stu-id="0b806-144">Notice the use of wildcard characters for <strong>@P2</strong>.</span></span>  
  
  ```  
  EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024',  @P1 = '0000003262',@P2 = '*&*'  
  ```  
  
   <span data-ttu-id="0b806-145">在此示例中，可能会收到一个错误，指出不找任何数据。</span><span class="sxs-lookup"><span data-stu-id="0b806-145">In this example, you might get an error stating that no data was found.</span></span> <span data-ttu-id="0b806-146">这是因为查询中搜索 **'\*&\*** 作为一个字符串，而不考虑星号 （\*） 作为通配符。</span><span class="sxs-lookup"><span data-stu-id="0b806-146">This is because the query searches for **'\*&\*'** as a string and does not consider asterisk (\*) as a wildcard character.</span></span>  
  
- <span data-ttu-id="0b806-147">始终必须以 YYYYMMDD 格式表示指定日期值。</span><span class="sxs-lookup"><span data-stu-id="0b806-147">You must always specify a date values in YYYYMMDD format.</span></span>  
  
- <span data-ttu-id="0b806-148">如果执行具有 variant 类型的 SAP 系统中定义的查询，您可以指定变量名作为命令的一部分。</span><span class="sxs-lookup"><span data-stu-id="0b806-148">If you are executing a query that has a variant defined in the SAP system, you can specify the name of the variant as part of the command.</span></span> <span data-ttu-id="0b806-149">例如：</span><span class="sxs-lookup"><span data-stu-id="0b806-149">For example:</span></span>  
  
  ```  
  EXECQUERY myquery @usergroup='mygroup',@variant = 'variant1'  
  ```  
  
  > [!NOTE]
  >  <span data-ttu-id="0b806-150">不需要指定变量的名称，如果默认变体在 SAP 系统中定义的查询。</span><span class="sxs-lookup"><span data-stu-id="0b806-150">You do not need to specify a variant name if a default variant is defined for the query in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b806-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b806-151">See Also</span></span>  
 [<span data-ttu-id="0b806-152">使用 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="0b806-152">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)