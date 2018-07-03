---
title: '步骤 3a: Salesforce 机会通知接收到 BizTalk Server |Microsoft Docs'
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
ms.openlocfilehash: 4a51340d8812a8b42871d63c8fc52eeee6e05312
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999438"
---
# <a name="step-3a-receive-salesforce-opportunity-notification-into-biztalk-server"></a>步骤 3a: Salesforce 机会通知接收到 BizTalk Server
在此步骤中，我们将开始创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 我们应先包括将从 Salesforce 获取的机会通知消息的消息架构，然后再开始创建业务流程来处理消息。  
  
### <a name="to-include-the-salesforce-opportunities-notification-schema"></a>包括 Salesforce 机会通知架构  
  
1. 登录到 Salesforce.com 门户。 在 Salesforce 门户中，单击位于页面右上角的登录名，然后单击**安装程序**。  
  
2. 在左窗格中下,**应用安装程序**，展开**创建**，展开**工作流和审批**，然后单击**工作流规则**。  
  
3. 在中**所有工作流规则**页上，单击**关闭机会**前面创建的工作流。  
  
4. 在中**关闭机会**工作流规则页上，单击**NewOp1**出站消息工作流操作。  
  
5. 在中**NewOp1**出站消息工作流操作页上，右键单击该链接**单击查看 WSDL**，单击**目标另存为**，然后指定你想要保存的位置WSDL 中。  
  
   > [!NOTE]
   >  必须使用 .wsdl 扩展名保存该文件。  
  
6. 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中创建 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 对于本教程，让我们将项目命名为`BtsSalesforceIntegration`。  
  
7. 右键单击[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目在解决方案资源管理器中，依次指向**添加**，然后单击**添加生成的项**。  
  
8. 在中**添加生成的项**对话框中，单击**使用 WCF 服务**，然后单击**添加**以启动**BizTalk WCF 服务使用**向导。 在欢迎页上，单击**下一步**。  
  
9. 上**元数据来源**页上，选择**元数据文件 （WSDL 和 XSD）** 选项，并单击**下一步**。  
  
10. 上**元数据文件**页上，单击**添加**，然后导航到保存从 Salesforce 门户下载的 WSDL 文件的位置。 选择 WSDL 文件，然后单击**下一步**。  
  
11. 在下一页上，将设置为命名空间`NotificationService`，然后单击**导入**。 此时向导会将架构文件和业务流程添加到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目。 用于从 Salesforce 接收机会通知的消息架构是**NotificationService_soap_sforce_com_2005_09_outbound.xsd**。  
  
### <a name="to-create-an-orchestration-to-receive-the-notification-message"></a>创建用于接收通知消息的业务流程  
  
1. 完成后**BizTalk WCF 服务使用**向导、 业务流程 (**NotificationService.odx**，在此示例中) 添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。  
  
2. 打开业务流程文件，并在业务流程视图中添加两个新消息变量。 命名它们`NotificationMessage`和`NotificationAck`。 为这两个消息变量设置消息类型，如下所示：  
  
   1.  设置**NotificationMessage**到*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notifications*。 此消息变量表示从 Salesforce 收到的机会通知消息。  
  
   2.  设置**NotificationAck**到*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notificationsResponse*。 此消息变量表示发送回 Salesforce 的机会通知确认消息。  
  
3. 向业务流程添加“接收”形状。 在该形状上设置以下属性：  
  
   1.  设置**激活**到**True**。  
  
   2.  设置**名称**到*ReceiveNotificationMessage*。  
  
   3.  设置**消息**到*NotificationMessage*。  
  
4. 在“接收”形状后添加“构造消息”形状。 将为该消息形状`ConstructNotificationResponse`并设置**构造的消息**属性设置为`NotificationAck`。 在构造消息中，我们还会创建一个映射来生成要发送回 Salesforce 的通知确认消息。  
  
   1.  在“构造消息”形状中，添加“转换”形状。 双击转换形状，然后在转换配置对话框中，选择**新的映射**选项。  
  
   2.  映射名称指定为`BtsSalesforceIntegration.MapNotificationResponse`。  
  
   3.  设置源作为**NotificationMessage**和作为目标**NotificationAck**。  
  
   4.  请确保复选框**当我单击确定时，启动 BizTalk 映射器**处于选中状态。  
  
   5.  在中**MapNotificationResponse.btm**，我们将创建要发送回 Salesforce 的通知响应。 每次 Salesforce 发送通知，它都需要发送确认进行回应。 通知响应消息的架构显示**Ack**在响应中的元素属于布尔类型。 因此，在映射中，你必须删除**值映射**functoid，并设置其两个输入值 （Condition 和 Result） 到`true`。 单击**确定**以保存该 functoid。  
  
   6.  连接**值映射**到 functoid **Ack**目标架构中的元素。  
  
5. 在业务流程中，在“构造消息”形状后添加要用于将确认发送回 Salesforce 的“发送”形状。  
  
   -   设置**名称**到*SendNotificationAck*。  
  
   -   设置**消息**到*NotificationAck*。  
  
6. 在业务流程中，添加用于接收 Salesforce 通知消息并在发送确认作为响应的端口。 在“端口配置”向导中，选择以下选项：  
  
   - 将端口名称指定为`SalesforceNotificationPort`。  
  
   - 选择用于创建新的端口类型的选项。  
  
   - 设置**通信模式**到*请求-响应*。  
  
   - 设置**端口通信方向**到*我将接收请求并发送响应*并设置**端口绑定**到*指定更高版本*.  
  
     连接**请求**操作的端口与接收形状 (*ReceiveNotificationMessage*) 和**响应**该端口与发送形状的操作 (*SendNotificationAck*)。 下面的屏幕快照描述了业务流程的一部分，该部分从 Salesforce 接收机会通知并发送回确认：  
  
     ![机会通知接收和发送响应](../core/media/bts-sf-recvnotificationorch.jpg "BTS_SF_RecvNotificationOrch")  
  
   迄今，我们已设置这样的解决方案：从 Salesforce 接收机会通知并发送回确认。 在随后的主题中，我们将在此解决方案的基础上构建，并开始处理机会通知，以获取有关可获得的销售机会种类的详细信息。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：在 Visual Studio 中创建 BizTalk Server 解决方案](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)