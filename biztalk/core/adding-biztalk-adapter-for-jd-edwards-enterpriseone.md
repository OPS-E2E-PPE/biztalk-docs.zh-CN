---
title: 添加用于 JD Edwards EnterpriseOne 的 BizTalk 适配器 |Microsoft Docs
description: 将 JD Edwards EnterpriseOne 添加到 BizTalk 管理、 创建发送端口、 配置传输属性和 BizTalk Server 中使用 JD Edwards EnterpriseOne 适配器时使用 XMLReceive 和 XMLTransmit 管道
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: baecebcd-c324-40aa-bacf-876f45b6c37f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66e0403ed0ebce64d97efc5819fd5003ca0cfdab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360925"
---
# <a name="configure-jd-edwards-enterpriseone-artifacts-in-biztalk-administration"></a>在 BizTalk 管理中配置 JD Edwards EnterpriseOne 项目
用于 J.D.Edwards EnterpriseOne 的 Microsoft BizTalk 适配器包含接收处理程序和发送处理程序文件夹。 文件夹包含 BizTalkServerApplication。 用于 J.D.Edwards EnterpriseOne 的 BizTalk 适配器是可创建对象;在进程中运行它与 BizTalk Server 运行，而不在独立的主机进程中。  

## <a name="add-the-adapter-to-biztalk-administration"></a>将适配器添加到 BizTalk 管理 

1.  打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**平台设置**.  

2.  右键单击**适配器**，选择**新建**，然后选择**适配器**。  

3.  输入适配器的名称。 例如，输入`JDEEnterpriseOne`。  

4.  选择**JDEEnterpriseOne**从**适配器**列表，然后选择**确定**。  

## <a name="create-the-send-port"></a>创建发送端口  

1.  在中**BizTalk Server 管理**，展开**应用程序**，然后展开你想要托管项目的应用程序

2.  右键单击**发送端口**，选择**新建**，然后选择**静态要求响应端口**。  

3.  在中**发送端口属性**对话框框中，执行以下操作：  

    -   在中**名称**，输入发送端口名称。 例如，输入 `SendToJDE`。  

    -   在中**类型**下拉列表中，选择**JDEdwards**。  

    -   在中**发送处理程序**下拉列表中，选择发送处理程序地址。  

5.  选择**确定**以保存所做的更改。

## <a name="configure-the-transport-properties"></a>配置传输属性

JD Edwards EnterpriseOne 传输属性用于设计和运行时。 在中**传输属性**，设置连接和凭据参数特定于服务器系统和你尝试访问的对象。  

 设置连接参数之后, 可以浏览 JD Edwards EnterpriseOne 系统表、 视图和适配器向导中的过程。  

 当连接到 JD Edwards EnterpriseOne 时，参数将传递到连接对象 （用户、 密码、 环境）。 它会返回 JD Edwards EnterpriseOne 应用程序业务函数的实例。 通过企业/应用程序服务器和其上定义的 TCP/IP 端口的名称来进一步定义这些凭据[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]侦听。  

> [!NOTE]
>  企业服务器名称和端口的默认值配置在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 它们将从名为 jdeinterop.ini 的文件进行读取。 如果您收到登录错误，请仔细检查凭据和值。  

### <a name="enter-the-properties"></a>输入属性  

1. 在 BizTalk Server 管理中，展开**应用程序**，然后展开你的应用程序。  

2. 右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。  

3. 在中**发送端口属性**，选择**名称**，并为此端口的名称。 例如，输入 `JDEEnterpriseOneSend`。  

4. 下**常规**，在**传输类型**框中，选择**JDE EnterpriseOne**下拉列表中。  

5. 在中**地址 (URI)** 属性中，选择省略号 (**...**). **JDE EnterpriseOne 传输属性**打开： 

    ![](../core/media/jdeenterprise-trans.gif "JDEEnterprise_Trans")  

