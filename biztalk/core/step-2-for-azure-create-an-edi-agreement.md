---
title: 步骤 2 （适用于 Azure):创建 EDI 协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a8003697-4955-45c0-ba0b-e7c293a050a2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38150af85186ec811383e52a455bd5591edbbb02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392761"
---
# <a name="step-2-for-azure-create-an-edi-agreement"></a><span data-ttu-id="0bc92-102">步骤 2 （适用于 Azure):创建 EDI 协议</span><span class="sxs-lookup"><span data-stu-id="0bc92-102">Step 2 (For Azure): Create an EDI Agreement</span></span>
<span data-ttu-id="0bc92-103">在本主题中，您将创建使用 Azure BizTalk 门户可用作合作伙伴的一部分[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0bc92-103">In this topic, you will create partners using the Azure BizTalk portal available as part of the [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span></span> <span data-ttu-id="0bc92-104">此外将创建两个合作伙伴 （Northwind 和 Contoso） 来处理发送的 X12 销售订单消息通过 Contoso 向 Northwind 之间的协议。</span><span class="sxs-lookup"><span data-stu-id="0bc92-104">You will also create an agreement between the two partners (Northwind and Contoso) to process the X12 sales order message sent by Contoso to Northwind.</span></span>  
  
### <a name="to-create-partners"></a><span data-ttu-id="0bc92-105">若要创建合作伙伴</span><span class="sxs-lookup"><span data-stu-id="0bc92-105">To create partners</span></span>  
  
1.  <span data-ttu-id="0bc92-106">使用你的 Microsoft 帐户，登录到门户网站，网址[ http://go.microsoft.com/fwlink/p/?LinkId=235056 ](http://go.microsoft.com/fwlink/p/?LinkId=235056)。</span><span class="sxs-lookup"><span data-stu-id="0bc92-106">Using your Microsoft account, log into the portal at [http://go.microsoft.com/fwlink/p/?LinkId=235056](http://go.microsoft.com/fwlink/p/?LinkId=235056).</span></span>  
  
2.  <span data-ttu-id="0bc92-107">创建 Northwind 的合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0bc92-107">Create a partner for Northwind.</span></span> <span data-ttu-id="0bc92-108">遵循的步骤[合作伙伴和配置文件](http://msdn.microsoft.com/library/windowsazure/hh689791)创建合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0bc92-108">Follow the steps at [Partners and Profiles](http://msdn.microsoft.com/library/windowsazure/hh689791) to create a partner.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="0bc92-109">将为托管合作伙伴此合作伙伴标记。</span><span class="sxs-lookup"><span data-stu-id="0bc92-109">Mark this partner as the managed partner.</span></span>  
  
3.  <span data-ttu-id="0bc92-110">重复步骤来为 Contoso 创建合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0bc92-110">Repeat the steps to create a partner for Contoso.</span></span> <span data-ttu-id="0bc92-111">***不这样做***将为托管合作伙伴此合作伙伴标记。</span><span class="sxs-lookup"><span data-stu-id="0bc92-111">***Do not*** mark this partner as a managed partner.</span></span>  
  
### <a name="to-create-an-agreement"></a><span data-ttu-id="0bc92-112">若要创建协议</span><span class="sxs-lookup"><span data-stu-id="0bc92-112">To create an agreement</span></span>  
  
1.  <span data-ttu-id="0bc92-113">在门户的主页上，单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-113">In the portal home page, click **Agreements**.</span></span>  
  
2.  <span data-ttu-id="0bc92-114">上**协议**页上，单击**X12**选项卡上，如果您尚不在该选项卡上。然后单击**创建协议**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-114">On the **Agreements** page, click the **X12** tab if you are not already on that tab. Then click **Create Agreement**.</span></span>  
  
3.  <span data-ttu-id="0bc92-115">在中**新协议**页上，输入以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="0bc92-115">In the **New Agreement** page, enter the following details:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="0bc92-116">**字段**</span><span class="sxs-lookup"><span data-stu-id="0bc92-116">**Field**</span></span>|<span data-ttu-id="0bc92-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="0bc92-117">**Description**</span></span>|  
    |<span data-ttu-id="0bc92-118">“属性”</span><span class="sxs-lookup"><span data-stu-id="0bc92-118">Name</span></span>|<span data-ttu-id="0bc92-119">输入协议的名称。</span><span class="sxs-lookup"><span data-stu-id="0bc92-119">Enter a name for the agreement.</span></span> <span data-ttu-id="0bc92-120">对于本教程，将名称指定为`DemoAgreement`。</span><span class="sxs-lookup"><span data-stu-id="0bc92-120">For this tutorial, specify the name as `DemoAgreement`.</span></span><br /><br /> <span data-ttu-id="0bc92-121">**注意：** 这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="0bc92-121">**Note:** This is a mandatory field.</span></span> <span data-ttu-id="0bc92-122">协议名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0bc92-122">The name for the agreement must be unique.</span></span>|  
    |<span data-ttu-id="0bc92-123">Description</span><span class="sxs-lookup"><span data-stu-id="0bc92-123">Description</span></span>|<span data-ttu-id="0bc92-124">输入注释或协议的说明。</span><span class="sxs-lookup"><span data-stu-id="0bc92-124">Enter notes or a description for the agreement.</span></span>|  
    |<span data-ttu-id="0bc92-125">合作伙伴 1 配置文件 （托管）</span><span class="sxs-lookup"><span data-stu-id="0bc92-125">Partner 1 Profile (managed)</span></span>|<span data-ttu-id="0bc92-126">选择协议的托管的合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0bc92-126">Select the managed partner for the agreement.</span></span> <span data-ttu-id="0bc92-127">托管的合作伙伴是托管服务提供商合作伙伴，在协议部署期间为该合作伙伴部署管道。</span><span class="sxs-lookup"><span data-stu-id="0bc92-127">A managed partner is a partner managed by the service provider and the pipelines are deployed for that partner during agreement deployment.</span></span> <span data-ttu-id="0bc92-128">通常由服务提供商托管的合作伙伴配置为托管合作伙伴而企业合作伙伴未标记为托管合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0bc92-128">Typically partners managed by service provider are configured as a managed partner while the enterprise partners are not marked as managed partners.</span></span><br /><br /> <span data-ttu-id="0bc92-129">**注意：** 对于本教程中，托管的合作伙伴是**Northwind**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-129">**Note:** For this tutorial, the managed partner is **Northwind**.</span></span><br /><br /> <span data-ttu-id="0bc92-130">**注意：** 配置文件字段中显示的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="0bc92-130">**Note:** The default profile is displayed in the Profile field.</span></span> <span data-ttu-id="0bc92-131">选择所需的配置文件已配置的合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0bc92-131">Choose the desired profile which has been configured for the partner.</span></span>|  
    |<span data-ttu-id="0bc92-132">合作伙伴 2 配置文件</span><span class="sxs-lookup"><span data-stu-id="0bc92-132">Partner 2 Profile</span></span>|<span data-ttu-id="0bc92-133">选择合作伙伴协议 （不是托管的合作伙伴）。</span><span class="sxs-lookup"><span data-stu-id="0bc92-133">Select the partner for the agreement (who is not a managed partner).</span></span><br /><br /> <span data-ttu-id="0bc92-134">**注意：** 配置文件字段中显示的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="0bc92-134">**Note:** The default profile is displayed in the Profile field.</span></span> <span data-ttu-id="0bc92-135">选择所需的配置文件已配置的合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0bc92-135">Choose the desired profile which has been configured for the partner.</span></span>|  
  
     <span data-ttu-id="0bc92-136">**标识**</span><span class="sxs-lookup"><span data-stu-id="0bc92-136">**Identities**</span></span>  
  
    |<span data-ttu-id="0bc92-137">**字段**</span><span class="sxs-lookup"><span data-stu-id="0bc92-137">**Field**</span></span>|<span data-ttu-id="0bc92-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="0bc92-138">**Description**</span></span>|  
    |---------------|---------------------|  
    |<span data-ttu-id="0bc92-139">合作伙伴 1 ID 限定符</span><span class="sxs-lookup"><span data-stu-id="0bc92-139">Partner 1 ID Qualifier</span></span>|<span data-ttu-id="0bc92-140">选择向贸易合作伙伴提供唯一业务标识的身份验证限定符。</span><span class="sxs-lookup"><span data-stu-id="0bc92-140">Select an authenticating qualifier that provides unique business identities to the trading partners.</span></span> <span data-ttu-id="0bc92-141">对于本教程中，选择**ZZ-双方约定**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-141">For this tutorial, select **ZZ-Mutually Defined**.</span></span>|  
    |<span data-ttu-id="0bc92-142">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="0bc92-142">Value</span></span>|<span data-ttu-id="0bc92-143">输入`Northwind`。</span><span class="sxs-lookup"><span data-stu-id="0bc92-143">Enter `Northwind`.</span></span>|  
    |<span data-ttu-id="0bc92-144">合作伙伴 2 ID 限定符</span><span class="sxs-lookup"><span data-stu-id="0bc92-144">Partner 2 ID Qualifier</span></span>|<span data-ttu-id="0bc92-145">选择向贸易合作伙伴提供唯一业务标识的身份验证限定符。</span><span class="sxs-lookup"><span data-stu-id="0bc92-145">Select an authenticating qualifier that provides unique business identities to the trading partners.</span></span> <span data-ttu-id="0bc92-146">对于本教程中，选择**ZZ-双方约定**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-146">For this tutorial, select **ZZ-Mutually Defined**.</span></span>|  
    |<span data-ttu-id="0bc92-147">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="0bc92-147">Value</span></span>|<span data-ttu-id="0bc92-148">输入`Contoso`。</span><span class="sxs-lookup"><span data-stu-id="0bc92-148">Enter `Contoso`.</span></span>|  
  
     <span data-ttu-id="0bc92-149">**跟踪**</span><span class="sxs-lookup"><span data-stu-id="0bc92-149">**Tracking**</span></span>  
  
    |<span data-ttu-id="0bc92-150">**字段**</span><span class="sxs-lookup"><span data-stu-id="0bc92-150">**Field**</span></span>|<span data-ttu-id="0bc92-151">**说明**</span><span class="sxs-lookup"><span data-stu-id="0bc92-151">**Description**</span></span>|  
    |---------------|---------------------|  
    |<span data-ttu-id="0bc92-152">跟踪发送端消息属性</span><span class="sxs-lookup"><span data-stu-id="0bc92-152">Track Send side message properties</span></span>|<span data-ttu-id="0bc92-153">选中此项可向合作伙伴发送 EDI 消息时，存储消息属性。</span><span class="sxs-lookup"><span data-stu-id="0bc92-153">Check this to store the message properties when the EDI message is sent to the partner.</span></span> <span data-ttu-id="0bc92-154">存储后，您可以通过单击查询此数据**跟踪**Azure BizTalk 门户的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="0bc92-154">Once stored, you can query this data by clicking **Tracking** from the left pane on the Azure BizTalk Portal.</span></span><br /><br /> <span data-ttu-id="0bc92-155">启用时，您还可以通过检查来存储消息正文**跟踪发送端消息正文**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-155">When enabled, you can also store the message body by checking **Track Send side message body**.</span></span>|  
    |<span data-ttu-id="0bc92-156">跟踪接收端消息属性</span><span class="sxs-lookup"><span data-stu-id="0bc92-156">Track Receive side message properties</span></span>|<span data-ttu-id="0bc92-157">选中此项可从合作伙伴接收 EDI 消息时，存储消息属性。</span><span class="sxs-lookup"><span data-stu-id="0bc92-157">Check this to store the message properties when the EDI message is received from a partner.</span></span> <span data-ttu-id="0bc92-158">存储后，您可以通过单击查询此数据**跟踪**Azure BizTalk 门户的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="0bc92-158">Once stored, you can query this data by clicking **Tracking** from the left pane on the Azure BizTalk Portal.</span></span><br /><br /> <span data-ttu-id="0bc92-159">启用时，您还可以通过检查来存储消息正文**跟踪接收端消息正文**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-159">When enabled, you can also store the message body by checking **Track Receive side message body**.</span></span>|  
  
4.  <span data-ttu-id="0bc92-160">单击 **“继续”**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-160">Click **Continue**.</span></span>  
  
     <span data-ttu-id="0bc92-161">单击**继续**添加两个新选项卡，一个用于接收设置，另一个用于发送设置。</span><span class="sxs-lookup"><span data-stu-id="0bc92-161">Clicking **Continue** adds two new tabs, one for receive settings and the other for send settings.</span></span> <span data-ttu-id="0bc92-162">每个选项卡是两个合作伙伴，一个用于接收消息，另一个用于发送消息之间的单向协议。</span><span class="sxs-lookup"><span data-stu-id="0bc92-162">Each tab is for a one-way agreement between the two partners, one for receiving messages and the other for sending messages.</span></span>  
  
5.  <span data-ttu-id="0bc92-163">指定接收设置。</span><span class="sxs-lookup"><span data-stu-id="0bc92-163">Specify the receive settings.</span></span>  
  
    1.  <span data-ttu-id="0bc92-164">上**传输**页上，将**传输类型**为 HTTP。</span><span class="sxs-lookup"><span data-stu-id="0bc92-164">On the **Transport** page, set the **Transport type** to HTTP.</span></span>  
  
         <span data-ttu-id="0bc92-165">**终结点**字段显示的 URL，Contoso 必须向其发送 X12 销售订单消息。</span><span class="sxs-lookup"><span data-stu-id="0bc92-165">The **Endpoint** field shows the URL to which Contoso must send the X12 sales order message.</span></span>  
  
    2.  <span data-ttu-id="0bc92-166">上**协议**页上，指定以下值。</span><span class="sxs-lookup"><span data-stu-id="0bc92-166">On the **Protocol** page, specify the following values.</span></span>  
  
        1.  <span data-ttu-id="0bc92-167">如果需要，请为 ISA1、 ISA2、 ISA3 和 ISA4 指定值。</span><span class="sxs-lookup"><span data-stu-id="0bc92-167">If required, specify values for ISA1, ISA2, ISA3, and ISA4.</span></span>  
  
        2.  <span data-ttu-id="0bc92-168">下**确认**，选择**预期的 TA1**并**预期的 997**如果你想要接收的响应中生成技术和功能确认消息。</span><span class="sxs-lookup"><span data-stu-id="0bc92-168">Under **Acknowledgements**, select **TA1 expected** and **997 expected** if you want to generate technical and functional acknowledgements in response for receiving the message.</span></span>  
  
        3.  <span data-ttu-id="0bc92-169">下**架构**，单击**上载**按钮并上载**X12 840 架构**(从下载[ http://go.microsoft.com/fwlink/p/?LinkId=235057 ](http://go.microsoft.com/fwlink/p/?LinkId=235057)) 和**SalesOrder**架构 (你在中创建[若要创建 EDI 项目中的架构](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateSchema))。</span><span class="sxs-lookup"><span data-stu-id="0bc92-169">Under **Schemas**, click the **Upload** button and upload the **X12 840 schema** (you downloaded from [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)) and the **SalesOrder** schema (you created in [To create a schema within the EDI project](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateSchema)).</span></span>  
  
             <span data-ttu-id="0bc92-170">设置下的以下属性**架构**部分。</span><span class="sxs-lookup"><span data-stu-id="0bc92-170">Set the following properties under the **Schemas** section.</span></span>  
  
            |||  
            |-|-|  
            |<span data-ttu-id="0bc92-171">版本</span><span class="sxs-lookup"><span data-stu-id="0bc92-171">Version</span></span>|<span data-ttu-id="0bc92-172">00401</span><span class="sxs-lookup"><span data-stu-id="0bc92-172">00401</span></span>|  
            |<span data-ttu-id="0bc92-173">事务类型 (ST1)</span><span class="sxs-lookup"><span data-stu-id="0bc92-173">Transaction Type (ST1)</span></span>|<span data-ttu-id="0bc92-174">840</span><span class="sxs-lookup"><span data-stu-id="0bc92-174">840</span></span>|  
            |<span data-ttu-id="0bc92-175">架构</span><span class="sxs-lookup"><span data-stu-id="0bc92-175">Schema</span></span>|<span data-ttu-id="0bc92-176">/X12_00401_840.xsd</span><span class="sxs-lookup"><span data-stu-id="0bc92-176">/X12_00401_840.xsd</span></span>|  
  
    3.  <span data-ttu-id="0bc92-177">上**转换**页上，上载你在中创建的转换[创建 EDI 项目中的转换](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateTrfm)。</span><span class="sxs-lookup"><span data-stu-id="0bc92-177">On the **Transform** page, upload the transform you created in [To create a transform within the EDI project](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateTrfm).</span></span>  
  
         <span data-ttu-id="0bc92-178">下**选择你想要为此协议的一部分执行的映射**，选择 **/X12_00401_840.xsd**有关**架构**和 **/EDI840TOSALESORDER。TRFM**有关**转换文件名称**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-178">Under **Choose the maps you want to execute as part of this agreement**, choose **/X12_00401_840.xsd** for **Schemas** and **/EDI840TOSALESORDER.TRFM** for **Transform file name**.</span></span>  
  
    4.  <span data-ttu-id="0bc92-179">上**路由**页上，选择**路由到服务总线队列**并提供消息发送到队列的相对地址。</span><span class="sxs-lookup"><span data-stu-id="0bc92-179">On the **Route** page, select **Route to Service Bus Queue** and provide the relative address of the queue to which the message is sent.</span></span> <span data-ttu-id="0bc92-180">对于本教程中，指定相对地址作为`queueordersedi`，以便完整的 URL 是`https://<namespace>.servicebus.appfabriclabs.com/queueordersedi`。</span><span class="sxs-lookup"><span data-stu-id="0bc92-180">For this tutorial, specify the relative address as `queueordersedi` so that the complete URL is `https://<namespace>.servicebus.appfabriclabs.com/queueordersedi`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0bc92-181">本教程会覆盖在消息挂起设置中指定的失败的消息发送到终结点你的方案。</span><span class="sxs-lookup"><span data-stu-id="0bc92-181">This tutorial does not cover the scenario where a failed message is sent to the endpoint you specify in the Message Suspension Settings.</span></span> <span data-ttu-id="0bc92-182">但是，对于成功部署该协议，必须为此设置提供一个值。</span><span class="sxs-lookup"><span data-stu-id="0bc92-182">However, for successful deployment of the agreement, you must provide a value for this setting.</span></span> <span data-ttu-id="0bc92-183">您可以输入一个非空值。</span><span class="sxs-lookup"><span data-stu-id="0bc92-183">You can enter a non-empty value.</span></span>  
  
6.  <span data-ttu-id="0bc92-184">指定发送设置。</span><span class="sxs-lookup"><span data-stu-id="0bc92-184">Specify the send settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bc92-185">在本教程中所述的方案，不需要针对该协议的任何发送端配置。</span><span class="sxs-lookup"><span data-stu-id="0bc92-185">For the scenario described in this tutorial, you don’t need any send-side configuration for the agreement.</span></span> <span data-ttu-id="0bc92-186">但是，协议不能部署而无需指定发送设置中，即使它们是虚拟值。</span><span class="sxs-lookup"><span data-stu-id="0bc92-186">However, an agreement cannot be deployed without specifying the send settings, even if they are dummy values.</span></span> <span data-ttu-id="0bc92-187">而且，在**发送设置**选项卡上，您无需提供任何虚拟值**入站 URI**，**转换**，以及**批处理**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-187">Also, On the **Send Settings** tab, you don’t need to provide any dummy values for **Inbound URI**, **Transform**, and **Batching**.</span></span>  
  
    1.  <span data-ttu-id="0bc92-188">上**协议**页面上，在**架构**，单击**上载**按钮并上载架构代表 X12 840 消息。</span><span class="sxs-lookup"><span data-stu-id="0bc92-188">On the **Protocol** page, under **Schemas**, click the **Upload** button and upload the schema for the X12 840 message.</span></span>  
  
         <span data-ttu-id="0bc92-189">设置**版本**到**00401**，**事务类型**到**840**，并**架构**到**X12_00401_840**。</span><span class="sxs-lookup"><span data-stu-id="0bc92-189">Set the **Version** to **00401**, **Transaction Type** to **840**, and **Schema** to **X12_00401_840**.</span></span>  
  
    2.  <span data-ttu-id="0bc92-190">上**传输**页上，指定终结点向合作伙伴发送响应消息或确认。</span><span class="sxs-lookup"><span data-stu-id="0bc92-190">On the **Transport** page, specify the endpoints where the response messages or acknowledgements will be sent to the partners.</span></span> <span data-ttu-id="0bc92-191">您必须指定终结点每个成功处理的消息，以及由于处理失败的挂起的消息。</span><span class="sxs-lookup"><span data-stu-id="0bc92-191">You must specify an endpoint each for the messages that are processed successfully as well as the messages that get suspended due to a failure in processing.</span></span>  
  
7.  <span data-ttu-id="0bc92-192">单击**部署协议**以部署协议。</span><span class="sxs-lookup"><span data-stu-id="0bc92-192">Click **Deploy Agreement** to deploy the agreement.</span></span> <span data-ttu-id="0bc92-193">在中显示的 URL 现在部署协议**传输**页**接收设置**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0bc92-193">The agreement is now deployed at the URL that was displayed in the **Transport** page of the **Receive Settings** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc92-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bc92-194">See Also</span></span>  
 [<span data-ttu-id="0bc92-195">教程 4：创建混合应用程序使用 BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bc92-195">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)