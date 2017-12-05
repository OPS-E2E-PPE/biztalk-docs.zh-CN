---
title: "如何： 将服务发布到 UDDI 3.0 注册表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c3bd0ed-e5f1-43eb-98d1-e3247a565ba2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da3d2dc400c031ab5febda1568cb18ce5180366b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-publish-a-service-to-the-uddi-30-registry"></a><span data-ttu-id="9dabc-102">如何： 将服务发布到 UDDI 3.0 注册表</span><span class="sxs-lookup"><span data-stu-id="9dabc-102">How to: Publish a Service to the UDDI 3.0 Registry</span></span>
## <a name="goal"></a><span data-ttu-id="9dabc-103">目的</span><span class="sxs-lookup"><span data-stu-id="9dabc-103">Goal</span></span>  
 <span data-ttu-id="9dabc-104">本部分演示如何使用 UDDI 服务网站发布内就能解决从为了 ESB 消息路由路线的 Web 服务终结点。</span><span class="sxs-lookup"><span data-stu-id="9dabc-104">This section demonstrates how to use the UDDI Service site to publish a Web service endpoint that can be resolved from within an itinerary for the purpose of routing an ESB message.</span></span> <span data-ttu-id="9dabc-105">将复制现有 PurchaseOrderSubmitOrderService 服务目前发布到注册表。</span><span class="sxs-lookup"><span data-stu-id="9dabc-105">You will duplicate the existing PurchaseOrderSubmitOrderService service presently published to the registry.</span></span>  
  
 <span data-ttu-id="9dabc-106">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="9dabc-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="9dabc-107">将服务发布到通用、 描述、 发现和集成 (UDDI) 3 使用 UDDI 发行者工具的注册表。</span><span class="sxs-lookup"><span data-stu-id="9dabc-107">Publish a service to the Universal Description, Discovery, and Integration (UDDI) 3 registry using the UDDI Publisher tool.</span></span>  
  
-   <span data-ttu-id="9dabc-108">测试使用解析使用 UDDI3 解析程序的服务终结点路线路由滑动服务发布。</span><span class="sxs-lookup"><span data-stu-id="9dabc-108">Test the service publication using an itinerary routing slip that resolves the service endpoint using a UDDI3 resolver.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9dabc-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="9dabc-109">Prerequisites</span></span>  
 <span data-ttu-id="9dabc-110">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)和 （你可以安装它在 %esb 安装 Folder%\Bin\ UDDI 发行者工具的执行Microsoft.Practices.ESB.UDDIPublisher.exe)。</span><span class="sxs-lookup"><span data-stu-id="9dabc-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) and the execution of the UDDI Publisher tool (you can install it at %ESB Install Folder%\Bin\Microsoft.Practices.ESB.UDDIPublisher.exe).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="9dabc-111">步骤</span><span class="sxs-lookup"><span data-stu-id="9dabc-111">Steps</span></span>  
  
#### <a name="to-create-the-newposervice-in-the-uddi-registry"></a><span data-ttu-id="9dabc-112">在发布的 UDDI 注册表中创建 NewPOService</span><span class="sxs-lookup"><span data-stu-id="9dabc-112">To create the NewPOService in the UDDI registry</span></span>  
  
1.  <span data-ttu-id="9dabc-113">在 Internet Explorer 中，浏览到 UDDI 服务网站 （默认情况下，此 URL 为 http://localhost/uddi）。</span><span class="sxs-lookup"><span data-stu-id="9dabc-113">In Internet Explorer, browse to the UDDI Service site (by default, the URL for this is http://localhost/uddi).</span></span>  
  
2.  <span data-ttu-id="9dabc-114">上**uddi 服务**页上，单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-114">On the **uddi Services** page, click **Publish**.</span></span>  
  
3.  <span data-ttu-id="9dabc-115">在发布窗格中，右键单击**Microsoft.Practices.ESB**，然后单击**添加服务**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-115">In the Publish pane, right-click **Microsoft.Practices.ESB**, and then click **Add Service**.</span></span>  
  
4.  <span data-ttu-id="9dabc-116">在以下页面上，选择**指定要使用的密钥**，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-116">On the following page, select **Specify a key to use**, and then click **Continue**.</span></span>  
  
