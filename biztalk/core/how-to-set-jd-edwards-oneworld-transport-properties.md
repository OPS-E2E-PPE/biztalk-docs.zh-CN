---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2dbfa33f316dc48d696bdcb7f16b6506e918a9c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383927"
---
# <a name="how-to-set-jd-edwards-oneworld-transport-properties"></a>如何设置 JD Edwards OneWorld 传输属性

## <a name="overview"></a>概述
JD Edwards OneWorld 传输属性系统定义用于设计和运行时登录。 设置这些凭据以在设计时浏览 JD Edwards OneWorld 业务函数，并在运行时进行调用。  
  
 在与 JD Edwards OneWorld 建立连接，则将参数传递给连接对象 （用户、 密码、 环境）。 它会返回 JD Edwards OneWorld 应用程序业务函数的实例。 通过企业/应用程序服务器和定义的服务在其侦听的 TCP/IP 端口的名称来进一步定义这些凭据。  
  
 从名为 jdeinterop.ini 的文件中读取企业服务器名称和端口。 这些值必须是系统定义设置中的相同。  
  
> [!NOTE]
>  所有项目都均区分大小写。  
  
## <a name="set-the-transport-properties"></a>设置传输属性  
 在中**传输属性**对话框中，你设置特定于服务器系统和你尝试访问的对象的连接和凭据参数。  
  
1.  提供凭据。  
  
     您可以访问 JD Edwards OneWorld 系统使用以下方法之一：  
  
    -   登录凭据 （密码、 用户名）：如果使用此方法，请转到步骤 5。  
  
    -   单一登录。  
  
2.  若要使用单一登录 (SSO)，选择**是**中**使用 SSO**。  
  
     有关如何设置 SSO 的详细信息，请参阅[适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)  
  
3.  在列表中选择关联应用程序。  
  
     关联应用程序，由企业单一登录工具创建代表 JD Edwards OneWorld 之类的应用程序。 用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 从指定的关联应用程序的服务器系统的 SSO 凭据数据库检索这些凭据。 凭据是启动 BizTalk Server 项目的应用程序用户。  
  
     有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications3.md)。  
  
4.  展开**JD Edwards OneWorld 系统**节点并输入所需的所有信息以连接到 JD Edwards OneWorld 服务器。  
  
     ![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")  
  
     设置连接参数后，您可以浏览 JD Edwards OneWorld 系统。 有关详细信息，请参阅[导入到 BizTalk Server 项目 JD Edwards OneWorld 架构](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)。  
  
5.  输入一个值，表示在调用，例如 200 数**最大并发调用**如有必要。  
  
     `Max Concurrent Calls`参数可以优化您的配置。 在吞吐量超过了后端处理能力，以激活消息重载保护中使用此参数。 默认值为-1，表示不限制调用。  
  
     当 BizTalk Server 将消息提交到传输适配器时，它首先从适配器接收一批。 它将调用`TransmitMessage`对批，将每个消息传送。 完成后，BizTalk Server 调用`Done`批处理，然后适配器开始将消息传输到后端上。 如果 BizTalk Server 调用之前获取多个批次`Done`，可能永远不会发生。 通过在批处理中设置的最大消息数，可以控制到后端的消息。  
  
     更改此参数在一分钟; 内将生效BizTalk Server 必须检索保存在 SQL 数据库中的适配器配置的更改。  
  
6.  选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。  
  
     例如，您希望自动重新启动它将失去与服务器的连接，或者如果将内容添加到服务器并且不会出现在 Microsoft 适配器向导中选择的过程。  
  
    > [!NOTE]
    >  退出当前浏览会话之前不刷新 browsingagent.exe。 例如，你必须退出**生成的添加项**浏览会话并重新进入以便更新 browsingagent.exe。  
  
7.  提供所需的所有信息后，单击**Apply**，然后单击**确定**接受连接信息。  
  
     必须设置用于 JD Edwards OneWorld 访问 JD Edwards OneWorld 的 BizTalk 适配器的连接参数。  
  
## <a name="adapter-required-properties"></a>所需的适配器属性  
 如果你未在控制面板中设置全局环境变量，就可以做到在本部分中。  
  
|参数|Description|  
|---------------|-----------------|  
|`Host`|键入主机服务器计算机名称的名称 (例如， `actsvr1`); 或的计算机的 IP 地址 (例如， `123.456.0.789`)。|  
|JAVA_HOME|键入 JDK 安装的完整路径。|  
|JDE Edwards 环境|例如，JD Edwards OneWorld 中键入环境名称`DV7333`。<br /><br /> DV7333 是开发环境的公用名，PY7333 是原型环境和 PD7333 是生产环境。|  
|JDEdwards JAR 文件|输入每个 JAR 文件的完整路径和文件名称：<br /><br /> -   Connector.jar<br />-   Kernel.jar<br />-   JDEJAccess.jar<br />-   JDEActionalInterop.jar<br /><br /> 必须用分号 （;） 和没有空格分隔每个 jar 文件。 例如：<br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|Password|键入指定用户的密码。|  
|Port|键入将要交换数据的端口号 (例如， `6009`)。|  
|用户名|键入将用于登录到 JD Edwards OneWorld 系统的 JD Edwards OneWorld 用户名。|  
  
