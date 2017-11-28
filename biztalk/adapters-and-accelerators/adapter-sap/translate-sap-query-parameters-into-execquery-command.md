---
title: "将转换为 EXECQUERY 命令中 BizTalk mySAP 适配器中 SAP 查询参数 |Microsoft 文档"
description: "转换到 EXECQUERY，示例使用的 SAP 查询的指南"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a545e20-2607-4946-a60d-0a227b86d093
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efb50db3e499970c0504f81467d382aee31c868f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="translate-sap-query-parameters-into-execquery-command"></a><span data-ttu-id="24216-103">将 SAP 查询参数转换为 EXECQUERY 命令</span><span class="sxs-lookup"><span data-stu-id="24216-103">Translate SAP query parameters into EXECQUERY command</span></span>
<span data-ttu-id="24216-104">说明如何查询的参数转换成 EXECQUERY 命令文本。</span><span class="sxs-lookup"><span data-stu-id="24216-104">Explains how the parameters of a query translate into an EXECQUERY command text.</span></span> <span data-ttu-id="24216-105">本主题使用自定义的 SAP 查询 ZQUERY_TST_NEW 的示例。</span><span class="sxs-lookup"><span data-stu-id="24216-105">This topic uses the example of a custom SAP query, ZQUERY_TST_NEW.</span></span>  
  
## <a name="open-the-query-in-sap-gui"></a><span data-ttu-id="24216-106">在 SAP GUI 中打开查询</span><span class="sxs-lookup"><span data-stu-id="24216-106">Open the Query in SAP GUI</span></span>  
 <span data-ttu-id="24216-107">执行以下步骤以在 SAP 中打开查询。</span><span class="sxs-lookup"><span data-stu-id="24216-107">Perform the following steps to open the query in SAP.</span></span> <span data-ttu-id="24216-108">此处提供的步骤适用于 ZQUERY_TST_NEW 查询，特定于 SAP 版本。</span><span class="sxs-lookup"><span data-stu-id="24216-108">The steps provided here are for ZQUERY_TST_NEW query and are specific to SAP versions.</span></span>  
  
1.  <span data-ttu-id="24216-109">运行事务 SQ01。</span><span class="sxs-lookup"><span data-stu-id="24216-109">Run the transaction SQ01.</span></span>  
  
2.  <span data-ttu-id="24216-110">在**从用户组的查询**页上，单击**快速查看器**。</span><span class="sxs-lookup"><span data-stu-id="24216-110">In the **Query from User Group** page, click **Quick Viewer**.</span></span>  
  
3.  <span data-ttu-id="24216-111">在**快速查看器**页上，在**快速查看**文本框中，键入`ZQUERY_TST_NEW`，然后单击**显示**。</span><span class="sxs-lookup"><span data-stu-id="24216-111">In the **Quick Viewer** page, in the **Quick View** text box, type `ZQUERY_TST_NEW`, and then click **Display**.</span></span>  
  
4.  <span data-ttu-id="24216-112">在**快速查看器**页上，单击**选择字段**选项卡可以列出在查询中的所有参数。</span><span class="sxs-lookup"><span data-stu-id="24216-112">In the **Quick Viewer** page, click the **Selection fields** tab to list all the parameters in the query.</span></span>  
  
     <span data-ttu-id="24216-113">下图显示在查询定义中的所有参数。</span><span class="sxs-lookup"><span data-stu-id="24216-113">The following figure shows all the parameters in the query definition.</span></span>  
  
     <span data-ttu-id="24216-114">![有关 SAP 查询的参数列表](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")</span><span class="sxs-lookup"><span data-stu-id="24216-114">![List of parameters for an SAP query](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")</span></span>  
  
5.  <span data-ttu-id="24216-115">单击 **“执行”**。</span><span class="sxs-lookup"><span data-stu-id="24216-115">Click **Execute**.</span></span> <span data-ttu-id="24216-116">将显示以下页。</span><span class="sxs-lookup"><span data-stu-id="24216-116">The following page is displayed.</span></span>  
  
     <span data-ttu-id="24216-117">![为 SAP 查询提供参数值](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")</span><span class="sxs-lookup"><span data-stu-id="24216-117">![Provide parameter values for an SAP query](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")</span></span>  
  
6.  <span data-ttu-id="24216-118">单击黄色箭头以定义每个参数。</span><span class="sxs-lookup"><span data-stu-id="24216-118">Click the yellow arrows to define each parameter.</span></span> <span data-ttu-id="24216-119">你可以定义特定允许/非允许的值或您可以定义允许/非允许的值的范围。</span><span class="sxs-lookup"><span data-stu-id="24216-119">You can either define specific allowable/non-allowable values or you can define a range of allowable/non-allowable values.</span></span>  <span data-ttu-id="24216-120">必须根据配置在 SAP GUI 中的每个参数的值指定 EXECQUERY 语法。</span><span class="sxs-lookup"><span data-stu-id="24216-120">The EXECQUERY syntax must be specified based on the values configured in the SAP GUI for each parameter.</span></span>  
  
 <span data-ttu-id="24216-121">下一节提供有关如何在 SAP GUI 中定义的值和如何将这些值转换为 EXECQUERY 语法说明。</span><span class="sxs-lookup"><span data-stu-id="24216-121">The next section provides an explanation about how the values are defined in the SAP GUI and how those values translate to EXECQUERY syntax.</span></span>  
  
