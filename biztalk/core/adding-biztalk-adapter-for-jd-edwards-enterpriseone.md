---
title: "为博士 Edwards EnterpriseOne 添加 BizTalk 适配器 |Microsoft 文档"
description: "将博士 Edwards EnterpriseOne 添加到 BizTalk 管理、 创建发送端口、 配置传输属性中，和在 BizTalk Server 中使用博士 Edwards EnterpriseOne 适配器时使用 XMLReceive 和 XMLTransmit 管道"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baecebcd-c324-40aa-bacf-876f45b6c37f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46496172a1f436a302e5131f5ff55ede66c2a751
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="configure-jd-edwards-enterpriseone-artifacts-in-biztalk-administration"></a>在 BizTalk 管理中配置博士 Edwards EnterpriseOne 项目
用于 J.D.Edwards EnterpriseOne 的 Microsoft BizTalk 适配器包含接收处理程序和发送处理程序文件夹。 这两个文件夹包含 BizTalkServerApplication。 用于 J.D.Edwards EnterpriseOne 的 BizTalk 适配器是可创建的；它在 BizTalk Server 进程内运行，而不是在独立的主机进程中运行。  
  
## <a name="add-the-adapter-to-biztalk-administration"></a>将适配器添加到 BizTalk 管理 
  
1.  打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**平台设置**.  
  
2.  右键单击**适配器**，选择**新建**，然后选择**适配器**。  
  
3.  输入适配器的名称。 例如，输入`JDEEnterpriseOne`。  
  
4.  选择**JDEEnterpriseOne**从**适配器**列表，然后选择**确定**。  

## <a name="create-the-send-port"></a>创建发送端口  
  
1.  在**BizTalk Server 管理**，展开**应用程序**，然后展开你想要托管项目的应用程序
  
2.  右键单击**发送端口**，选择**新建**，然后选择**静态请求-响应端口**。  
  
3.  在**发送端口属性**对话框框中，执行以下操作：  
  
    -   在**名称**，输入发送端口名称。 例如，输入`SendToJDE`。  
  
    -   在**类型**下拉列表中，选择**JDEdwards**。  
  
    -   在**发送处理程序**下拉列表中，选择发送处理程序地址。  
  
5.  单击“确定”保存更改。

## <a name="configure-the-transport-properties"></a>配置传输属性

JD Edwards EnterpriseOne 传输属性用于设计和运行时。 在**传输属性**，设置的连接和凭据参数特定于服务器系统和你尝试访问的对象。  
  
 设置连接参数之后，您可以在适配器向导中浏览 JD Edwards EnterpriseOne 系统表、视图和步骤。  
  
 在建立与 JD Edwards EnterpriseOne 的连接后，参数将传递到连接对象（用户、密码、环境）。 该参数返回 JD Edwards EnterpriseOne 应用程序业务功能的实例。 通过企业/应用程序服务器名称及 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 侦听的已定义的 TCP/IP 端口可进一步定义这些凭据。  
  
> [!NOTE]
>  企业服务器名称和端口的默认值在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中配置。 它们将从名为 jdeinterop.ini 的文件进行读取。 如果你收到登录错误，请仔细检查凭据和值。  
  
### <a name="enter-the-properties"></a>输入属性  
  
1.  在 BizTalk Server 管理中，展开**应用程序**，然后展开你的应用程序。  
  
2.  右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。  
  
3.  在**发送端口属性**，选择**名称**，和为此端口的名称。 例如，输入`JDEEnterpriseOneSend`。  
  
4.  下**常规**中**传输类型**框中，选择**JDE EnterpriseOne**下拉列表中。  
  
5.  在**地址 (URI)**属性，选择省略号 (**...**). **JDE EnterpriseOne 传输属性**打开： 
  
     ![](../core/media/jdeenterprise-trans.gif "JDEEnterprise_Trans")  
  
