---
title: 适配器注册向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- utilities, Adapter Registration Wizard
- Adapter Registration Wizard
ms.assetid: bd15d0c7-01bb-41f9-9157-cdcf4bb4e39a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13842e4edda428f53cc4d11c2cbe7c06407fe2e1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004798"
---
# <a name="adapter-registry-wizard"></a><span data-ttu-id="6030f-102">适配器注册向导</span><span class="sxs-lookup"><span data-stu-id="6030f-102">Adapter Registry Wizard</span></span>
<span data-ttu-id="6030f-103">适配器注册向导用于创建所需配置和注册自定义适配器的注册表文件。</span><span class="sxs-lookup"><span data-stu-id="6030f-103">You use the Adapter Registry Wizard to create the registry files needed to configure and register a custom adapter.</span></span>  

## <a name="location-in-sdk"></a><span data-ttu-id="6030f-104">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="6030f-104">Location in SDK</span></span>  
 <span data-ttu-id="6030f-105">*\<安装路径\>* \SDK\Utilities\AdapterRegistryWizard\\</span><span class="sxs-lookup"><span data-stu-id="6030f-105">*\<Installation Path\>* \SDK\Utilities\AdapterRegistryWizard\\</span></span>  

## <a name="to-run-this-utility"></a><span data-ttu-id="6030f-106">运行本实用工具</span><span class="sxs-lookup"><span data-stu-id="6030f-106">To Run This Utility</span></span>  
 <span data-ttu-id="6030f-107">通过运行 AdapterRegistryWizard.exe 可执行程序启动该向导。</span><span class="sxs-lookup"><span data-stu-id="6030f-107">Start the wizard by running the AdapterRegistryWizard.exe executable.</span></span> <span data-ttu-id="6030f-108">向导中的页面将提示您与适配器及其支持的属性有关的信息。</span><span class="sxs-lookup"><span data-stu-id="6030f-108">The pages that follow prompt you for information about your adapter and the properties that it supports.</span></span> <span data-ttu-id="6030f-109">在后面的部分中将介绍各适配器注册向导页。</span><span class="sxs-lookup"><span data-stu-id="6030f-109">The individual Adapter Registry Wizard pages are described in the sections that follow.</span></span>  

### <a name="generic-adapter-properties-page"></a><span data-ttu-id="6030f-110">“一般适配器属性”页</span><span class="sxs-lookup"><span data-stu-id="6030f-110">Generic Adapter Properties page</span></span>  
 <span data-ttu-id="6030f-111">使用“一般适配器属性”页可指定适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="6030f-111">Use the Generic Adapter Properties page to specify adapter properties.</span></span>  


|                              <span data-ttu-id="6030f-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6030f-112">Use this</span></span>                              |                                                                                           <span data-ttu-id="6030f-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6030f-113">To do this</span></span>                                                                                           |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                     <span data-ttu-id="6030f-114">**传输适配器类型**</span><span class="sxs-lookup"><span data-stu-id="6030f-114">**Transport adapter type**</span></span>                     |                                                                                   <span data-ttu-id="6030f-115">指定适配器类型。</span><span class="sxs-lookup"><span data-stu-id="6030f-115">Specify the adapter type.</span></span>                                                                                    |
|                       <span data-ttu-id="6030f-116">**属性命名空间**</span><span class="sxs-lookup"><span data-stu-id="6030f-116">**Property namespace**</span></span>                       | <span data-ttu-id="6030f-117">指定适配器命名空间。</span><span class="sxs-lookup"><span data-stu-id="6030f-117">Specify the adapter namespace.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6030f-118"> 此命名空间中的消息上下文上存储特定于适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="6030f-118"> stores adapter-specific properties on the message context in this namespace.</span></span> |
| <span data-ttu-id="6030f-119">**适配器可以接收消息并将其提交到 BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="6030f-119">**Adapter can receive messages and submit them to BizTalk Server**</span></span> |                                  <span data-ttu-id="6030f-120">标识适配器支持的通信模式。</span><span class="sxs-lookup"><span data-stu-id="6030f-120">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="6030f-121">用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="6030f-121">Used to calculate the Constraints registry entry for the adapter.</span></span>                                   |
|         <span data-ttu-id="6030f-122">**适配器可以从 BizTalk Server 发送消息**</span><span class="sxs-lookup"><span data-stu-id="6030f-122">**Adapter can send messages from BizTalk Server**</span></span>          |                                  <span data-ttu-id="6030f-123">标识适配器支持的通信模式。</span><span class="sxs-lookup"><span data-stu-id="6030f-123">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="6030f-124">用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="6030f-124">Used to calculate the Constraints registry entry for the adapter.</span></span>                                   |