5.  <span data-ttu-id="9dabc-117">在以下页上，单击**esb**密钥分区。</span><span class="sxs-lookup"><span data-stu-id="9dabc-117">On the following page, click the **esb** key partition.</span></span> <span data-ttu-id="9dabc-118">在**密钥后缀**框中，键入**newposervice**，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-118">In the **Key Suffix** box, type **newposervice**, and then click **Continue**.</span></span>  
  
6.  <span data-ttu-id="9dabc-119">在以下页面中下, 一步 (**新的服务名称**)，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-119">On the following page, next to (**New Service Name**), click **Edit**.</span></span> <span data-ttu-id="9dabc-120">将服务**NewPOService**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-120">Name the service **NewPOService**, and then click **Update**.</span></span>  
  
7.  <span data-ttu-id="9dabc-121">单击**添加说明**，键入服务的说明 (例如，**示例服务**)，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-121">Click **Add Description**, type a description for the service (for example, **Sample Service**), and then click **Update**.</span></span>  
  
#### <a name="to-add-a-binding-for-the-newposervice"></a><span data-ttu-id="9dabc-122">若要将绑定添加为 NewPOService</span><span class="sxs-lookup"><span data-stu-id="9dabc-122">To add a binding for the NewPOService</span></span>  
  
1.  <span data-ttu-id="9dabc-123">单击**绑定**选项卡上，并依次**添加绑定**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-123">Click the **Bindings** tab, and then click **Add Binding**.</span></span>  
  
2.  <span data-ttu-id="9dabc-124">选择**指定要使用的密钥**，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-124">Select **Specify a key to use**, and then click **Continue**.</span></span>  
  
3.  <span data-ttu-id="9dabc-125">在以下页上，单击**esb**密钥分区。</span><span class="sxs-lookup"><span data-stu-id="9dabc-125">On the following page, click the **esb** key partition.</span></span> <span data-ttu-id="9dabc-126">在**密钥后缀**框中，键入**newposervicebinding**，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-126">In the **Key Suffix** box, type **newposervicebinding**, and then click **Continue**.</span></span>  
  
4.  <span data-ttu-id="9dabc-127">下**接入点**，单击**编辑**，然后完成以下：</span><span class="sxs-lookup"><span data-stu-id="9dabc-127">Under **Access Point**, click **Edit**, and then complete the following:</span></span>  
  
    1.  <span data-ttu-id="9dabc-128">在**接入点**框中，键入**http://localhost/ESB.CanadianServices/SubmitPOService.asmx**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-128">In the **Access Point** box, type **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span></span>  
  
    2.  <span data-ttu-id="9dabc-129">在**使用类型**下拉列表中，单击**终结点**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-129">In the **Use Type** drop-down list, click **endpoint**, and then click **Update**.</span></span>  
  
#### <a name="to-configure-the-binding-instance-information"></a><span data-ttu-id="9dabc-130">若要配置的绑定实例信息</span><span class="sxs-lookup"><span data-stu-id="9dabc-130">To configure the binding instance information</span></span>  
  
1.  <span data-ttu-id="9dabc-131">单击**实例信息**选项卡上，并依次**添加实例信息**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-131">Click the **Instance Info** tab, and then click **Add Instance Info**.</span></span>  
  
2.  <span data-ttu-id="9dabc-132">在**搜索 tModel 名称中包含**框中，键入**%esb%** ，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-132">In the **Search for tModel names containing** box, type **%esb%** and then click **Search**.</span></span>  
  
3.  <span data-ttu-id="9dabc-133">找到并单击**tModel**为**transporttype**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-133">Locate and click the **tModel** for **transporttype**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9dabc-134">若要完成此过程中的剩余步骤，你可能需要第 1 页和第 2 页之间发生更改。</span><span class="sxs-lookup"><span data-stu-id="9dabc-134">To complete the remaining steps in this procedure, you may be required to change between page 1 and page 2.</span></span>  
  
4.  <span data-ttu-id="9dabc-135">在**说明**部分中，单击**添加说明**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-135">In the **Descriptions** section, click **Add Description**.</span></span>  
  
