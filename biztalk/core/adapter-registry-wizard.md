---
title: "适配器注册表向导 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- utilities, Adapter Registration Wizard
- Adapter Registration Wizard
ms.assetid: bd15d0c7-01bb-41f9-9157-cdcf4bb4e39a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f07ef6adc96a4f5819cd5438b4a5d24ce6fc0770
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-registry-wizard"></a><span data-ttu-id="c9b65-102">适配器注册表向导</span><span class="sxs-lookup"><span data-stu-id="c9b65-102">Adapter Registry Wizard</span></span>
<span data-ttu-id="c9b65-103">适配器注册表向导用于创建配置和注册的自定义适配器所需的注册表文件。</span><span class="sxs-lookup"><span data-stu-id="c9b65-103">You use the Adapter Registry Wizard to create the registry files needed to configure and register a custom adapter.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="c9b65-104">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="c9b65-104">Location in SDK</span></span>  
 <span data-ttu-id="c9b65-105">*\<安装路径 >*\SDK\Utilities\AdapterRegistryWizard\\</span><span class="sxs-lookup"><span data-stu-id="c9b65-105">*\<Installation Path>*\SDK\Utilities\AdapterRegistryWizard\\</span></span>  
  
## <a name="to-run-this-utility"></a><span data-ttu-id="c9b65-106">运行本实用工具</span><span class="sxs-lookup"><span data-stu-id="c9b65-106">To Run This Utility</span></span>  
 <span data-ttu-id="c9b65-107">通过运行 AdapterRegistryWizard.exe 可执行程序启动该向导。</span><span class="sxs-lookup"><span data-stu-id="c9b65-107">Start the wizard by running the AdapterRegistryWizard.exe executable.</span></span> <span data-ttu-id="c9b65-108">向导中的页面将提示您与适配器及其支持的属性有关的信息。</span><span class="sxs-lookup"><span data-stu-id="c9b65-108">The pages that follow prompt you for information about your adapter and the properties that it supports.</span></span> <span data-ttu-id="c9b65-109">在后面的部分中将介绍各适配器注册向导页。</span><span class="sxs-lookup"><span data-stu-id="c9b65-109">The individual Adapter Registry Wizard pages are described in the sections that follow.</span></span>  
  
### <a name="generic-adapter-properties-page"></a><span data-ttu-id="c9b65-110">“一般适配器属性”页</span><span class="sxs-lookup"><span data-stu-id="c9b65-110">Generic Adapter Properties page</span></span>  
 <span data-ttu-id="c9b65-111">使用“一般适配器属性”页可指定适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="c9b65-111">Use the Generic Adapter Properties page to specify adapter properties.</span></span>  
  
|<span data-ttu-id="c9b65-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c9b65-112">Use this</span></span>|<span data-ttu-id="c9b65-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c9b65-113">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="c9b65-114">**传输适配器类型**</span><span class="sxs-lookup"><span data-stu-id="c9b65-114">**Transport adapter type**</span></span>|<span data-ttu-id="c9b65-115">指定适配器类型。</span><span class="sxs-lookup"><span data-stu-id="c9b65-115">Specify the adapter type.</span></span>|  
|<span data-ttu-id="c9b65-116">**属性命名空间**</span><span class="sxs-lookup"><span data-stu-id="c9b65-116">**Property namespace**</span></span>|<span data-ttu-id="c9b65-117">指定的适配器命名空间。</span><span class="sxs-lookup"><span data-stu-id="c9b65-117">Specify the adapter namespace.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c9b65-118">在此命名空间中的消息上下文上存储特定于适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="c9b65-118"> stores adapter-specific properties on the message context in this namespace.</span></span>|  
|<span data-ttu-id="c9b65-119">**适配器可以接收消息并将其提交给 BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="c9b65-119">**Adapter can receive messages and submit them to BizTalk Server**</span></span>|<span data-ttu-id="c9b65-120">标识适配器支持的通信模式。</span><span class="sxs-lookup"><span data-stu-id="c9b65-120">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="c9b65-121">用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="c9b65-121">Used to calculate the Constraints registry entry for the adapter.</span></span>|  
|<span data-ttu-id="c9b65-122">**适配器可以将消息从 BizTalk Server 发送**</span><span class="sxs-lookup"><span data-stu-id="c9b65-122">**Adapter can send messages from BizTalk Server**</span></span>|<span data-ttu-id="c9b65-123">标识适配器支持的通信模式。</span><span class="sxs-lookup"><span data-stu-id="c9b65-123">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="c9b65-124">用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="c9b65-124">Used to calculate the Constraints registry entry for the adapter.</span></span>|  
  
