---
title: 如何： 将服务发布到 UDDI 3.0 注册表 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c3bd0ed-e5f1-43eb-98d1-e3247a565ba2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5ab38da9c78831b319d8c64e789b442fb6eef5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008014"
---
# <a name="how-to-publish-a-service-to-the-uddi-30-registry"></a><span data-ttu-id="2fed3-102">如何： 将服务发布到 UDDI 3.0 注册表</span><span class="sxs-lookup"><span data-stu-id="2fed3-102">How to: Publish a Service to the UDDI 3.0 Registry</span></span>
## <a name="goal"></a><span data-ttu-id="2fed3-103">目的</span><span class="sxs-lookup"><span data-stu-id="2fed3-103">Goal</span></span>  
 <span data-ttu-id="2fed3-104">本部分演示如何使用 UDDI 服务站点发布内就能解决从为路由 ESB 消息路线的 Web 服务终结点。</span><span class="sxs-lookup"><span data-stu-id="2fed3-104">This section demonstrates how to use the UDDI Service site to publish a Web service endpoint that can be resolved from within an itinerary for the purpose of routing an ESB message.</span></span> <span data-ttu-id="2fed3-105">将复制现有 PurchaseOrderSubmitOrderService 服务目前发布到注册表。</span><span class="sxs-lookup"><span data-stu-id="2fed3-105">You will duplicate the existing PurchaseOrderSubmitOrderService service presently published to the registry.</span></span>  

 <span data-ttu-id="2fed3-106">在本操作指南主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2fed3-106">In this How-to topic, you will complete the following steps:</span></span>  

-   <span data-ttu-id="2fed3-107">将服务发布到通用描述、 发现和集成 (UDDI) 3 注册表使用 UDDI 发布者工具。</span><span class="sxs-lookup"><span data-stu-id="2fed3-107">Publish a service to the Universal Description, Discovery, and Integration (UDDI) 3 registry using the UDDI Publisher tool.</span></span>  

-   <span data-ttu-id="2fed3-108">测试使用路线传送名单解析服务终结点使用 UDDI3 解析程序服务发布。</span><span class="sxs-lookup"><span data-stu-id="2fed3-108">Test the service publication using an itinerary routing slip that resolves the service endpoint using a UDDI3 resolver.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="2fed3-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="2fed3-109">Prerequisites</span></span>  
 <span data-ttu-id="2fed3-110">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)和 UDDI 发布者工具 （你可以安装在 %esb 安装 Folder%\Bin\ 的执行Microsoft.Practices.ESB.UDDIPublisher.exe)。</span><span class="sxs-lookup"><span data-stu-id="2fed3-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) and the execution of the UDDI Publisher tool (you can install it at %ESB Install Folder%\Bin\Microsoft.Practices.ESB.UDDIPublisher.exe).</span></span>  

## <a name="steps"></a><span data-ttu-id="2fed3-111">步骤</span><span class="sxs-lookup"><span data-stu-id="2fed3-111">Steps</span></span>  

#### <a name="to-create-the-newposervice-in-the-uddi-registry"></a><span data-ttu-id="2fed3-112">若要在 UDDI 注册表中创建 NewPOService</span><span class="sxs-lookup"><span data-stu-id="2fed3-112">To create the NewPOService in the UDDI registry</span></span>  