5.  <span data-ttu-id="9dabc-136">在**说明**框中，键入**ESB 路线使用的传输类型**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-136">In the **Description** box, type **Transport Type for ESB Itinerary Use**, and then click **Update**.</span></span>  
  
6.  <span data-ttu-id="9dabc-137">单击**实例详细信息**选项卡上，并依次**编辑**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-137">Click the **Instance Details** tab, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="9dabc-138">在**实例参数**框中，键入**WCF BasicHttp**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-138">In the **Instance Parameters** box, type **WCF-BasicHttp**, and then click **Update**.</span></span>  
  
8.  <span data-ttu-id="9dabc-139">在**说明**部分中，单击**添加说明**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-139">In the **Descriptions** section, click **Add Description**.</span></span>  
  
9. <span data-ttu-id="9dabc-140">在**说明**框中，键入**WCF 基本 HTTP 传输**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-140">In the **Description** box, type **WCF Basic HTTP Transport**, and then click **Update**.</span></span>  
  
10. <span data-ttu-id="9dabc-141">在发布窗格中，在**NewPOService**，单击**http://localhost/esb.canadianservices/submitposervice.asmx**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-141">In the Publish pane, under **NewPOService**, click **http://localhost/esb.canadianservices/submitposervice.asmx**.</span></span>  
  
11. <span data-ttu-id="9dabc-142">上**实例信息**选项卡上，单击**添加实例信息**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-142">On the **Instance Info** tab, click **Add Instance Info**.</span></span>  
  
12. <span data-ttu-id="9dabc-143">使用前面所述的步骤，添加以下实例的信息，根据下表中显示的值。</span><span class="sxs-lookup"><span data-stu-id="9dabc-143">Using the steps described earlier, add the following instance information, according to the values shown in the following table.</span></span>  
  
    |<span data-ttu-id="9dabc-144">tModel</span><span class="sxs-lookup"><span data-stu-id="9dabc-144">tModel</span></span>|<span data-ttu-id="9dabc-145">Description</span><span class="sxs-lookup"><span data-stu-id="9dabc-145">Description</span></span>|<span data-ttu-id="9dabc-146">参数</span><span class="sxs-lookup"><span data-stu-id="9dabc-146">Parameter</span></span>|<span data-ttu-id="9dabc-147">参数说明</span><span class="sxs-lookup"><span data-stu-id="9dabc-147">Parameter description</span></span>|  
    |------------|-----------------|---------------|---------------------------|  
    |<span data-ttu-id="9dabc-148">microsoft-com:esb:runtimeresolution:messageexchangepattern</span><span class="sxs-lookup"><span data-stu-id="9dabc-148">microsoft-com:esb:runtimeresolution:messageexchangepattern</span></span>|<span data-ttu-id="9dabc-149">消息交换模式</span><span class="sxs-lookup"><span data-stu-id="9dabc-149">Message Exchange Pattern</span></span>|<span data-ttu-id="9dabc-150">双向</span><span class="sxs-lookup"><span data-stu-id="9dabc-150">Two-Way</span></span>|<span data-ttu-id="9dabc-151">双向操作</span><span class="sxs-lookup"><span data-stu-id="9dabc-151">Two-way operation</span></span>|  
    |<span data-ttu-id="9dabc-152">microsoft-com:esb:runtimeresolution:cachetimeout</span><span class="sxs-lookup"><span data-stu-id="9dabc-152">microsoft-com:esb:runtimeresolution:cachetimeout</span></span>|<span data-ttu-id="9dabc-153">缓存超时值</span><span class="sxs-lookup"><span data-stu-id="9dabc-153">Cache Timeout</span></span>|<span data-ttu-id="9dabc-154">-1</span><span class="sxs-lookup"><span data-stu-id="9dabc-154">-1</span></span>|<span data-ttu-id="9dabc-155">当前已禁用</span><span class="sxs-lookup"><span data-stu-id="9dabc-155">Currently disabled</span></span>|  
    |<span data-ttu-id="9dabc-156">microsoft-com:esb:runtimeresolution:jaxrpcresponse</span><span class="sxs-lookup"><span data-stu-id="9dabc-156">microsoft-com:esb:runtimeresolution:jaxrpcresponse</span></span>|<span data-ttu-id="9dabc-157">JaxRpcResponse</span><span class="sxs-lookup"><span data-stu-id="9dabc-157">JaxRpcResponse</span></span>|<span data-ttu-id="9dabc-158">false</span><span class="sxs-lookup"><span data-stu-id="9dabc-158">false</span></span>||  
    |<span data-ttu-id="9dabc-159">microsoft-com:esb:runtimeresolution:action</span><span class="sxs-lookup"><span data-stu-id="9dabc-159">microsoft-com:esb:runtimeresolution:action</span></span>|<span data-ttu-id="9dabc-160">服务操作</span><span class="sxs-lookup"><span data-stu-id="9dabc-160">Service Action</span></span>|<span data-ttu-id="9dabc-161">将订单</span><span class="sxs-lookup"><span data-stu-id="9dabc-161">submitOrder</span></span>|<span data-ttu-id="9dabc-162">指定要调用的服务方法</span><span class="sxs-lookup"><span data-stu-id="9dabc-162">Specifies the service method to invoke</span></span>|  
    |<span data-ttu-id="9dabc-163">microsoft-com:esb:runtimeresolution:targetnamespace</span><span class="sxs-lookup"><span data-stu-id="9dabc-163">microsoft-com:esb:runtimeresolution:targetnamespace</span></span>|<span data-ttu-id="9dabc-164">服务 Namespace</span><span class="sxs-lookup"><span data-stu-id="9dabc-164">Service Namespace</span></span>|<span data-ttu-id="9dabc-165">http://globalbank.esb.dynamicresolution.com/canadianservices</span><span class="sxs-lookup"><span data-stu-id="9dabc-165">http://globalbank.esb.dynamicresolution.com/canadianservices</span></span>|<span data-ttu-id="9dabc-166">目标命名空间</span><span class="sxs-lookup"><span data-stu-id="9dabc-166">Target namespace</span></span>|  
  
