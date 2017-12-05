---
title: "教程： 使用 TIBCO 企业消息服务的 BizTalk 适配器将数据发送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1912d594-3839-4e04-bc40-93bd7cc0b309
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2e2dc6fe0c1427ac959ce77d6ff4f46b4f4285
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-send-data"></a>教程 1：使用适用于 TIBCO Enterprise Message Service 的 BizTalk 适配器来发送数据
您可以使用用于 TIBCO Enterprise Message Service (EMS) 的 BizTalk 适配器将数据发送至 TIBCO 系统。 本演练描述了对此进行说明的一个 SDK 示例。  
  
## <a name="prerequisites"></a>先决条件  
  
-   用于 TIBCO EMS 的 BizTalk 适配器要求将 TIBCO EMS C# API（即 TIBCO.EMS.dll）添加到全局程序集缓存 (GAC) 中。 有关安装程序集的详细信息，请参阅[TIBCO 企业消息服务要求和限制](../core/tibco-enterprise-message-service-requirements-and-limitations.md)。  
  
-   为了生成并部署该示例，请在运行此适配器的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例从某文件夹中选择一个 XML 文件，将该文件发送至业务流程，然后使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器在 TIBCO 系统中创建记录。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 此示例中，在 Visual Studio 中设计演示 BizTalk 适配器用于 TIBCO 企业消息服务与 BizTalk 业务流程的基本功能。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例的默认位置为  
  
 C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWaySend  
  
 下表列出并介绍了示例中的文件。  
  
|**运行时项目文件名**|**运行时项目文件说明**|  
|----------------------------------|------------------------------------------|  
|OneWaySend.btproj<br /><br /> OneWaySend.sln|应用程序的项目和解决方案文件。|  
|Schema.xsd|应用程序的架构文件。|  
|Orchestration.odx|应用程序使用的业务流程。|  
|TIBCOEMSOneWaySend.snk|强命名密钥文件。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a>创建用于 TIBCO EMS 的 BizTalk 适配器的新实例  
  
1.  启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。 单击**启动**，**所有程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
3.  右键单击**适配器**和指向**新建**，**适配器**以显示**适配器属性**对话框。  
  
4.  输入一个值**名称**字段，例如**TIBCO EMS**。  
  
5.  选择**TIBCO 企业消息系统**从列表中可用的适配器**适配器**下拉列表中单击**确定**。  
  
#### <a name="create-a-biztalk-send-port"></a>创建 BizTalk 发送端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**。  
  
2.  右键单击**发送端口**和指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。  
  
3.  输入一个值**名称**字段，例如**TIBCOEMSOneWaySP**。  
  
4.  从中的可用适配器的列表中选择 TIBCO EMS 适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。  
  
    > [!NOTE]
    >  该值是在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建 TIBCO Enterprise Message System 适配器时所指定的名称。  
  
5.  输入值**服务器连接定义**:  
  
    |**属性**|**值**|  
    |------------------|---------------|  
    |目标|服务器目标队列或主题名称。|  
    |端口号|TIBCO 服务器正在侦听的端口。 默认值为 7222。|  
    |服务器名称|TIBCO EMS 服务器的名称。|  
  
6.  输入值**用户凭据**:  
  
    |**属性**|**值**|  
    |------------------|---------------|  
    |密码|TIBCO EMS 服务器的密码。|  
    |用户名|TIBCO EMS 服务器的用户名。|  
  
     有关属性的详细信息，请参阅[创建 TIBCO 企业消息服务发送处理程序](../core/creating-tibco-enterprise-message-service-send-handlers.md)。  
  
7.  单击 **“确定”**。  
  
8.  选择**XML 传输**从管道中提供的列表的管道**发送管道**下拉列表中单击**确定**。  
  
9. 右键单击发送端口，然后单击**启动**登记和启动发送端口。  
  
#### <a name="create-a-file-receive-port"></a>创建文件接收端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收端口**。  
  
2.  右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**以显示接收端口属性对话框。  
  
3.  输入一个值**名称**字段，例如**TIBCOEMSOneWayFileRP**，然后单击**确定**。  
  
#### <a name="create-a-file-receive-location"></a>创建文件接收位置  
  
1.  为要监视的文件接收位置创建文件夹，例如 C:\Filesource。  
  
2.  右键单击新的接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。  
  
3.  输入一个值**名称**字段，例如**TIBCOEMSOneWayFileRL**。  
  
