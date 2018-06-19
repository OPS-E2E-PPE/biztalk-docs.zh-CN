---
title: 动态解析示例的工作原理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7789316d-f2c4-4018-a8e8-dd9359f1664f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe7d7b473482c432c8e3ae9ca48cab414a9e9573
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "22294885"
---
# <a name="how-the-dynamic-resolution-sample-works"></a><span data-ttu-id="90894-102">动态解析示例的工作原理</span><span class="sxs-lookup"><span data-stu-id="90894-102">How the Dynamic Resolution Sample Works</span></span>
<span data-ttu-id="90894-103">动态解析示例使用上一节中所述的所有消息传送示例 ESB 调度程序反汇编程序管道组件。</span><span class="sxs-lookup"><span data-stu-id="90894-103">The Dynamic Resolution sample uses the ESB Dispatcher Disassembler pipeline component for all the messaging examples described in the previous section.</span></span>  
  
 <span data-ttu-id="90894-104">为单向消息传递方案，该示例解析终结点使用静态、 BRE 或 XPATH 冲突解决程序，代理到文件、 FTP 或 MQSeries 来自文件的协议。</span><span class="sxs-lookup"><span data-stu-id="90894-104">For one-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, or XPATH Resolver and brokers the protocol from FILE to FILE, FTP, or MQSeries.</span></span>  
  
 <span data-ttu-id="90894-105">为双向消息传递方案，该示例解析终结点使用静态、 BRE、 UDDI 或 XPATH 冲突解决程序，代理为 SOAP 或 WCF BasicHttp 来自 SOAP 的协议。</span><span class="sxs-lookup"><span data-stu-id="90894-105">For two-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, UDDI, or XPATH Resolver and brokers the protocol from SOAP to either SOAP or WCF-BasicHttp.</span></span> <span data-ttu-id="90894-106">此外，示例解析和执行使用 BRE 冲突解决程序，它使用消息上下文属性和消息正文中包含的事实数据以确定解析结果的 Microsoft BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="90894-106">In addition, the examples resolve and execute Microsoft BizTalk maps using the BRE Resolver, which uses facts contained in the message context properties and the message body to determine the resolution result.</span></span>  
  
 <span data-ttu-id="90894-107">解析过程的结果是双向的所有示例都提交到 ESB 其消息。位于 http://localhost/ESB.CanadianServices/SubmitPOService.asmx CanadianServices Web 服务。</span><span class="sxs-lookup"><span data-stu-id="90894-107">The result of the resolution process is that all the two-way examples submit their message to the ESB.CanadianServices Web service located at http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span></span> <span data-ttu-id="90894-108">此外，具体取决于解析结果中，该示例执行**将订单**或**submitPurchase**操作。</span><span class="sxs-lookup"><span data-stu-id="90894-108">In addition, depending on the resolution result, the example executes either the **submitOrder** or the **submitPurchase** action.</span></span> <span data-ttu-id="90894-109">此外，ESB 调度程序反汇编程序管道组件动态执行 BizTalk 映射，具体取决于指定或解析的操作。</span><span class="sxs-lookup"><span data-stu-id="90894-109">Additionally, the ESB Dispatcher Disassembler pipeline component dynamically executes a BizTalk map, depending on the specified or the resolved action.</span></span>  
  
 <span data-ttu-id="90894-110">图 1 显示 DynamicResolutionReqResp_SOAP 的配置的管道接收位置。</span><span class="sxs-lookup"><span data-stu-id="90894-110">Figure 1 shows the configured pipelines for the DynamicResolutionReqResp_SOAP receive location.</span></span>  
  
 <span data-ttu-id="90894-111">![动态解析管道](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6 DynamicResolutionPipelines")</span><span class="sxs-lookup"><span data-stu-id="90894-111">![Dynamic Resolution Pipelines](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")</span></span>  
  
 <span data-ttu-id="90894-112">**图 1**</span><span class="sxs-lookup"><span data-stu-id="90894-112">**Figure 1**</span></span>  
  
 <span data-ttu-id="90894-113">**配置的管道的 DynamicResolutionReqResp_SOAP 接收动态解析示例应用程序的位置**</span><span class="sxs-lookup"><span data-stu-id="90894-113">**The configured pipelines of the DynamicResolutionReqResp_SOAP receive location of the Dynamic Resolution sample application**</span></span>  
  
 <span data-ttu-id="90894-114">图 2 显示了使用 ESB 调度程序反汇编程序 ESBReceiveXML 组件的每个实例属性。</span><span class="sxs-lookup"><span data-stu-id="90894-114">Figure 2 shows the per-instance properties of the ESBReceiveXML component that uses the ESB Dispatcher Disassembler.</span></span>  
  
 <span data-ttu-id="90894-115">![动态解析接收 XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6 DynamicResolutionReceiveXML")</span><span class="sxs-lookup"><span data-stu-id="90894-115">![Dynamic Resolution Receive XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")</span></span>  
  
 <span data-ttu-id="90894-116">**图 2**</span><span class="sxs-lookup"><span data-stu-id="90894-116">**Figure 2**</span></span>  
  
 <span data-ttu-id="90894-117">**中的动态解析 ESBReceiveXML 管道的组件的每个实例属性示例应用程序**</span><span class="sxs-lookup"><span data-stu-id="90894-117">**The per-instance properties for the components in the ESBReceiveXML pipeline of the Dynamic Resolution sample application**</span></span>  
  
 <span data-ttu-id="90894-118">以下属性图 2 所示：</span><span class="sxs-lookup"><span data-stu-id="90894-118">The following properties are shown in Figure 2:</span></span>  
  
