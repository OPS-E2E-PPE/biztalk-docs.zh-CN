---
title: 演练： 模块 3-从业务流程访问 SharePoint 属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, orchestrations
- Windows SharePoint Services adapter tutorials, accessing SharePoint properties
ms.assetid: 310c4002-3416-44c6-b409-1d5467063e28
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23bc9f0b1f2d350864509536a393de639e108e2d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010958"
---
# <a name="walkthrough-module-3---accessing-sharepoint-properties-from-an-orchestration"></a>演练： 模块 3-从业务流程访问 SharePoint 属性
本演练是的延续[演练： 模块 2-将与 Windows SharePoint Services Adapter 集成 Office](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)并演示如何访问在传入消息的 Windows SharePoint Services 上下文属性运行时间，并确定使用动态端口业务流程中的属性上基于该消息的目标。 有关 Windows SharePoint Services 适配器的简介，请参阅[什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md)。  
  
## <a name="prerequisites"></a>先决条件  
 以下为执行本主题中步骤的前提条件：  
  
-   你必须具有 BizTalk Server 上运行的完整安装的单个服务器部署[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。  
  
-   你必须完成以下演练：[演练： 模块 1-发送和接收消息与 Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)和[演练： 模块 2-与 Windows 集成 OfficeSharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)  
  
 有关在多服务器部署中使用 Windows SharePoint Services 适配器的信息，请参阅[设置和部署 Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)。  
  
## <a name="modify-the-biztalk-project"></a>修改 BizTalk 项目  
 在此过程中修改中的 PurchaseOrder 架构[演练： 模块 2-将与 Windows SharePoint Services Adapter 集成 Office](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)。 此过程说明如何升级架构属性以方便在 BizTalk 业务流程中进行访问。  
  
#### <a name="modify-the-purchaseorderxsd-schema"></a>修改 PurchaseOrder.xsd 架构  
  
1.  启动**Microsoft Visual Studio**。  
  
2.  单击**文件**，单击**打开**，然后单击**项目/解决方案**。  
  
3.  浏览到`OrderProcess.sln`文件，，然后单击**打开**。  
  
4.  在**解决方案资源管理器**，右键单击`OrderProcessSchema.xsd`文件，，然后单击**打开**。  
  
5.  在**BizTalk 编辑器**，展开`PurchaseOrder`。  
  
6.  右键单击`Amount`，单击**Promote**，然后单击**快速升级**。  
  
7.  单击 **“确定”**。  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]当前项目中为此创建一个属性的架构。  
  
8.  保存 `PurchaseOrder.xsd`。  
  
## <a name="create-an-orchestration"></a>创建业务流程  
 在此过程中将创建新的 BizTalk 业务流程。 此过程创建用于处理由 Windows Sharepoint Services 适配器所接收消息的业务流程。  
  
#### <a name="add-a-biztalk-orchestration"></a>添加 BizTalk 业务流程  
  
1.  在**解决方案资源管理器**，右键单击`OrderProcess`项目中，单击**添加**，然后单击**新项**。  
  
2.  下**类别**，选择**Orchestration 文件**。  
  
3.  下**模板**，选择**BizTalk 业务流程**。  
  
4.  类型`MyCompanyOrderProcessing`中**名称**字段，然后再单击**添加**。  
  
## <a name="create-receive-information"></a>创建接收信息  
 在此过程中，将为业务流程创建新消息、接收端口和接收形状。 此过程说明如何配置用于接收来自 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的消息的业务流程。  
  
#### <a name="create-a-new-message"></a>创建新消息的步骤  
  
1.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。 此操作将生成一条名为 `Message_1` 的新消息。  
  
2.  右键单击`Message_1`，单击**重命名**，然后键入`Message_PO`。  
  
3.  右键单击`Message_PO`，然后单击**属性窗口**。  
  
4.  在**消息类型**属性中，展开**架构**，然后选择`OrderProcess.OrderProcessSchema`架构。  
  
#### <a name="add-a-receive-port-to-the-orchestration"></a>向业务流程添加接收端口  
  
1.  下**BizTalk 业务流程**在工具箱中，拖动**端口**形状上的与端口图面。 此时将启动端口配置向导。  
  
2.  在欢迎屏幕上，单击**下一步**。  
  
3.  类型`ReceivePurchaseOrder`中**名称**字段，然后再单击**下一步**。  
  
4.  选择**创建新的端口类型**。  
  
5.  类型`PurchaseOrderPT`中**端口类型名称**字段，然后再单击**下一步**。  
  
6.  上**端口绑定屏幕**，保留默认值，然后单击**下一步**。  
  
7.  单击 **“完成”**。  
  
8.  在**业务流程视图**下**端口类型**，展开`PurchaseOrderPT`端口类型。  
  
