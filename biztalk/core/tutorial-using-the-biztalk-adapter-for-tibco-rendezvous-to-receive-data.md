---
title: 教程：使用 TIBCO Rendezvous 适配器接收 |Microsoft Docs
description: 若要使用 BizTalk Server 中的 TIBCO Rendezvous 的 BizTalk 适配器从 TIBCO 系统接收数据的分步指南
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58e7a739-701d-4085-a840-54f81c55e943
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce3d1e3737b56fc8a943d1fdee849a3eb2de5c6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393831"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a>教程：使用用于 TIBCO Rendezvous 的 BizTalk 适配器接收数据
可以使用用于 TIBCO Rendezvous 的 BizTalk 适配器从 TIBCO 系统接收数据。 本演练介绍阐释了这一点的 SDK 示例。  

## <a name="prerequisites"></a>先决条件  

安装[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器上运行才能生成和部署示例。  

## <a name="about-the-sample"></a>有关该示例 
- 此示例使用用于 TIBCO Rendezvous 的 BizTalk 适配器从 TIBCO 系统接收数据。 业务流程处理消息，并使用文件适配器将数据写入为 XML 文件中指定的文件夹。  

- 此示例中，在设计[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，说明使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器，BizTalk 业务流程的基本功能。  

    > [!NOTE]
    >  该示例假定您知道如何从应用程序处理的 TIBCO 发送一条消息。  

- 该示例的默认位置是`C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`，包括以下文件： 

    |**Runtime 项目文件名**|**运行时项目文件说明**|  
    |---|---|  
    |OneWayReceive.btproj,<br /><br /> OneWayReceive.sln|应用程序的项目和解决方案文件。|  
    |PureMessage.xsd，|应用程序的架构文件。|  
    |TIBCORvOWR.odx|使用应用程序的业务流程。|  
    |TIBCORv.snk|强名称密钥文件。|  


## <a name="step-1-add-the-adapter-to-biztalk-administration"></a>第 1 步：将适配器添加到 BizTalk 管理

1.  在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  

3.  右键单击**适配器**，然后指向**新建**，**适配器...** 若要显示**适配器属性**对话框。  

4.  输入一个值**名称**字段，例如**TIBCO Rendezvous**。  

5.  选择**tibco （) Rendezvous(r)** 从列表中可用的适配器**适配器**下拉列表中单击**确定**。  

## <a name="step-2-create-a-receive-port"></a>第 2 步：创建接收端口  

1.  在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。  

2.  右键单击接收端口文件夹，然后单击**新建**，**单向接收端口...** 以显示**接收端口属性**对话框。  

3.  输入一个值**名称**字段，例如**TIBCORvOneWayRP**，然后单击**确定**。  

## <a name="step-3-create-a-receive-location"></a>步骤 3：创建接收位置  

1. 右键单击新接收端口，然后单击**新建**，**接收位置...** 若要显示**接收位置属性**对话框。  

2. 输入一个值**名称**字段。 例如，输入**TIBCORvOneWayRL**。  

3. 从中可用的适配器列表中选择 TIBCO Rendezvous 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。  

   > [!NOTE]
   >  此值是在中创建 TIBCO 适配器时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

4. 输入一个值**RendezvousSubjectName**下**AdapterRequiredProperties**。  

5. 输入值**认证的侦听程序属性**:  


   |   **属性**   |                                                                         **ReplTest1**                                                                          |
   |------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | 分类帐文件名称 |                                             要用于持久性认证的消息传递的分类帐文件名称。                                             |
   |  可重复使用名称   | 若要使用认证的消息传递的可重用通信名称。 名称必须是唯一的而在网络上的所有认证的消息通信名称。 |


6. 输入值**凭据**:  


   | **属性** |                   **ReplTest1**                    |
   |--------------|------------------------------------------------|
   |   Password   | TIBCO Rendezvous 服务器的密码。  |
   |  “用户名”   | TIBCO Rendezvous 服务器的用户名。 |


7. 输入值**RendezvousTransport**:  

   |**属性**|**ReplTest1**|  
   |------------------|---------------|  
   |后台程序|Rendezvous 传输后台程序参数。|  
   |网络|Rendezvous 传输网络参数。|  
   |服务|Rendezvous 传输服务参数。|  

    有关属性的详细信息，请参阅[创建接收项目](../core/creating-tibco-rendezvous-receive-handlers.md)。  

8. 单击“确定” 。  

9. 选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。  

10. 右键单击接收位置，然后单击**启用**。  

## <a name="step-4-create-a-one-way-send-port"></a>步骤 4：创建一个单向发送端口  

1. 创建发送端口，例如 C:\FilesOut 要使用的目标文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。  

3. 右键单击**发送端口**，然后指向**新建**，**静态单向发送端口...** 若要显示**发送端口属性**对话框。  

4. 输入一个值**名称**字段，例如**TIBCORvOneWayFileSP**。  

5. 选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。  

6. 有关**目标文件夹**属性中，输入前面创建的文件夹的位置，然后单击**确定**。  

7. 选择**XMLTransmit**中的可用管道列表**发送管道**下拉列表中单击**确定**。  

8. 右键单击发送端口，然后单击**启动**以登记并启动发送端口。  

## <a name="step-5-build-and-deploy-the-project"></a>步骤 5：生成并部署项目  

1. 右键单击 OneWayReceive 项目在解决方案资源管理器中的，单击**属性**以启动项目的项目设计器。  

2. 单击**部署**选项卡。  

3. 输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。  

4. 右键单击 OneWayReceive 项目在解决方案资源管理器中的，单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。  

## <a name="step-6-bind-enlist-and-start-the-orchestration"></a>步骤 6：绑定、 登记，并启动业务流程  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。  

2. 单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。  

3. 双击业务流程以显示**业务流程属性**对话框。  

4. 单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。  

5. 指定适当的值的绑定选项，例如：  


   | **参数** |        **ReplTest1**         |
   |---------------|--------------------------|
   |     主机      | BizTalkServerApplication |
   |   SendPort    |   TIBCORvOneWayFileSP    |
   |  ReceivePort  |     TIBCORvOneWayRP      |


6. 单击“确定” 。  

7. 右键单击该业务流程，然后单击**启动**以登记并启动业务流程。  

## <a name="step-7-confirm-the-application-receives-a-message"></a>步骤 7：确认应用程序收到一条消息  

- 打开文件发送端口配置为发送到计算机并验证已生成输出文档的文件夹。  

  如果成功处理的文档实例，会发生以下事件序列：  

1.  TIBCO Rendezvous 适配器从 TIBCO 系统接收消息，并将其发布到 MessageBox 作为 BizTalk 消息。  

2.  业务流程订阅此发布的消息，以便 BizTalk 消息引擎会激活业务流程的实例，并将消息发送到业务流程实例。  

3.  业务流程实例将消息发布回 MessageBox。  

4.  File 发送端口订阅此消息，以便 BizTalk 向文件适配器发送的消息。  

5.  文件适配器写入包含结果集限于指定的输出文件夹的消息。  

## <a name="see-also"></a>请参阅  
 [教程：使用用于 TIBCO Rendezvous 的 BizTalk 适配器发送数据](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md)   
 [教程：使用用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)