-   <span data-ttu-id="90894-119">**启用**。</span><span class="sxs-lookup"><span data-stu-id="90894-119">**Enabled**.</span></span> <span data-ttu-id="90894-120">此属性确定管道是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="90894-120">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="90894-121">如果此值设置为**False**，而不处理传递的消息。</span><span class="sxs-lookup"><span data-stu-id="90894-121">If this is set to **False**, messages pass through without processing.</span></span>  
  
-   <span data-ttu-id="90894-122">**终结点**。</span><span class="sxs-lookup"><span data-stu-id="90894-122">**Endpoint**.</span></span> <span data-ttu-id="90894-123">此属性是用来确定要加载，请的冲突解决程序的连接字符串，并指定终结点配置。</span><span class="sxs-lookup"><span data-stu-id="90894-123">This property is the connection string used to determine which resolver to load, and it specifies the endpoint configuration.</span></span>  
  
-   <span data-ttu-id="90894-124">**映射名称**。</span><span class="sxs-lookup"><span data-stu-id="90894-124">**MapName**.</span></span> <span data-ttu-id="90894-125">此属性是用来确定哪些冲突解决程序，以加载和执行哪些 BizTalk 映射的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="90894-125">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="90894-126">它可以是映射的而不是映射的解析程序连接字符串的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="90894-126">It can be the fully qualified name of a map instead of a resolver connection string.</span></span>  
  
-   <span data-ttu-id="90894-127">**验证**。</span><span class="sxs-lookup"><span data-stu-id="90894-127">**Validate**.</span></span> <span data-ttu-id="90894-128">当设置为**True** （默认设置），ESB 调度程序拆装器组件指示 ESB 转换服务以验证对源架构中的映射定义源消息将解析和执行。</span><span class="sxs-lookup"><span data-stu-id="90894-128">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>  
  
 <span data-ttu-id="90894-129">图 3 显示了使用 ESB 调度程序 ESBSendPassthrough 组件的每个实例属性。</span><span class="sxs-lookup"><span data-stu-id="90894-129">Figure 3 shows the per-instance properties of the ESBSendPassthrough component that uses the ESB Dispatcher.</span></span>  
  
 <span data-ttu-id="90894-130">![动态解析发送传递](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6 DynamicResolutionSendPassthrough")</span><span class="sxs-lookup"><span data-stu-id="90894-130">![Dynamic Resolution Send Passthrough](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")</span></span>  
  
 <span data-ttu-id="90894-131">**图 3**</span><span class="sxs-lookup"><span data-stu-id="90894-131">**Figure 3**</span></span>  
  
 <span data-ttu-id="90894-132">**中的动态解析 ESBSendPassthrough 管道的组件的每个实例属性示例应用程序**</span><span class="sxs-lookup"><span data-stu-id="90894-132">**The per-instance properties for the components in the ESBSendPassthrough pipeline of the Dynamic Resolution sample application**</span></span>  
  
 <span data-ttu-id="90894-133">以下属性图 3 所示：</span><span class="sxs-lookup"><span data-stu-id="90894-133">The following properties are shown in Figure 3:</span></span>  
  
-   <span data-ttu-id="90894-134">**启用**。</span><span class="sxs-lookup"><span data-stu-id="90894-134">**Enabled**.</span></span> <span data-ttu-id="90894-135">此属性确定管道是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="90894-135">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="90894-136">如果此值设置为**False**，而不处理传递的消息。</span><span class="sxs-lookup"><span data-stu-id="90894-136">If this is set to **False**, messages pass through without processing.</span></span>  
  
-   <span data-ttu-id="90894-137">**终结点**。</span><span class="sxs-lookup"><span data-stu-id="90894-137">**Endpoint**.</span></span> <span data-ttu-id="90894-138">此属性是用来确定负载和终结点配置的解析程序的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="90894-138">This property is the connection string used to determine which resolver to load and the end-point configuration.</span></span>  
  
-   <span data-ttu-id="90894-139">**映射名称**。</span><span class="sxs-lookup"><span data-stu-id="90894-139">**MapName**.</span></span> <span data-ttu-id="90894-140">此属性是用来确定哪些冲突解决程序，以加载和执行哪些 BizTalk 映射的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="90894-140">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="90894-141">映射的完全限定的名称可以代替冲突解决程序的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="90894-141">A fully qualified name of a map can be used in place of a resolver's connection string.</span></span>  
  
-   <span data-ttu-id="90894-142">**验证**。</span><span class="sxs-lookup"><span data-stu-id="90894-142">**Validate**.</span></span> <span data-ttu-id="90894-143">当设置为**True** （默认设置），ESB 调度程序拆装器组件指示 ESB 转换服务以验证对源架构中的映射定义源消息将解析和执行。</span><span class="sxs-lookup"><span data-stu-id="90894-143">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>