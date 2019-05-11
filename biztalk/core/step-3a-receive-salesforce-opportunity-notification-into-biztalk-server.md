---
title: 步骤 3a:Salesforce 机会通知接收到 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be9de6e3-6bd9-4275-b2fb-0a756c51aabf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c323d7f7975eb20f78aba0c6259d9c998779b1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392584"
---
# <a name="step-3a-receive-salesforce-opportunity-notification-into-biztalk-server"></a><span data-ttu-id="56cc8-102">步骤 3a:Salesforce 机会通知接收到 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="56cc8-102">Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server</span></span>
<span data-ttu-id="56cc8-103">在此步骤中，我们开始创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="56cc8-103">In this step, we start creating a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="56cc8-104">我们应先包括我们将从 Salesforce 获取然后再开始创建业务流程来处理该消息的机会通知消息的消息架构。</span><span class="sxs-lookup"><span data-stu-id="56cc8-104">We should first include the message schema for the opportunities notification message that we’ll get from Salesforce and then start creating an orchestration to process the message.</span></span>  
  
### <a name="to-include-the-salesforce-opportunities-notification-schema"></a><span data-ttu-id="56cc8-105">若要包括 Salesforce 机会通知架构</span><span class="sxs-lookup"><span data-stu-id="56cc8-105">To include the Salesforce opportunities notification schema</span></span>  
  
1. <span data-ttu-id="56cc8-106">登录到 Salesforce.com 门户。</span><span class="sxs-lookup"><span data-stu-id="56cc8-106">Login to the Salesforce.com portal.</span></span> <span data-ttu-id="56cc8-107">在 Salesforce 门户中，单击位于页面右上角的登录名，然后单击**安装程序**。</span><span class="sxs-lookup"><span data-stu-id="56cc8-107">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2. <span data-ttu-id="56cc8-108">在左窗格中下,**应用安装程序**，展开**创建**，展开**工作流和审批**，然后单击**工作流规则**。</span><span class="sxs-lookup"><span data-stu-id="56cc8-108">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span>  
  
3. <span data-ttu-id="56cc8-109">在中**所有工作流规则**页上，单击**关闭机会**前面创建的工作流。</span><span class="sxs-lookup"><span data-stu-id="56cc8-109">In the **All Workflow Rules** page, click the **Closed Opportunity** workflow that you created earlier.</span></span>  
  
4. <span data-ttu-id="56cc8-110">在中**关闭机会**工作流规则页上，单击**NewOp1**出站消息工作流操作。</span><span class="sxs-lookup"><span data-stu-id="56cc8-110">In the **Closed Opportunity** workflow rule page, click **NewOp1** outbound message workflow action.</span></span>  
  
5. <span data-ttu-id="56cc8-111">在中**NewOp1**出站消息工作流操作页上，右键单击该链接**单击查看 WSDL**，单击**目标另存为**，然后指定你想要保存的位置WSDL 中。</span><span class="sxs-lookup"><span data-stu-id="56cc8-111">In the **NewOp1** outbound message workflow action page, right-click the link **Click for WSDL**, click **Save target as**, and then specify the location where you want to save the WSDL.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="56cc8-112">必须使用.wsdl 扩展名保存该文件。</span><span class="sxs-lookup"><span data-stu-id="56cc8-112">You must save the file with a .wsdl extension.</span></span>  
  
6. <span data-ttu-id="56cc8-113">创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="56cc8-113">Create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="56cc8-114">对于本教程，让我们将项目命名为`BtsSalesforceIntegration`。</span><span class="sxs-lookup"><span data-stu-id="56cc8-114">For this tutorial, let us name the project as `BtsSalesforceIntegration`.</span></span>  
  