1.  <span data-ttu-id="2fed3-113">在 Internet Explorer 中，浏览到 UDDI 服务站点 (默认情况下，此 URL 是 http://localhost/uddi) 。</span><span class="sxs-lookup"><span data-stu-id="2fed3-113">In Internet Explorer, browse to the UDDI Service site (by default, the URL for this is http://localhost/uddi).</span></span>  

2.  <span data-ttu-id="2fed3-114">上**uddi 服务**页上，单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-114">On the **uddi Services** page, click **Publish**.</span></span>  

3.  <span data-ttu-id="2fed3-115">在发布窗格中，右键单击**Microsoft.Practices.ESB**，然后单击**添加的服务**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-115">In the Publish pane, right-click **Microsoft.Practices.ESB**, and then click **Add Service**.</span></span>  

4.  <span data-ttu-id="2fed3-116">在以下页上，选择**指定要使用的密钥**，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-116">On the following page, select **Specify a key to use**, and then click **Continue**.</span></span>  

5.  <span data-ttu-id="2fed3-117">在以下页上，单击**esb**键分区。</span><span class="sxs-lookup"><span data-stu-id="2fed3-117">On the following page, click the **esb** key partition.</span></span> <span data-ttu-id="2fed3-118">在中**密钥后缀**框中，键入**newposervice**，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-118">In the **Key Suffix** box, type **newposervice**, and then click **Continue**.</span></span>  

6.  <span data-ttu-id="2fed3-119">在以下页上下, 一步 (**新的服务名称**)，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-119">On the following page, next to (**New Service Name**), click **Edit**.</span></span> <span data-ttu-id="2fed3-120">将服务命名**NewPOService**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-120">Name the service **NewPOService**, and then click **Update**.</span></span>  

7.  <span data-ttu-id="2fed3-121">单击**添加描述**，键入服务的说明 (例如，**示例服务**)，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-121">Click **Add Description**, type a description for the service (for example, **Sample Service**), and then click **Update**.</span></span>  

#### <a name="to-add-a-binding-for-the-newposervice"></a><span data-ttu-id="2fed3-122">若要将绑定添加为 NewPOService</span><span class="sxs-lookup"><span data-stu-id="2fed3-122">To add a binding for the NewPOService</span></span>  

1.  <span data-ttu-id="2fed3-123">单击**绑定**选项卡，然后依次**添加绑定**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-123">Click the **Bindings** tab, and then click **Add Binding**.</span></span>  

2.  <span data-ttu-id="2fed3-124">选择**指定要使用的密钥**，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-124">Select **Specify a key to use**, and then click **Continue**.</span></span>  

3.  <span data-ttu-id="2fed3-125">在以下页上，单击**esb**键分区。</span><span class="sxs-lookup"><span data-stu-id="2fed3-125">On the following page, click the **esb** key partition.</span></span> <span data-ttu-id="2fed3-126">在中**密钥后缀**框中，键入**newposervicebinding**，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-126">In the **Key Suffix** box, type **newposervicebinding**, and then click **Continue**.</span></span>  

4.  <span data-ttu-id="2fed3-127">下**接入点**，单击**编辑**，然后完成以下：</span><span class="sxs-lookup"><span data-stu-id="2fed3-127">Under **Access Point**, click **Edit**, and then complete the following:</span></span>  

    1.  <span data-ttu-id="2fed3-128">在中**接入点**框中，键入**http://localhost/ESB.CanadianServices/SubmitPOService.asmx**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-128">In the **Access Point** box, type **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span></span>  

    2.  <span data-ttu-id="2fed3-129">在中**使用类型**下拉列表中，单击**终结点**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-129">In the **Use Type** drop-down list, click **endpoint**, and then click **Update**.</span></span>  

#### <a name="to-configure-the-binding-instance-information"></a><span data-ttu-id="2fed3-130">若要配置的绑定实例信息</span><span class="sxs-lookup"><span data-stu-id="2fed3-130">To configure the binding instance information</span></span>  

1. <span data-ttu-id="2fed3-131">单击**实例信息**选项卡，然后依次**添加实例信息**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-131">Click the **Instance Info** tab, and then click **Add Instance Info**.</span></span>  

2. <span data-ttu-id="2fed3-132">在中**tModel 名称中包含搜索**框中，键入 **%esb%** ，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-132">In the **Search for tModel names containing** box, type **%esb%** and then click **Search**.</span></span>  

3. <span data-ttu-id="2fed3-133">找到并单击**tModel**有关**transporttype**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-133">Locate and click the **tModel** for **transporttype**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="2fed3-134">若要完成此过程中的剩余步骤，您可能需要第 1 页和第 2 页之间进行更改。</span><span class="sxs-lookup"><span data-stu-id="2fed3-134">To complete the remaining steps in this procedure, you may be required to change between page 1 and page 2.</span></span>  

4. <span data-ttu-id="2fed3-135">在中**说明**部分中，单击**添加说明**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-135">In the **Descriptions** section, click **Add Description**.</span></span>  

5. <span data-ttu-id="2fed3-136">在中**描述**框中，键入**ESB 路线使用的传输类型**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-136">In the **Description** box, type **Transport Type for ESB Itinerary Use**, and then click **Update**.</span></span>  

6. <span data-ttu-id="2fed3-137">单击**实例的详细信息**选项卡，然后依次**编辑**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-137">Click the **Instance Details** tab, and then click **Edit**.</span></span>  

7. <span data-ttu-id="2fed3-138">在中**实例参数**框中，键入**Wcf-basichttp**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-138">In the **Instance Parameters** box, type **WCF-BasicHttp**, and then click **Update**.</span></span>  

8. <span data-ttu-id="2fed3-139">在中**说明**部分中，单击**添加说明**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-139">In the **Descriptions** section, click **Add Description**.</span></span>  

9. <span data-ttu-id="2fed3-140">在中**描述**框中，键入**WCF 基本 HTTP 传输**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-140">In the **Description** box, type **WCF Basic HTTP Transport**, and then click **Update**.</span></span>  

10. <span data-ttu-id="2fed3-141">在发布窗格下**NewPOService**，单击**http://localhost/esb.canadianservices/submitposervice.asmx**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-141">In the Publish pane, under **NewPOService**, click **http://localhost/esb.canadianservices/submitposervice.asmx**.</span></span>  

11. <span data-ttu-id="2fed3-142">上**实例信息**选项卡上，单击**添加实例信息**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-142">On the **Instance Info** tab, click **Add Instance Info**.</span></span>  

12. <span data-ttu-id="2fed3-143">使用前面所述的步骤，添加以下实例信息，根据下表中显示的值。</span><span class="sxs-lookup"><span data-stu-id="2fed3-143">Using the steps described earlier, add the following instance information, according to the values shown in the following table.</span></span>  


    |                           <span data-ttu-id="2fed3-144">tModel</span><span class="sxs-lookup"><span data-stu-id="2fed3-144">tModel</span></span>                           |       <span data-ttu-id="2fed3-145">Description</span><span class="sxs-lookup"><span data-stu-id="2fed3-145">Description</span></span>        |                          <span data-ttu-id="2fed3-146">参数</span><span class="sxs-lookup"><span data-stu-id="2fed3-146">Parameter</span></span>                           |         <span data-ttu-id="2fed3-147">参数说明</span><span class="sxs-lookup"><span data-stu-id="2fed3-147">Parameter description</span></span>          |
    |------------------------------------------------------------|--------------------------|--------------------------------------------------------------|----------------------------------------|
    | <span data-ttu-id="2fed3-148">microsoft-com:esb:runtimeresolution:messageexchangepattern</span><span class="sxs-lookup"><span data-stu-id="2fed3-148">microsoft-com:esb:runtimeresolution:messageexchangepattern</span></span> | <span data-ttu-id="2fed3-149">消息交换模式</span><span class="sxs-lookup"><span data-stu-id="2fed3-149">Message Exchange Pattern</span></span> |                           <span data-ttu-id="2fed3-150">双向</span><span class="sxs-lookup"><span data-stu-id="2fed3-150">Two-Way</span></span>                            |           <span data-ttu-id="2fed3-151">双向操作</span><span class="sxs-lookup"><span data-stu-id="2fed3-151">Two-way operation</span></span>            |
    |      <span data-ttu-id="2fed3-152">microsoft-com:esb:runtimeresolution:cachetimeout</span><span class="sxs-lookup"><span data-stu-id="2fed3-152">microsoft-com:esb:runtimeresolution:cachetimeout</span></span>      |      <span data-ttu-id="2fed3-153">缓存超时</span><span class="sxs-lookup"><span data-stu-id="2fed3-153">Cache Timeout</span></span>       |                              <span data-ttu-id="2fed3-154">-1</span><span class="sxs-lookup"><span data-stu-id="2fed3-154">-1</span></span>                              |           <span data-ttu-id="2fed3-155">当前已禁用</span><span class="sxs-lookup"><span data-stu-id="2fed3-155">Currently disabled</span></span>           |
    |     <span data-ttu-id="2fed3-156">microsoft-com:esb:runtimeresolution:jaxrpcresponse</span><span class="sxs-lookup"><span data-stu-id="2fed3-156">microsoft-com:esb:runtimeresolution:jaxrpcresponse</span></span>     |      <span data-ttu-id="2fed3-157">JaxRpcResponse</span><span class="sxs-lookup"><span data-stu-id="2fed3-157">JaxRpcResponse</span></span>      |                            <span data-ttu-id="2fed3-158">false</span><span class="sxs-lookup"><span data-stu-id="2fed3-158">false</span></span>                             |                                        |
    |         <span data-ttu-id="2fed3-159">microsoft-com:esb:runtimeresolution:action</span><span class="sxs-lookup"><span data-stu-id="2fed3-159">microsoft-com:esb:runtimeresolution:action</span></span>         |      <span data-ttu-id="2fed3-160">服务操作</span><span class="sxs-lookup"><span data-stu-id="2fed3-160">Service Action</span></span>      |                         <span data-ttu-id="2fed3-161">submitOrder</span><span class="sxs-lookup"><span data-stu-id="2fed3-161">submitOrder</span></span>                          | <span data-ttu-id="2fed3-162">指定要调用的服务方法</span><span class="sxs-lookup"><span data-stu-id="2fed3-162">Specifies the service method to invoke</span></span> |
    |    <span data-ttu-id="2fed3-163">microsoft-com:esb:runtimeresolution:targetnamespace</span><span class="sxs-lookup"><span data-stu-id="2fed3-163">microsoft-com:esb:runtimeresolution:targetnamespace</span></span>     |    <span data-ttu-id="2fed3-164">服务 Namespace</span><span class="sxs-lookup"><span data-stu-id="2fed3-164">Service Namespace</span></span>     | http://globalbank.esb.dynamicresolution.com/canadianservices |            <span data-ttu-id="2fed3-165">目标命名空间</span><span class="sxs-lookup"><span data-stu-id="2fed3-165">Target namespace</span></span>            |

#### <a name="to-configure-the-binding-categorization"></a><span data-ttu-id="2fed3-166">若要配置绑定分类</span><span class="sxs-lookup"><span data-stu-id="2fed3-166">To configure the binding categorization</span></span>  

1.  <span data-ttu-id="2fed3-167">在发布窗格下**NewPOService**，单击**http://localhost/esb.canadianservices/submitposervice.asmx**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-167">In the Publish pane, under **NewPOService**, click **http://localhost/esb.canadianservices/submitposervice.asmx**.</span></span>  

2.  <span data-ttu-id="2fed3-168">上**类别**选项卡上，单击**添加自定义类别**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-168">On the **Categories** tab, click **Add Custom Category**.</span></span>  

3.  <span data-ttu-id="2fed3-169">在中**搜索**框中，键入 **%esb%** ，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-169">In the **Search** box, type **%esb%** and then click **Search**.</span></span>  

4.  <span data-ttu-id="2fed3-170">找到并单击**microsoft-com:esb:runtimeresolution:biztalkapplication** tModel。</span><span class="sxs-lookup"><span data-stu-id="2fed3-170">Locate and click the **microsoft-com:esb:runtimeresolution:biztalkapplication** tModel.</span></span>  

5.  <span data-ttu-id="2fed3-171">在中**Key-name**框中，键入**BizTalk 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-171">In the **Key Name** box, type **BizTalk Application**.</span></span>  

6.  <span data-ttu-id="2fed3-172">在中**键值**框中，键入**Microsoft.Practices.ESB**，然后单击**添加类别**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-172">In the **Key Value** box, type **Microsoft.Practices.ESB**, and then click **Add Category**.</span></span>  

7.  <span data-ttu-id="2fed3-173">使用前面所述的步骤，添加以下自定义类别中，根据下表中显示的值。</span><span class="sxs-lookup"><span data-stu-id="2fed3-173">Using the steps described earlier, add the following custom categories, according to the values shown in the following table.</span></span>  

    |<span data-ttu-id="2fed3-174">tModel</span><span class="sxs-lookup"><span data-stu-id="2fed3-174">tModel</span></span>|<span data-ttu-id="2fed3-175">项名</span><span class="sxs-lookup"><span data-stu-id="2fed3-175">Key name</span></span>|<span data-ttu-id="2fed3-176">密钥值</span><span class="sxs-lookup"><span data-stu-id="2fed3-176">Key value</span></span>|  
    |------------|--------------|---------------|  
    |<span data-ttu-id="2fed3-177">microsoft-com:esb:runtimeresolution:portname</span><span class="sxs-lookup"><span data-stu-id="2fed3-177">microsoft-com:esb:runtimeresolution:portname</span></span>|<span data-ttu-id="2fed3-178">端口名称</span><span class="sxs-lookup"><span data-stu-id="2fed3-178">Port Name</span></span>|<span data-ttu-id="2fed3-179">NewPOService</span><span class="sxs-lookup"><span data-stu-id="2fed3-179">NewPOService</span></span>|  
    |<span data-ttu-id="2fed3-180">microsoft-com:esb:runtimeresolution:transporttype</span><span class="sxs-lookup"><span data-stu-id="2fed3-180">microsoft-com:esb:runtimeresolution:transporttype</span></span>|<span data-ttu-id="2fed3-181">传输类型</span><span class="sxs-lookup"><span data-stu-id="2fed3-181">Transport Type</span></span>|<span data-ttu-id="2fed3-182">WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="2fed3-182">WCF-BasicHttp</span></span>|  

#### <a name="to-locate-the-service-in-the-uddi-registry"></a><span data-ttu-id="2fed3-183">若要在 UDDI 注册表中找到的服务</span><span class="sxs-lookup"><span data-stu-id="2fed3-183">To locate the service in the UDDI registry</span></span>  

1.  <span data-ttu-id="2fed3-184">在 Internet Explorer 中，在**uddi 服务**页上，单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-184">In Internet Explorer, on the **uddi Services** page, click **Search**.</span></span>  

2.  <span data-ttu-id="2fed3-185">单击**Services**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2fed3-185">Click the **Services** tab.</span></span>  

3.  <span data-ttu-id="2fed3-186">在中**服务名称**框中，键入 **%PO%**，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-186">In the **Service Name** box, type **%PO%**, and then click **Search**.</span></span>  

4.  <span data-ttu-id="2fed3-187">在中**搜索**窗格中，在**结果**选项卡上，单击**NewPOService**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-187">In the **Search** pane, on the **Results** tab, click **NewPOService**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="2fed3-188">这会确认该服务已成功发布到注册表。</span><span class="sxs-lookup"><span data-stu-id="2fed3-188">This confirms the service was successfully published to the registry.</span></span>  

#### <a name="to-create-an-itinerary-model-to-test-the-uddi-service-publication"></a><span data-ttu-id="2fed3-189">若要创建路线模型来测试 UDDI 服务发布</span><span class="sxs-lookup"><span data-stu-id="2fed3-189">To create an itinerary model to test the UDDI service publication</span></span>  

1.  <span data-ttu-id="2fed3-190">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="2fed3-190">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  

2.  <span data-ttu-id="2fed3-191">在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-191">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  

3.  <span data-ttu-id="2fed3-192">在中**添加新项**对话框中**名称**框中，键入**NewBindingKeySearch**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-192">In the **Add New Item** dialog box, in the **Name** box, type **NewBindingKeySearch**, and then click **Add**.</span></span>  

#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="2fed3-193">若要配置的路线属性</span><span class="sxs-lookup"><span data-stu-id="2fed3-193">To configure the properties of the itinerary</span></span>  

1.  <span data-ttu-id="2fed3-194">在 Visual Studio 中，单击的设计图面**NewBindingKeySearch.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-194">In Visual Studio, click the design surface of **NewBindingKeySearch.itinerary**.</span></span> <span data-ttu-id="2fed3-195">在中**NewBindingKeySearch**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="2fed3-195">In the **NewBindingKeySearch** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="2fed3-196">在中**是请求响应**下拉列表中，单击**True**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-196">In the **Is Request Response** drop-down list, click **True**.</span></span>  

    2.  <span data-ttu-id="2fed3-197">在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-197">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  

    3.  <span data-ttu-id="2fed3-198">在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="2fed3-198">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  

    4.  <span data-ttu-id="2fed3-199">在中**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\NewBindingKeySearch**中**文件名**框中，然后依次**保存**.</span><span class="sxs-lookup"><span data-stu-id="2fed3-199">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\NewBindingKeySearch** in the **File name** box, and then click **Save**.</span></span>  

        > [!NOTE]
        >  <span data-ttu-id="2fed3-200">此步骤中，可将路线以 XML 形式导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="2fed3-200">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="2fed3-201">通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。</span><span class="sxs-lookup"><span data-stu-id="2fed3-201">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="2fed3-202">您将完成此过程更高版本的本操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="2fed3-202">You will complete this process later in this How-to topic.</span></span>  

#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="2fed3-203">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="2fed3-203">To define the structure of the itinerary</span></span>  

1.  <span data-ttu-id="2fed3-204">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="2fed3-204">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="2fed3-205">在中**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="2fed3-205">In the **OnRamp1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="2fed3-206">单击**名称**属性，并键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-206">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  

    2.  <span data-ttu-id="2fed3-207">在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-207">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  

    3.  <span data-ttu-id="2fed3-208">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-208">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  

    4.  <span data-ttu-id="2fed3-209">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary.Response**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-209">In the **Receive Port** drop-down list, click **OnRamp.Itinerary.Response**.</span></span>  

2.  <span data-ttu-id="2fed3-210">从工具箱拖动**路线服务**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="2fed3-210">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="2fed3-211">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="2fed3-211">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="2fed3-212">单击**名称**属性，并键入**TransformNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-212">Click the **Name** property, and then type **TransformNAOrder**.</span></span>  

    2.  <span data-ttu-id="2fed3-213">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-213">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  

    3.  <span data-ttu-id="2fed3-214">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-214">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  

    4.  <span data-ttu-id="2fed3-215">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-215">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  

3.  <span data-ttu-id="2fed3-216">右键单击**冲突解决程序**系列**TransformNAOrder**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-216">Right-click the **Resolver** collection of the **TransformNAOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="2fed3-217">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="2fed3-217">In the **Resolver1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="2fed3-218">单击**名称**属性，并键入**NAOrder_to_CNOrder**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-218">Click the **Name** property, and then type **NAOrder_to_CNOrder**.</span></span>  

    2.  <span data-ttu-id="2fed3-219">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-219">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  

    3.  <span data-ttu-id="2fed3-220">在中**转换的类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-220">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  

4.  <span data-ttu-id="2fed3-221">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-221">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="2fed3-222">将从连接**ReceiveNAOrder**到模型元素**TransformNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="2fed3-222">Drag a connection from the **ReceiveNAOrder** model element to the **TransformNAOrder** model element.</span></span>  

5.  <span data-ttu-id="2fed3-223">从工具箱拖动**路线服务**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="2fed3-223">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="2fed3-224">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="2fed3-224">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="2fed3-225">单击**名称**属性，并键入**BindingKeyRoute**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-225">Click the **Name** property, and then type **BindingKeyRoute**.</span></span>  

    2.  <span data-ttu-id="2fed3-226">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-226">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  

    3.  <span data-ttu-id="2fed3-227">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-227">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  

    4.  <span data-ttu-id="2fed3-228">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-228">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  

6.  <span data-ttu-id="2fed3-229">右键单击**冲突解决程序**系列**BindingKeyRoute**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-229">Right-click the **Resolver** collection of the **BindingKeyRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="2fed3-230">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="2fed3-230">In the **Resolver1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="2fed3-231">单击**名称**属性，并键入**BindingKeySearch**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-231">Click the **Name** property, and then type **BindingKeySearch**.</span></span>  

    2.  <span data-ttu-id="2fed3-232">在中**解析程序实现**下拉列表中，单击**Uddi3 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-232">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  

    3.  <span data-ttu-id="2fed3-233">在中**冲突解决程序名字对象**下拉列表中，单击**UDDI3**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-233">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  

    4.  <span data-ttu-id="2fed3-234">单击**绑定键**属性，并键入**uddi:esb:newposervicebinding**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-234">Click the **Binding key** property, and then type **uddi:esb:newposervicebinding**.</span></span> <span data-ttu-id="2fed3-235">若要查找的键的值，请单击 http://localhost/ESB.CanadianServices/SubmitPOService.asmx UDDI，在服务，然后单击更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="2fed3-235">To find the key value, click the http://localhost/ESB.CanadianServices/SubmitPOService.asmx service in UDDI, and then click More Details.</span></span>  

7.  <span data-ttu-id="2fed3-236">右键单击**BindingKeySearch**冲突解决程序，并单击**测试解析程序配置**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-236">Right-click the **BindingKeySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="2fed3-237">验证显示在输出窗口中的输出。</span><span class="sxs-lookup"><span data-stu-id="2fed3-237">Verify the output displayed in the Output window.</span></span>  

8.  <span data-ttu-id="2fed3-238">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-238">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="2fed3-239">将从连接**TransformNAOrder**到模型元素**BindingKeyRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="2fed3-239">Drag a connection from the **TransformNAOrder** model element to the **BindingKeyRoute** model element.</span></span>  

9. <span data-ttu-id="2fed3-240">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**BindingKeyRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="2fed3-240">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BindingKeyRoute** model element.</span></span> <span data-ttu-id="2fed3-241">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="2fed3-241">In the **OffRamp1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="2fed3-242">单击**名称**属性，并键入**SendCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-242">Click the **Name** property, and then type **SendCNOrder**.</span></span>  

    2.  <span data-ttu-id="2fed3-243">在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-243">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  

    3.  <span data-ttu-id="2fed3-244">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-244">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  

    4.  <span data-ttu-id="2fed3-245">在中**发送端口**下拉列表中，单击**DynamicResolutionSolicitResp**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-245">In the **Send Port** drop-down list, click **DynamicResolutionSolicitResp**.</span></span>  

10. <span data-ttu-id="2fed3-246">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**BindingKeyRoute**模型元素和**SendCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="2fed3-246">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BindingKeyRoute** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="2fed3-247">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="2fed3-247">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  

    1.  <span data-ttu-id="2fed3-248">单击**名称**属性，并键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-248">Click the **Name** property, and then type **SendPortFilter**.</span></span>  

    2.  <span data-ttu-id="2fed3-249">在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-249">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  

    3.  <span data-ttu-id="2fed3-250">在中**关闭负载增加**下拉列表中，展开**SendCNOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-250">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  

11. <span data-ttu-id="2fed3-251">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-251">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="2fed3-252">将从连接**BindingKeyRoute**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="2fed3-252">Drag a connection from the **BindingKeyRoute** model element to the **SendPortFilter** model element.</span></span>  

12. <span data-ttu-id="2fed3-253">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-253">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="2fed3-254">将从连接**SendPortFilter**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="2fed3-254">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  

#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="2fed3-255">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="2fed3-255">To export the model for use with the Itinerary Test Client</span></span>  

1.  <span data-ttu-id="2fed3-256">在 Visual Studio 中，右键单击设计图面的**NewBindingKeySearch**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-256">In Visual Studio, right-click the design surface of the **NewBindingKeySearch** itinerary, and then click **Export Model**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="2fed3-257">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="2fed3-257">The XML version of the itinerary opens in Visual Studio.</span></span>  

2.  <span data-ttu-id="2fed3-258">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="2fed3-258">Save all project artifacts.</span></span>  

3.  <span data-ttu-id="2fed3-259">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (NewBindingKeySearch.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="2fed3-259">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (NewBindingKeySearch.xml).</span></span>  

#### <a name="to-test-the-itinerary"></a><span data-ttu-id="2fed3-260">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="2fed3-260">To test the itinerary</span></span>  

1.  <span data-ttu-id="2fed3-261">打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="2fed3-261">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  

2.  <span data-ttu-id="2fed3-262">在路线测试客户端，在**Web 服务选项**组中，清除**使用 WCF 服务**框，然后选择**双向服务**复选框。</span><span class="sxs-lookup"><span data-stu-id="2fed3-262">In the Itinerary Test Client, in the **Web Service Options** group, clear the **Use WCF Service** box and then select the **Two-Way Service** check box.</span></span>  

3.  <span data-ttu-id="2fed3-263">单击**负载路线**按钮。</span><span class="sxs-lookup"><span data-stu-id="2fed3-263">Click the **Load Itinerary** button.</span></span>  

4.  <span data-ttu-id="2fed3-264">在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="2fed3-264">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="2fed3-265">选择**NewBindingKeySearch.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="2fed3-265">Select **NewBindingKeySearch.xml**, and then click **Open** to load the itinerary.</span></span>  

5.  <span data-ttu-id="2fed3-266">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="2fed3-266">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  

6.  <span data-ttu-id="2fed3-267">在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="2fed3-267">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  

7.  <span data-ttu-id="2fed3-268">在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="2fed3-268">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="2fed3-269">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="2fed3-269">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  

8.  <span data-ttu-id="2fed3-270">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="2fed3-270">Click the **Submit Request** button.</span></span> <span data-ttu-id="2fed3-271">测试完成后，单击**确定**若要消除出现的确认。</span><span class="sxs-lookup"><span data-stu-id="2fed3-271">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  

9. <span data-ttu-id="2fed3-272">验证是否正确响应消息出现在**结果**的文本框中**Itineray 测试客户端**。</span><span class="sxs-lookup"><span data-stu-id="2fed3-272">Verify that the correct response message appears in the **Result** text box of the **Itineray Test Client**.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="2fed3-273">其他资源</span><span class="sxs-lookup"><span data-stu-id="2fed3-273">Additional Resources</span></span>  
 <span data-ttu-id="2fed3-274">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="2fed3-274">For more information, see the following related topics:</span></span>  

-   [<span data-ttu-id="2fed3-275">如何：使用 UDDI 绑定密钥搜索解析服务终结点</span><span class="sxs-lookup"><span data-stu-id="2fed3-275">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  

-   [<span data-ttu-id="2fed3-276">如何：使用 UDDI 类别搜索解析服务终结点</span><span class="sxs-lookup"><span data-stu-id="2fed3-276">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  

-   [<span data-ttu-id="2fed3-277">开发活动</span><span class="sxs-lookup"><span data-stu-id="2fed3-277">Development Activities</span></span>](../esb-toolkit/development-activities.md)