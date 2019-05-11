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
ms.openlocfilehash: 36a103dd40bfce3c4207d1d37eae0afd93fb868f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361261"
---
# <a name="adapter-registry-wizard"></a><span data-ttu-id="4bf22-102">适配器注册向导</span><span class="sxs-lookup"><span data-stu-id="4bf22-102">Adapter Registry Wizard</span></span>
<span data-ttu-id="4bf22-103">适配器注册向导用于创建所需配置和注册自定义适配器的注册表文件。</span><span class="sxs-lookup"><span data-stu-id="4bf22-103">You use the Adapter Registry Wizard to create the registry files needed to configure and register a custom adapter.</span></span>  

## <a name="location-in-sdk"></a><span data-ttu-id="4bf22-104">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="4bf22-104">Location in SDK</span></span>  
 <span data-ttu-id="4bf22-105">*\<安装路径\>* \SDK\Utilities\AdapterRegistryWizard\\</span><span class="sxs-lookup"><span data-stu-id="4bf22-105">*\<Installation Path\>* \SDK\Utilities\AdapterRegistryWizard\\</span></span>  

## <a name="to-run-this-utility"></a><span data-ttu-id="4bf22-106">若要运行此实用程序</span><span class="sxs-lookup"><span data-stu-id="4bf22-106">To Run This Utility</span></span>  
 <span data-ttu-id="4bf22-107">通过运行 AdapterRegistryWizard.exe 可执行文件启动向导。</span><span class="sxs-lookup"><span data-stu-id="4bf22-107">Start the wizard by running the AdapterRegistryWizard.exe executable.</span></span> <span data-ttu-id="4bf22-108">向导中的页面提示您有关您的适配器和它所支持的属性信息。</span><span class="sxs-lookup"><span data-stu-id="4bf22-108">The pages that follow prompt you for information about your adapter and the properties that it supports.</span></span> <span data-ttu-id="4bf22-109">各适配器注册向导页所述后面的部分。</span><span class="sxs-lookup"><span data-stu-id="4bf22-109">The individual Adapter Registry Wizard pages are described in the sections that follow.</span></span>  

### <a name="generic-adapter-properties-page"></a><span data-ttu-id="4bf22-110">泛型适配器属性页</span><span class="sxs-lookup"><span data-stu-id="4bf22-110">Generic Adapter Properties page</span></span>  
 <span data-ttu-id="4bf22-111">泛型适配器属性页用于指定适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="4bf22-111">Use the Generic Adapter Properties page to specify adapter properties.</span></span>  


|                              <span data-ttu-id="4bf22-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4bf22-112">Use this</span></span>                              |                                                                                           <span data-ttu-id="4bf22-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4bf22-113">To do this</span></span>                                                                                           |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                     <span data-ttu-id="4bf22-114">**传输适配器类型**</span><span class="sxs-lookup"><span data-stu-id="4bf22-114">**Transport adapter type**</span></span>                     |                                                                                   <span data-ttu-id="4bf22-115">指定的适配器类型。</span><span class="sxs-lookup"><span data-stu-id="4bf22-115">Specify the adapter type.</span></span>                                                                                    |
|                       <span data-ttu-id="4bf22-116">**属性命名空间**</span><span class="sxs-lookup"><span data-stu-id="4bf22-116">**Property namespace**</span></span>                       | <span data-ttu-id="4bf22-117">指定适配器命名空间。</span><span class="sxs-lookup"><span data-stu-id="4bf22-117">Specify the adapter namespace.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4bf22-118">此命名空间中的消息上下文上存储特定于适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="4bf22-118">stores adapter-specific properties on the message context in this namespace.</span></span> |
| <span data-ttu-id="4bf22-119">**适配器可以接收消息并将其提交到 BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="4bf22-119">**Adapter can receive messages and submit them to BizTalk Server**</span></span> |                                  <span data-ttu-id="4bf22-120">标识适配器支持的通信模式。</span><span class="sxs-lookup"><span data-stu-id="4bf22-120">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="4bf22-121">用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="4bf22-121">Used to calculate the Constraints registry entry for the adapter.</span></span>                                   |
|         <span data-ttu-id="4bf22-122">**适配器可以从 BizTalk Server 发送消息**</span><span class="sxs-lookup"><span data-stu-id="4bf22-122">**Adapter can send messages from BizTalk Server**</span></span>          |                                  <span data-ttu-id="4bf22-123">标识适配器支持的通信模式。</span><span class="sxs-lookup"><span data-stu-id="4bf22-123">Identify communication patterns supported by the adapter.</span></span> <span data-ttu-id="4bf22-124">用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="4bf22-124">Used to calculate the Constraints registry entry for the adapter.</span></span>                                   |

