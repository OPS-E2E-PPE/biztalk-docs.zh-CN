---
title: 动态解析示例工作原理 |Microsoft Docs
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
ms.openlocfilehash: bab7a46a02dc080fa27b9df2b30614bc8a45c6e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976430"
---
# <a name="how-the-dynamic-resolution-sample-works"></a><span data-ttu-id="3425c-102">动态解析示例工作原理</span><span class="sxs-lookup"><span data-stu-id="3425c-102">How the Dynamic Resolution Sample Works</span></span>
<span data-ttu-id="3425c-103">动态解析示例使用上一节中所述的所有消息传送示例 ESB 调度程序反汇编程序管道组件。</span><span class="sxs-lookup"><span data-stu-id="3425c-103">The Dynamic Resolution sample uses the ESB Dispatcher Disassembler pipeline component for all the messaging examples described in the previous section.</span></span>  

 <span data-ttu-id="3425c-104">单向消息传送方案，该示例解析终结点使用静态、 BRE 或 XPATH 冲突解决程序并中转站到文件、 FTP 或 MQSeries 的文件中的协议。</span><span class="sxs-lookup"><span data-stu-id="3425c-104">For one-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, or XPATH Resolver and brokers the protocol from FILE to FILE, FTP, or MQSeries.</span></span>  

 <span data-ttu-id="3425c-105">双向消息传送方案，该示例解析使用静态、 BRE、 UDDI 或 XPATH 冲突解决程序的终结点并中转站为 SOAP 或 WCF BasicHttp 的 SOAP 的协议。</span><span class="sxs-lookup"><span data-stu-id="3425c-105">For two-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, UDDI, or XPATH Resolver and brokers the protocol from SOAP to either SOAP or WCF-BasicHttp.</span></span> <span data-ttu-id="3425c-106">此外，示例解析和执行使用 BRE 冲突解决程序，它使用消息上下文属性和消息正文中包含的事实数据确定解析结果的 Microsoft BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="3425c-106">In addition, the examples resolve and execute Microsoft BizTalk maps using the BRE Resolver, which uses facts contained in the message context properties and the message body to determine the resolution result.</span></span>  

 <span data-ttu-id="3425c-107">解析过程的结果是双向的所有示例都提交到 ESB 其消息。CanadianServices Web 服务位于http://localhost/ESB.CanadianServices/SubmitPOService.asmx。</span><span class="sxs-lookup"><span data-stu-id="3425c-107">The result of the resolution process is that all the two-way examples submit their message to the ESB.CanadianServices Web service located at http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span></span> <span data-ttu-id="3425c-108">此外，具体取决于解析结果，该示例执行任一**submitOrder**或**submitPurchase**操作。</span><span class="sxs-lookup"><span data-stu-id="3425c-108">In addition, depending on the resolution result, the example executes either the **submitOrder** or the **submitPurchase** action.</span></span> <span data-ttu-id="3425c-109">此外，ESB 调度程序反汇编程序管道组件可以动态执行 BizTalk 映射时，具体取决于指定或解析的操作。</span><span class="sxs-lookup"><span data-stu-id="3425c-109">Additionally, the ESB Dispatcher Disassembler pipeline component dynamically executes a BizTalk map, depending on the specified or the resolved action.</span></span>  

 <span data-ttu-id="3425c-110">图 1 显示了 DynamicResolutionReqResp_SOAP 配置的管道接收位置。</span><span class="sxs-lookup"><span data-stu-id="3425c-110">Figure 1 shows the configured pipelines for the DynamicResolutionReqResp_SOAP receive location.</span></span>  

 <span data-ttu-id="3425c-111">![动态解析管道](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")</span><span class="sxs-lookup"><span data-stu-id="3425c-111">![Dynamic Resolution Pipelines](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")</span></span>  

 <span data-ttu-id="3425c-112">**图 1**</span><span class="sxs-lookup"><span data-stu-id="3425c-112">**Figure 1**</span></span>  

 <span data-ttu-id="3425c-113">**DynamicResolutionReqResp_SOAP 配置的管道接收的动态解析示例应用程序的位置**</span><span class="sxs-lookup"><span data-stu-id="3425c-113">**The configured pipelines of the DynamicResolutionReqResp_SOAP receive location of the Dynamic Resolution sample application**</span></span>  

 <span data-ttu-id="3425c-114">图 2 显示了使用 ESB 调度程序拆装器的 ESBReceiveXML 组件的每个实例的属性。</span><span class="sxs-lookup"><span data-stu-id="3425c-114">Figure 2 shows the per-instance properties of the ESBReceiveXML component that uses the ESB Dispatcher Disassembler.</span></span>  

 <span data-ttu-id="3425c-115">![动态解析接收 XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")</span><span class="sxs-lookup"><span data-stu-id="3425c-115">![Dynamic Resolution Receive XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")</span></span>  

 <span data-ttu-id="3425c-116">**图 2**</span><span class="sxs-lookup"><span data-stu-id="3425c-116">**Figure 2**</span></span>  

 <span data-ttu-id="3425c-117">**动态解析示例应用程序在 ESBReceiveXML 管道中的组件基于实例的属性**</span><span class="sxs-lookup"><span data-stu-id="3425c-117">**The per-instance properties for the components in the ESBReceiveXML pipeline of the Dynamic Resolution sample application**</span></span>  

 <span data-ttu-id="3425c-118">图 2 显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="3425c-118">The following properties are shown in Figure 2:</span></span>  

