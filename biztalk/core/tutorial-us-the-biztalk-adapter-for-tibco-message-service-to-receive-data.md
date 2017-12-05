---
title: "教程： 使用 BizTalk Adapter for TIBCO 企业消息服务接收数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc5a63ec-1897-4c9b-b37f-cdcec151b1c9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ee9994861772be8fabe04a04e9bb30111cc1bc4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-receive-data"></a>教程：使用 TIBCO Enterprise Message Service 的 BizTalk 适配器以接收数据
您可以使用适用于 TIBCO Enterprise Message Service (EMS) 的 BizTalk 适配器从 TIBCO 系统接收数据。 本演练描述了对此进行说明的一个 SDK 示例。  
  
## <a name="prerequisites"></a>先决条件  
  
-   适用于 TIBCO Enterprise Message Service 的 BizTalk 适配器要求您向全局程序集缓存 (GAC) 中添加 TIBCO EMS C# API 和 TIBCO.EMS.dll。 有关安装程序集的详细信息，请参阅[TIBCO 企业消息服务要求和限制](../core/tibco-enterprise-message-service-requirements-and-limitations.md)。  
  
-   为了生成并部署该示例，请在运行此适配器的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例从文件夹提取 XML 文件，将该文件发送到业务流程，然后使用适用于 TIBCO Enterprise Message Service 的 BizTalk 适配器从 TIBCO 系统检索数据。 结果将写入一个 XML 文件。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 此示例中，在 Visual Studio 中设计演示 BizTalk 适配器用于 TIBCO 企业消息服务与 BizTalk 业务流程的基本功能。  
  
> [!NOTE]
>  本示例假定您知道如何发送来自 TIBCO 的消息以供应用程序处理。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例的默认位置为  
  
 C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive  
  
 下表显示了本示例中的文件及其用途说明：  
  
|**运行时项目文件名**|**运行时项目文件说明**|  
|----------------------------------|------------------------------------------|  
|OneWayReceive.btproj,<br /><br /> OneWayReceive.sln|应用程序的项目和解决方案文件。|  
|Schema.xsd,|应用程序的架构文件。|  
|Orchestration.odx|应用程序使用的业务流程。|  
|TIBCOEMSOneWaySend.snk|强命名密钥文件。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a>创建用于 TIBCO EMS 的 BizTalk 适配器的新实例  
  
1.  启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。 单击**启动**，**程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
3.  右键单击**适配器**和指向**新建**，**适配器**以显示**适配器属性**对话框。  
  
4.  输入一个值**名称**字段，例如**TIBCO EMS**。  
  
5.  选择**TIBCO 企业消息系统**从列表中可用的适配器**适配器**下拉列表中单击**确定**。  
  
#### <a name="create-a-biztalk-receive-port"></a>创建 BizTalk 接收端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收端口**。  
  
2.  右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**以显示接收端口属性对话框。  
  
3.  输入一个值**名称**字段，例如**TIBCOEMSOneWayRP**，然后单击**确定**。  
  
#### <a name="create-a-biztalk-receive-location"></a>创建 BizTalk 接收位置  
  
1.  右键单击新的接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。  
  
2.  输入一个值**名称**字段，例如**TIBCOEMSOneWayRL**。  
  
3.  从中的可用适配器的列表中选择 TIBCO EMS 适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。  
  
    > [!NOTE]
    >  该值是在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建 TIBCO 适配器时指定的名称。  
  
4.  输入值**服务器连接定义**:  
  
    |**属性**|**值**|  
    |------------------|---------------|  
    |目标|服务器目标队列或主题名称。|  
    |端口号|TIBCO 服务器正在侦听的端口。 默认值为 7222。|  
    |服务器名称|TIBCO EMS 服务器的名称。|  
  
5.  输入值**用户凭据**:  
  
    |**属性**|**值**|  
    |------------------|---------------|  
    |密码|TIBCO EMS 服务器的密码。|  
    |用户名|TIBCO EMS 服务器的用户名。|  
  
     有关属性的详细信息，请参阅[创建 TIBCO 企业消息服务接收处理程序](../core/creating-tibco-enterprise-message-service-receive-handlers.md)。  
  
6.  单击 **“确定”**。  
  
7.  选择**XMLReceive**从列表中的可用管道**接收管道**下拉列表框中，单击**确定**。  
  
8.  右键单击接收位置，然后单击**启用**。  
  
#### <a name="create-a-one-way-file-send-port"></a>创建单向文件发送端口  
  
1.  创建发送端口要使用的目标文件夹，例如 C:\FilesOut。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**。  
  
3.  右键单击**发送端口**和指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。  
  
4.  输入一个值**名称**字段，例如**TIBCOEMSOneWayFileSP**。  
  
5.  选择**文件**从列表中的可用适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。  
  
6.  有关**目标文件夹**属性，输入前面创建的文件夹的位置，然后单击**确定**。  
  
7.  选择**XMLTransmit**从管道中提供的列表的管道**发送管道**下拉列表中单击**确定**。  
  
8.  右键单击发送端口，然后单击**启动**登记和启动发送端口。  
  
#### <a name="build-and-deploy-the-project"></a>生成并部署项目  
  
1.  右键单击解决方案资源管理器中的 OneWayReceive 项目，然后单击**属性**以启动项目设计器中为该项目。  
  
2.  单击**部署**选项卡。  
  
3.  输入适当的值为**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。  
  
4.  右键单击解决方案资源管理器中的 OneWayReceive 项目，然后单击**部署**以生成项目并将其部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。  
  
#### <a name="bind-and-enlist-the-orchestration"></a>绑定并登记业务流程  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。  
  
2.  单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**密钥刷新你键盘上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。  
  
3.  双击要显示的业务流程**业务流程属性**对话框。  
  
4.  单击**绑定**显示业务流程的绑定选项对话框的左窗格中。  
  
5.  指定绑定选项的适当值，例如：  
  
    |**参数**|**值**|  
    |-------------------|---------------|  
    |主机|BizTalkServerApplication|  
    |FileSendPort|TIBCOEMSOneWayFileSP|  
    |TibcoEMSOneWayReceiveOperation|TIBCOEMSOneWayRP|  
  
6.  单击 **“确定”**。  
  
#### <a name="start-the-orchestration"></a>启动业务流程  
  
-   在[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]管理控制台中，右键单击业务流程，然后单击**启动**登记和启动业务流程。  
  
#### <a name="verify-that-the-application-receives-a-message"></a>验证应用程序是否收到消息  
  
-   打开将文件发送端口配置为发送到的目标文件夹，并验证是否已生成输出文档。 此文件应包含适用于 TIBCO Enterprise Message Service 的 BizTalk 适配器处理的查询结果。  
  
 成功处理文档实例后，会发生以下事件序列：  
  
1.  TIBCO EMS 适配器从 TIBCO 系统接收消息，并将其作为 BizTalk 消息发布到 MessageBox。  
  
2.  业务流程会订阅此发布的消息，以便 BizTalk 消息引擎能够激活业务流程的实例，并将该消息发送到业务流程实例。  
  
3.  业务流程实例将此消息发布回 MessageBox。  
  
4.  文件发送端口会订阅此消息，以便 BizTalk 能够将消息发送到文件适配器。  
  
5.  文件适配器将包含结果集的消息写入到指定的输出文件夹。  
  
## <a name="see-also"></a>另请参阅  
 [教程： 使用 TIBCO 企业消息服务的 BizTalk 适配器将数据发送](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md)   
 [教程： 使用 Microsoft BizTalk Adapter for TIBCO 企业消息服务](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)