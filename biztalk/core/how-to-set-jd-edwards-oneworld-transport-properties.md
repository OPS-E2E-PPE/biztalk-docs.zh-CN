---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 5290f424bbeb5cf54e78c903c50a6c2d945bc8cc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014124"
---
# <a name="how-to-set-jd-edwards-oneworld-transport-properties"></a>如何设置博士 Edwards OneWorld 传输属性

## <a name="overview"></a>概述
JD Edwards OneWorld 传输属性系统定义用于设计和运行时登录。 在设计时，将这些凭据设置为浏览 JD Edwards OneWorld 业务函数，并在运行时进行调用。  
  
 在建立与 JD Edwards OneWorld 的连接后，将参数传递给连接对象（用户、密码、环境）。 它将返回 JD Edwards OneWorld 应用程序业务函数的一个实例。 通过企业/应用程序服务器名称及服务侦听到的已定义的 TCP/IP 端口可进一步定义这些凭据。  
  
 从名为 jdeinterop.ini 文件读取企业服务器名称和端口。 这些值必须是相同的系统定义设置中。  
  
> [!NOTE]
>  所有条目都要区分大小写。  
  
## <a name="set-the-transport-properties"></a>设置传输属性  
 在**传输属性**对话框中，你可以设置特定于服务器系统和你尝试访问的对象的连接和凭据参数。  
  
1.  提供凭据。  
  
     您可以使用以下方法之一访问 JD Edwards OneWorld 系统：  
  
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
  
## <a name="adapter-required-properties"></a>所需的适配器属性  
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
  