- <span data-ttu-id="3425c-119">**启用**。</span><span class="sxs-lookup"><span data-stu-id="3425c-119">**Enabled**.</span></span> <span data-ttu-id="3425c-120">此属性确定管道是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="3425c-120">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="3425c-121">如果此值设置为**False**，而无需处理传递的消息。</span><span class="sxs-lookup"><span data-stu-id="3425c-121">If this is set to **False**, messages pass through without processing.</span></span>  

- <span data-ttu-id="3425c-122">**终结点**。</span><span class="sxs-lookup"><span data-stu-id="3425c-122">**Endpoint**.</span></span> <span data-ttu-id="3425c-123">此属性是用来确定要加载，冲突解决程序的连接字符串，并指定终结点配置。</span><span class="sxs-lookup"><span data-stu-id="3425c-123">This property is the connection string used to determine which resolver to load, and it specifies the endpoint configuration.</span></span>  

- <span data-ttu-id="3425c-124">**MapName**。</span><span class="sxs-lookup"><span data-stu-id="3425c-124">**MapName**.</span></span> <span data-ttu-id="3425c-125">此属性是用来确定要加载的冲突解决程序和执行的 BizTalk 映射的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="3425c-125">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="3425c-126">它可以是映射而不是冲突解决程序连接字符串的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="3425c-126">It can be the fully qualified name of a map instead of a resolver connection string.</span></span>  

- <span data-ttu-id="3425c-127">**验证**。</span><span class="sxs-lookup"><span data-stu-id="3425c-127">**Validate**.</span></span> <span data-ttu-id="3425c-128">如果设置为 **，则返回 True** （默认设置），ESB 调度程序拆装器组件指示 ESB 转换服务来验证根据源架构是在映射中定义的源消息将解析和执行。</span><span class="sxs-lookup"><span data-stu-id="3425c-128">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>  

  <span data-ttu-id="3425c-129">图 3 显示了使用 ESB 调度程序的 ESBSendPassthrough 组件的每个实例的属性。</span><span class="sxs-lookup"><span data-stu-id="3425c-129">Figure 3 shows the per-instance properties of the ESBSendPassthrough component that uses the ESB Dispatcher.</span></span>  

  <span data-ttu-id="3425c-130">![动态解析发送直通](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")</span><span class="sxs-lookup"><span data-stu-id="3425c-130">![Dynamic Resolution Send Passthrough](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")</span></span>  

  <span data-ttu-id="3425c-131">**图 3**</span><span class="sxs-lookup"><span data-stu-id="3425c-131">**Figure 3**</span></span>  

  <span data-ttu-id="3425c-132">**动态解析示例应用程序在 ESBSendPassthrough 管道中的组件基于实例的属性**</span><span class="sxs-lookup"><span data-stu-id="3425c-132">**The per-instance properties for the components in the ESBSendPassthrough pipeline of the Dynamic Resolution sample application**</span></span>  

  <span data-ttu-id="3425c-133">图 3 显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="3425c-133">The following properties are shown in Figure 3:</span></span>  

- <span data-ttu-id="3425c-134">**启用**。</span><span class="sxs-lookup"><span data-stu-id="3425c-134">**Enabled**.</span></span> <span data-ttu-id="3425c-135">此属性确定管道是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="3425c-135">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="3425c-136">如果此值设置为**False**，而无需处理传递的消息。</span><span class="sxs-lookup"><span data-stu-id="3425c-136">If this is set to **False**, messages pass through without processing.</span></span>  

- <span data-ttu-id="3425c-137">**终结点**。</span><span class="sxs-lookup"><span data-stu-id="3425c-137">**Endpoint**.</span></span> <span data-ttu-id="3425c-138">此属性是用来确定负载和终结点配置的冲突解决程序的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="3425c-138">This property is the connection string used to determine which resolver to load and the end-point configuration.</span></span>  

- <span data-ttu-id="3425c-139">**MapName**。</span><span class="sxs-lookup"><span data-stu-id="3425c-139">**MapName**.</span></span> <span data-ttu-id="3425c-140">此属性是用来确定要加载的冲突解决程序和执行的 BizTalk 映射的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="3425c-140">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="3425c-141">映射的完全限定的名称可以代替冲突解决程序的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="3425c-141">A fully qualified name of a map can be used in place of a resolver's connection string.</span></span>  

- <span data-ttu-id="3425c-142">**验证**。</span><span class="sxs-lookup"><span data-stu-id="3425c-142">**Validate**.</span></span> <span data-ttu-id="3425c-143">如果设置为 **，则返回 True** （默认设置），ESB 调度程序拆装器组件指示 ESB 转换服务来验证根据源架构是在映射中定义的源消息将解析和执行。</span><span class="sxs-lookup"><span data-stu-id="3425c-143">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>