### <a name="inbound-part-page"></a><span data-ttu-id="6030f-125">“入站部分”页</span><span class="sxs-lookup"><span data-stu-id="6030f-125">Inbound Part page</span></span>  
 <span data-ttu-id="6030f-126">使用“入站部分”页可以指定您的适配器的入站接收逻辑。</span><span class="sxs-lookup"><span data-stu-id="6030f-126">Use the Inbound Part page to specify inbound receiving logic for your adapter.</span></span>  

|<span data-ttu-id="6030f-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6030f-127">Use this</span></span>|<span data-ttu-id="6030f-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6030f-128">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="6030f-129">**“浏览”**</span><span class="sxs-lookup"><span data-stu-id="6030f-129">**Browse**</span></span>|<span data-ttu-id="6030f-130">选择为您的适配器实现入站接收逻辑的程序集。</span><span class="sxs-lookup"><span data-stu-id="6030f-130">Select the assembly that implements the inbound receiving logic for your adapter.</span></span> <span data-ttu-id="6030f-131">在下拉列表中显示此程序集公开的公共类型的列表。</span><span class="sxs-lookup"><span data-stu-id="6030f-131">A list of the public types exposed by this assembly appear in the drop-down list.</span></span> <span data-ttu-id="6030f-132">从下拉列表中选择指定程序集内实现此适配器的入站逻辑的类型。</span><span class="sxs-lookup"><span data-stu-id="6030f-132">Select the type within the specified assembly that implements the inbound logic for this adapter from the drop-down list.</span></span>|  
|<span data-ttu-id="6030f-133">**适配器支持请求-响应协议**</span><span class="sxs-lookup"><span data-stu-id="6030f-133">**Adapter supports request-response protocol**</span></span>|<span data-ttu-id="6030f-134">指定您的适配器的接收性能。</span><span class="sxs-lookup"><span data-stu-id="6030f-134">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="6030f-135">用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="6030f-135">Used to calculate the Constraints registry entry for your adapter.</span></span>|  
|<span data-ttu-id="6030f-136">**适配器是独立 （不同进程中承载）**</span><span class="sxs-lookup"><span data-stu-id="6030f-136">**Adapter is isolated (that is hosted in a different process)**</span></span>|<span data-ttu-id="6030f-137">指定您的适配器的接收性能。</span><span class="sxs-lookup"><span data-stu-id="6030f-137">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="6030f-138">用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="6030f-138">Used to calculate the Constraints registry entry for your adapter.</span></span>|  

### <a name="outbound-part-page"></a><span data-ttu-id="6030f-139">“出站部分”页</span><span class="sxs-lookup"><span data-stu-id="6030f-139">Outbound Part page</span></span>  
 <span data-ttu-id="6030f-140">使用“出站部分”页可以指定您的适配器的出站接收逻辑。</span><span class="sxs-lookup"><span data-stu-id="6030f-140">Use the Outbound Part page to specify outbound receiving logic for your adapter.</span></span>  

|<span data-ttu-id="6030f-141">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6030f-141">Use this</span></span>|<span data-ttu-id="6030f-142">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6030f-142">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="6030f-143">**“浏览”**</span><span class="sxs-lookup"><span data-stu-id="6030f-143">**Browse**</span></span>|<span data-ttu-id="6030f-144">选择为您的适配器实现出站接收逻辑的程序集。</span><span class="sxs-lookup"><span data-stu-id="6030f-144">Select the assembly that implements the outbound receiving logic for your adapter.</span></span> <span data-ttu-id="6030f-145">在下拉列表中将显示此程序集公开的公共类型的列表。</span><span class="sxs-lookup"><span data-stu-id="6030f-145">A list of the public types exposed by this assembly appears in the drop-down list .</span></span> <span data-ttu-id="6030f-146">从下拉列表中选择实现此适配器的出站逻辑的指定程序集的类型。</span><span class="sxs-lookup"><span data-stu-id="6030f-146">Select the type for the specified assembly that implements the outbound logic for this adapter from the drop-down list.</span></span> <span data-ttu-id="6030f-147">您还必须输入用于标识此适配器使用协议的别名的逗号分隔的列表（例如 submit://）。</span><span class="sxs-lookup"><span data-stu-id="6030f-147">You must also enter a comma-separated list of aliases used to identify the protocol used by this adapter (for example, submit://).</span></span>|  
|<span data-ttu-id="6030f-148">**适配器支持要求-响应协议**</span><span class="sxs-lookup"><span data-stu-id="6030f-148">**Adapter supports solicit-response protocol**</span></span>|<span data-ttu-id="6030f-149">标识您的适配器的传输性能。</span><span class="sxs-lookup"><span data-stu-id="6030f-149">Identify the transmitting capabilities of your adapter.</span></span> <span data-ttu-id="6030f-150">这些值用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="6030f-150">These values are used to calculate the Constraints registry entry for your adapter.</span></span>|  

