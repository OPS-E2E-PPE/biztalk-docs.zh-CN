---
title: "步骤 4： 配置 BizTalk Server 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d60e6a82-51af-41e5-a755-5f337492ba2f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6587e0a8ff84b352ba6f029a7687139daabb72a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-configure-the-biztalk-server-solution"></a>步骤 4： 配置 BizTalk Server 解决方案
在上一步中，你创建并部署了一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序，以将 Salesforce 通知接收到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，并将详细信息插入到本地 SQL Server 数据库。 在本步骤中，我们将在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中配置应用程序。 配置应用程序主要涉及创建对应于我们在业务流程中创建的逻辑端口的物理端口。 它还涉及将物理端口绑定到逻辑端口。 我们将执行以下步骤来配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序。  
  
-   配置请求-响应 WCF-BasicHttpRelay 接收位置，以接收来自 Salesforce 的机会通知。  
  
-   配置请求-响应 WCF-WebHttp 发送端口，将查询发送到 Salesforce，以检索与收到的机会通知有关的产品详细信息。 此发送端口还接收来自 Salesforce 的查询响应。  
  
-   配置单向 WCF-SQL 发送端口，以将来自 Salesforce 的查询响应插入到本地 SQL Server 数据库。  
  
-   通过将业务流程中的逻辑端口与在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建的物理端口相关联，配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序。  
  
### <a name="to-configure-the-wcf-basichttprelay-receive-location"></a>配置 WCF-BasicHttpRelay 接收位置  
  
1.  打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 展开应用程序节点并查找**SalesforceIntegration**应用程序。 该应用程序是在你从 Visual Studio 部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目时创建的。  
  
2.  展开**SalesforceIntegration**应用程序中，右键单击**接收端口**，指向**新建**，然后单击**请求-响应接收端口**. 将端口名称指定为`ReceiveOppNotification`从左窗格中，单击**接收位置**。  
  
3.  在“接收位置属性”对话框中，指定以下值：  
  
    |||  
    |-|-|  
    |Name|输入`ReceiveOppNotification`。|  
    |类型|选择**WCF BasicHttpRelay**|  
    |接收处理程序|选择**BizTalkServerApplication**|  
    |接收管道|选择**XMLReceive**|  
    |发送管道|选择**PassThruTransmit**|  
  
     单击**配置**针对端口类型。  
  
