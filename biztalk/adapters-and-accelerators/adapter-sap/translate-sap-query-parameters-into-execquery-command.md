---
title: 将 SAP 查询参数转换为 EXECQUERY 命令 mySAP 适配器在 BizTalk 中 |Microsoft Docs
description: SAP 将查询转换为 EXECQUERY，示例的指南
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a545e20-2607-4946-a60d-0a227b86d093
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8ffd480e952e0df7114a93f6cb2a5baf631ad96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021692"
---
# <a name="translate-sap-query-parameters-into-execquery-command"></a><span data-ttu-id="9170d-103">将 SAP 查询参数转换为 EXECQUERY 命令</span><span class="sxs-lookup"><span data-stu-id="9170d-103">Translate SAP query parameters into EXECQUERY command</span></span>
<span data-ttu-id="9170d-104">介绍如何将查询的参数转换为 EXECQUERY 命令文本。</span><span class="sxs-lookup"><span data-stu-id="9170d-104">Explains how the parameters of a query translate into an EXECQUERY command text.</span></span> <span data-ttu-id="9170d-105">本主题使用的自定义 SAP 查询 ZQUERY_TST_NEW 示例。</span><span class="sxs-lookup"><span data-stu-id="9170d-105">This topic uses the example of a custom SAP query, ZQUERY_TST_NEW.</span></span>  
  
## <a name="open-the-query-in-sap-gui"></a><span data-ttu-id="9170d-106">SAP GUI 中打开查询</span><span class="sxs-lookup"><span data-stu-id="9170d-106">Open the Query in SAP GUI</span></span>  
 <span data-ttu-id="9170d-107">执行以下步骤以在 SAP 中打开查询。</span><span class="sxs-lookup"><span data-stu-id="9170d-107">Perform the following steps to open the query in SAP.</span></span> <span data-ttu-id="9170d-108">此处提供的步骤适用于 ZQUERY_TST_NEW 查询，并且特定于 SAP 版本。</span><span class="sxs-lookup"><span data-stu-id="9170d-108">The steps provided here are for ZQUERY_TST_NEW query and are specific to SAP versions.</span></span>  
  
1. <span data-ttu-id="9170d-109">运行事务 SQ01。</span><span class="sxs-lookup"><span data-stu-id="9170d-109">Run the transaction SQ01.</span></span>  
  
2. <span data-ttu-id="9170d-110">在中**用户组中的查询**页上，单击**快速查看器**。</span><span class="sxs-lookup"><span data-stu-id="9170d-110">In the **Query from User Group** page, click **Quick Viewer**.</span></span>  
  
3. <span data-ttu-id="9170d-111">在中**快速查看器**页上，在**快速查看**文本框中，键入`ZQUERY_TST_NEW`，然后单击**显示**。</span><span class="sxs-lookup"><span data-stu-id="9170d-111">In the **Quick Viewer** page, in the **Quick View** text box, type `ZQUERY_TST_NEW`, and then click **Display**.</span></span>  
  
4. <span data-ttu-id="9170d-112">在中**快速查看器**页上，单击**选定内容字段**选项卡可以列出在查询中的所有参数。</span><span class="sxs-lookup"><span data-stu-id="9170d-112">In the **Quick Viewer** page, click the **Selection fields** tab to list all the parameters in the query.</span></span>  
  
    <span data-ttu-id="9170d-113">下图显示在查询定义的所有参数。</span><span class="sxs-lookup"><span data-stu-id="9170d-113">The following figure shows all the parameters in the query definition.</span></span>  
  
    <span data-ttu-id="9170d-114">![有关 SAP 查询的参数列表](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")</span><span class="sxs-lookup"><span data-stu-id="9170d-114">![List of parameters for an SAP query](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")</span></span>  
  
5. <span data-ttu-id="9170d-115">单击 **“执行”**。</span><span class="sxs-lookup"><span data-stu-id="9170d-115">Click **Execute**.</span></span> <span data-ttu-id="9170d-116">将显示以下页面。</span><span class="sxs-lookup"><span data-stu-id="9170d-116">The following page is displayed.</span></span>  
  
    <span data-ttu-id="9170d-117">![为 SAP 查询提供参数值](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")</span><span class="sxs-lookup"><span data-stu-id="9170d-117">![Provide parameter values for an SAP query](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")</span></span>  
  
6. <span data-ttu-id="9170d-118">单击黄色箭头来定义每个参数。</span><span class="sxs-lookup"><span data-stu-id="9170d-118">Click the yellow arrows to define each parameter.</span></span> <span data-ttu-id="9170d-119">您可以定义特定允许/非允许的值也可以定义一系列允许/非允许的值。</span><span class="sxs-lookup"><span data-stu-id="9170d-119">You can either define specific allowable/non-allowable values or you can define a range of allowable/non-allowable values.</span></span>  <span data-ttu-id="9170d-120">必须在每个参数将 SAP GUI 中配置的值指定 EXECQUERY 语法。</span><span class="sxs-lookup"><span data-stu-id="9170d-120">The EXECQUERY syntax must be specified based on the values configured in the SAP GUI for each parameter.</span></span>  
  
   <span data-ttu-id="9170d-121">下一节提供有关如何将 SAP GUI 中定义的值以及如何将这些值转换为 EXECQUERY 语法说明。</span><span class="sxs-lookup"><span data-stu-id="9170d-121">The next section provides an explanation about how the values are defined in the SAP GUI and how those values translate to EXECQUERY syntax.</span></span>  
  
