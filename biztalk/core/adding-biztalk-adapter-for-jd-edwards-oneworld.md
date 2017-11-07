---
title: "为博士 Edwards OneWorld 添加 BizTalk 适配器 |Microsoft 文档"
description: "将博士 Edwards OneWorld 添加到 BizTalk 管理、 创建发送端口、 配置传输属性中，和在 BizTalk Server 中使用博士 Edwards OneWorld 适配器时使用 XMLReceive 和 XMLTransmit 管道"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03126f4e-9156-4c0c-ab5c-0627f0c05263
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 784323634d3084efd0b56aac1d5dbc97f2b4329f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="configure-jd-edwards-enterpriseone-artifacts-in-biztalk-administration"></a>在 BizTalk 管理中配置博士 Edwards EnterpriseOne 项目
适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器包含“接收处理程序”文件夹和“发送处理程序”文件夹。 “发送处理程序”文件夹包含 BizTalkServerApplication。 适用于 JD Edwards OneWorld 的 BizTalk 适配器是可以创建的，它在与 BizTalk 服务器相关的进程中运行，而不在隔离的主机进程中运行。  

## <a name="add-the-adapter-to-biztalk-administration"></a>将适配器添加到 BizTalk 管理 

1.  打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**平台设置**.  
  
2.  右键单击**适配器**，选择**新建**，然后选择**适配器**。  
  
3.  输入适配器的名称。 例如，输入`JDEOneWorld`。  
  
4.  选择**JDEOneWorld**从**适配器**列表，然后选择**确定**。  

  
### <a name="check-if-the-adapter-is-working"></a>检查是否正在工作的适配器 
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以验证适配器是否正确运作，可以通过查看**逻辑系统**窗口。 在初始安装时，该窗口为空，因为您还没有建立到服务器系统的连接，也没有建立任何逻辑系统。  
  
 
1.  在**BizTalk Server 管理**，展开**平台设置**，展开**适配器**，然后选择**JDEOneWorld**。  
  
2.  在细节窗格中，右键单击**BizTalkServerApplication**，然后选择**属性**。  
  
3.  选择**属性**选项卡。  
  
4.  设置 SQL 连接参数。  
  
    -   **定义 SQL 数据库参数-**的 SQL Server 名称和数据库是那些在安装设置。 在这个文本区域，您可以重新定义适用于该适配器的服务器和数据库。  
  
5.  选择**关闭**退出**逻辑系统**窗口。  
  
     下一步是使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 添加逻辑系统。  

## <a name="create-the-send-port"></a>创建发送端口  
  
1.  在**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。  
  
2.  右键单击**发送端口**，选择**新建**，然后选择**静态请求-响应发送端口**。  
  
    > [!NOTE]
    >  你还可以使用**静态单向端口**。  
  
3.  在**发送端口属性**，选择**名称**字段，并输入发送端口名称。 例如，输入**SendToJDE**。  
  
4.  在**类型**下拉列表中，选择**JDEOneWorld**。  
  
5.  在**URI**下拉列表中，选择发送处理程序。  
  
6.  选择“确定”。 

## <a name="configure-the-transport-properties"></a>配置传输属性
JD Edwards OneWorld 传输属性系统定义用于设计和运行时登录。 在设计时，将这些凭据设置为浏览 JD Edwards OneWorld 业务函数，并在运行时进行调用。  
  
 在建立与 JD Edwards OneWorld 的连接后，将参数传递给连接对象（用户、密码、环境）。 它将返回 JD Edwards OneWorld 应用程序业务函数的一个实例。 通过企业/应用程序服务器名称及服务侦听到的已定义的 TCP/IP 端口可进一步定义这些凭据。  
  
 从名为 jdeinterop.ini 文件读取企业服务器名称和端口。 这些值必须是相同的系统定义设置中。  
  
> [!NOTE]
>  所有条目都要区分大小写。  
  
### <a name="set-the-properties"></a>设置的属性  
 在**传输属性**对话框中，你可以设置特定于服务器系统和你尝试访问的对象的连接和凭据参数。  
  
1.  提供凭据。 您可以使用以下方法之一访问 JD Edwards OneWorld 系统：  
  
    -   登录凭据 （密码、 用户名称）： 如果你使用此方法，请转到步骤 5。  
  
    -   单一登录。  
  
2.  若要使用单一登录 (SSO)，选择**是**中**使用 SSO**。  
  
     有关如何设置 SSO 的详细信息，请参阅[适配器中的安全](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)  
  