7. <span data-ttu-id="56cc8-115">右键单击[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目在解决方案资源管理器中，依次指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="56cc8-115">Right-click the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project in the Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
8. <span data-ttu-id="56cc8-116">在中**添加生成的项**对话框中，单击**使用 WCF 服务**，然后单击**添加**以启动**BizTalk WCF 服务使用**向导。</span><span class="sxs-lookup"><span data-stu-id="56cc8-116">In the **Add Generated Items** dialog box, click **Consume WCF Service**, and then click **Add** to launch the **BizTalk WCF Service Consuming** wizard.</span></span> <span data-ttu-id="56cc8-117">在欢迎页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="56cc8-117">On the welcome page, click **Next**.</span></span>  
  
9. <span data-ttu-id="56cc8-118">上**元数据来源**页上，选择**元数据文件 （WSDL 和 XSD）** 选项，并单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="56cc8-118">On the **Metadata Source** page, select the **Metadata Files (WSDL and XSD)** option, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="56cc8-119">上**元数据文件**页上，单击**添加**，然后导航到保存从 Salesforce 门户下载的 WSDL 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="56cc8-119">On the **Metadata Files** page, click **Add**, and then navigate to the location where you saved the WSDL file downloaded from the Salesforce portal.</span></span> <span data-ttu-id="56cc8-120">选择 WSDL 文件，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="56cc8-120">Select the WSDL file and then click **Next**.</span></span>  
  
11. <span data-ttu-id="56cc8-121">在下一页上，将设置为命名空间`NotificationService`，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="56cc8-121">In the next page, set the namespace as `NotificationService` and then click **Import**.</span></span> <span data-ttu-id="56cc8-122">该向导将添加的架构文件和业务流程传递到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="56cc8-122">The wizard adds the schema files and an orchestration to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="56cc8-123">用于从 Salesforce 接收机会通知的消息架构是**NotificationService_soap_sforce_com_2005_09_outbound.xsd**。</span><span class="sxs-lookup"><span data-stu-id="56cc8-123">The message schema for receiving opportunity notifications from Salesforce is **NotificationService_soap_sforce_com_2005_09_outbound.xsd**.</span></span>  
  
### <a name="to-create-an-orchestration-to-receive-the-notification-message"></a><span data-ttu-id="56cc8-124">若要创建一个业务流程接收通知消息</span><span class="sxs-lookup"><span data-stu-id="56cc8-124">To create an orchestration to receive the notification message</span></span>  
  
1. <span data-ttu-id="56cc8-125">完成后**BizTalk WCF 服务使用**向导、 业务流程 (**NotificationService.odx**，在此示例中) 添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="56cc8-125">After you complete the **BizTalk WCF Service Consuming** wizard, an orchestration (**NotificationService.odx**, in this example) is added to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
2. <span data-ttu-id="56cc8-126">打开业务流程文件并在业务流程视图中，添加两个新消息变量。</span><span class="sxs-lookup"><span data-stu-id="56cc8-126">Open the orchestration file and in the Orchestration view, add two new message variables.</span></span> <span data-ttu-id="56cc8-127">命名它们`NotificationMessage`和`NotificationAck`。</span><span class="sxs-lookup"><span data-stu-id="56cc8-127">Name them `NotificationMessage` and `NotificationAck`.</span></span> <span data-ttu-id="56cc8-128">设置这些消息变量的消息类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="56cc8-128">Set the message type for these message variables as follows:</span></span>  
  
   1.  <span data-ttu-id="56cc8-129">设置**NotificationMessage**到*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notifications*。</span><span class="sxs-lookup"><span data-stu-id="56cc8-129">Set **NotificationMessage** to *NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notifications*.</span></span> <span data-ttu-id="56cc8-130">此消息变量表示从 Salesforce 收到的机会通知消息。</span><span class="sxs-lookup"><span data-stu-id="56cc8-130">This message variable represents the opportunity notification message received from Salesforce.</span></span>  
  
   2.  <span data-ttu-id="56cc8-131">设置**NotificationAck**到*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notificationsResponse*。</span><span class="sxs-lookup"><span data-stu-id="56cc8-131">Set **NotificationAck** to *NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notificationsResponse*.</span></span> <span data-ttu-id="56cc8-132">此消息变量表示发送回 Salesforce 的机会通知确认消息。</span><span class="sxs-lookup"><span data-stu-id="56cc8-132">This message variable represents the opportunity notification acknowledgement message sent back to Salesforce.</span></span>  
  
3. <span data-ttu-id="56cc8-133">向业务流程添加接收形状。</span><span class="sxs-lookup"><span data-stu-id="56cc8-133">Add a receive shape to the orchestration.</span></span> <span data-ttu-id="56cc8-134">该形状上设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="56cc8-134">Set the following properties on the shape:</span></span>  
  
   1.  <span data-ttu-id="56cc8-135">设置**激活**到**True**。</span><span class="sxs-lookup"><span data-stu-id="56cc8-135">Set **Activate** to **True**.</span></span>  
  
   2.  <span data-ttu-id="56cc8-136">设置**名称**到*ReceiveNotificationMessage*。</span><span class="sxs-lookup"><span data-stu-id="56cc8-136">Set **Name** to *ReceiveNotificationMessage*.</span></span>  
  
   3.  <span data-ttu-id="56cc8-137">设置**消息**到*NotificationMessage*。</span><span class="sxs-lookup"><span data-stu-id="56cc8-137">Set **Message** to *NotificationMessage*.</span></span>  
  
4. <span data-ttu-id="56cc8-138">在接收形状后添加构造消息形状。</span><span class="sxs-lookup"><span data-stu-id="56cc8-138">Add a Construct Message shape after the Receive shape.</span></span> <span data-ttu-id="56cc8-139">将为该消息形状`ConstructNotificationResponse`并设置**构造的消息**属性设置为`NotificationAck`。</span><span class="sxs-lookup"><span data-stu-id="56cc8-139">Name the message shape as `ConstructNotificationResponse` and set the **Messages Constructed** property to `NotificationAck`.</span></span> <span data-ttu-id="56cc8-140">构造消息的一部分，我们还会创建一个映射来生成要发送回 Salesforce 的通知确认消息。</span><span class="sxs-lookup"><span data-stu-id="56cc8-140">As part of the construct message, we’ll also create a map to generate a notification acknowledgement message to be sent back to Salesforce.</span></span>  
  
   1.  <span data-ttu-id="56cc8-141">在构造消息形状内添加转换形状。</span><span class="sxs-lookup"><span data-stu-id="56cc8-141">Within the Construct Message shape, add a Transform shape.</span></span> <span data-ttu-id="56cc8-142">双击转换形状，然后在转换配置对话框中，选择**新的映射**选项。</span><span class="sxs-lookup"><span data-stu-id="56cc8-142">Double-click the Transform shape and in the Transform Configuration dialog box, select the **New Map** option.</span></span>  
  
   2.  <span data-ttu-id="56cc8-143">映射名称指定为`BtsSalesforceIntegration.MapNotificationResponse`。</span><span class="sxs-lookup"><span data-stu-id="56cc8-143">Specify the map name as `BtsSalesforceIntegration.MapNotificationResponse`.</span></span>  
  
   3.  <span data-ttu-id="56cc8-144">设置源作为**NotificationMessage**和作为目标**NotificationAck**。</span><span class="sxs-lookup"><span data-stu-id="56cc8-144">Set Source as **NotificationMessage** and Destination as **NotificationAck**.</span></span>  
  
   4.  <span data-ttu-id="56cc8-145">请确保复选框**当我单击确定时，启动 BizTalk 映射器**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="56cc8-145">Make sure the check box **When I click OK, launch the BizTalk Mapper** is selected.</span></span>  
  
   5.  <span data-ttu-id="56cc8-146">在中**MapNotificationResponse.btm**，我们将创建要发送回 Salesforce 的通知响应。</span><span class="sxs-lookup"><span data-stu-id="56cc8-146">In **MapNotificationResponse.btm**, we’ll create a notification response to be sent back to Salesforce.</span></span> <span data-ttu-id="56cc8-147">每次 Salesforce 发送通知，它期望返回确认。</span><span class="sxs-lookup"><span data-stu-id="56cc8-147">Every time Salesforce sends a notification, it expects an acknowledgement in return.</span></span> <span data-ttu-id="56cc8-148">通知响应消息的架构显示**Ack**在响应中的元素属于布尔类型。</span><span class="sxs-lookup"><span data-stu-id="56cc8-148">The schema of the notification response message shows that the **Ack** element in the response is of type Boolean.</span></span> <span data-ttu-id="56cc8-149">因此，在映射中，你必须删除**值映射**functoid，并设置其两个输入值 （Condition 和 Result） 到`true`。</span><span class="sxs-lookup"><span data-stu-id="56cc8-149">So, in the map, you must drop a **Value Mapping** functoid and set its two input values (Condition and Result) to `true`.</span></span> <span data-ttu-id="56cc8-150">单击**确定**以保存该 functoid。</span><span class="sxs-lookup"><span data-stu-id="56cc8-150">Click **OK** to save the functoid.</span></span>  
  
   6.  <span data-ttu-id="56cc8-151">连接**值映射**到 functoid **Ack**目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="56cc8-151">Connect the **Value Mapping** functoid to the **Ack** element in the destination schema.</span></span>  
  
5. <span data-ttu-id="56cc8-152">在业务流程，构造消息形状后添加将用于将确认发送回 Salesforce 的发送形状。</span><span class="sxs-lookup"><span data-stu-id="56cc8-152">In the orchestration, after the Construct Message shape, add a Send shape that will be used to send the acknowledgement back to Salesforce.</span></span>  
  
   -   <span data-ttu-id="56cc8-153">设置**名称**到*SendNotificationAck*。</span><span class="sxs-lookup"><span data-stu-id="56cc8-153">Set **Name** to *SendNotificationAck*.</span></span>  
  
   -   <span data-ttu-id="56cc8-154">设置**消息**到*NotificationAck*。</span><span class="sxs-lookup"><span data-stu-id="56cc8-154">Set **Message** to *NotificationAck*.</span></span>  
  
6. <span data-ttu-id="56cc8-155">在业务流程，添加用于接收 Salesforce 通知消息，并在响应中发送确认的端口。</span><span class="sxs-lookup"><span data-stu-id="56cc8-155">In the orchestration, add a port to receive Salesforce notification message and send the acknowledgement in response.</span></span> <span data-ttu-id="56cc8-156">在端口配置向导中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="56cc8-156">In the Port Configuration wizard, select the following options:</span></span>  
  
   - <span data-ttu-id="56cc8-157">将端口名称指定为`SalesforceNotificationPort`。</span><span class="sxs-lookup"><span data-stu-id="56cc8-157">Specify the port name as `SalesforceNotificationPort`.</span></span>  
  
   - <span data-ttu-id="56cc8-158">选择选项以创建新的端口类型。</span><span class="sxs-lookup"><span data-stu-id="56cc8-158">Select the option to create a new port type.</span></span>  
  
   - <span data-ttu-id="56cc8-159">设置**通信模式**到*请求-响应*。</span><span class="sxs-lookup"><span data-stu-id="56cc8-159">Set **Communication Pattern** to *Request-Response*.</span></span>  
  
   - <span data-ttu-id="56cc8-160">设置**端口通信方向**到*我将接收请求并发送响应*并设置**端口绑定**到*指定更高版本*.</span><span class="sxs-lookup"><span data-stu-id="56cc8-160">Set **Port direction of communication** to *I’ll be receiving a request and sending a response* and set **Port binding** to *Specify later*.</span></span>  
  
     <span data-ttu-id="56cc8-161">连接**请求**操作的端口与接收形状 (*ReceiveNotificationMessage*) 和**响应**该端口与发送形状的操作 (*SendNotificationAck*)。</span><span class="sxs-lookup"><span data-stu-id="56cc8-161">Connect the **Request** operation of port to the Receive shape (*ReceiveNotificationMessage*) and the **Response** operation of the port to the Send shape (*SendNotificationAck*).</span></span> <span data-ttu-id="56cc8-162">以下屏幕快照描述了从 Salesforce 接收机会通知并发送回确认的业务流程的一部分：</span><span class="sxs-lookup"><span data-stu-id="56cc8-162">The following screenshot depicts the part of the orchestration that receives an opportunity notification from Salesforce and sends an acknowledgement back:</span></span>  
  
     <span data-ttu-id="56cc8-163">![机会通知接收和发送响应](../core/media/bts-sf-recvnotificationorch.jpg "BTS_SF_RecvNotificationOrch")</span><span class="sxs-lookup"><span data-stu-id="56cc8-163">![Receive opportunity notification and send response](../core/media/bts-sf-recvnotificationorch.jpg "BTS_SF_RecvNotificationOrch")</span></span>  
  
   <span data-ttu-id="56cc8-164">到目前为止，我们已设置其中从 Salesforce 收到的机会通知并确认发送回解决方案。</span><span class="sxs-lookup"><span data-stu-id="56cc8-164">By now, we have set up the solution where an opportunity notification is received from Salesforce and an acknowledgement is sent back.</span></span> <span data-ttu-id="56cc8-165">在随后的主题，我们将构建此解决方案，若要开始处理机会通知，以获取有关销售机会种类的可用的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="56cc8-165">In the subsequent topics, we’ll build on this solution to start processing the opportunity notification to get more details about the kind of sales opportunity available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cc8-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="56cc8-166">See Also</span></span>  
 [<span data-ttu-id="56cc8-167">步骤 3：在 Visual Studio 中创建的 BizTalk Server 解决方案</span><span class="sxs-lookup"><span data-stu-id="56cc8-167">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)