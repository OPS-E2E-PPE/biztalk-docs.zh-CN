---
title: 教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器接收数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc5a63ec-1897-4c9b-b37f-cdcec151b1c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e8697598b0f4eff86e72fde53747ba0259af8c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399153"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-receive-data"></a>教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器接收数据
可以使用用于 TIBCO Enterprise Message Service (EMS) 的 BizTalk 适配器从 TIBCO 系统接收数据。 本演练介绍阐释了这一点的 SDK 示例。  

## <a name="prerequisites"></a>先决条件  

- 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器要求将 TIBCO EMS C# API，TIBCO 添加。EMS.dll，到全局程序集缓存 (GAC)。 有关安装该程序集的详细信息，请参阅[TIBCO Enterprise Message Service 要求和限制](../core/tibco-enterprise-message-service-requirements-and-limitations.md)。  

- 安装[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器上运行才能生成和部署示例。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例提取一个文件夹中的 XML 文件、 将该文件发送到业务流程，然后使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器从 TIBCO 系统检索数据。 将结果写入到 XML 文件。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 此示例中，在 Visual Studio 中设计说明使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器，BizTalk 业务流程的基本功能。  

> [!NOTE]
>  该示例假定您知道如何从应用程序处理的 TIBCO 发送一条消息。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 该示例的默认位置是  

 C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive  

 下表显示了本示例中的文件及其用途说明：  

|**Runtime 项目文件名**|**运行时项目文件说明**|  
|----------------------------------|------------------------------------------|  
|OneWayReceive.btproj,<br /><br /> OneWayReceive.sln|应用程序的项目和解决方案文件。|  
|Schema.xsd，|应用程序的架构文件。|  
|Orchestration.odx|使用应用程序的业务流程。|  
|TIBCOEMSOneWaySend.snk|强名称密钥文件。|  

## <a name="how-to-use-this-sample"></a>如何使用此示例  

#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a>创建用于 TIBCO EMS 的 BizTalk 适配器的新实例  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 单击**启动**，**程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  

3. 右键单击**适配器**，然后指向**新建**，**适配器**以显示**适配器属性**对话框。  

4. 输入一个值**名称**字段，例如**TIBCO EMS**。  

5. 选择**TIBCO Enterprise Message System**从列表中可用的适配器**适配器**下拉列表中单击**确定**。  

#### <a name="create-a-biztalk-receive-port"></a>创建 BizTalk 接收端口  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。  

2. 右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**显示接收端口属性对话框。  

3. 输入一个值**名称**字段，例如**TIBCOEMSOneWayRP**，然后单击**确定**。  

#### <a name="create-a-biztalk-receive-location"></a>创建 BizTalk 接收位置  

1. 右键单击新接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。  

2. 输入一个值**名称**字段，例如**TIBCOEMSOneWayRL**。  

3. 从中可用的适配器列表中选择 TIBCO EMS 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。  

   > [!NOTE]
   >  此值是在中创建 TIBCO 适配器时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

4. 输入值**服务器连接定义**:  


   | **属性** |                                **ReplTest1**                                |
   |--------------|-------------------------------------------------------------------------|
   | 目标  |               服务器目标队列或主题名称。               |
   | 端口号  | TIBCO 服务器正在侦听的端口。 默认值为 7222。 |
   | 服务器名称  |                    TIBCO EMS 服务器的名称。                    |


5. 输入值**用户凭据**:  

   |**属性**|**ReplTest1**|  
   |------------------|---------------|  
   |Password|TIBCO EMS 服务器的密码。|  
   |“用户名”|TIBCO EMS 服务器的用户名。|  

    有关属性的详细信息，请参阅[创建 TIBCO Enterprise Message Service 接收处理程序](../core/creating-tibco-enterprise-message-service-receive-handlers.md)。  

6. 单击“确定” 。  

7. 选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。  

8. 右键单击接收位置，然后单击**启用**。  

#### <a name="create-a-one-way-file-send-port"></a>创建一个单向 file 发送端口  

1. 创建发送端口，例如 C:\FilesOut 要使用的目标文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。  

3. 右键单击**发送端口**，然后指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。  

4. 输入一个值**名称**字段，例如**TIBCOEMSOneWayFileSP**。  

5. 选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。  

6. 有关**目标文件夹**属性中，输入前面创建的文件夹的位置，然后单击**确定**。  

7. 选择**XMLTransmit**中的可用管道列表**发送管道**下拉列表中单击**确定**。  

8. 右键单击发送端口，然后单击**启动**以登记并启动发送端口。  

#### <a name="build-and-deploy-the-project"></a>生成并部署项目  

1. 右键单击 OneWayReceive 项目在解决方案资源管理器中的，单击**属性**以启动项目的项目设计器。  

2. 单击**部署**选项卡。  

3. 输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。  

4. 右键单击 OneWayReceive 项目在解决方案资源管理器中的，单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。  

#### <a name="bind-and-enlist-the-orchestration"></a>绑定并登记业务流程  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。  

2. 单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。  

3. 双击业务流程以显示**业务流程属性**对话框。  

4. 单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。  

5. 指定适当的值的绑定选项，例如：  


   |         **参数**          |        **ReplTest1**         |
   |--------------------------------|--------------------------|
   |              主机              | BizTalkServerApplication |
   |          FileSendPort          |   TIBCOEMSOneWayFileSP   |
   | TibcoEMSOneWayReceiveOperation |     TIBCOEMSOneWayRP     |


6. 单击“确定” 。  

#### <a name="start-the-orchestration"></a>启动业务流程  

- 在中[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]管理控制台中，右键单击该业务流程，然后单击**启动**以登记并启动业务流程。  

#### <a name="verify-that-the-application-receives-a-message"></a>验证应用程序收到一条消息  

- 打开文件发送端口配置为将发送到并验证已生成输出文档的文件夹。 此文件应包含用于 TIBCO Enterprise Message Service 的 BizTalk 适配器处理查询的结果。  

  如果成功处理的文档实例，会发生以下事件序列：  

1.  TIBCO EMS 适配器从 TIBCO 系统接收消息，并将其发布到 MessageBox 作为 BizTalk 消息。  

2.  业务流程订阅此发布的消息，以便 BizTalk 消息引擎会激活业务流程的实例，并将消息发送到业务流程实例。  

3.  业务流程实例将消息发布回 MessageBox。  

4.  File 发送端口订阅此消息，以便 BizTalk 向文件适配器发送的消息。  

5.  文件适配器写入包含结果集限于指定的输出文件夹的消息。  

## <a name="see-also"></a>请参阅  
 [教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器发送数据](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md)   
 [教程：使用用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)