---
title: "步骤 2： 配置 WCF 自定义单向发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way send port, configuring
- migration
ms.assetid: ae13222e-42e7-45a7-9b2a-0a6779b21736
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aab14799076d3f774130b357ab90c5ed5335f4a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-configure-a-wcf-custom-one-way-send-port"></a><span data-ttu-id="b72a6-102">步骤 2： 配置 WCF 自定义单向发送端口</span><span class="sxs-lookup"><span data-stu-id="b72a6-102">Step 2: Configure a WCF-Custom One-way Send Port</span></span>
<span data-ttu-id="b72a6-103">![步骤 2 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="b72a6-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="b72a6-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="b72a6-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="b72a6-105">**目标：**在此步骤中，配置将平面文件 IDOC 发送到 SAP 系统的 WCF 自定义端口。</span><span class="sxs-lookup"><span data-stu-id="b72a6-105">**Objective:** In this step, you configure a WCF-Custom port to send the flat-file IDOC to an SAP system.</span></span> <span data-ttu-id="b72a6-106">配置端口之后, 你将配置 BizTalk 应用程序使用 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="b72a6-106">After configuring the port, you configure the BizTalk application to use the WCF-Custom send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b72a6-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="b72a6-107">Prerequisites</span></span>  
 <span data-ttu-id="b72a6-108">你必须已生成并部署你的 vPrev BizTalk 项目，以将 Idoc 发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="b72a6-108">You must have built and deployed your vPrev BizTalk project to send IDOCs to an SAP system.</span></span>  
  
### <a name="to-configure-a-wcf-custom-one-way-send-port"></a><span data-ttu-id="b72a6-109">若要配置 WCF 自定义单向发送端口</span><span class="sxs-lookup"><span data-stu-id="b72a6-109">To configure a WCF-Custom one-way send port</span></span>  
  
1.  <span data-ttu-id="b72a6-110">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b72a6-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="b72a6-111">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="b72a6-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="b72a6-112">展开你要在其下创建发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b72a6-112">Expand the application under which you want to create the send port.</span></span>  
  
4.  <span data-ttu-id="b72a6-113">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b72a6-113">Right-click **Send Ports**, point to **New**, and click **Static One-way Send Port**.</span></span>  
  
5.  <span data-ttu-id="b72a6-114">在**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="b72a6-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="b72a6-115">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b72a6-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="b72a6-116">在**WCF 自定义传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b72a6-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="b72a6-117">单击**常规**选项卡上，然后在**地址 (URI)**字段中，指定连接 URI，将消息发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="b72a6-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI to send messages to the SAP system.</span></span> <span data-ttu-id="b72a6-118">有关连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="b72a6-118">For more information about the connection URI, see [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
         <span data-ttu-id="b72a6-119">![连接在发送端口中指定的 URI](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")</span><span class="sxs-lookup"><span data-stu-id="b72a6-119">![Connection URI specified in the send port](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")</span></span>  
  
    2.  <span data-ttu-id="b72a6-120">上**常规**选项卡上，在**操作**文本框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="b72a6-120">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="b72a6-121">若要发送平面文件 IDOC，必须使用**SendIdoc**操作公开的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b72a6-121">To send a flat-file IDOC, you must use the **SendIdoc** operation exposed by the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="b72a6-122">**SendIdoc**操作允许适配器客户端发送到的 Idoc 具有弱类型的架构。</span><span class="sxs-lookup"><span data-stu-id="b72a6-122">**SendIdoc** operation enables adapter clients to send IDOCs having a weakly-typed schema.</span></span> <span data-ttu-id="b72a6-123">有关详细信息，请参阅[SAP 中的 Idoc 上的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="b72a6-123">For more information, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span> <span data-ttu-id="b72a6-124">下图显示**操作**文本框中的操作**SendIdoc**操作。</span><span class="sxs-lookup"><span data-stu-id="b72a6-124">The following figure shows the **Action** text box with the action for the **SendIdoc** operation.</span></span>  
  
         <span data-ttu-id="b72a6-125">![指定操作中发送端口](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")</span><span class="sxs-lookup"><span data-stu-id="b72a6-125">![Specify action in the send port](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")</span></span>  
  
    3.  <span data-ttu-id="b72a6-126">单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sapBinding**。</span><span class="sxs-lookup"><span data-stu-id="b72a6-126">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span>  
  
    4.  <span data-ttu-id="b72a6-127">单击**凭据**选项卡，并指定要连接到 SAP 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="b72a6-127">Click the **Credentials** tab and specify the credentials to connect to an SAP system.</span></span>  
  
    5.  <span data-ttu-id="b72a6-128">单击**消息**选项卡上，然后在**出站 WCF 消息正文**部分中，选择**模板**选项。</span><span class="sxs-lookup"><span data-stu-id="b72a6-128">Click the **Messages** tab, and in the **Outbound WCF message body** section, choose the **Template** option.</span></span>  
  
    6.  <span data-ttu-id="b72a6-129">在**XML**文本框中，指定将用于构造 WCF 消息的模板。</span><span class="sxs-lookup"><span data-stu-id="b72a6-129">In the **XML** text box, specify the template that will be used to construct the WCF message.</span></span> <span data-ttu-id="b72a6-130">通过这样做，你创建一条消息，符合**SendIdoc**操作的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b72a6-130">By doing so, you create a message that conforms to the **SendIdoc** operation for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="b72a6-131">有关的消息结构的详细信息**SendIdoc**操作，请参阅[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="b72a6-131">For more information about the message structure for the **SendIdoc** operation, see [Message Schemas for IDOC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span></span>  
  
         <span data-ttu-id="b72a6-132">![为出站 WCF 消息指定模板](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")</span><span class="sxs-lookup"><span data-stu-id="b72a6-132">![Specify template for outbound WCF message](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")</span></span>  
  
         <span data-ttu-id="b72a6-133">对于 SendIdoc 操作中，你必须指定以下模板：</span><span class="sxs-lookup"><span data-stu-id="b72a6-133">For the SendIdoc operation, you must specify the following template:</span></span>  
  
        ```  
        <SendIdoc xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/">  
        <idocData><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/></idocData>  
        </SendIdoc>  
        ```  
  
         <span data-ttu-id="b72a6-134">在前面的模板中，`bts-msg-body`是创建使用平面文件拆装器与文件关联的 XML IDOC 接收端口。</span><span class="sxs-lookup"><span data-stu-id="b72a6-134">In the preceding template, the `bts-msg-body` is XML IDOC that is created using the flat-file disassembler associated with the file receive port.</span></span> <span data-ttu-id="b72a6-135">XML IDOC 封装在 SendIdoc 消息。</span><span class="sxs-lookup"><span data-stu-id="b72a6-135">The XML IDOC is encapsulated in the SendIdoc message.</span></span>  
  
    7.  <span data-ttu-id="b72a6-136">单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b72a6-136">Click **Apply**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="b72a6-137">在**发送端口属性**对话框中，从**发送处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="b72a6-137">In the **Send Port Properties** dialog box, from the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="b72a6-138">从**发送管道**下拉列表中，选择**ConvertToFlatFile**。</span><span class="sxs-lookup"><span data-stu-id="b72a6-138">From the **Send pipeline** drop-down list, select **ConvertToFlatFile**.</span></span> <span data-ttu-id="b72a6-139">此平面文件汇编器管道已 vPrev BizTalk 项目的一部分，用于将 XML IDOC 转换为平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="b72a6-139">This flat-file assembler pipeline is already a part of the vPrev BizTalk project and is used to convert an XML IDOC to a flat-file IDOC.</span></span>  
  
10. <span data-ttu-id="b72a6-140">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b72a6-140">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="b72a6-141">若要配置 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="b72a6-141">To configure the BizTalk application</span></span>  
  
1.  <span data-ttu-id="b72a6-142">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，展开其中部署业务流程的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b72a6-142">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2.  <span data-ttu-id="b72a6-143">右键单击 BizTalk 应用程序，然后再选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="b72a6-143">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3.  <span data-ttu-id="b72a6-144">从左窗格中，单击要配置业务流程。</span><span class="sxs-lookup"><span data-stu-id="b72a6-144">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="b72a6-145">从右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="b72a6-145">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4.  <span data-ttu-id="b72a6-146">下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。</span><span class="sxs-lookup"><span data-stu-id="b72a6-146">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
    1.  <span data-ttu-id="b72a6-147">选择将的平面文件 IDOC 放置位置的文件端口。</span><span class="sxs-lookup"><span data-stu-id="b72a6-147">Select the file port where you will drop the flat-file IDOC.</span></span>  
  
    2.  <span data-ttu-id="b72a6-148">选择你在本主题前面创建的 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="b72a6-148">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
    3.  <span data-ttu-id="b72a6-149">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b72a6-149">Click **OK**.</span></span>  
  
     <span data-ttu-id="b72a6-150">有关配置应用程序的详细信息，请参阅"如何为配置应用程序"在[http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)。</span><span class="sxs-lookup"><span data-stu-id="b72a6-150">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b72a6-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b72a6-151">Next Steps</span></span>  
 <span data-ttu-id="b72a6-152">你现在已经完成迁移到将 Idoc 发送到 SAP 系统使用基于 WCF 的 BizTalk 项目 vPrev BizTalk 项目[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b72a6-152">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends IDOCs to an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="b72a6-153">你必须现在测试迁移的 BizTalk 应用程序发送平面文件 IDOC 中, 所述[步骤 3： 测试迁移应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)。</span><span class="sxs-lookup"><span data-stu-id="b72a6-153">You must now test the migrated BizTalk application by sending a flat-file IDOC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b72a6-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b72a6-154">See Also</span></span>  
 [<span data-ttu-id="b72a6-155">教程 3：迁移 SAP 发送 IDOC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="b72a6-155">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)