## <a name="frame-an-execquery-syntax"></a><span data-ttu-id="24216-122">帧 EXECQUERY 语法</span><span class="sxs-lookup"><span data-stu-id="24216-122">Frame an EXECQUERY Syntax</span></span>  
 <span data-ttu-id="24216-123">我们来看看起来像 EXECQUERY 语法基于查询定义中定义的参数值。</span><span class="sxs-lookup"><span data-stu-id="24216-123">Let’s look at what the EXECQUERY syntax looks like based on the parameter values defined in the query definition.</span></span> <span data-ttu-id="24216-124">若要理解这一点，我们将显示的值配置的第一个参数的方式示例**两位数**，将转换为**ZQUERY_TST_NEW**查询。</span><span class="sxs-lookup"><span data-stu-id="24216-124">To understand this, we’ll show examples of how the values configured for the first parameter, **Two digit number**, translate to the  **ZQUERY_TST_NEW** query.</span></span>  
  
 <span data-ttu-id="24216-125">首先，我们假设中的值**单一 vals** （带有绿色圆点） 的选项卡定义如下面的屏幕截图中所示：</span><span class="sxs-lookup"><span data-stu-id="24216-125">First, let’s assume the values in the **Single vals** tab (with a green dot) are defined as shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="24216-126">![查询可能需要的参数值列表](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")</span><span class="sxs-lookup"><span data-stu-id="24216-126">![List of parameter values that a query can take](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24216-127">单击旁的黄色箭头后，会出现此对话框**两位数**参数。</span><span class="sxs-lookup"><span data-stu-id="24216-127">This dialog box appears after you click the yellow arrow against the **Two digit number** parameter.</span></span>  
  
 <span data-ttu-id="24216-128">在这种情况下，EXECQUERY 语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="24216-128">In such a case, the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5'  
```  
  
 <span data-ttu-id="24216-129">对于相同的查询，除了中的值**单一 vals**选项卡 （带有绿色圆点），你还可以具有值**单一 vals** （包含的一个红点） 的选项卡定义为以下：</span><span class="sxs-lookup"><span data-stu-id="24216-129">For the same query, in addition to the values in the **Single vals** tab (with a green dot), you can also have the values in the **Single vals** tab (with a red dot) defined as following:</span></span>  
  
 <span data-ttu-id="24216-130">![查询不能采用的参数值的列表](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")</span><span class="sxs-lookup"><span data-stu-id="24216-130">![List of parameter values that a query cannot take](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")</span></span>  
  
 <span data-ttu-id="24216-131">在这种情况下，EXECQUERY 语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="24216-131">In such a case, EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8'  
```  
  
 <span data-ttu-id="24216-132">现在，如果你将值添加到**范围**选项卡上 （带有绿色圆点），如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="24216-132">Now, if you add values to the **Ranges** tab (with a green dot), like shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="24216-133">![查询可能需要的参数值的范围](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")</span><span class="sxs-lookup"><span data-stu-id="24216-133">![Range of parameter values that a query can take](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")</span></span>  
  
 <span data-ttu-id="24216-134">EXECQUERY 语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="24216-134">the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5'  
```  
  
 <span data-ttu-id="24216-135">同样，如果你将值添加到**范围**选项卡上 （与一个红点），如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="24216-135">Similarly, if you add values to the **Ranges** tab (with a red dot), like shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="24216-136">![查询不能采用的参数值的范围](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")</span><span class="sxs-lookup"><span data-stu-id="24216-136">![Range of parameter values that a query cannot take](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")</span></span>  
  
 <span data-ttu-id="24216-137">EXECQUERY 语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="24216-137">the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5', NOT @P1 BETWEEN '6' AND '8'  
```  
  
 <span data-ttu-id="24216-138">为简单和了解，本主题仅讨论的第一个参数，**两位数**。</span><span class="sxs-lookup"><span data-stu-id="24216-138">For simplicity and understanding, this topic only talks about the first parameter, **Two digit number**.</span></span> <span data-ttu-id="24216-139">可以使用类似的方法来确定如何为其他参数定义的值转换为 EXECQUERY 语法。</span><span class="sxs-lookup"><span data-stu-id="24216-139">You can use similar methods to determine how values defined for other parameters translate into an EXECQUERY syntax.</span></span>  
  
