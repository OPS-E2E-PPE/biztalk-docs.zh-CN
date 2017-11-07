---
title: "教程： 使用 TIBCO 会合适配器接收 |Microsoft 文档"
description: "分步指南，以便用 TIBCO 会合 BizTalk Server 中的 BizTalk Adapter 来从 TIBCO 系统接收数据"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58e7a739-701d-4085-a840-54f81c55e943
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75aaba0cc2e455676e78381c04934dda30741a85
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a>教程：使用适用于 TIBCO Rendezvous 的 BizTalk 适配器来接收数据
您可以使用用于 TIBCO Rendezvous 的 BizTalk 适配器接收来自 TIBCO 系统的数据。 本演练描述了对此进行说明的一个 SDK 示例。  
  
## <a name="prerequisites"></a>先决条件  
  
为了生成并部署该示例，请在运行此适配器的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="about-the-sample"></a>有关该示例 
- 本示例使用用于 TIBCO Rendezvous 的 BizTalk 适配器接收来自 TIBCO 系统的数据。 业务流程处理消息并使用文件适配器将数据编写为指定文件夹中的 XML 文件。  
  
- 本示例在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中设计，它使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器以及 BizTalk 业务流程来说明基本功能。  
  
    > [!NOTE]
    >  本示例假定您知道如何发送来自 TIBCO 的消息以供应用程序处理。  
  
- 此示例的默认位置是`C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive`，并包括以下文件： 
  
    |**运行时项目文件名**|**运行时项目文件说明**|  
    |---|---|  
    |OneWayReceive.btproj,<br /><br /> OneWayReceive.sln|应用程序的项目和解决方案文件。|  
    |PureMessage.xsd，|应用程序的架构文件。|  
    |TIBCORvOWR.odx|应用程序使用的业务流程。|  
    |TIBCORv.snk|强命名密钥文件。|  
  
  
## <a name="step-1-add-the-adapter-to-biztalk-administration"></a>步骤 1： 将适配器添加到 BizTalk 管理
  
1.  在**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
3.  右键单击**适配器**和指向**新建**，**适配器...** 若要显示**适配器属性**对话框。  
  
4.  输入一个值**名称**字段，例如**TIBCO 会合**。  
  
5.  选择**TIBCO(r) Rendezvous(r)**从列表中可用的适配器**适配器**下拉列表中单击**确定**。  
  
## <a name="step-2-create-a-receive-port"></a>步骤 2： 创建接收端口  
  
1.  在**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收端口**。  
  
2.  右键单击接收端口文件夹，然后单击**新建**，**单向接收端口...**以显示**接收端口属性**对话框。  
  
3.  输入一个值**名称**字段，例如**TIBCORvOneWayRP**，然后单击**确定**。  
  
## <a name="step-3-create-a-receive-location"></a>步骤 3： 创建接收位置  
  
1.  右键单击新的接收端口，然后单击**新建**，**接收位置...** 若要显示**接收位置属性**对话框。  
  
2.  输入一个值**名称**字段。 例如，输入**TIBCORvOneWayRL**。  
  
3.  从中的可用适配器的列表中选择 TIBCO 会合适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。  
  
    > [!NOTE]
    >  该值是在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建 TIBCO 适配器时指定的名称。  
  
4.  输入一个值**RendezvousSubjectName**下**AdapterRequiredProperties**。  
  
5.  输入值**认证侦听程序属性**:  
  
    |**属性**|**值**|  
    |------------------|---------------|  
    |分类帐文件名称|用于持久性认证消息传递的分类帐文件名。|  
    |可重复使用的名称|用于已验证消息传递的可重用的通信名称。 在网络上所有已验证消息通信名称中，该名称必须是唯一的。|  
  
6.  输入值**凭据**:  
  
    |**属性**|**值**|  
    |------------------|---------------|  
    |密码|TIBCO Rendezvous 服务器的密码。|  
    |用户名|TIBCO Rendezvous 服务器的用户名。|  
  
