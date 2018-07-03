---
title: 演练： 模块 2-将集成 Office 与 Windows SharePoint Services 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- InfoPath forms, creating
- InfoPath forms, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, integrating Microsoft Office
- Windows SharePoint Services, document libraries
ms.assetid: 2f81a712-bb20-4c32-bbac-fb438deded38
caps.latest.revision: 48
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79297c55152688821ba5b472335eade1d31b0ffe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022387"
---
# <a name="walkthrough-module-2---integrating-office-with-the-windows-sharepoint-services-adapter"></a>演练： 模块 2-Office 与 Windows SharePoint Services 适配器相集成
本演练是的延续[演练： 模块 1-发送和接收消息与 Windows SharePoint Services 适配器](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)，并演示如何将与 Microsoft Office 集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基于内容的创建路由 (CBR) 应用程序。 Windows SharePoint Services 适配器的介绍，请参阅[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)。  
  
## <a name="prerequisites"></a>必要條件  
 以下为执行本主题中步骤的前提条件：  
  
- 必须具有包含 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 完整安装的单服务器部署。  
  
- 你必须完成以下演练：[演练： 模块 1-发送和接收消息与 Windows SharePoint Services 适配器](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)  
  
  在多服务器部署中使用 Windows SharePoint Services 适配器的信息，请参阅[设置和部署 Windows SharePoint Services 适配器](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)。  
  
## <a name="create-a-biztalk-project"></a>创建 BizTalk 项目  
 在此过程中，使用 BizTalk 编辑器来创建空的 BizTalk 项目和架构。 此过程对于为随后将用到的 InfoPath 表单创建架构是必需的。  
  
#### <a name="create-a-strong-name-key-file"></a>创建强名称密钥文件  
  
1.  启动**Visual Studio 命令提示符**。  
  
2.  类型`sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`，然后按**Enter**。 将写入密钥对。  
  
3.  关闭命令提示符。  
  
#### <a name="create-an-empty-biztalk-project"></a>创建空的 BizTalk 项目  
  
1.  启动**Microsoft Visual Studio**。  
  
2.  单击**文件**，**新建**，然后单击**项目**。  
  
3.  下**项目类型**，选择**BizTalk 项目**。  
  
4.  下**模板**，选择**空的 BizTalk Server 项目**。  
  
5.  类型`OrderProcess`中**名称**字段。  
  
6.  键入到工作目录中的文件路径**位置**字段。 例如， `C:\WSSAdapterWalkthrough\`。  
  
7.  单击“确定” 。  
  
#### <a name="associate-the-key-file-with-the-assembly"></a>将密钥文件与程序集相关联  
  
1.  在解决方案资源管理器中右键单击`OrderProcess`项目，然后依次**属性**启动项目设计器。  
  
2.  单击“签名”  选项卡。  
  
3.  选择“为程序集签名”  选项，单击下拉列表中的“选择强名称密钥文件”  选项，然后单击“浏览” 。  
  
4.  键入 `C:\WSSAdapterWalkthrough\OrderProcess.snk`。  
  
5.  单击 **“打开”**。  
  
#### <a name="create-an-xsd-schema-by-using-the-biztalk-editor"></a>使用 BizTalk 编辑器创建 XSD 架构  
  
1. 在解决方案资源管理器中右键单击`OrderProcess`项目中，单击**添加**，然后单击**新项**。  
  
2. 下**类别**，单击**架构文件**。  
  
3. 下**模板**，单击**架构**。  
  
4. 类型`OrderProcessSchema`中**名称**字段，，然后单击**添加**。  
  
5. 在属性窗口`OrderProcessSchema`，选择`Qualified`有关**Element FormDefault**属性。  
  
6. 在属性窗口`OrderProcessSchema`，类型`http://OrderProcess.PurchaseOrder`中**Target Namespace**字段。  
  
7. 在中**BizTalk 编辑器**，右键单击`Root`，单击**重命名**，然后键入`PurchaseOrder`。  
  
8. 右键单击**PurchaseOrder**节点中，单击**插入 Schema 节点**，然后单击**子字段元素**。  
  
9. 将其命名为 `PurchaseOrderID`。  
  
10. 创建另一个子字段元素并将其命名为 `BillTo`。  
  
11. 创建另一个子字段元素并将其命名为 `Amount`。  
  
12. 在属性窗口中设置**数据类型**属性`Amount`为 xs: unsignedint。  
  