## <a name="frame-an-execquery-syntax"></a><span data-ttu-id="9170d-122">帧 EXECQUERY 语法</span><span class="sxs-lookup"><span data-stu-id="9170d-122">Frame an EXECQUERY Syntax</span></span>  
 <span data-ttu-id="9170d-123">让我们看看起来像 EXECQUERY 语法基于查询定义中定义的参数值。</span><span class="sxs-lookup"><span data-stu-id="9170d-123">Let’s look at what the EXECQUERY syntax looks like based on the parameter values defined in the query definition.</span></span> <span data-ttu-id="9170d-124">若要理解这一点，我们展示的第一个参数值的配置方式的示例**两位数**，将转换为**ZQUERY_TST_NEW**查询。</span><span class="sxs-lookup"><span data-stu-id="9170d-124">To understand this, we’ll show examples of how the values configured for the first parameter, **Two digit number**, translate to the  **ZQUERY_TST_NEW** query.</span></span>  
  
 <span data-ttu-id="9170d-125">首先，让我们假定中的值**单一 vals** （带有绿色圆点） 的选项卡定义如下面的屏幕截图中所示：</span><span class="sxs-lookup"><span data-stu-id="9170d-125">First, let’s assume the values in the **Single vals** tab (with a green dot) are defined as shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="9170d-126">![查询可以采用的参数值的列表](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")</span><span class="sxs-lookup"><span data-stu-id="9170d-126">![List of parameter values that a query can take](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9170d-127">单击黄色箭头后，会显示此对话框**两位数字**参数。</span><span class="sxs-lookup"><span data-stu-id="9170d-127">This dialog box appears after you click the yellow arrow against the **Two digit number** parameter.</span></span>  
  
 <span data-ttu-id="9170d-128">在这种情况下，EXECQUERY 语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="9170d-128">In such a case, the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5'  
```  
  
 <span data-ttu-id="9170d-129">为同一查询中，除了中的值**单一 vals**选项卡 （带有绿色圆点），你还可以使用值**单一 vals** （用红点） 的选项卡定义如下所示：</span><span class="sxs-lookup"><span data-stu-id="9170d-129">For the same query, in addition to the values in the **Single vals** tab (with a green dot), you can also have the values in the **Single vals** tab (with a red dot) defined as following:</span></span>  
  
 <span data-ttu-id="9170d-130">![查询不能采用的参数值的列表](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")</span><span class="sxs-lookup"><span data-stu-id="9170d-130">![List of parameter values that a query cannot take](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")</span></span>  
  
 <span data-ttu-id="9170d-131">在这种情况下，EXECQUERY 语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="9170d-131">In such a case, EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8'  
```  
  
 <span data-ttu-id="9170d-132">现在，如果您将值添加到**范围**选项卡上 （带有绿色圆点），如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="9170d-132">Now, if you add values to the **Ranges** tab (with a green dot), like shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="9170d-133">![查询可以采用的参数值的范围](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")</span><span class="sxs-lookup"><span data-stu-id="9170d-133">![Range of parameter values that a query can take](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")</span></span>  
  
 <span data-ttu-id="9170d-134">EXECQUERY 语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="9170d-134">the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5'  
```  
  
 <span data-ttu-id="9170d-135">同样，如果您将值添加到**范围**选项卡 （具有一个红点），如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="9170d-135">Similarly, if you add values to the **Ranges** tab (with a red dot), like shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="9170d-136">![查询不能采用的参数值的范围](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")</span><span class="sxs-lookup"><span data-stu-id="9170d-136">![Range of parameter values that a query cannot take](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")</span></span>  
  
 <span data-ttu-id="9170d-137">EXECQUERY 语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="9170d-137">the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5', NOT @P1 BETWEEN '6' AND '8'  
```  
  
 <span data-ttu-id="9170d-138">为简单起见和理解，本主题只讨论的第一个参数**两位数字**。</span><span class="sxs-lookup"><span data-stu-id="9170d-138">For simplicity and understanding, this topic only talks about the first parameter, **Two digit number**.</span></span> <span data-ttu-id="9170d-139">可以使用类似的方法来确定如何为其他参数定义的值转换为 EXECQUERY 语法。</span><span class="sxs-lookup"><span data-stu-id="9170d-139">You can use similar methods to determine how values defined for other parameters translate into an EXECQUERY syntax.</span></span>  
  