### <a name="inbound-part-page"></a><span data-ttu-id="4bf22-125">入站的部件页</span><span class="sxs-lookup"><span data-stu-id="4bf22-125">Inbound Part page</span></span>  
 <span data-ttu-id="4bf22-126">使用入站部分页可以指定您的适配器的入站接收逻辑。</span><span class="sxs-lookup"><span data-stu-id="4bf22-126">Use the Inbound Part page to specify inbound receiving logic for your adapter.</span></span>  

|<span data-ttu-id="4bf22-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4bf22-127">Use this</span></span>|<span data-ttu-id="4bf22-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4bf22-128">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="4bf22-129">**“浏览”**</span><span class="sxs-lookup"><span data-stu-id="4bf22-129">**Browse**</span></span>|<span data-ttu-id="4bf22-130">选择实现您的适配器的入站接收逻辑的程序集。</span><span class="sxs-lookup"><span data-stu-id="4bf22-130">Select the assembly that implements the inbound receiving logic for your adapter.</span></span> <span data-ttu-id="4bf22-131">在下拉列表中显示此程序集公开的公共类型的列表。</span><span class="sxs-lookup"><span data-stu-id="4bf22-131">A list of the public types exposed by this assembly appear in the drop-down list.</span></span> <span data-ttu-id="4bf22-132">选择实现此适配器从下拉列表的入站的逻辑的指定程序集内的类型。</span><span class="sxs-lookup"><span data-stu-id="4bf22-132">Select the type within the specified assembly that implements the inbound logic for this adapter from the drop-down list.</span></span>|  
|<span data-ttu-id="4bf22-133">**适配器支持请求-响应协议**</span><span class="sxs-lookup"><span data-stu-id="4bf22-133">**Adapter supports request-response protocol**</span></span>|<span data-ttu-id="4bf22-134">指定您的适配器的接收功能。</span><span class="sxs-lookup"><span data-stu-id="4bf22-134">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="4bf22-135">用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="4bf22-135">Used to calculate the Constraints registry entry for your adapter.</span></span>|  
|<span data-ttu-id="4bf22-136">**适配器是独立 （不同进程中承载）**</span><span class="sxs-lookup"><span data-stu-id="4bf22-136">**Adapter is isolated (that is hosted in a different process)**</span></span>|<span data-ttu-id="4bf22-137">指定您的适配器的接收功能。</span><span class="sxs-lookup"><span data-stu-id="4bf22-137">Specify the receive capabilities of your adapter.</span></span> <span data-ttu-id="4bf22-138">用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="4bf22-138">Used to calculate the Constraints registry entry for your adapter.</span></span>|  

### <a name="outbound-part-page"></a><span data-ttu-id="4bf22-139">出站部件页</span><span class="sxs-lookup"><span data-stu-id="4bf22-139">Outbound Part page</span></span>  
 <span data-ttu-id="4bf22-140">使用出站部分页可以指定您的适配器的出站接收逻辑。</span><span class="sxs-lookup"><span data-stu-id="4bf22-140">Use the Outbound Part page to specify outbound receiving logic for your adapter.</span></span>  