#### <a name="to-configure-the-binding-categorization"></a><span data-ttu-id="9dabc-167">若要配置的绑定分类</span><span class="sxs-lookup"><span data-stu-id="9dabc-167">To configure the binding categorization</span></span>  
  
1.  <span data-ttu-id="9dabc-168">在发布窗格中，在**NewPOService**，单击**http://localhost/esb.canadianservices/submitposervice.asmx**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-168">In the Publish pane, under **NewPOService**, click **http://localhost/esb.canadianservices/submitposervice.asmx**.</span></span>  
  
2.  <span data-ttu-id="9dabc-169">上**类别**选项卡上，单击**添加自定义类别**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-169">On the **Categories** tab, click **Add Custom Category**.</span></span>  
  
3.  <span data-ttu-id="9dabc-170">在**搜索**框中，键入**%esb%** ，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-170">In the **Search** box, type **%esb%** and then click **Search**.</span></span>  
  
4.  <span data-ttu-id="9dabc-171">找到并单击**microsoft-com:esb:runtimeresolution:biztalkapplication** tModel。</span><span class="sxs-lookup"><span data-stu-id="9dabc-171">Locate and click the **microsoft-com:esb:runtimeresolution:biztalkapplication** tModel.</span></span>  
  
5.  <span data-ttu-id="9dabc-172">在**密钥名称**框中，键入**BizTalk 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-172">In the **Key Name** box, type **BizTalk Application**.</span></span>  
  
6.  <span data-ttu-id="9dabc-173">在**键值**框中，键入**Microsoft.Practices.ESB**，然后单击**添加类别**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-173">In the **Key Value** box, type **Microsoft.Practices.ESB**, and then click **Add Category**.</span></span>  
  