13. 创建另一个子字段元素并将其命名为 `PurchaseOrderDate`。  
  
14. 在属性窗口中设置**数据类型**属性`PurchaseOrderDate`为 xs: datetime。  
  
15. 单击**文件**，然后单击**全部保存**。  
  
16. 关闭 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
## <a name="create-an-infopath-form"></a>创建 InfoPath 表单  
 在此过程中，基于在上一步骤中创建的架构来创建另一个文档库和 InfoPath 表单。 此 InfoPath 表单将用于向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提交文档。  
  
> [!NOTE]
>  本演练需要 Microsoft Office InfoPath 2007  
  
#### <a name="create-a-new-document-library"></a>创建新文档库  
  
1.  打开 Web 浏览器并导航到所创建站点的 URL。 例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
2.  在顶部导航栏上，单击**创建**。  
  
3.  下**文档库**，单击**文档库**。  
  
4.  在中**名称和描述**部分中，键入`InfoPathSolutions`中**名称字段**。  
  
5.  在中**导航**部分中，选择**是**快速启动栏上显示此窗体库。  
  
6.  在中**文档模板**部分中，选择`None`有关**文档模板**。  
  
7.  单击 **“创建”**。 将重定向到刚创建的空库。  
  
8.  在左侧，单击**修改设置和栏**。  
  
9. 下**列**，单击**添加一个新列**。  
  
10. 下**名称和类型**，类型`Namespace`中**名称**字段。  
  
11. 单击“确定” 。  
  
12. 关闭 `WSSAdapterWalkthrough` 网站。  
  
#### <a name="create-an-infopath-form-based-on-the-orderprocessschema-schema-file"></a>基于 OrderProcessSchema 架构文件创建 InfoPath 表单  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office InfoPath 2007**。  
  
2.  在中**填写表单**对话框中，选择**设计窗体。**  
  
3.  在中**设计窗体**任务窗格中，选择**从 XML 文档或架构新建**。  
  
4.  在中**数据源向导**，单击**浏览**并选择在上一个过程中创建的架构文件。 例如， `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`。  
  
5.  单击“下一步” ，然后单击“完成” 。  
  
6.  在中**数据源**任务窗格中，右键单击**PurchaseOrder**节点，，然后单击**带有控件的节**。 这将在模板上创建表单。  
  
7.  单击**文件**，单击**保存**，然后单击**保存**。  
  
8.  在中**另存为**对话框中，键入`PurchaseOrder.xsn`中**文件名**字段，，然后单击**保存**。  
  
9. 单击**文件**，然后单击**发布**。  
  
10. 在中**发布向导**，单击**下一步**。  
  
11. 选择**到 Web 服务器**，然后单击**下一步**。  
  
12. 键入路径和文件名你`InfoPathSolutions`文档库，然后依次**下一步**。 例如， `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`。  
  
13. 单击**完成**，然后单击**关闭**。  
  
14. 关闭 Microsoft InfoPath。  
  
## <a name="modify-the-sharepoint-document-libraries"></a>修改 SharePoint 文档库  
 在此过程中，将更新 PurchaseOrder.xsn 文件的命名空间属性，并修改目标文档库。 为基于内容的路由方案确定已发布文档的订户时，此命名空间用作变量。  
  
#### <a name="update-the-namespace-for-purchaseorderxsn"></a>更新 PurchaseOrder.xsn 的命名空间  
  
1.  打开 Web 浏览器并导航到所创建站点的 URL。 例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
2.  在左侧下,**文档**，单击`InfoPathSolutions`。  
  
3.  将指针移`PurchaseOrder.xsn`，右键单击它，，然后单击**编辑属性**。  
  
4.  类型`http://OrderProcess.PurchaseOrder`中**Namespace**字段，，然后单击**保存并关闭**。  
  
#### <a name="modify-the-destination-document-library"></a>修改目标文档库  
  
1.  在顶部导航栏上，单击**文档和列表**。  
  
2.  下**文档库**，单击**目标**。  
  
3.  在左侧，单击**修改设置和栏**。  
  
4.  下**列**，单击**添加新列**。  
  
5.  下**名称和类型**，类型`Partner Name`中**列名**字段。  
  
6.  单击“确定” 。  
  
7.  关闭 `WSSAdapterWalkthrough` 网站。  
  
## <a name="modify-the-send-port-from-walkthrough-1"></a>修改演练 1 中的发送端口  
 在此过程中，您将修改演练 1 中的发送端口。 只有执行此过程，才能确保将此演练中处理的文档正确路由到该发送端口。  
  