|<span data-ttu-id="4bf22-141">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4bf22-141">Use this</span></span>|<span data-ttu-id="4bf22-142">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4bf22-142">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="4bf22-143">**“浏览”**</span><span class="sxs-lookup"><span data-stu-id="4bf22-143">**Browse**</span></span>|<span data-ttu-id="4bf22-144">选择实现您的适配器的出站接收逻辑的程序集。</span><span class="sxs-lookup"><span data-stu-id="4bf22-144">Select the assembly that implements the outbound receiving logic for your adapter.</span></span> <span data-ttu-id="4bf22-145">在下拉列表中将显示此程序集公开的公共类型的列表。</span><span class="sxs-lookup"><span data-stu-id="4bf22-145">A list of the public types exposed by this assembly appears in the drop-down list .</span></span> <span data-ttu-id="4bf22-146">为实现此适配器从下拉列表中的出站逻辑的指定程序集选择的类型。</span><span class="sxs-lookup"><span data-stu-id="4bf22-146">Select the type for the specified assembly that implements the outbound logic for this adapter from the drop-down list.</span></span> <span data-ttu-id="4bf22-147">您还必须输入用于标识此适配器使用的协议的别名的逗号分隔列表 (例如，提交: / /)。</span><span class="sxs-lookup"><span data-stu-id="4bf22-147">You must also enter a comma-separated list of aliases used to identify the protocol used by this adapter (for example, submit://).</span></span>|  
|<span data-ttu-id="4bf22-148">**适配器支持要求-响应协议**</span><span class="sxs-lookup"><span data-stu-id="4bf22-148">**Adapter supports solicit-response protocol**</span></span>|<span data-ttu-id="4bf22-149">确定您的适配器的传输性能。</span><span class="sxs-lookup"><span data-stu-id="4bf22-149">Identify the transmitting capabilities of your adapter.</span></span> <span data-ttu-id="4bf22-150">这些值用于计算适配器的约束注册表条目。</span><span class="sxs-lookup"><span data-stu-id="4bf22-150">These values are used to calculate the Constraints registry entry for your adapter.</span></span>|  

### <a name="adapter-management-page"></a><span data-ttu-id="4bf22-151">适配器管理页</span><span class="sxs-lookup"><span data-stu-id="4bf22-151">Adapter Management page</span></span>  
 <span data-ttu-id="4bf22-152">使用适配器管理页可以指定您的适配器的设计时管理逻辑。</span><span class="sxs-lookup"><span data-stu-id="4bf22-152">Use the Adapter Management page to specify design-time management logic for your adapter.</span></span>  

|<span data-ttu-id="4bf22-153">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4bf22-153">Use this</span></span>|<span data-ttu-id="4bf22-154">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4bf22-154">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="4bf22-155">**“浏览”**</span><span class="sxs-lookup"><span data-stu-id="4bf22-155">**Browse**</span></span>|<span data-ttu-id="4bf22-156">选择实现您的适配器的设计时适配器管理逻辑的程序集。</span><span class="sxs-lookup"><span data-stu-id="4bf22-156">Select the assembly that implements the design-time adapter management logic for your adapter.</span></span> <span data-ttu-id="4bf22-157">在下拉列表中将显示此程序集公开的公共类型的列表。</span><span class="sxs-lookup"><span data-stu-id="4bf22-157">A list of the public types exposed by this assembly appears in the drop-down list.</span></span> <span data-ttu-id="4bf22-158">指定实现适配器管理逻辑，从下拉列表中此适配器的程序集选择的类型。</span><span class="sxs-lookup"><span data-stu-id="4bf22-158">Select the type for the specified assembly that implements the adapter management logic for this adapter from the drop-down list.</span></span>|  

### <a name="output-file-name"></a><span data-ttu-id="4bf22-159">输出文件的名称</span><span class="sxs-lookup"><span data-stu-id="4bf22-159">Output File name</span></span>  
 <span data-ttu-id="4bf22-160">使用输出文件名称页可以指定输出文件的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="4bf22-160">Use the Output file name page to specify an output file name and location.</span></span>  

|<span data-ttu-id="4bf22-161">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4bf22-161">Use this</span></span>|<span data-ttu-id="4bf22-162">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4bf22-162">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="4bf22-163">**“浏览”**</span><span class="sxs-lookup"><span data-stu-id="4bf22-163">**Browse**</span></span>|<span data-ttu-id="4bf22-164">选择输出文件的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="4bf22-164">Choose an output file name and location.</span></span> <span data-ttu-id="4bf22-165">适配器注册表写入此文件。</span><span class="sxs-lookup"><span data-stu-id="4bf22-165">The adapter registry is written to this file.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="4bf22-166">备注</span><span class="sxs-lookup"><span data-stu-id="4bf22-166">Remarks</span></span>  
 <span data-ttu-id="4bf22-167">适配器注册向导实用程序填充企业单一登录 (SSO) 配置存储属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="4bf22-167">The Adapter Registry Wizard utility populates the Enterprise Single Sign-On (SSO) configuration store properties with default values.</span></span> <span data-ttu-id="4bf22-168">如果您的适配器不使用框架提供的适配器处理程序和位置适配器属性的标准属性页，则必须编辑注册表文件手动来修改这些值。</span><span class="sxs-lookup"><span data-stu-id="4bf22-168">If your adapter does not use the standard property pages provided by the Adapter Framework for handler and location adapter properties, you must edit the registry file manually to modify these values.</span></span> <span data-ttu-id="4bf22-169">有关这些设置的详细信息，请参阅"注册的 SSO 配置存储的适配器属性"主题中[注册适配器](../core/registering-an-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="4bf22-169">For more information about these settings, see "Registration of adapter properties for SSO configuration store" in the topic [Registering an Adapter](../core/registering-an-adapter.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="4bf22-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="4bf22-170">See Also</span></span>  
 <span data-ttu-id="4bf22-171">[SDK 中的实用工具](../core/utilities-in-the-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="4bf22-171">[Utilities in the SDK](../core/utilities-in-the-sdk.md) </span></span>  
 [<span data-ttu-id="4bf22-172">注册适配器</span><span class="sxs-lookup"><span data-stu-id="4bf22-172">Registering an Adapter</span></span>](../core/registering-an-adapter.md)