9. 右键单击`Operation_1`，单击**重命名**，然后键入`PurchaseOrderOperation`。  
  
#### <a name="add-a-receive-shape-to-the-orchestration"></a>向业务流程添加接收形状  
  
1.  下**BizTalk 业务流程**在工具箱中，拖动**接收**形状上的与业务流程。  
  
2.  右键单击接收形状，并依次**属性窗口**。  
  
3.  设置**激活**属性`True`。  
  
    > [!NOTE]
    >  如果激活属性设置为 false，则会出现以下错误:"错误 X2214： 必须指定至少一个已初始化的相关集非激活接收在非自相关端口上的"  
  
4.  类型`Receive_PO`中**名称**字段。  
  
5.  在**属性窗口**，选择`Message_PO`消息属性。  
  
6.  选择`ReceivePurchaseOrder.PurchaseOrderOperation.Request`为**操作**属性。 此操作会将该端口与业务流程设计器中的接收形状关联在一起。  
  
## <a name="create-send-information"></a>创建发送信息  
 在此过程中，将为业务流程创建新消息、发送端口和决策结构。 此过程说明如何配置包含决策逻辑的业务流程，以及如何配置向发送端口发送消息的业务流程。  
  
#### <a name="create-a-new-message"></a>创建新消息的步骤  
  
1.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。 此操作将生成一条名为 `Message_1` 的新消息。  
  
2.  右键单击`Message_1`，单击**重命名**，然后键入`Message_Task`。  
  
3.  右键单击`Message_Task`，然后单击**属性窗口**。  
  
4.  在**消息类型**属性中，展开**架构**，然后选择`OrderProcess.OrderProcessSchema`架构。  
  
#### <a name="add-a-send-port-to-the-orchestration"></a>向业务流程添加发送端口  
  
1.  下**BizTalk 业务流程**在工具箱中，拖动**端口**形状上的与端口图面。 此时将启动端口配置向导。  
  
2.  在欢迎屏幕上，单击**下一步**。  
  
3.  类型`SendPurchaseOrder`中**名称**字段，然后再单击**下一步**。  
  
4.  选择**使用现有的端口类型**。  
  
5.  下**可用端口类型**，选择`OrderProcess.PurchaseOrderPT`，然后单击**下一步**。  
  
6.  上**端口绑定屏幕**下**端口的通信的方向**，选择`I'll always be sending messages on this port`，然后单击**下一步**。  
  
7.  单击 **“完成”**。  
  
#### <a name="add-a-send-shape-to-the-orchestration"></a>向业务流程添加发送形状  
  
1.  下**BizTalk 业务流程**在工具箱中，拖动**发送**到业务流程设计器形状。 将其放置在 `Receive_PO` 接收形状的下方。  
  
2.  右键单击发送形状，并依次**属性窗口**。  
  
3.  类型`Send_PO`中**名称**字段。  
  
4.  选择`Message_PO`为**消息**属性。  
  
5.  选择`SendPurchaseOrder.PurchaseOrderOperation.Request`为**操作**属性。 此操作会将该端口与业务流程设计器中的发送形状关联在一起。  
  
#### <a name="add-a-decide-shape-to-the-orchestration"></a>将判定形状添加到业务流程  
  
1.  下**BizTalk 业务流程**在工具箱中，拖动**确定**到业务流程设计器形状。 将其放置在 `Send_PO` 发送形状的下方。  
  
2.  右键单击确定形状，并依次**属性窗口。**  
  
3.  类型`NeedsApproval`中**名称**字段。  
  
4.  在业务流程设计器中，单击**Rule_1**确定形状上。  
  
5.  在属性窗口中，键入`ApprovalRequired`为**名称**属性。  
  
6.  单击**表达式**属性字段，然后再单击省略号 (**...**) 按钮。  
  
7.  在 BizTalk 表达式编辑器中，键入或复制以下内容：  
  
    ```  
    Message_PO(OrderProcess.PropertySchema.Amount) > 1000  
    ```  
  
8.  单击 **“确定”**。  
  
#### <a name="add-another-send-port-to-the-orchestration"></a>向业务流程添加其他发送端口  
  
1.  下**BizTalk 业务流程**在工具箱中，拖动**端口**形状上的与端口图面。 此时将启动端口配置向导。  
  
2.  在欢迎屏幕上，单击**下一步**。  
  
3.  类型`SendToTasksList`中**名称**字段，然后再单击**下一步**。  
  
4.  选择**使用现有的端口类型**。  
  
5.  下**可用端口类型**，选择`OrderProcess.PurchaseOrderPT`，然后单击**下一步**。  
  
6.  上**端口绑定屏幕**下**端口的通信的方向**，选择`I'll always be sending messages on this port`。  
  
7.  下**端口绑定**，选择`Dynamic`，然后单击**下一步**。  
  
8.  单击 **“完成”**。  
  
