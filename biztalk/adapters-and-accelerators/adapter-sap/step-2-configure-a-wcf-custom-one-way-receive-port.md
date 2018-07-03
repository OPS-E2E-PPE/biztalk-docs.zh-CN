---
title: 步骤 2： 配置 WCF 自定义单向接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way receive port, configuring
- migration
ms.assetid: e2a8f074-64d5-4e6c-84d0-318fb606c0ba
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d3320e7a2e6b948309087f2b33def57db9db0c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990294"
---
# <a name="step-2-configure-a-wcf-custom-one-way-receive-port"></a><span data-ttu-id="1953d-102">步骤 2： 配置 WCF 自定义单向接收端口</span><span class="sxs-lookup"><span data-stu-id="1953d-102">Step 2: Configure a WCF-Custom One-way Receive Port</span></span>
<span data-ttu-id="1953d-103">![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="1953d-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="1953d-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="1953d-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="1953d-105">**目标：** 在此步骤中，配置 WCF 自定义端口以接收来自 SAP 系统的平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="1953d-105">**Objective:** In this step, you configure a WCF-Custom port to receive a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="1953d-106">后配置端口时，你可以配置 BizTalk 应用程序以使用 WCF 自定义接收端口。</span><span class="sxs-lookup"><span data-stu-id="1953d-106">After configuring the port, you configure the BizTalk application to use the WCF-Custom receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1953d-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="1953d-107">Prerequisites</span></span>  
 <span data-ttu-id="1953d-108">你必须构建和部署 vPrev BizTalk 项目以接收来自 SAP 系统的 Idoc。</span><span class="sxs-lookup"><span data-stu-id="1953d-108">You must have built and deployed your vPrev BizTalk project to receive IDOCs from an SAP system.</span></span>  
  
### <a name="to-configure-a-wcf-custom-one-way-receive-port"></a><span data-ttu-id="1953d-109">若要配置 WCF 自定义单向接收端口</span><span class="sxs-lookup"><span data-stu-id="1953d-109">To configure a WCF-Custom one-way receive port</span></span>  
  
1. <span data-ttu-id="1953d-110">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1953d-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="1953d-111">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="1953d-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="1953d-112">展开要在其下创建接收端口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1953d-112">Expand the application under which you want create the receive port.</span></span>  
  
4. <span data-ttu-id="1953d-113">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="1953d-113">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port**.</span></span>  
  
5. <span data-ttu-id="1953d-114">在中**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="1953d-114">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6. <span data-ttu-id="1953d-115">上**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="1953d-115">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="1953d-116">**接收位置属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="1953d-116">The **Receive Location Properties** dialog box appears.</span></span>  
  
7. <span data-ttu-id="1953d-117">在中**接收位置属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1953d-117">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="1953d-118">指定接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="1953d-118">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="1953d-119">从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1953d-119">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="1953d-120">在中**Wcf-custom 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1953d-120">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="1953d-121">单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定连接 URI 从 SAP 系统接收消息。</span><span class="sxs-lookup"><span data-stu-id="1953d-121">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI to receive messages from the SAP system.</span></span> <span data-ttu-id="1953d-122">连接以接收来自 SAP 系统的消息的 URI 必须采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="1953d-122">The connection URI to receive messages from the SAP system must be in the following format:</span></span>  
  
      ```  
      sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
      ```  
  
       <span data-ttu-id="1953d-123">下图显示端口属性对话框中，使用指定的 URI:</span><span class="sxs-lookup"><span data-stu-id="1953d-123">The following figure shows the port properties dialog box with the URI specified:</span></span>  
  
       <span data-ttu-id="1953d-124">![连接 URI 从 SAP 接收消息](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")</span><span class="sxs-lookup"><span data-stu-id="1953d-124">![Connection URI to receive messages from SAP](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")</span></span>  
  
       <span data-ttu-id="1953d-125">有关连接 URI 的详细信息，请参阅[创建连接到 SAP 系统](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="1953d-125">For more information about the connection URI, see [Create a  connection to the SAP system](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span></span>  
  
   2. <span data-ttu-id="1953d-126">单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sapBinding**。</span><span class="sxs-lookup"><span data-stu-id="1953d-126">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="1953d-127">请确保指定的接收端口的以下绑定属性。</span><span class="sxs-lookup"><span data-stu-id="1953d-127">Make sure you specify the following binding properties for the receive port.</span></span>  
  
      |<span data-ttu-id="1953d-128">绑定属性</span><span class="sxs-lookup"><span data-stu-id="1953d-128">Binding property</span></span>|<span data-ttu-id="1953d-129">设置到的值</span><span class="sxs-lookup"><span data-stu-id="1953d-129">Set value to</span></span>|  
      |----------------------|------------------|  
      |<span data-ttu-id="1953d-130">FlatFileSegmentIndicator</span><span class="sxs-lookup"><span data-stu-id="1953d-130">flatFileSegmentIndicator</span></span>|<span data-ttu-id="1953d-131">**SegmentType**。</span><span class="sxs-lookup"><span data-stu-id="1953d-131">**SegmentType**.</span></span> <span data-ttu-id="1953d-132">这表示平面文件应包含在 IDOC 中的每个段的段类型。</span><span class="sxs-lookup"><span data-stu-id="1953d-132">This indicates that the flat files should contain the segment type for each segment in the IDOC.</span></span>|  
      |<span data-ttu-id="1953d-133">PadReceivedIdocWithSpaces</span><span class="sxs-lookup"><span data-stu-id="1953d-133">padReceivedIdocWithSpaces</span></span>|<span data-ttu-id="1953d-134">**True**。</span><span class="sxs-lookup"><span data-stu-id="1953d-134">**True**.</span></span> <span data-ttu-id="1953d-135">指定是否对 IDOC 中的每行填充为正确长度的空间。</span><span class="sxs-lookup"><span data-stu-id="1953d-135">Specifies whether each line in the IDOC is padded with spaces to the correct length.</span></span>|  
      |<span data-ttu-id="1953d-136">ReceiveIDocFormat</span><span class="sxs-lookup"><span data-stu-id="1953d-136">receiveIDocFormat</span></span>|<span data-ttu-id="1953d-137">**字符串**。</span><span class="sxs-lookup"><span data-stu-id="1953d-137">**String**.</span></span> <span data-ttu-id="1953d-138">这将指定 IDOC 消息，应表示为单个字符串字段。</span><span class="sxs-lookup"><span data-stu-id="1953d-138">This specifies that the IDOC message should be represented as a single string field.</span></span>|  
  
       <span data-ttu-id="1953d-139">有关绑定属性的详细信息，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1953d-139">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
   3. <span data-ttu-id="1953d-140">单击**他人**选项卡，然后指定用于连接到 SAP 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="1953d-140">Click the **Others** tab, and specify the credentials to connect to an SAP system.</span></span>  
  
   4. <span data-ttu-id="1953d-141">单击**消息**选项卡上，然后在**入站 BizTalk 消息正文**部分中，选择**路径**选项。</span><span class="sxs-lookup"><span data-stu-id="1953d-141">Click the **Messages** tab, and in the **Inbound BizTalk message body** section, choose the **Path** option.</span></span>  
  
   5. <span data-ttu-id="1953d-142">在中**正文路径表达式**文字框中，指定要从 XML 消息中提取平面文件 IDOC 的 XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="1953d-142">In the **Body path expression** text box, specify the XPath query to extract the flat-file IDOC from the XML message.</span></span> <span data-ttu-id="1953d-143">这样，接收端口从 IDOC 提取数据并裁剪掉一部分的 XML 标记**ReceiveIdoc**操作的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1953d-143">By doing so, the receive port extracts the data from the IDOC and trims the XML tag that is part of the **ReceiveIdoc** operation for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="1953d-144">有关的消息架构的详细信息**ReceiveIdoc**操作，请参阅[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="1953d-144">For more information about the message schema for the **ReceiveIdoc** operation, see [Message Schemas for IDOC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span></span>  
  
       <span data-ttu-id="1953d-145">![XPath 查询以提取平面&#45;文件 IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")</span><span class="sxs-lookup"><span data-stu-id="1953d-145">![XPath query to extract the flat&#45;file IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")</span></span>  
  
       <span data-ttu-id="1953d-146">必须指定以下 XPath 查询：</span><span class="sxs-lookup"><span data-stu-id="1953d-146">You must specify the following XPath query:</span></span>  
  
      ```  
      /*[local-name()='ReceiveIdoc']/*[local-name()='idocData']  
      ```  
  
   6. <span data-ttu-id="1953d-147">从**节点编码**下拉列表中，选择**字符串**。</span><span class="sxs-lookup"><span data-stu-id="1953d-147">From the **Node encoding** drop-down list, select **String**.</span></span>  
  
   7. <span data-ttu-id="1953d-148">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1953d-148">Click **Apply**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="1953d-149">在接收位置属性对话框中，从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="1953d-149">In the Receive Location Properties dialog box, from the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="1953d-150">从**接收管道**下拉列表中，选择**ConvertToXML**。</span><span class="sxs-lookup"><span data-stu-id="1953d-150">From the **Receive pipeline** drop-down list, select **ConvertToXML**.</span></span> <span data-ttu-id="1953d-151">此平面文件拆装器管道已将平面文件 IDOC 转换为 XML IDOC vPrev BizTalk 项目的一部分。</span><span class="sxs-lookup"><span data-stu-id="1953d-151">This flat-file disassembler pipeline is already a part of the vPrev BizTalk project to convert a flat-file IDOC to an XML IDOC.</span></span>  
  
11. <span data-ttu-id="1953d-152">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="1953d-152">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="1953d-153">若要配置的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="1953d-153">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="1953d-154">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，以及其中部署该业务流程的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1953d-154">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="1953d-155">右键单击 BizTalk 应用程序，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="1953d-155">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="1953d-156">从左窗格中，单击业务流程配置。</span><span class="sxs-lookup"><span data-stu-id="1953d-156">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="1953d-157">在右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="1953d-157">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="1953d-158">下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。</span><span class="sxs-lookup"><span data-stu-id="1953d-158">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="1953d-159">选择 WCF 自定义接收本主题中前面创建的端口。</span><span class="sxs-lookup"><span data-stu-id="1953d-159">Select the WCF-Custom receive port you created earlier in this topic.</span></span>  
  
   2. <span data-ttu-id="1953d-160">选择在收到平面文件 IDOC 的位置的文件端口。</span><span class="sxs-lookup"><span data-stu-id="1953d-160">Select a file port where you will receive the flat-file IDOC.</span></span>  
  
   3. <span data-ttu-id="1953d-161">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="1953d-161">Click **OK**.</span></span>  
  
      <span data-ttu-id="1953d-162">有关配置应用程序的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=102360 ](http://go.microsoft.com/fwlink/?LinkId=102360)。</span><span class="sxs-lookup"><span data-stu-id="1953d-162">For more information about configuring an application, see [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1953d-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1953d-163">Next Steps</span></span>  
 <span data-ttu-id="1953d-164">你现在已经完成迁移到 BizTalk 项目中使用基于 WCF 的 SAP 系统接收 Idoc vPrev BizTalk 项目的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1953d-164">You have now completed migration of your vPrev BizTalk project to a BizTalk project that receives IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="1953d-165">你必须现在测试已迁移的 BizTalk 应用程序通过接收平面文件 IDOC 中所述[第 3 步： 测试迁移应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)。</span><span class="sxs-lookup"><span data-stu-id="1953d-165">You must now test the migrated BizTalk application by receiving a flat-file IDOC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1953d-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="1953d-166">See Also</span></span>  
 [<span data-ttu-id="1953d-167">教程 4：迁移 SAP 接收 IDOC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="1953d-167">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)