### <a name="inbound-part-page"></a><span data-ttu-id="c9b65-125">“入站部分”页</span><span class="sxs-lookup"><span data-stu-id="c9b65-125">Inbound Part page</span></span>  
 <span data-ttu-id="c9b65-126">使用“入站部分”页可以指定您的适配器的入站接收逻辑。</span><span class="sxs-lookup"><span data-stu-id="c9b65-126">Use the Inbound Part page to specify inbound receiving logic for your adapter.</span></span>  
  
|<span data-ttu-id="c9b65-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c9b65-127">Use this</span></span>|<span data-ttu-id="c9b65-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c9b65-128">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="c9b65-129">**浏览**</span><span class="sxs-lookup"><span data-stu-id="c9b65-129">**Browse**</span></span>|<span data-ttu-id="c9b65-130">选择为您的适配器实现入站接收逻辑的程序集。</span><span class="sxs-lookup"><span data-stu-id="c9b65-130">Select the assembly that implements the inbound receiving logic for your adapter.</span></span> <span data-ttu-id="c9b65-131">在下拉列表中显示此程序集公开的公共类型的列表。</span><span class="sxs-lookup"><span data-stu-id="c9b65-131">A list of the public types exposed by this assembly appear in the drop-down list.</span></span> <span data-ttu-id="c9b65-132">从下拉列表中选择指定程序集内实现此适配器的入站逻辑的类型。</span><span class="sxs-lookup"><span data-stu-id="c9b65-132">Select the type within the specified assembly that implements the inbound logic for this adapter from the drop-down list.</span></span>|  
|<span data-ttu-id="c9b65-133">**适配器支持请求-响应协议**</span><span class="sxs-lookup"><span data-stu-id="c9b65-133">**Adapter supports request-response protocol**</span></span>|<span data-ttu-id="c9b65-134">指定您的适配器的接收性能。</span><span class="sxs-lookup"><span data-stu-id="c9b65-134">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="c9b65-135">用于计算你的适配器的约束注册表项。</span><span class="sxs-lookup"><span data-stu-id="c9b65-135">Used to calculate the Constraints registry entry for your adapter.</span></span>|  
|<span data-ttu-id="c9b65-136">**适配器是独立 （承载于不同的进程）**</span><span class="sxs-lookup"><span data-stu-id="c9b65-136">**Adapter is isolated (that is hosted in a different process)**</span></span>|<span data-ttu-id="c9b65-137">指定您的适配器的接收性能。</span><span class="sxs-lookup"><span data-stu-id="c9b65-137">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="c9b65-138">用于计算你的适配器的约束注册表项。</span><span class="sxs-lookup"><span data-stu-id="c9b65-138">Used to calculate the Constraints registry entry for your adapter.</span></span>|  
  
### <a name="outbound-part-page"></a><span data-ttu-id="c9b65-139">“出站部分”页</span><span class="sxs-lookup"><span data-stu-id="c9b65-139">Outbound Part page</span></span>  
 <span data-ttu-id="c9b65-140">使用“出站部分”页可以指定您的适配器的出站接收逻辑。</span><span class="sxs-lookup"><span data-stu-id="c9b65-140">Use the Outbound Part page to specify outbound receiving logic for your adapter.</span></span>  
  
|<span data-ttu-id="c9b65-141">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c9b65-141">Use this</span></span>|<span data-ttu-id="c9b65-142">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c9b65-142">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="c9b65-143">**浏览**</span><span class="sxs-lookup"><span data-stu-id="c9b65-143">**Browse**</span></span>|<span data-ttu-id="c9b65-144">选择为您的适配器实现出站接收逻辑的程序集。</span><span class="sxs-lookup"><span data-stu-id="c9b65-144">Select the assembly that implements the outbound receiving logic for your adapter.</span></span> <span data-ttu-id="c9b65-145">此程序集公开的公共类型列表将显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="c9b65-145">A list of the public types exposed by this assembly appears in the drop-down list .</span></span> <span data-ttu-id="c9b65-146">从下拉列表中选择实现此适配器的出站逻辑的指定程序集的类型。</span><span class="sxs-lookup"><span data-stu-id="c9b65-146">Select the type for the specified assembly that implements the outbound logic for this adapter from the drop-down list.</span></span> <span data-ttu-id="c9b65-147">您还必须输入用于标识此适配器使用协议的别名的逗号分隔的列表（例如 submit://）。</span><span class="sxs-lookup"><span data-stu-id="c9b65-147">You must also enter a comma-separated list of aliases used to identify the protocol used by this adapter (for example, submit://).</span></span>|  
|<span data-ttu-id="c9b65-148">**适配器支持请求作出响应协议**</span><span class="sxs-lookup"><span data-stu-id="c9b65-148">**Adapter supports solicit-response protocol**</span></span>|<span data-ttu-id="c9b65-149">标识您的适配器的传输性能。</span><span class="sxs-lookup"><span data-stu-id="c9b65-149">Identify the transmitting capabilities of your adapter.</span></span> <span data-ttu-id="c9b65-150">这些值用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="c9b65-150">These values are used to calculate the Constraints registry entry for your adapter.</span></span>|  
  