#### <a name="add-a-send-shape-to-the-decide-shape"></a>向判定形状添加发送形状  
  
1.  下**BizTalk 业务流程**在工具箱中，拖动**发送**到业务流程设计器形状。 将其放置在 `ApprovalRequired` 形状的下方。  
  
2.  右键单击发送形状，并依次**属性窗口**  
  
3.  类型`CreateApprovalTask`中**名称**字段。  
  
4.  选择`Message_Task`为**消息**属性。  
  
5.  选择`SendToTasksList.PurchaseOrderOperation.Request`为**操作**属性。 此操作会将该端口与业务流程设计器中的发送形状关联在一起。  
  
## <a name="create-an-expression"></a>创建表达式  
 在此过程中，将向解决方案中添加可将任务路径值赋予变量的表达式形状。 此过程说明如何向业务流程添加逻辑以修改动态发送端口的属性。  
  
#### <a name="create-a-new-expression"></a>创建新的表达式  
  
1.  下**BizTalk 业务流程**在工具箱中，拖动**表达式**之前调整`CreateApprovalTask`发送形状。  
  
2.  右键单击表达式形状，并依次**属性窗口。**  
  
3.  类型`SetPortDestination`中**名称**字段。  
  
4.  单击**表达式**属性字段，然后再单击省略号 (**...**) 按钮。  
  
5.  在**BizTalk 表达式编辑器**，键入以下命令：  
  
    ```  
    SendToTasksList(Microsoft.XLANGs.BaseTypes.Address) = "wss://localhost/sites/WSSAdapterWalkthrough/Lists/Tasks/";  
    ```  
  
6.  单击 **“确定”**。  
  
## <a name="construct-a-new-message"></a>构造新消息  
 在此过程中，将向解决方案中添加构造形状，该形状将在业务流程内构造消息类型的新实例。 此过程说明如何创建作为入站消息副本的新消息，以及接下来如何修改该新消息的上下文属性。 此步骤是必需的，因为消息在 BizTalk 中是不可改变的，也就是说，在你构造原始消息之后，就不能修改原始消息了。  
  
#### <a name="add-a-construct-shape"></a>添加构造形状  
  
1.  下**BizTalk 业务流程**在工具箱中，拖动**构造消息**之前调整`SetPortDestination`表达式形状。  
  
2.  右键单击构造消息形状，并依次**属性窗口。**  
  
3.  类型`ConstructTaskMessage`中**名称**字段。  
  
4.  选择`Message_Task`为**消息构造**属性。  
  
5.  下**BizTalk 业务流程**在工具箱中，拖动**消息分配**调整`ConstructTaskMessage`**构造消息**形状。  
  
6.  在**属性窗口**，类型`InitTaskMessage`中**名称**字段。  
  
7.  单击**表达式**属性字段，然后再单击省略号 (**...**) 按钮。  
  
8.  在**BizTalk 表达式编辑器**，键入或复制下列文本：  
  
    ```  
    Message_Task = Message_PO;  
    Message_Task(WSS.ConfigOverwrite) = "no";  
    Message_Task(WSS.ConfigNamespaceAliases)= "orchns='http://OrderProcess.PurchaseOrder'";  
    Message_Task(WSS.ConfigPropertiesXml) = "<ConfigPropertiesXml><PropertyName1>Title</PropertyName1><PropertySource1>Approve %XPATH=//orchns:PurchaseOrder/orchns:PurchaseOrderID%</PropertySource1><PropertyName3>Status</PropertyName3><PropertySource3>Not Started</PropertySource3><PropertyName4>Priority</PropertyName4><PropertySource4>(1) High</PropertySource4></ConfigPropertiesXml>";  
    ```  
  
    > [!IMPORTANT]
    >  为这些上下文属性提供的值都是区分大小写的。 在使用上下文属性设置动态端口的配置值时，必须确保使用正确的大小写格式，否则，如果 BizTalk 尝试将文档路由到指定的发送端口，将会出现错误。  
  
9. 单击 **“确定”**。  
  
10. 单击**文件**，然后单击**保存所有**。  
  
## <a name="build-the-biztalk-project"></a>生成 BizTalk 项目  
 在此过程中，将生成并部署 BizTalk 项目。 此步骤对于创建和部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在运行时使用的程序集来说是必需的。  
  
#### <a name="build-and-deploy-the-solution"></a>生成并部署解决方案  
  
1.  单击**生成**，然后单击**生成 OrderProcess**。  
  
2.  单击**生成**，然后单击**部署 OrderProcess**。  
  
3.  关闭 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
## <a name="modify-the-receive-location-and-send-port"></a>修改接收位置和发送端口  
 在此过程中，将修改现有的接收位置和发送端口，以便对管道使用 XML 处理。 接收 XML 管道保持在业务流程处理过程中所使用的消息属性，发送 XML 管道保持在业务流程中应用的消息属性，这些消息属性随后将用于消息路由。  
  