### <a name="adapter-management-page"></a><span data-ttu-id="6030f-151">“适配器管理”页</span><span class="sxs-lookup"><span data-stu-id="6030f-151">Adapter Management page</span></span>  
 <span data-ttu-id="6030f-152">使用“适配器管理”页可以指定您的适配器的设计时管理逻辑。</span><span class="sxs-lookup"><span data-stu-id="6030f-152">Use the Adapter Management page to specify design-time management logic for your adapter.</span></span>  

|<span data-ttu-id="6030f-153">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6030f-153">Use this</span></span>|<span data-ttu-id="6030f-154">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6030f-154">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="6030f-155">**“浏览”**</span><span class="sxs-lookup"><span data-stu-id="6030f-155">**Browse**</span></span>|<span data-ttu-id="6030f-156">选择为您的适配器实现设计时适配器管理逻辑的程序集。</span><span class="sxs-lookup"><span data-stu-id="6030f-156">Select the assembly that implements the design-time adapter management logic for your adapter.</span></span> <span data-ttu-id="6030f-157">此程序集公开的公用类型列表将出现在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="6030f-157">A list of the public types exposed by this assembly appears in the drop-down list.</span></span> <span data-ttu-id="6030f-158">从下拉列表中选择为此适配器实现适配器管理逻辑的指定程序集类型。</span><span class="sxs-lookup"><span data-stu-id="6030f-158">Select the type for the specified assembly that implements the adapter management logic for this adapter from the drop-down list.</span></span>|  

### <a name="output-file-name"></a><span data-ttu-id="6030f-159">输出文件名</span><span class="sxs-lookup"><span data-stu-id="6030f-159">Output File name</span></span>  
 <span data-ttu-id="6030f-160">使用“输出文件名”页可以指定输出文件名和位置。</span><span class="sxs-lookup"><span data-stu-id="6030f-160">Use the Output file name page to specify an output file name and location.</span></span>  

|<span data-ttu-id="6030f-161">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6030f-161">Use this</span></span>|<span data-ttu-id="6030f-162">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6030f-162">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="6030f-163">**“浏览”**</span><span class="sxs-lookup"><span data-stu-id="6030f-163">**Browse**</span></span>|<span data-ttu-id="6030f-164">选择输出文件名和位置。</span><span class="sxs-lookup"><span data-stu-id="6030f-164">Choose an output file name and location.</span></span> <span data-ttu-id="6030f-165">适配器注册表将写入此文件。</span><span class="sxs-lookup"><span data-stu-id="6030f-165">The adapter registry is written to this file.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="6030f-166">Remarks</span><span class="sxs-lookup"><span data-stu-id="6030f-166">Remarks</span></span>  
 <span data-ttu-id="6030f-167">适配器注册向导实用程序使用默认值填充企业单一登录 (SSO) 配置存储属性。</span><span class="sxs-lookup"><span data-stu-id="6030f-167">The Adapter Registry Wizard utility populates the Enterprise Single Sign-On (SSO) configuration store properties with default values.</span></span> <span data-ttu-id="6030f-168">如果您的适配器没有使用适配器框架提供的标准属性页来用于处理程序和位置适配器属性，则必须手动编辑注册表文件以修改这些值。</span><span class="sxs-lookup"><span data-stu-id="6030f-168">If your adapter does not use the standard property pages provided by the Adapter Framework for handler and location adapter properties, you must edit the registry file manually to modify these values.</span></span> <span data-ttu-id="6030f-169">有关这些设置的详细信息，请参阅"注册的 SSO 配置存储的适配器属性"主题中[注册适配器](../core/registering-an-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6030f-169">For more information about these settings, see "Registration of adapter properties for SSO configuration store" in the topic [Registering an Adapter](../core/registering-an-adapter.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="6030f-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="6030f-170">See Also</span></span>  
 <span data-ttu-id="6030f-171">[SDK 中的实用工具](../core/utilities-in-the-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="6030f-171">[Utilities in the SDK](../core/utilities-in-the-sdk.md) </span></span>  
 [<span data-ttu-id="6030f-172">注册适配器</span><span class="sxs-lookup"><span data-stu-id="6030f-172">Registering an Adapter</span></span>](../core/registering-an-adapter.md)