6. 在中**JDE EnterpriseOne 传输属性**属性中，展开**适配器必需属性**，并输入所需的所有信息以连接到 JD Edwards EnterpriseOne 服务器。  使用以下准则来设置传输属性：  


   |                      使用此                       |                                                                                                                                                                                                            若要执行此操作                                                                                                                                                                                                             |
   |-----------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |           **适配器必需属性**           |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                        主机                         |                                                                                                                   键入主机服务器计算机的名称 (例如：<br /><br /> `actsvr1`)<br /><br /> -或者-<br /><br /> （例如，键入计算机的 IP 地址<br /><br /> `123.456.0.789`)                                                                                                                    |
   |                      JAVA_HOME                      |                                                                                                                                                                  键入 JDK 安装的完整路径 （例如，<br /><br /> `C:\jdk1sdk1.4.2_07`)                                                                                                                                                                  |
   |                JDEdwards 环境                |                                                                                  在 JD Edwards EnterpriseOne 中键入环境的名称 (例如， `DV7333`)。<br /><br /> DV7333 是开发环境的公用名，PY7333 是原型环境和 PD7333 是生产环境。                                                                                   |
   |                 JDEdwards JAR 文件                 | 输入每个 JAR 文件的完整路径和文件名称：<br /><br /> -   C:\JDEOWJars\Connector.jar<br />-   C:\JDEOWJars\Kernel.jar<br />-Program Files\Microsoft BizTalk Adapters for Enterprise applications\j.d. Edwards EnterpriseOne(r)\Classes\JDEDynAccess.jar<br /><br /> 每个 jar 文件必须 （例如，用分号 （;） 和没有空格分隔<br /><br /> `<c:>\Connector.jar;<c:>\Kernel.jar;`) |
   |                      Password                       |                                                              键入用户密码。 如果不使用单一登录 (SSO)，则必须设置凭据参数，用于访问服务器系统的 JD Edwards EnterpriseOne 的 BizTalk 适配器。 密码对应于用户名，并确定授予访问数据库时的权限。                                                              |
   |                        Port                         |                                                                                                                                                                         键入数字标识符的发送或接收端口 (例如， `6009`)。                                                                                                                                                                          |
   |                      用户名                      |                                                                                                                                                                                         键入在用户的名称，然后单击**确定**。                                                                                                                                                                                         |
   | **启动数据源所需的属性\*\\**\* |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                  数据源名称                   |                                                                                                                                                                           键入数据源的名称。 此名称是必需的所有数据类型。                                                                                                                                                                            |
   |                   数据库所有者                    |                                                                                                                                                                                               键入数据库所有者的名称。                                                                                                                                                                                                |
   |                数据库服务器名称                 |                                                                                                                                                                                               键入数据库服务器的名称。                                                                                                                                                                                               |
   |                数据库服务器端口                 |                                                                                                                                                                                     键入数据库服务器端口的标识编号。                                                                                                                                                                                      |
   |                    数据库类型                    |                                                                                                          键入数据库类型的单个字符。 例如：<br /><br /> **我**-iSeries<br /><br /> **O** - Oracle<br /><br /> **S** -SQL Server<br /><br /> **L** -SQL Server OLEDB<br /><br /> **W** - UDB                                                                                                           |
   |               物理数据库名称                |                                                                                                                                                                      键入物理数据库的名称。 此名称是必需的所有数据库类型。                                                                                                                                                                       |
   |               **并发控制**               |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                最大并发调用数                 |                                                                                                                    键入用于值的数值**最大并发调用**。 此数字表示的最大并发调用数，例如， `10`。<br /><br /> 此字段的默认值为 5。                                                                                                                    |
   |                  **刷新代理**                  |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                    刷新代理                    |                           选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。<br /><br /> 例如，您希望自动重新启动它将失去与服务器的连接，或者如果将内容添加到服务器并且不会出现在 Microsoft 适配器向导中选择的过程。                           |
   |                 **安全服务器**                 |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                安全服务器名称                 |                                                                                                                                                             键入安全服务器的名称。 此字段是可选的默认为 JD Edwards 服务器主机。                                                                                                                                                              |
   |                服务名称连接                 |                                                                                                                                                  键入安全服务器和对象配置映射 (OCM) 使用的端口号。 默认值为 JD Edwards 服务器端口。                                                                                                                                                  |
   |                 **单一登录**                  |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                关联应用程序                |                                                                                                                                                                        仅当使用 SSO，请从下拉列表中选择关联应用程序。                                                                                                                                                                        |
   |                       使用 SSO                       |                                                                                                                                                                           选择**是**如果您使用的 SSO; 密码则不需要在这种情况下。                                                                                                                                                                           |


7. 选择**确定**以接受所有属性。  