7.  <span data-ttu-id="9dabc-174">使用前面所述的步骤，添加以下自定义类别中，根据下表中显示的值。</span><span class="sxs-lookup"><span data-stu-id="9dabc-174">Using the steps described earlier, add the following custom categories, according to the values shown in the following table.</span></span>  
  
    |<span data-ttu-id="9dabc-175">tModel</span><span class="sxs-lookup"><span data-stu-id="9dabc-175">tModel</span></span>|<span data-ttu-id="9dabc-176">项名</span><span class="sxs-lookup"><span data-stu-id="9dabc-176">Key name</span></span>|<span data-ttu-id="9dabc-177">密钥值</span><span class="sxs-lookup"><span data-stu-id="9dabc-177">Key value</span></span>|  
    |------------|--------------|---------------|  
    |<span data-ttu-id="9dabc-178">microsoft-com:esb:runtimeresolution:portname</span><span class="sxs-lookup"><span data-stu-id="9dabc-178">microsoft-com:esb:runtimeresolution:portname</span></span>|<span data-ttu-id="9dabc-179">端口名称</span><span class="sxs-lookup"><span data-stu-id="9dabc-179">Port Name</span></span>|<span data-ttu-id="9dabc-180">NewPOService</span><span class="sxs-lookup"><span data-stu-id="9dabc-180">NewPOService</span></span>|  
    |<span data-ttu-id="9dabc-181">microsoft-com:esb:runtimeresolution:transporttype</span><span class="sxs-lookup"><span data-stu-id="9dabc-181">microsoft-com:esb:runtimeresolution:transporttype</span></span>|<span data-ttu-id="9dabc-182">传输类型</span><span class="sxs-lookup"><span data-stu-id="9dabc-182">Transport Type</span></span>|<span data-ttu-id="9dabc-183">WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="9dabc-183">WCF-BasicHttp</span></span>|  
  
#### <a name="to-locate-the-service-in-the-uddi-registry"></a><span data-ttu-id="9dabc-184">若要查找 UDDI 注册表中的服务</span><span class="sxs-lookup"><span data-stu-id="9dabc-184">To locate the service in the UDDI registry</span></span>  
  
1.  <span data-ttu-id="9dabc-185">在 Internet Explorer 中，在**uddi 服务**页上，单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-185">In Internet Explorer, on the **uddi Services** page, click **Search**.</span></span>  
  
2.  <span data-ttu-id="9dabc-186">单击**服务**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9dabc-186">Click the **Services** tab.</span></span>  
  
3.  <span data-ttu-id="9dabc-187">在**服务名称**框中，键入**%PO%**，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-187">In the **Service Name** box, type **%PO%**, and then click **Search**.</span></span>  
  
4.  <span data-ttu-id="9dabc-188">在**搜索**窗格中，在**结果**选项卡上，单击**NewPOService**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-188">In the **Search** pane, on the **Results** tab, click **NewPOService**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9dabc-189">这样会确认服务已成功发布到注册表。</span><span class="sxs-lookup"><span data-stu-id="9dabc-189">This confirms the service was successfully published to the registry.</span></span>  
  
#### <a name="to-create-an-itinerary-model-to-test-the-uddi-service-publication"></a><span data-ttu-id="9dabc-190">若要创建路线模型来测试 UDDI 服务发布</span><span class="sxs-lookup"><span data-stu-id="9dabc-190">To create an itinerary model to test the UDDI service publication</span></span>  
  
1.  <span data-ttu-id="9dabc-191">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="9dabc-191">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="9dabc-192">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-192">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="9dabc-193">在**添加新项**对话框中，在**名称**框中，键入**NewBindingKeySearch**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-193">In the **Add New Item** dialog box, in the **Name** box, type **NewBindingKeySearch**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="9dabc-194">若要配置路线的属性</span><span class="sxs-lookup"><span data-stu-id="9dabc-194">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="9dabc-195">在 Visual Studio 中，单击的设计图面**NewBindingKeySearch.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-195">In Visual Studio, click the design surface of **NewBindingKeySearch.itinerary**.</span></span> <span data-ttu-id="9dabc-196">在**NewBindingKeySearch**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="9dabc-196">In the **NewBindingKeySearch** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9dabc-197">在**是请求响应**下拉列表中，单击**True**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-197">In the **Is Request Response** drop-down list, click **True**.</span></span>  
  
    2.  <span data-ttu-id="9dabc-198">在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-198">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="9dabc-199">在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="9dabc-199">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    4.  <span data-ttu-id="9dabc-200">在**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\NewBindingKeySearch**中**文件名**框中，并依次**保存**.</span><span class="sxs-lookup"><span data-stu-id="9dabc-200">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\NewBindingKeySearch** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9dabc-201">此步骤允许您路线作为 XML 导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="9dabc-201">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="9dabc-202">通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="9dabc-202">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="9dabc-203">你将完成本操作方法主题中后面此过程。</span><span class="sxs-lookup"><span data-stu-id="9dabc-203">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="9dabc-204">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="9dabc-204">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="9dabc-205">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="9dabc-205">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="9dabc-206">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="9dabc-206">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9dabc-207">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-207">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="9dabc-208">在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-208">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="9dabc-209">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-209">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="9dabc-210">在**接收端口**下拉列表中，单击**OnRamp.Itinerary.Response**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-210">In the **Receive Port** drop-down list, click **OnRamp.Itinerary.Response**.</span></span>  
  