3.  在列表中选择一个关联应用程序。  
  
     企业单一登录工具创建的关联应用程序代表诸如 JD Edwards OneWorld 之类的应用程序。 用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 这些凭据是从服务器系统的 SSO 凭据数据库中为指定关联应用程序检索的。 凭据是启动 BizTalk Server 项目的应用程序用户的凭据。  
  
     有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications3.md)。  
  
4.  展开**博士 Edwards OneWorld 系统**节点然后输入博士 Edwards OneWorld 服务器连接的所有必要的信息。  
  
     ![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")  
  
     设置连接参数后，您可以浏览 JD Edwards OneWorld 系统。 有关详细信息，请参阅[导入到 BizTalk 服务器项目博士 Edwards OneWorld 架构](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)。  
  
5.  输入一个值，在表示的调用，例如 200、 数**最大并发调用**如有必要。  
  
     `Max Concurrent Calls`参数可以优化你的配置。 在吞吐量超过了后端处理能力的情况下，可以使用此参数激活消息重载保护。 默认值为 -1，表示调用不受限制。  
  
     在 BizTalk Server 将消息提交到传输适配器后，首先会从该适配器收到一个批。 它调用批上的 `TransmitMessage` 以传输每个消息。 完成上述操作后，BizTalk Server 对批调用 `Done`，然后适配器开始将消息传输到后端。 如果在调用 `Done` 前，BizTalk Server 获得了多个批，这可能就永远不会发生。 通过设置批中的最大消息数量，可以控制传输到后端的消息。  
  
     更改此参数后，所做更改会在一分钟内生效；BizTalk Server 必须检索 SQL 数据库中保存的对适配器配置的更改。  
  
6.  选择**是**为**刷新代理**强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。  
  
     例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者向服务器中添加了内容，但是由于它没有显示在 Microsoft 适配器向导中而无法选择它。  
  
    > [!NOTE]
    >  browsingagent.exe 在退出当前浏览会话之前不会进行刷新。 例如，你必须退出**生成的添加项**浏览会话并重新输入更新 browsingagent.exe。  
  
7.  提供所有所需的信息后，单击**应用**，然后单击**确定**接受连接信息。  
  
     您必须为用于 JD Edwards OneWorld 的 BizTalk 适配器设置连接参数才能访问 JD Edwards OneWorld。  
  
### <a name="adapter-required-properties"></a>所需的适配器属性  
 如果没有在控制面板中设置全局环境变量，则可以在此部分中执行这项工作。  
  
|参数|Description|  
|---------------|-----------------|  
|`Host`|键入主机服务器计算机名称的名称 (例如， `actsvr1`); 或计算机的 IP 地址 (例如， `123.456.0.789`)。|  
|JAVA_HOME|键入 JDK 安装的完整路径。|  
|JDE Edwards 环境|例如，键入博士 Edwards OneWorld 环境的名称`DV7333`。<br /><br /> DV7333 是开发环境的公用名，PY7333 是原型环境的公用名，PD7333 是生产环境的公用名。|  
|JDEdwards JAR 文件|输入每个 JAR 文件的完整路径和文件名称：<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br />-JDEActionalInterop.jar<br /><br /> 每个 jar 文件必须用分号 (;) 分隔，中间不留空格。 例如：<br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|密码|键入指定用户的密码。|  
|端口|键入将交换数据的端口号 (例如， `6009`)。|  
|用户名|键入将用于登录 JD Edwards OneWorld 系统的 JD Edwards OneWorld 用户名。|  

## <a name="use-the-xmltransmit-and-xmlreceive-pipelines"></a>使用 XMLTransmit 和 XMLReceive 管道
Microsoft BizTalk Adapter for 博士 Edwards OneWorld 要求你选择 XMLTransmit 和 XMLReceive 为发送和接收管道。  
  
1.  在**BizTalk Server 管理**，展开**应用程序**，然后展开你的应用程序。  
  
2.  选择**发送端口**，右键单击你发送端口，然后选择**属性**。  
  
3.  在**发送端口属性**，执行以下操作：  
  
    1.  选择从发送管道**发送管道**下拉列表。  
  
    2.  选择从接收管道**接收管道**下拉列表。  
  
4.  选择“确定”。  

## <a name="next-steps"></a>后续步骤
[将适配器架构导入 Visual Studio](importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)  
[使用消息上下文属性](using-message-context-properties2.md)