4.  在“WCF-BasicHttpRelay 传输属性”对话框中，指定以下值：  
  
    1.  上**常规**选项卡上，为**地址 (URI)**，输入`https://btssalesforce.servicebus.windows.net/notifications/opportunity`。 在这里， **btssalesforce**是你在中创建的命名空间[步骤 1： 创建服务总线 Namespace](../core/step-1-create-a-service-bus-namespace.md)。 指定以下是你在 Salesforce 中创建工作流时指定的相同 URL 的 URL[步骤 2： 设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)。 设置工作流在其中每次有机会的阶段设置为关闭入选，Salesforce 发送通知到的 URL *https://btssalesforce.servicebus.windows.net/notifications/opportunity*。 我们在此处指定与接收位置配置部分相同的 URL。 启用了接收位置时，将在 [!INCLUDE[winazure](../includes/winazure-md.md)] 中创建由 URL 指定的中继终结点。  
  
    2.  上**安全**选项卡上，指定下列各项：  
  
        -   有关**安全模式**，选择**传输**和**中继客户端身份验证类型**，选择**无**。  
  
        -   选择**启用服务发现**复选框以发布中的服务行为[服务注册表](http://msdn.microsoft.com/library/windowsazure/dd582704.aspx)。 指定**显示名称**表示与其注册表发布服务的名称。 你可以设置**发现模式**向公有或私有。 对于本教程中，设置**显示名称**到`SF Outbound Notification`和**发现模式**到**公共**。  
  
        -   在访问控制服务中，单击**编辑**。 有关**访问控制服务 STS Uri**，输入`https://btssalesforce-sb.accesscontrol.windows.net/`。 有关**颁发者名称**和**颁发者密钥**，输入值保存在[步骤 1： 创建服务总线 Namespace](../core/step-1-create-a-service-bus-namespace.md)为**默认用户**和**默认密钥**字段。  
  
    3.  单击**确定**直到退出所有打开的对话框。  
  
### <a name="to-configure-the-wcf-webhttp-send-port"></a>配置 WCF-WebHttp 发送端口  
  
1.  展开**SalesforceIntegration**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**.  
  
2.  在“发送端口属性”对话框中，指定以下值：  
  
    |||  
    |-|-|  
    |Name|输入`SalesforceREST`。|  
    |类型|选择**WCF WebHttp**|  
    |发送处理程序|选择**BizTalkServerApplication**|  
    |发送管道|选择**PassThruTransmit**|  
    |接收管道|选择**AddNamespace**单击针对管道配置管道的省略号按钮。<br /><br /> -在**阶段 1： 解码**，为**NamespaceBase**，输入`http://BtsSalesforceIntegration.QueryResult`。 这是你在中创建的 QueryResult.xsd 架构命名空间[步骤 3b： 从 Salesforce 使用 WCF WebHttp 适配器检索机会详细信息](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)。 当**AddNamespace**接收管道收到来自 Salesforce 的响应，它会此命名空间添加到响应消息。 默认情况下，来自 Salesforce 的响应消息不包括任何命名空间。<br />     有关**NamespacePrefix**，输入`sf`。<br />-在**阶段 2： 反汇编**，接受默认值，然后单击**确定**。|  
  
     在发送端口属性对话框中，单击**配置**针对端口类型。  
  
3.  在“WCF-WebHttp 传输属性”对话框中，指定以下值：  
  
    1.  在 **“常规”** 选项卡上，请执行下列操作：  
  
        -   有关**地址 (URI)**，输入`https://<Salesforce_instance_name>.salesforce.com/services/data/v24.0`。 你可以通过在你打开 Salesforce.com 门户的地址栏中复制 https:// 与 Salesforce.com 之间的文本，检索 Salesforce 实例名。 例如，如果在 Salesforce 门户的 URL 是*https://**na15**.salesforce.com/home/home.jsp*，Salesforce 实例名称是**na15**.  
  
        -   下**HTTP 方法和 URL 映射**框中，指定下列各项：  
  
            ```  
            <BtsHttpUrlMapping>  
            <Operation Method="GET" Url="/query?q={VAR}" />  
            </BtsHttpUrlMapping>  
            ```  
  
             下面是如何使用此设置-若要查询 Salesforce 检索有关机会通知的详细信息，我们必须执行的 Salesforce REST 终结点上的 GET 操作 (中指定**地址**字段) 和追加若要检索的机会详细信息的查询。 因此，URL 应如下所示：  
  
            ```  
            https://na15.salesforce.com/services/data/v24.0/query?q=<query_string>  
            ```  
  
             我们已有的 Salesforce REST 终结点的一部分**地址 (URI)**字段。 因此，作为的一部分**HTTP 方法和 URL 映射**属性，指定使用 GET 方法和追加**{VAR}**作为变量。  
  
        -   在**变量映射**框中，单击**编辑**。 在此框中，你指定如何为值**{VAR}**变量在运行时将推导。  
  
             在[步骤 3b： 从 Salesforce 使用 WCF WebHttp 适配器检索机会详细信息](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)，我们已升级的查询属性，这将导致中创建**PropertySchema.xsd**。 我们将使用**查询**该架构，通过将该元素映射到 URL 中的 {VAR} 变量传递的查询字符串中的元素。  
  
             在变量映射对话框中，**变量**列中列出的指定更早版本，例如，变量名称**VAR**。 在**属性名称**列中，指定要传递给该变量的查询字符串的提升属性的名称。 在本教程中，该属性的名称是**查询**。 最后，为**属性 Namespace**，指定的命名空间**PropertySchema.xsd**，即`https://BtsSalesforceIntegration.PropertySchema`。 单击 **“确定”**。  
  
             ![常规选项卡上的 WCF &#45;WebHttp 适配器](../core/media/bts-sf-webhttp-general.jpg "BTS_SF_WebHttp_General")  
  
    2.  上**安全**选项卡上，为**安全模式**，选择**传输**。  
  
    3.  上**行为**选项卡上，使用你在中创建的自定义行为[步骤 3d： 启用 BizTalk Server 发送和接收来自 Salesforce](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)向 Salesforce 进行身份验证。 若要使用该行为，请执行以下操作：  
  
        -   右键单击**EndpointBehavior** ，然后选择**将扩展添加**。  
  
        -   在**选择行为扩展**对话框中，选择**Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce**。 我们在将行为添加到 machine.config 时已使用此行为名称。  
  
        -   选择新添加的行为，然后指定以下值：  
  
            |||  
            |-|-|  
            |consumerKey（必需）|指定你的 Salesforce 帐户的使用者密钥。 你可以通过转到在创建的连接的 Salesforce 应用程序检索的使用者密钥[步骤 2： 设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)。|  
            |consumerSecret（必需）|检索使用者机密来自 Salesforce 连接的应用程序中创建[步骤 2： 设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)。|  
            |密码（必需）|指定 Salesforce 帐户的密码。 若要从第三方应用程序连接到 Salesforce，必须以密码后跟安全令牌的格式指定密码。 例如，如果密码是**密码**和令牌**XXXXXX**，必须输入`passwordXXXXXX`。|  
            |sessionTimeout|此项的默认值为 300。|  
            |用户名（必需）|指定 Salesforce 开发人员登录帐户。|  
  
             ![WCF &#45; 的行为选项卡WebHttp 适配器](../core/media/bts-sf-webhttp-behavior.jpg "BTS_SF_WebHttp_Behavior")  
  
    4.  上**消息**选项卡上，在**出站消息**框中，为**禁止显示谓词的正文**，输入`GET`。 对于 GET 方法，这可以确保在要发送给 Salesforce 的请求中没有任何消息负载。  
  
    5.  单击**确定**直到退出所有打开的对话框。  
  
### <a name="to-configure-the-wcf-sql-send-port"></a>配置 WCF-SQL 发送端口  
  
1.  展开**SalesforceIntegration**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**.  
  
2.  在“发送端口属性”对话框中，指定以下值：  
  
    |||  
    |-|-|  
    |Name|输入`SendToSQL`。|  
    |类型|选择**WCF SQL**|  
    |发送处理程序|选择**BizTalkServerApplication**|  
    |发送管道|选择**XMLTransmit**|  
  
     在发送端口属性对话框中，单击**配置**针对端口类型。  
  
3.  在“WCF-SQL 传输属性”对话框中，指定以下值：  
  
    1.  在 **“常规”** 选项卡上，请执行下列操作：  
  
        -   下`Endpoint Address`，单击**配置**。 有关**InitialCatalog**属性，指定包含必须在其中输入 Salesforce 响应中的数据的表的数据库名称。 对于本教程中，输入此值为`Orders`。 有关**服务器**属性，输入服务器名称，SQL Server 数据库安装。  
  
        -   下**SOAP 操作标头**，指定要用于插入操作**OrderDetails**表。 必须输入`TableOp/Insert/dbo/OrderDetails`。  
  
    2.  在“凭据”选项卡上，如果你将所有项留空，则适配器将使用 Windows 身份验证连接到 SQL Server 数据库。 如果你要使用任何其他形式的身份验证，则可以指定相关值。  
  
    3.  单击**确定**直到退出所有打开的对话框。  
  
### <a name="to-configure-the-biztalk-server-application"></a>配置 BizTalk Server 应用程序  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**SalesforceIntegration**应用程序，，然后单击**配置**。  
  
2.  在配置应用程序对话框中，选择**NotificationServiceClient**业务流程，并从右窗格中执行以下操作：  
  
    1.  对于主机，选择**BizTalkServerApplication**。  
  
    2.  映射逻辑接收端口**SalesforceNotificationPort**于物理接收端口， **ReceiveOppNotification**。  
  
    3.  逻辑发送端口映射**SalesforceRESTInterface**的物理发送端口， **SalesforceREST**。  
  
    4.  逻辑发送端口映射**SendToSQL**的物理发送端口， **SendToSQL**。  
  
     单击 **“确定”**。  
  
3.  右键单击**SalesforceIntegration**应用程序，然后单击**启动**。 这将启动**NotificationServiceClient**业务流程，使接收位置，并开始发送端口。  
  
 在本主题中，我们通过将业务流程中的逻辑端口与物理端口相关联，完成了在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中配置解决方案。