2.  <span data-ttu-id="9dabc-211">从工具箱中，拖动**路线服务**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="9dabc-211">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="9dabc-212">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="9dabc-212">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9dabc-213">单击**名称**属性，再然后键入**TransformNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-213">Click the **Name** property, and then type **TransformNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="9dabc-214">在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-214">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="9dabc-215">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-215">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="9dabc-216">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-216">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="9dabc-217">右键单击**冲突解决程序**集合**TransformNAOrder**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-217">Right-click the **Resolver** collection of the **TransformNAOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="9dabc-218">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="9dabc-218">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9dabc-219">单击**名称**属性，再然后键入**NAOrder_to_CNOrder**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-219">Click the **Name** property, and then type **NAOrder_to_CNOrder**.</span></span>  
  
    2.  <span data-ttu-id="9dabc-220">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-220">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="9dabc-221">在**转换类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-221">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
4.  <span data-ttu-id="9dabc-222">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-222">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9dabc-223">将从连接**ReceiveNAOrder**到模型元素**TransformNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="9dabc-223">Drag a connection from the **ReceiveNAOrder** model element to the **TransformNAOrder** model element.</span></span>  
  
5.  <span data-ttu-id="9dabc-224">从工具箱中，拖动**路线服务**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="9dabc-224">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="9dabc-225">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="9dabc-225">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9dabc-226">单击**名称**属性，再然后键入**BindingKeyRoute**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-226">Click the **Name** property, and then type **BindingKeyRoute**.</span></span>  
  
    2.  <span data-ttu-id="9dabc-227">在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-227">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="9dabc-228">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-228">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="9dabc-229">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-229">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
6.  <span data-ttu-id="9dabc-230">右键单击**冲突解决程序**集合**BindingKeyRoute**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-230">Right-click the **Resolver** collection of the **BindingKeyRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="9dabc-231">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="9dabc-231">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9dabc-232">单击**名称**属性，再然后键入**BindingKeySearch**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-232">Click the **Name** property, and then type **BindingKeySearch**.</span></span>  
  
    2.  <span data-ttu-id="9dabc-233">在**解析程序实现**下拉列表中，单击**Uddi3 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-233">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="9dabc-234">在**冲突解决程序名字对象**下拉列表中，单击**UDDI3**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-234">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  
  
    4.  <span data-ttu-id="9dabc-235">单击**绑定密钥**属性，再然后键入**uddi:esb:newposervicebinding**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-235">Click the **Binding key** property, and then type **uddi:esb:newposervicebinding**.</span></span> <span data-ttu-id="9dabc-236">若要查找的键值，单击 UDDI 中的 http://localhost/ESB.CanadianServices/SubmitPOService.asmx 服务，然后单击更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9dabc-236">To find the key value, click the http://localhost/ESB.CanadianServices/SubmitPOService.asmx service in UDDI, and then click More Details.</span></span>  
  
7.  <span data-ttu-id="9dabc-237">右键单击**BindingKeySearch**冲突解决程序，，然后单击**测试解析程序配置**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-237">Right-click the **BindingKeySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9dabc-238">验证显示在输出窗口中的输出。</span><span class="sxs-lookup"><span data-stu-id="9dabc-238">Verify the output displayed in the Output window.</span></span>  
  
8.  <span data-ttu-id="9dabc-239">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-239">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9dabc-240">将从连接**TransformNAOrder**到模型元素**BindingKeyRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="9dabc-240">Drag a connection from the **TransformNAOrder** model element to the **BindingKeyRoute** model element.</span></span>  
  