#### <a name="modify-the-receive-location"></a>修改接收位置  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理。**  
  
2.  展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理管理单元**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收位置**节点。  
  
3.  右键单击`SourceLocation`，然后单击**属性**。  
  
4.  在**接收位置属性**对话框中，在**常规**，选择`XMLReceive`为**接收管道**属性。  
  
5.  单击 **“确定”**。  
  
#### <a name="modify-the-send-port"></a>修改发送端口  
  
1.  单击**发送端口**节点。  
  
2.  右键单击`SendToDestination`，然后单击**属性**。  
  
3.  在**发送端口属性**对话框中，在**常规**，选择`XMLTransmit`为**发送管道**属性。  
  
4.  选择**筛选器**选项卡。  
  
5.  选择现有条件，按 DELETE 键，，然后单击**确定**。  
  
#### <a name="start-a-new-send-port"></a>启动新的发送端口  
  
1.  单击**发送端口**节点。  
  
2.  右键单击`OrderProcess_1.0.0.0_OrderProcess.MyCompanyOrderProcess_SendToTasksList_<GUID>`，然后单击**启动**。  
  
> [!NOTE]
>  如果此项不可见，则可能必须刷新控制台。  
  
## <a name="bind-the-orchestration"></a>绑定业务流程的步骤  
 在此过程中，将业务流程绑定到指定端口。 此过程对于将物理端口绑定到你构建并部署的业务流程是必需的。  
  
#### <a name="bind-the-orchestration"></a>绑定业务流程的步骤  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**业务流程**节点。  
  
2.  右键单击`OrderProcess.MyCompanyOrderProcessing`业务流程，，然后单击**属性**。  
  
3.  选择**绑定**选项卡。  
  
4.  下**主机**，选择`BizTalkServerApplication`中**主机**字段。  
  
5.  下**绑定**，选择`FromSource`为`ReceivePurchaseOrder`入站逻辑端口。  
  
6.  下**绑定**，选择`SendToDestination`为`SendPurchaseOrder`出站逻辑端口。  
  
7.  单击 **“确定”**。  
  
8.  右键单击`OrderProcess.MyCompanyOrderProcessing`业务流程，，然后单击**启动**。  
  
## <a name="send-a-message-through-the-system"></a>通过系统发送消息  
 在此过程中，将创建 InfoPath 表单并将其上载到 Windows SharePoint Services 网站。 Windows SharePoint Services 适配器将接受该消息并将其存档在存档文档库中，然后将其发送到目标文档库。 在处理此消息的过程中，将访问有助于确定目标的 Windows SharePoint Services 上下文属性。  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a>创建要通过系统发送的 InfoPath 表单  
  
1.  打开 Web 浏览器并导航到所创建站点的 URL。 例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
2.  在“快速启动”菜单中，单击“`InfoPathSolutions`”。  
  
3.  单击`PurchaseOrder`文件以显示**文件下载**对话框中，然后单击**打开**。 InfoPath 将加载该表单。  
  
4.  在**采购订单 ID**字段中，键入`1003`。  
  
5.  在**帐单到**字段中，键入`John Doe`。  
  
6.  在**量**字段中，键入`1750`。  
  
7.  在**采购订单日期**字段中，键入`1/3/2005`。  
  
8.  单击 **“保存”**。  
  
9. 在**另存为**对话框中，键入`http://<server_name>/sites/WSSAdapterWalkthrough/Source`中**文件名**字段，，然后按 ENTER。  
  
10. 类型`PurchaseOrder3.xml`中**文件名**字段，然后再单击**保存**。  
  
11. 关闭 InfoPath。  
  
12. 在 Web 浏览器中，单击**文档和列表**。  
  
13. 下**文档库**，单击**目标**。  
  
14. 在目标文档库中，你现在将看到你在此库中列出了消息。 你还将在存档文档库中找到存档副本。  
  
15. 单击 **“主页”**。  
  
16. 下**列出**，单击**任务**。  
  
17. 在“任务”列表中，将看到新创建的批准任务。  
  
> [!NOTE]
>  由于采购订单金额超过了 1,000.00 美元，因此创建了该任务。  
  
## <a name="summary"></a>摘要  
 在本演练中，你学习了如何访问 Windows SharePoint Services 上下文属性，以及如何确定经过动态端口的消息的目标。  
  
## <a name="next-steps"></a>后续步骤  
 接下来请学习 Windows SharePoint Services 适配器部分的其余内容。 有关详细信息，请参阅“另请参见”部分中的主题。  
  
## <a name="see-also"></a>另请参阅  
 [什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services 适配器演练](../core/windows-sharepoint-services-adapter-walkthroughs.md)