7.  输入值**RendezvousTransport**:  
  
    |**属性**|**值**|  
    |------------------|---------------|  
    |后台程序|Rendezvous 传输后台程序参数。|  
    |Network|Rendezvous 传输网络参数。|  
    |服务|Rendezvous 传输服务参数。|  
  
     有关属性的详细信息，请参阅[创建接收项目](../core/creating-tibco-rendezvous-receive-handlers.md)。  
  
8.  单击 **“确定”**。  
  
9. 选择**XMLReceive**从列表中的可用管道**接收管道**下拉列表框中，单击**确定**。  
  
10. 右键单击接收位置，然后单击**启用**。  
  
## <a name="step-4-create-a-one-way-send-port"></a>步骤 4： 创建单向发送端口  
  
1.  创建发送端口要使用的目标文件夹，例如 C:\FilesOut。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**。  
  
3.  右键单击**发送端口**和指向**新建**，**静态单向发送端口...** 若要显示**发送端口属性**对话框。  
  
4.  输入一个值**名称**字段，例如**TIBCORvOneWayFileSP**。  
  
5.  选择**文件**从列表中的可用适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。  
  
6.  有关**目标文件夹**属性，输入前面创建的文件夹的位置，然后单击**确定**。  
  
7.  选择**XMLTransmit**从管道中提供的列表的管道**发送管道**下拉列表中单击**确定**。  
  
8.  右键单击发送端口，然后单击**启动**登记和启动发送端口。  
  
## <a name="step-5-build-and-deploy-the-project"></a>步骤 5： 生成并部署项目  
  
1.  右键单击解决方案资源管理器中的 OneWayReceive 项目，然后单击**属性**以启动项目设计器中为该项目。  
  
2.  单击**部署**选项卡。  
  
3.  输入适当的值为**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。  
  
4.  右键单击解决方案资源管理器中的 OneWayReceive 项目，然后单击**部署**以生成项目并将其部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。  
  
## <a name="step-6-bind-enlist-and-start-the-orchestration"></a>步骤 6： 将绑定，登记，并启动业务流程  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。  
  
2.  单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**密钥刷新你键盘上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。  
  
3.  双击要显示的业务流程**业务流程属性**对话框。  
  
4.  单击**绑定**显示业务流程的绑定选项对话框的左窗格中。  
  
5.  指定绑定选项的适当值，例如：  
  
    |**参数**|**值**|  
    |-------------------|---------------|  
    |主机|BizTalkServerApplication|  
    |发送端口|TIBCORvOneWayFileSP|  
    |接收端口|TIBCORvOneWayRP|  
  
6.  单击 **“确定”**。  
  
7. 右键单击业务流程，然后单击**启动**登记和启动业务流程。  
  
## <a name="step-7-confirm-the-application-receives-a-message"></a>步骤 7： 确认应用程序收到一条消息  
  
-   打开文件发送端口配置为发送到计算机并验证已生成的输出文档的文件夹。  
  
 成功处理文档实例后，会发生以下事件序列：  
  
1.  TIBCO Rendezvous 适配器接收来自 TIBCO 系统的消息并将其作为 BizTalk 消息发布到 MessageBox。  
  
2.  业务流程会订阅此发布的消息，以便 BizTalk 消息引擎能够激活业务流程的实例，并将该消息发送到业务流程实例。  
  
3.  业务流程实例将此消息发布回 MessageBox。  
  
4.  文件发送端口会订阅此消息，以便 BizTalk 能够将消息发送到文件适配器。  
  
5.  文件适配器将包含结果集的消息写入到指定的输出文件夹。  
  
## <a name="see-also"></a>另请参阅  
 [教程： 使用 TIBCO 会合的 BizTalk 适配器将数据发送](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md)   
 [教程： 使用 Microsoft BizTalk Adapter for TIBCO 会合](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)