### <a name="bootstrap-data-source-required-properties"></a>启动数据源所需的属性  
 启动部分的单一登录用于提供对系统表的访问权限。 启动数据源信息定义 OCM 所在的数据源。  

 对于启动数据源参数，并非所有设置都需要所有平台。 如果使用的数据库，您可能需要更新的 [JDBJ-JDBC DRIVERS] 部分**jdeinterop.ini**声明 JDBC 驱动程序。 以下列表标识平台所需的设置：  

-   **iSeries**。 数据源名称、 数据库类型、 数据库服务器名称，物理数据库名称  

-   **Oracle**。 数据源名称、 数据库类型，物理数据库名称、 数据库所有者  

-   **SQL Server**。 数据源名称、 数据库类型、 数据库服务器名称、 数据库服务器端口、 物理数据库名称、 数据库所有者  

-   **SQL Server OLEDB**。 数据源名称、 数据库类型、 数据库服务器名称、 数据库服务器端口、 物理数据库名称、 数据库所有者  

-   **UDB**。 数据源名称、 数据库类型，物理数据库名称、 数据库所有者  

### <a name="optimize-configuration"></a>优化配置  
 以下信息可以帮助您优化用于 JD Edwards EnterpriseOne 的 BizTalk 适配器的配置。  

#### <a name="max-concurrent-calls-parameter"></a>最大并发调用参数  
 可以使用`Max Concurrent Calls`在吞吐量超过了后端处理能力的实例中的参数。 将参数添加到中的适配器**发送端口传输属性**页后，可以激活消息重载保护。 默认值为-1，这意味着不限制调用数量。  

 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将消息提交到传输适配器，它首先从适配器获取批并调用`TransmitMessage()`对批，将每个消息传送。 完成后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]调用`Done()`批处理，然后适配器开始将消息传输到后端上。  

 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]之前获得了多个批`Done`调用，`Done`命令可能永远不会发生。 通过在批处理中设置的最大消息数，可以控制到后端的消息。  

 在一分钟内，对参数的更改将生效。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须检索保存在 SQL 数据库中的适配器配置的更改。  

#### <a name="refresh-agent"></a>刷新代理  
 当选择**是**有关**刷新代理**，强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。  

 例如，您希望进程后，如果失去与服务器的连接或内容添加到服务器，并且它不会出现在选择 Microsoft 适配器向导时自动重新启动。  

 刷新代理参数在传输属性窗口中设置，并刷新浏览和运行时代理。 Runtimeagent.exe 在延迟一分钟或在下一步发送调用后刷新。  

> [!NOTE]
>  在终止当前浏览会话，则不刷新 browsingagent.exe。 例如，你必须退出"添加生成的项..." 浏览会话并重新进入以便刷新 browsingagent.exe。  

#### <a name="single-sign-on"></a>单一登录  
 有两种方法可用于访问 JD Edwards EnterpriseOne 系统。 可以使用登录凭据 （传输属性登录参数） 或单一登录 (SSO)。 选择**是**中**使用 SSO**字段以使用单一登录。  

 有关详细信息和设置单一登录设置的基本说明，请参阅[JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)。

 您还必须在下拉列表中选择关联应用程序。 关联应用程序，由企业单一登录工具创建代表 JD Edwards EnterpriseOne 之类的应用程序。 用于 JD Edwards EnterpriseOne 的 BizTalk 适配器使用应用程序用户的凭据。  

 从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。 凭据是启动的用户 （应用程序用户）[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。  

 有关如何创建关联应用程序的详细信息请参阅[创建关联应用程序](../core/creating-affiliate-applications4.md)。 您还可以指 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]联机帮助。  

## <a name="use-the-xmltransmit-and-xmlreceive-pipelines"></a>使用 XMLTransmit 和 XMLReceive 管道

此适配器要求您选择**XMLTransmit**并**XMLReceive**的发送和接收管道，分别。  


1.  在 BizTalk Server 管理中，展开**应用程序**，然后展开你的应用程序。  

2.  右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。  

3.  在中**发送端口属性**对话框框中，执行以下操作：  

    1.  例如，键入发送端口的名称`SendToJDEEnterpriseOne`。  

    2.  从**类型**下拉列表中，选择**JDE EnterpriseOne**。  

    3.  从**发送处理程序**下拉列表中，选择 URI。  

    4.  从发送管道下拉列表，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  

    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  

4.  单击“确定” 。  


## <a name="see-also"></a>请参阅  
 [开发应用程序](../core/developing-applications2.md)  
 [用于 JD Edwards EnterpriseOne 的单一登录和 BizTalk 适配器](../core/single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone.md)   