#### <a name="modify-the-send-port"></a>修改发送端口  
  
1. 打开**BizTalk Server 管理。**  
  
2. 展开**Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后依次**发送端口**节点。  
  
3. 右键单击`SendToDestination`，然后单击**属性**。  
  
4. 下**传输**，单击**配置**。  
  
5. 在中**文件名**字段中，键入`PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`。  
  
6. 在中**Namespace 别名**字段中，键入`pons="http://OrderProcess.PurchaseOrder"`。  
  
7. 在中**模板文档库**，类型`InfoPathSolutions`。  
  
8. 在中**模板 Namespace 栏**，类型`Namespace`。  
  
9. 选择`Yes`有关**Microsoft Office 集成**属性。  
  
10. 下**Windows SharePoint Services 集成**，类型`Partner Name`中**栏 01**字段。  
  
11. 类型`%XPATH=//pons:PurchaseOrder/pons:BillTo%`中**01 列值**字段中，单击**确定**，然后单击**确定**以退出**发送端口属性**对话框。  
  
#### <a name="restart-the-send-port"></a>重新启动发送端口  
  
1.  在中**BizTalk 管理控制台**，单击**发送端口**节点。  
  
2.  右键单击`SendToDestination`，然后单击**取消登记**。  
  
3.  右键单击`SendToDestination`，然后单击**启动**。  
  
4.  关闭**BizTalk 管理控制台**。  
  
## <a name="send-a-message-through-the-system"></a>通过系统发送消息  
 在此过程中，将创建 InfoPath 表单并将其上载到 Windows SharePoint Services 网站。 Windows SharePoint Services 适配器将接受该消息并将其存档在存档文档库中，然后将其发送到目标文档库。 此过程说明文档是如何通过 Windows Sharepoint Services 适配器，从 Sharepoint 网站流出，通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，到达 Sharepoint Services 网站的。  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a>创建要通过系统发送的 InfoPath 表单  
  
1.  打开 Web 浏览器并导航到所创建站点的 URL。 例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。  
  
2.  在左侧下,**文档**，单击`InfoPathSolutions`。  
  
3.  单击`PurchaseOrder`文件以显示**文件下载**对话框中，然后单击**打开**。 InfoPath 将加载该表单。  
  
4.  在中**采购订单 ID**字段中，键入`1002`。  
  
5.  在中**付款人**字段中，键入`John Doe`。  
  
6.  在中**量**字段中，键入`750`。  
  
7.  在中**采购订单日期**字段中，键入`1/2/2005`。  
  
8.  单击 **“保存”**。  
  
9. 在中**另存为**对话框中，键入`http://<server_name>/sites/WSSAdapterWalkthrough/Source`中**文件名**字段，并按 Enter。  
  
10. 类型`PurchaseOrder2.xml`中**文件名**字段，，然后单击**保存**。  
  
11. 关闭 Microsoft Office InfoPath。  
  
12. 在 Web 浏览器中，在顶部导航栏上，单击**文档和列表**。  
  
13. 下**文档库**，单击**目标**。  
  
14. 在目标文档库中，现在你将看到你的消息已列出。 你还将在存档文档库中找到存档副本。  
  
15. 在目标文档库中，单击 `PurchaseOrder1.xml`。 请注意，此 XML 文件通过 Microsoft Internet Explorer 打开。  
  
16. 在目标文档库中，单击 `PurchaseOrder2.xml`。 请注意，此 XML 文件通过 Microsoft Office InfoPath 打开。  
  
> [!NOTE]
>  在目标文档库中，“文件名”列应该包含“PurchaseOrderID”字段的值，“合作伙伴名称”列应该包含“BillTo”字段的值。  
  
## <a name="summary"></a>“摘要”  
 在本演练中，你学习了如何使用 Windows SharePoint Services 适配器和基于内容的路由 (CBR) 来添加与 Microsoft InfoPath 更紧密的集成。  
  
## <a name="next-steps"></a>后续步骤  
 现在，已完成本演练中，执行[演练： 模块 3-从业务流程中访问 SharePoint 属性](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)演练的工作已完成本演练中，使用扩展集成业务流程到项目中，并演示如何访问 SharePoint 属性从在其中。  
  
## <a name="see-also"></a>请参阅  
 [什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services 适配器演练](../core/windows-sharepoint-services-adapter-walkthroughs.md)