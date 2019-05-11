---
title: 教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器发送数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1912d594-3839-4e04-bc40-93bd7cc0b309
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 217abb544fa81faa667ca066d53bc126b88dcc48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266390"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-send-data"></a>教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器发送数据
您可以使用 BizTalk 适配器用于 TIBCO Enterprise Message Service (EMS) 将数据发送到 TIBCO 系统。 本演练介绍阐释了这一点的 SDK 示例。  

## <a name="prerequisites"></a>先决条件  

- 用于 TIBCO EMS 的 BizTalk 适配器要求将 TIBCO EMS C# API，TIBCO 添加。EMS.dll，到全局程序集缓存 (GAC)。 有关安装该程序集的详细信息，请参阅[TIBCO Enterprise Message Service 要求和限制](../core/tibco-enterprise-message-service-requirements-and-limitations.md)。  

- 安装[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器上运行才能生成和部署示例。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例提取文件文件夹中的 XML 文件，将该文件发送到业务流程，然后使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器在 TIBCO 系统中创建一条记录。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 此示例中，在 Visual Studio 中设计说明使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器，BizTalk 业务流程的基本功能。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 该示例的默认位置是  

 C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWaySend  

 下表列出并介绍了在示例中的文件。  

|**Runtime 项目文件名**|**运行时项目文件说明**|  
|----------------------------------|------------------------------------------|  
|OneWaySend.btproj<br /><br /> OneWaySend.sln|应用程序的项目和解决方案文件。|  
|Schema.xsd|应用程序的架构文件。|  
|Orchestration.odx|使用应用程序的业务流程。|  
|TIBCOEMSOneWaySend.snk|强名称密钥文件。|  

## <a name="how-to-use-this-sample"></a>如何使用此示例  

#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a>创建用于 TIBCO EMS 的 BizTalk 适配器的新实例  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 单击**启动**，**所有程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  

3. 右键单击**适配器**，然后指向**新建**，**适配器**以显示**适配器属性**对话框。  

4. 输入一个值**名称**字段，例如**TIBCO EMS**。  

5. 选择**TIBCO Enterprise Message System**从列表中可用的适配器**适配器**下拉列表中单击**确定**。  

#### <a name="create-a-biztalk-send-port"></a>创建 BizTalk 发送端口  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。  

2. 右键单击**发送端口**，然后指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。  

3. 输入一个值**名称**字段，例如**TIBCOEMSOneWaySP**。  

4. 从中可用的适配器列表中选择 TIBCO EMS 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。  

   > [!NOTE]
   >  此值是在中创建 TIBCO Enterprise Message System 适配器时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

5. 输入值**服务器连接定义**:  


   | **属性** |                                **ReplTest1**                                |
   |--------------|-------------------------------------------------------------------------|
   | 目标  |               服务器目标队列或主题名称。               |
   | 端口号  | TIBCO 服务器正在侦听的端口。 默认值为 7222。 |
   | 服务器名称  |                    TIBCO EMS 服务器的名称。                    |


6. 输入值**用户凭据**:  

   |**属性**|**ReplTest1**|  
   |------------------|---------------|  
   |Password|TIBCO EMS 服务器的密码。|  
   |“用户名”|TIBCO EMS 服务器的用户名。|  

    有关属性的详细信息，请参阅[创建 TIBCO Enterprise Message Service 发送处理程序](../core/creating-tibco-enterprise-message-service-send-handlers.md)。  

7. 单击“确定” 。  

8. 选择**XML 传输**中的可用管道列表**发送管道**下拉列表中单击**确定**。  

9. 右键单击发送端口，然后单击**启动**以登记并启动发送端口。  

#### <a name="create-a-file-receive-port"></a>创建文件接收端口  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。  

2. 右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**显示接收端口属性对话框。  

3. 输入一个值**名称**字段，例如**TIBCOEMSOneWayFileRP**，然后单击**确定**。  

#### <a name="create-a-file-receive-location"></a>创建文件接收位置  

1.  创建一个文件夹，文件接收位置监视，例如 C:\Filesource。  

2.  右键单击新接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。  

3.  输入一个值**名称**字段，例如**TIBCOEMSOneWayFileRL**。  

4.  选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。  

5.  输入您为前面创建的文件夹的位置**接收文件夹**属性，单击**确定**。  

6.  选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。  

7.  右键单击接收位置，然后单击**启用**。  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a>从适配器架构生成文档实例  

1.  右键单击 Schema.xsd 在解决方案资源管理器中的，单击**属性**。  

2.  在属性窗口中，单击以选中**输出实例文件名**下**常规**类别。  

3.  单击省略号按钮 （...） 以显示**选择输出文件**对话框。  

4.  指定的文件夹和输出文件实例名称，例如**C:\instance.xml**然后单击**保存**。  

    > [!NOTE]
    >  未指定为 file 接收位置在此处指定的文件夹的位置。  

5.  右键单击 Schema.xsd 在解决方案资源管理器中的，单击**生成实例**以在指定位置生成文档实例。  

#### <a name="modify-the-generated-document-instance"></a>修改生成的文档实例  

1.  在诸如记事本之类的文本编辑器中打开生成的文档实例，并编辑文档实例，以确保数据将在 TIBCO 系统中生成唯一的记录的内容。 例如，下面的代码显示了数据文件的第一部分：  

    ```  
    <ns0:Root xmlns:ns0="http://TibcoEMSOne_WaySend.TibcoEMSOneWaySendSchema">  
      <Name>Punya Palit</Name>  
      <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  

2.  保存修改后的文档实例。  

#### <a name="build-and-deploy-the-project"></a>生成并部署项目  

1. 右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**属性**以启动项目的项目设计器。  

2. 单击**部署**选项卡。  

3. 输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。  

4. 右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。  

#### <a name="bind-and-enlist-the-orchestration"></a>绑定并登记业务流程  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。  

2. 单击**刷新**按钮在 MMC 工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。  

3. 双击业务流程以显示**业务流程属性**对话框。  

4. 单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。  

5. 指定适当的值的绑定选项，例如：  


   |     **参数**      |        **ReplTest1**         |
   |------------------------|--------------------------|
   |          主机          | BizTalkServerApplication |
   |    FileReceivePort     |   TIBCOEMSOneWayFileRP   |
   | TibcoEMSOneWaySendPort |     TIBCOEMSOneWaySP     |


6. 单击“确定”。  

#### <a name="start-the-orchestration"></a>启动业务流程  

- 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击该业务流程，然后单击**启动**以登记并启动业务流程。  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a>拖放到该文件所监视的文件夹的文档实例接收位置  

-   复制到文件之前创建的文档实例接收文件夹应用程序监视器。  

#### <a name="verify-that-the-tibco-system-is-updated"></a>验证 TIBCO 系统已更新  

- 使用 TIBCO web 界面验证记录已创建从 XML 文件中的数据。  

  如果成功处理的文档实例，会发生以下事件序列：  

1.  文件适配器从文件夹中检索该文件，并将其发布到 MessageBox 作为 BizTalk 消息。  

2.  业务流程订阅此发布的消息，以便 BizTalk 消息引擎将激活业务流程的实例并将消息发送到业务流程实例。  

3.  业务流程实例处理使用业务流程中指定的逻辑消息，并将消息发布回 MessageBox。  

4.  TIBCO 发送端口订阅此发布消息，因此 BizTalk 消息引擎将消息发送到 TIBCO 发送端口。  

5.  发送端口将消息传 TIBCO Enterprise Message Service 的 BizTalk 适配器。  

6.  用于 TIBCO Enterprise Message Service 的 BizTalk 适配器将消息发送到 TIBCO 系统。  

## <a name="see-also"></a>请参阅  
 [教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器接收数据](../core/tutorial-us-the-biztalk-adapter-for-tibco-message-service-to-receive-data.md)   
 [教程：使用用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)