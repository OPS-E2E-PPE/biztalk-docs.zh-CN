---
title: 步骤 2： 配置 WCF 自定义单向发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way send port, configuring
- migration
ms.assetid: ae13222e-42e7-45a7-9b2a-0a6779b21736
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 662007dc6f75e1ca0459e53f576c816d23b71404
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005718"
---
# <a name="step-2-configure-a-wcf-custom-one-way-send-port"></a><span data-ttu-id="65adc-102">步骤 2： 配置 WCF 自定义单向发送端口</span><span class="sxs-lookup"><span data-stu-id="65adc-102">Step 2: Configure a WCF-Custom One-way Send Port</span></span>
<span data-ttu-id="65adc-103">![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="65adc-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="65adc-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="65adc-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="65adc-105">**目标：** 在此步骤中，配置用于将平面文件 IDOC 发送到 SAP 系统的 WCF 自定义端口。</span><span class="sxs-lookup"><span data-stu-id="65adc-105">**Objective:** In this step, you configure a WCF-Custom port to send the flat-file IDOC to an SAP system.</span></span> <span data-ttu-id="65adc-106">后配置端口时，BizTalk 应用程序使用 WCF 自定义发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="65adc-106">After configuring the port, you configure the BizTalk application to use the WCF-Custom send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="65adc-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="65adc-107">Prerequisites</span></span>  
 <span data-ttu-id="65adc-108">你必须构建和部署 vPrev BizTalk 项目以将 Idoc 发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="65adc-108">You must have built and deployed your vPrev BizTalk project to send IDOCs to an SAP system.</span></span>  
  
### <a name="to-configure-a-wcf-custom-one-way-send-port"></a><span data-ttu-id="65adc-109">若要配置 WCF 自定义单向发送端口</span><span class="sxs-lookup"><span data-stu-id="65adc-109">To configure a WCF-Custom one-way send port</span></span>  
  
1. <span data-ttu-id="65adc-110">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="65adc-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="65adc-111">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="65adc-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="65adc-112">展开要在其下创建发送端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="65adc-112">Expand the application under which you want to create the send port.</span></span>  
  
4. <span data-ttu-id="65adc-113">右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="65adc-113">Right-click **Send Ports**, point to **New**, and click **Static One-way Send Port**.</span></span>  
  
5. <span data-ttu-id="65adc-114">在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="65adc-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="65adc-115">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="65adc-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7. <span data-ttu-id="65adc-116">在中**Wcf-custom 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="65adc-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="65adc-117">单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定连接 URI，将消息发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="65adc-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI to send messages to the SAP system.</span></span> <span data-ttu-id="65adc-118">有关连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="65adc-118">For more information about the connection URI, see [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
       <span data-ttu-id="65adc-119">![在发送端口中指定的连接 URI](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")</span><span class="sxs-lookup"><span data-stu-id="65adc-119">![Connection URI specified in the send port](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")</span></span>  
  
   2. <span data-ttu-id="65adc-120">上**常规**选项卡上，在**操作**文字框中，键入操作的操作。</span><span class="sxs-lookup"><span data-stu-id="65adc-120">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="65adc-121">若要发送平面文件 IDOC，必须使用**SendIdoc**操作公开的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="65adc-121">To send a flat-file IDOC, you must use the **SendIdoc** operation exposed by the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="65adc-122">**SendIdoc**操作允许适配器客户端发送 Idoc 具有弱类型的架构。</span><span class="sxs-lookup"><span data-stu-id="65adc-122">**SendIdoc** operation enables adapter clients to send IDOCs having a weakly-typed schema.</span></span> <span data-ttu-id="65adc-123">有关详细信息，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="65adc-123">For more information, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span> <span data-ttu-id="65adc-124">下图显示**操作**的操作的文本框中**SendIdoc**操作。</span><span class="sxs-lookup"><span data-stu-id="65adc-124">The following figure shows the **Action** text box with the action for the **SendIdoc** operation.</span></span>  
  
       <span data-ttu-id="65adc-125">![在发送端口中指定操作](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")</span><span class="sxs-lookup"><span data-stu-id="65adc-125">![Specify action in the send port](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")</span></span>  
  
   3. <span data-ttu-id="65adc-126">单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sapBinding**。</span><span class="sxs-lookup"><span data-stu-id="65adc-126">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span>  
  
   4. <span data-ttu-id="65adc-127">单击**凭据**选项卡上，并指定用于连接到 SAP 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="65adc-127">Click the **Credentials** tab and specify the credentials to connect to an SAP system.</span></span>  
  
   5. <span data-ttu-id="65adc-128">单击**消息**选项卡上，然后在**出站 WCF 消息正文**部分中，选择**模板**选项。</span><span class="sxs-lookup"><span data-stu-id="65adc-128">Click the **Messages** tab, and in the **Outbound WCF message body** section, choose the **Template** option.</span></span>  
  
   6. <span data-ttu-id="65adc-129">在中**XML**文字框中，指定将用于构造 WCF 消息的模板。</span><span class="sxs-lookup"><span data-stu-id="65adc-129">In the **XML** text box, specify the template that will be used to construct the WCF message.</span></span> <span data-ttu-id="65adc-130">通过此操作，创建一条消息，符合**SendIdoc**操作的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="65adc-130">By doing so, you create a message that conforms to the **SendIdoc** operation for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="65adc-131">有关的消息结构的详细信息**SendIdoc**操作，请参阅[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="65adc-131">For more information about the message structure for the **SendIdoc** operation, see [Message Schemas for IDOC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span></span>  
  
       <span data-ttu-id="65adc-132">![指定出站 WCF 消息的模板](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")</span><span class="sxs-lookup"><span data-stu-id="65adc-132">![Specify template for outbound WCF message](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")</span></span>  
  
       <span data-ttu-id="65adc-133">对于 SendIdoc 操作中，您必须指定以下模板：</span><span class="sxs-lookup"><span data-stu-id="65adc-133">For the SendIdoc operation, you must specify the following template:</span></span>  
  
      ```  
      <SendIdoc xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/">  
      <idocData><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/></idocData>  
      </SendIdoc>  
      ```  
  
       <span data-ttu-id="65adc-134">在前面的模板，`bts-msg-body`是使用与文件相关联的平面文件拆装器创建的 XML IDOC 接收端口。</span><span class="sxs-lookup"><span data-stu-id="65adc-134">In the preceding template, the `bts-msg-body` is XML IDOC that is created using the flat-file disassembler associated with the file receive port.</span></span> <span data-ttu-id="65adc-135">XML IDOC 封装在 SendIdoc 消息。</span><span class="sxs-lookup"><span data-stu-id="65adc-135">The XML IDOC is encapsulated in the SendIdoc message.</span></span>  
  
   7. <span data-ttu-id="65adc-136">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="65adc-136">Click **Apply**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="65adc-137">在中**发送端口属性**对话框中，从**发送处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="65adc-137">In the **Send Port Properties** dialog box, from the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="65adc-138">从**发送管道**下拉列表中，选择**ConvertToFlatFile**。</span><span class="sxs-lookup"><span data-stu-id="65adc-138">From the **Send pipeline** drop-down list, select **ConvertToFlatFile**.</span></span> <span data-ttu-id="65adc-139">此平面文件组装器管道已经 vPrev BizTalk 项目的一部分，用于将 XML IDOC 转换为平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="65adc-139">This flat-file assembler pipeline is already a part of the vPrev BizTalk project and is used to convert an XML IDOC to a flat-file IDOC.</span></span>  
  
10. <span data-ttu-id="65adc-140">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="65adc-140">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="65adc-141">若要配置的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="65adc-141">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="65adc-142">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，以及其中部署该业务流程的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="65adc-142">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="65adc-143">右键单击 BizTalk 应用程序，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="65adc-143">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="65adc-144">从左窗格中，单击业务流程配置。</span><span class="sxs-lookup"><span data-stu-id="65adc-144">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="65adc-145">在右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="65adc-145">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="65adc-146">下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。</span><span class="sxs-lookup"><span data-stu-id="65adc-146">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="65adc-147">选择您将在何处放置平面文件 IDOC 的文件端口。</span><span class="sxs-lookup"><span data-stu-id="65adc-147">Select the file port where you will drop the flat-file IDOC.</span></span>  
  
   2. <span data-ttu-id="65adc-148">选择本主题中前面创建的 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="65adc-148">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
   3. <span data-ttu-id="65adc-149">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="65adc-149">Click **OK**.</span></span>  
  
      <span data-ttu-id="65adc-150">有关配置应用程序的详细信息，请参阅"如何配置应用程序的"网址[ http://go.microsoft.com/fwlink/?LinkId=102360 ](http://go.microsoft.com/fwlink/?LinkId=102360)。</span><span class="sxs-lookup"><span data-stu-id="65adc-150">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="65adc-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="65adc-151">Next Steps</span></span>  
 <span data-ttu-id="65adc-152">你现在已经完成迁移到 BizTalk 项目，将 Idoc 发送到 SAP 系统使用基于 WCF 的 vPrev BizTalk 项目的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="65adc-152">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends IDOCs to an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="65adc-153">你必须现在测试已迁移的 BizTalk 应用程序通过发送平面文件 IDOC 中所述[第 3 步： 测试迁移应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)。</span><span class="sxs-lookup"><span data-stu-id="65adc-153">You must now test the migrated BizTalk application by sending a flat-file IDOC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65adc-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="65adc-154">See Also</span></span>  
 [<span data-ttu-id="65adc-155">教程 3：迁移 SAP 发送 IDOC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="65adc-155">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)