4.  选择**文件**从列表中的可用适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。  
  
5.  输入以前为创建的文件夹的位置**接收文件夹**属性，然后单击**确定**。  
  
6.  选择**XMLReceive**从列表中的可用管道**接收管道**下拉列表框中，单击**确定**。  
  
7.  右键单击接收位置，然后单击**启用**。  
  
#### <a name="generate-a-document-instance-from-the-adapter-schema"></a>从适配器架构生成文档实例  
  
1.  右击 Schema.xsd 在解决方案资源管理器中的，单击**属性**。  
  
2.  在属性窗口中，单击以选中**输出实例文件名**选项下**常规**类别。  
  
3.  单击省略号按钮 （…） 以显示**选择输出文件**对话框。  
  
4.  指定的文件夹和输出文件实例的名称，例如**C:\instance.xml**单击**保存**。  
  
    > [!NOTE]
    >  请勿指定为此处的文件接收位置指定的文件夹位置。  
  
5.  右击 Schema.xsd 在解决方案资源管理器中的，单击**生成实例**在指定的位置生成文档实例。  
  
#### <a name="modify-the-generated-document-instance"></a>修改生成的文档实例  
  
1.  在文本编辑器（如记事本）中打开生成的文档实例，并编辑文档实例的内容以确保此数据将在 TIBCO 系统中生成唯一的记录。 例如，下面的代码显示了此数据文件的第一部分：  
  
    ```  
    <ns0:Root xmlns:ns0="http://TibcoEMSOne_WaySend.TibcoEMSOneWaySendSchema">  
      <Name>Punya Palit</Name>  
      <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  
  
2.  保存修改后的文档实例。  
  
#### <a name="build-and-deploy-the-project"></a>生成并部署项目  
  
1.  右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**属性**以启动项目设计器中为该项目。  
  
2.  单击**部署**选项卡。  
  
3.  输入适当的值为**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。  
  
4.  右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**部署**以生成项目并将其部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。  
  
#### <a name="bind-and-enlist-the-orchestration"></a>绑定并登记业务流程  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。  
  
2.  单击**刷新**中 MMC 工具栏或按按钮**F5**密钥刷新你键盘上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。  
  
3.  双击要显示的业务流程**业务流程属性**对话框。  
  
4.  单击**绑定**显示业务流程的绑定选项对话框的左窗格中。  
  
5.  指定绑定选项的适当值，例如：  
  
    |**参数**|**值**|  
    |-------------------|---------------|  
    |主机|BizTalkServerApplication|  
    |FileReceivePort|TIBCOEMSOneWayFileRP|  
    |TibcoEMSOneWaySendPort|TIBCOEMSOneWaySP|  
  
6.  单击“确定”。  
  
#### <a name="start-the-orchestration"></a>启动业务流程  
  
-   在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击业务流程，然后单击**启动**登记和启动业务流程。  
  
#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a>将文档实例拖到由文件接收位置监视的文件夹  
  
-   将早期创建的文档实例复制到应用程序监视的文件接收文件夹。  
  
#### <a name="verify-that-the-tibco-system-is-updated"></a>验证 TIBCO 系统是否已更新  
  
-   使用 TIBCO Web 界面验证是否已从 XML 文件中的数据创建记录。  
  
 成功处理文档实例后，会发生以下事件序列：  
  
1.  文件适配器从文件夹中检索文件，并作为 BizTalk 消息将其发布到 MessageBox。  
  
2.  业务流程订阅此发布消息，以便 BizTalk 消息引擎会激活业务流程的实例，并将该消息发送到该业务流程实例。  
  
3.  业务流程实例使用业务流程中指定的逻辑处理该消息，并将该消息发布回 MessageBox。  
  
4.  TIBCO 发送端口订阅此发布消息，以便 BizTalk 消息引擎将消息发送到 TIBCO 发送端口。  
  
5.  发送端口将消息传递给用于 TIBCO Enterprise Message Service 的 BizTalk 适配器。  
  
6.  用于 TIBCO Enterprise Message Service 的 BizTalk 适配器将消息发送到 TIBCO 系统。  
  
## <a name="see-also"></a>另请参阅  
 [教程： 使用 BizTalk Adapter for TIBCO 企业消息服务接收数据](../core/tutorial-us-the-biztalk-adapter-for-tibco-message-service-to-receive-data.md)   
 [教程： 使用 Microsoft BizTalk Adapter for TIBCO 企业消息服务](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)