6.  在**JDE EnterpriseOne 传输属性**属性中，展开**适配器所需属性**，然后输入博士 Edwards EnterpriseOne 服务器连接的所有必要的信息。  请使用以下指南设置传输属性：  
  
    |使用的项|若要执行此操作|  
    |--------------|----------------|  
    |**适配器所需的属性**||  
    |主机|键入主机服务器计算机的名称（例如：<br /><br /> `actsvr1`)<br /><br /> -或-<br /><br /> 键入计算机的 IP 地址（例如，<br /><br /> `123.456.0.789`)|  
    |JAVA_HOME|键入 JDK 安装的的完整路径（例如，<br /><br /> `C:\jdk1sdk1.4.2_07`)|  
    |JDEdwards 环境|键入博士 Edwards EnterpriseOne 环境的名称 (例如， `DV7333`)。<br /><br /> DV7333 是开发环境的公用名，PY7333 是原型环境的公用名，PD7333 是生产环境的公用名。|  
    |JDEdwards JAR 文件|输入每个 JAR 文件的完整路径和文件名：<br /><br /> -C:\JDEOWJars\Connector.jar<br />-C:\JDEOWJars\Kernel.jar<br />用于企业 Applications\J.D 程序 Files\Microsoft BizTalk 适配器。 Edwards EnterpriseOne(r) \Classes\JDEDynAccess.jar<br /><br /> 每个 jar 文件必须用分号 (;) 分开，中间不留空格（例如，<br /><br /> `<c:>\Connector.jar;<c:>\Kernel.jar;`)|  
    |密码|键入用户密码。 如果您不使用单一登录 (SSO)，则必须为用于 JD Edwards EnterpriseOne 的 BizTalk 适配器设置凭据参数以访问服务器系统。 密码对应于用户名，并在访问数据库时确定授予您的权限。|  
    |端口|键入数字标识符的发送或接收端口 (例如， `6009`)。|  
    |用户名|键入在用户的名称，然后单击**确定**。|  
    |**启动数据源所需的属性\*\***||  
    |数据源名称|键入数据源的名称。 对于所有数据类型，此名称是必需的。|  
    |数据库所有者|键入数据库所有者的名称。|  
    |数据库服务器名称|键入数据库服务器的名称。|  
    |数据库服务器端口|键入数据库服务器端口的标识编号。|  
    |数据库类型|为数据库类型键入单个字符。 例如：<br /><br /> **我**-iSeries<br /><br /> **O** -Oracle<br /><br /> **S** -SQL Server<br /><br /> **L** -SQL Server OLEDB<br /><br /> **W** -UDB|  
    |物理数据库名称|键入物理数据库的名称。 对于所有数据库类型，此名称是必需的。|  
    |**并发控制**||  
    |最大并发调用|键入数字值**最大并发调用**。 此数字表示的最大并发调用数，例如， `10`。<br /><br /> 此字段的默认值为 5。|  
    |**刷新代理**||  
    |刷新代理|选择**是**为**刷新代理**强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。<br /><br /> 例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者向服务器中添加了内容，但是由于它没有显示在 Microsoft 适配器向导中而无法选择它。|  
    |**安全服务器**||  
    |安全服务器名称|键入安全服务器的名称。 此字段是可选字段，默认为 JD Edwards 服务器主机。|  
    |服务名称连接|键入安全服务器和对象配置映射 (OCM） 使用的类型和端口号 默认为 JD Edwards 服务器端口。|  
    |**单一登录**||  
    |关联应用程序|仅当您使用的 SSO 时，才从下拉列表中选择关联应用程序。|  
    |使用 SSO|选择**是**如果你使用 SSO; 密码不需要在这种情况下。|  
  
7.  选择**确定**以接受所有属性。  
  
### <a name="bootstrap-data-source-required-properties"></a>启动数据源所需的属性  
 启动部分用于登录以提供对系统表的访问。 启动数据源信息定义 OCM 所在的数据源。  
  
 对于启动数据源参数，并非所有设置都是所有平台所必需的。 如果您使用的不常见的数据库，你可能需要更新的 [JDBj JDBC 驱动程序] 部分**jdeinterop.ini**声明 JDBC 驱动程序。 下表标识平台所需的设置：  
  
-   **iSeries**。 数据源名称、数据库类型、数据库服务器名、物理数据库名称  
  
-   **Oracle**。 数据源名称、数据库类型、物理数据库名称、数据库所有者  
  
-   **SQL Server**。 数据源名称、数据库类型、数据库服务器名称、数据库服务器端口、物理数据库名称、数据库所有者  
  
-   **SQL Server OLEDB**。 数据源名称、数据库类型、数据库服务器名称、数据库服务器端口、物理数据库名称、数据库所有者  
  
-   **UDB**。 数据源名称、数据库类型、物理数据库名称、数据库所有者  
  
### <a name="optimize-configuration"></a>优化配置  
 下列信息可以帮助您优化用于 JD Edwards EnterpriseOne 的 BizTalk 适配器的配置。  
  
#### <a name="max-concurrent-calls-parameter"></a>最大并发调用参数  
 在吞吐量超过了后端处理能力的情况下，可以使用 `Max Concurrent Calls` 参数。 将参数添加到中的适配器**发送端口传输属性**页后，可以激活消息重载保护。 默认值为 -1，表示不限制调用数量。  
  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将消息提交到传输适配器时，它首先接收来自适配器的一个批并对批调用 `TransmitMessage()` 以传输每个消息。 完成上述操作后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 对批调用 `Done()`，然后适配器开始将消息传输到后端。  
  
 如果调用 `Done` 之前 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 获取了多个批，则可能永远不会发生 `Done` 命令。 通过设置批中的最大消息数量，可以控制传输到后端的消息。  
  
 对参数的更改将在一分钟内生效。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须检索对保存到 SQL 数据库中为适配器配置的更改。  
  
#### <a name="refresh-agent"></a>刷新代理  
 当选择**是**为**刷新代理**，强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。  
  
 例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者向服务器中添加了内容，但是由于它在 Microsoft 适配器向导中不显示而无法选择它。  
  
 刷新代理参数在传输属性窗口中设置并刷新浏览和运行时代理。 runtimeagent.exe 在延迟一分钟或下一个发送调用之后进行刷新。  
  
> [!NOTE]
>  browsingagent.exe 在终止当前浏览会话之后进行刷新。 例如，你必须退出"添加生成的项..." 浏览会话和重新输入刷新 browsingagent.exe。  
  
#### <a name="single-sign-on"></a>单一登录  
 有两种方法可用于访问 JD Edwards EnterpriseOne 系统。 您可以使用登录凭据（传输属性登录参数）或单一登录 (SSO)。 选择**是**中**使用 SSO**字段用于单一登录。  
  
 有关详细信息和基本说明向上上单一登录设置，请参阅[博士 Edwards EnterpriseOne 的 BizTalk Adapter 中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)。
  
 您还必须在下拉列表中选择关联应用程序。 企业单一登录工具创建的关联应用程序代表诸如 JD Edwards EnterpriseOne 之类的应用程序。 用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 使用应用程序用户的凭据。  
  
 这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。 凭据是启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目的用户（应用程序用户）的凭据。  
  
 有关如何创建关联应用程序的详细信息请参阅[创建关联应用程序](../core/creating-affiliate-applications4.md)。 您也可以参阅 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 联机帮助。  

## <a name="use-the-xmltransmit-and-xmlreceive-pipelines"></a>使用 XMLTransmit 和 XMLReceive 管道

此适配器要求你选择**XMLTransmit**和**XMLReceive**为发送和接收管道分别。  
  
  
1.  在 BizTalk Server 管理中，展开**应用程序**，然后展开你的应用程序。  
  
2.  右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。  
  
3.  在**发送端口属性**对话框框中，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SendToJDEEnterpriseOne`。  
  
    2.  从**类型**下拉列表中，选择**JDE EnterpriseOne**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
4.  单击 **“确定”**。  


## <a name="see-also"></a>另请参阅  
 [开发应用程序](../core/developing-applications2.md)  
 [用于 JD Edwards EnterpriseOne 的单一登录和 BizTalk 适配器](../core/single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone.md)   