### <a name="adapter-management-page"></a><span data-ttu-id="c9b65-151">“适配器管理”页</span><span class="sxs-lookup"><span data-stu-id="c9b65-151">Adapter Management page</span></span>  
 <span data-ttu-id="c9b65-152">使用“适配器管理”页可以指定您的适配器的设计时管理逻辑。</span><span class="sxs-lookup"><span data-stu-id="c9b65-152">Use the Adapter Management page to specify design-time management logic for your adapter.</span></span>  
  
|<span data-ttu-id="c9b65-153">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c9b65-153">Use this</span></span>|<span data-ttu-id="c9b65-154">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c9b65-154">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="c9b65-155">**浏览**</span><span class="sxs-lookup"><span data-stu-id="c9b65-155">**Browse**</span></span>|<span data-ttu-id="c9b65-156">选择为您的适配器实现设计时适配器管理逻辑的程序集。</span><span class="sxs-lookup"><span data-stu-id="c9b65-156">Select the assembly that implements the design-time adapter management logic for your adapter.</span></span> <span data-ttu-id="c9b65-157">此程序集公开的公用类型列表将出现在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="c9b65-157">A list of the public types exposed by this assembly appears in the drop-down list.</span></span> <span data-ttu-id="c9b65-158">从下拉列表中选择为此适配器实现适配器管理逻辑的指定程序集类型。</span><span class="sxs-lookup"><span data-stu-id="c9b65-158">Select the type for the specified assembly that implements the adapter management logic for this adapter from the drop-down list.</span></span>|  
  
### <a name="output-file-name"></a><span data-ttu-id="c9b65-159">输出文件名</span><span class="sxs-lookup"><span data-stu-id="c9b65-159">Output File name</span></span>  
 <span data-ttu-id="c9b65-160">使用“输出文件名”页可以指定输出文件名和位置。</span><span class="sxs-lookup"><span data-stu-id="c9b65-160">Use the Output file name page to specify an output file name and location.</span></span>  
  
|<span data-ttu-id="c9b65-161">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c9b65-161">Use this</span></span>|<span data-ttu-id="c9b65-162">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c9b65-162">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="c9b65-163">**浏览**</span><span class="sxs-lookup"><span data-stu-id="c9b65-163">**Browse**</span></span>|<span data-ttu-id="c9b65-164">选择输出文件名和位置。</span><span class="sxs-lookup"><span data-stu-id="c9b65-164">Choose an output file name and location.</span></span> <span data-ttu-id="c9b65-165">适配器注册表将写入此文件。</span><span class="sxs-lookup"><span data-stu-id="c9b65-165">The adapter registry is written to this file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9b65-166">注释</span><span class="sxs-lookup"><span data-stu-id="c9b65-166">Remarks</span></span>  
 <span data-ttu-id="c9b65-167">适配器注册向导实用程序使用默认值填充企业单一登录 (SSO) 配置存储属性。</span><span class="sxs-lookup"><span data-stu-id="c9b65-167">The Adapter Registry Wizard utility populates the Enterprise Single Sign-On (SSO) configuration store properties with default values.</span></span> <span data-ttu-id="c9b65-168">如果您的适配器没有使用适配器框架提供的标准属性页来用于处理程序和位置适配器属性，则必须手动编辑注册表文件以修改这些值。</span><span class="sxs-lookup"><span data-stu-id="c9b65-168">If your adapter does not use the standard property pages provided by the Adapter Framework for handler and location adapter properties, you must edit the registry file manually to modify these values.</span></span> <span data-ttu-id="c9b65-169">有关这些设置的详细信息，请参阅"注册的 SSO 配置存储区的适配器属性"主题中[注册适配器](../core/registering-an-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="c9b65-169">For more information about these settings, see "Registration of adapter properties for SSO configuration store" in the topic [Registering an Adapter](../core/registering-an-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9b65-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9b65-170">See Also</span></span>  
 <span data-ttu-id="c9b65-171">[SDK 中的实用程序](../core/utilities-in-the-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="c9b65-171">[Utilities in the SDK](../core/utilities-in-the-sdk.md) </span></span>  
 [<span data-ttu-id="c9b65-172">注册的适配器</span><span class="sxs-lookup"><span data-stu-id="c9b65-172">Registering an Adapter</span></span>](../core/registering-an-adapter.md)