9. <span data-ttu-id="9dabc-241">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**BindingKeyRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="9dabc-241">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BindingKeyRoute** model element.</span></span> <span data-ttu-id="9dabc-242">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="9dabc-242">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9dabc-243">单击**名称**属性，再然后键入**SendCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-243">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="9dabc-244">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-244">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="9dabc-245">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-245">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="9dabc-246">在**发送端口**下拉列表中，单击**DynamicResolutionSolicitResp**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-246">In the **Send Port** drop-down list, click **DynamicResolutionSolicitResp**.</span></span>  
  
10. <span data-ttu-id="9dabc-247">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**BindingKeyRoute**模型元素和**SendCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="9dabc-247">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BindingKeyRoute** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="9dabc-248">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="9dabc-248">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9dabc-249">单击**名称**属性，再然后键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-249">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="9dabc-250">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-250">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="9dabc-251">在**关闭负载增加**下拉列表中，展开**SendCNOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-251">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
11. <span data-ttu-id="9dabc-252">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-252">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9dabc-253">将从连接**BindingKeyRoute**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="9dabc-253">Drag a connection from the **BindingKeyRoute** model element to the **SendPortFilter** model element.</span></span>  
  
12. <span data-ttu-id="9dabc-254">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-254">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9dabc-255">将从连接**SendPortFilter**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="9dabc-255">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="9dabc-256">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="9dabc-256">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="9dabc-257">在 Visual Studio 中，右键单击的设计图面**NewBindingKeySearch**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-257">In Visual Studio, right-click the design surface of the **NewBindingKeySearch** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9dabc-258">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="9dabc-258">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="9dabc-259">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="9dabc-259">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="9dabc-260">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (NewBindingKeySearch.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="9dabc-260">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (NewBindingKeySearch.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="9dabc-261">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="9dabc-261">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="9dabc-262">打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="9dabc-262">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="9dabc-263">在路线测试客户端，在**Web 服务选项**组中，清除**使用 WCF 服务**框中，然后选择**双向服务**复选框。</span><span class="sxs-lookup"><span data-stu-id="9dabc-263">In the Itinerary Test Client, in the **Web Service Options** group, clear the **Use WCF Service** box and then select the **Two-Way Service** check box.</span></span>  
  
3.  <span data-ttu-id="9dabc-264">单击**负载路线**按钮。</span><span class="sxs-lookup"><span data-stu-id="9dabc-264">Click the **Load Itinerary** button.</span></span>  
  
4.  <span data-ttu-id="9dabc-265">在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="9dabc-265">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="9dabc-266">选择**NewBindingKeySearch.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="9dabc-266">Select **NewBindingKeySearch.xml**, and then click **Open** to load the itinerary.</span></span>  
  
5.  <span data-ttu-id="9dabc-267">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="9dabc-267">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
6.  <span data-ttu-id="9dabc-268">在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="9dabc-268">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
7.  <span data-ttu-id="9dabc-269">在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="9dabc-269">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="9dabc-270">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="9dabc-270">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
8.  <span data-ttu-id="9dabc-271">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="9dabc-271">Click the **Submit Request** button.</span></span> <span data-ttu-id="9dabc-272">在测试完成后，单击**确定**关闭出现的确认。</span><span class="sxs-lookup"><span data-stu-id="9dabc-272">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
9. <span data-ttu-id="9dabc-273">验证是否正确的响应消息出现在**结果**文本框**Itineray 测试客户端**。</span><span class="sxs-lookup"><span data-stu-id="9dabc-273">Verify that the correct response message appears in the **Result** text box of the **Itineray Test Client**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="9dabc-274">其他资源</span><span class="sxs-lookup"><span data-stu-id="9dabc-274">Additional Resources</span></span>  
 <span data-ttu-id="9dabc-275">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="9dabc-275">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="9dabc-276">如何：使用 UDDI 绑定密钥搜索解析服务终结点</span><span class="sxs-lookup"><span data-stu-id="9dabc-276">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [<span data-ttu-id="9dabc-277">如何：使用 UDDI 类别搜索解析服务终结点</span><span class="sxs-lookup"><span data-stu-id="9dabc-277">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [<span data-ttu-id="9dabc-278">开发活动</span><span class="sxs-lookup"><span data-stu-id="9dabc-278">Development Activities</span></span>](../esb-toolkit/development-activities.md)