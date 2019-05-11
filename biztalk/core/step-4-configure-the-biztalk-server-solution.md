---
title: 步骤 4：配置 BizTalk Server 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60e6a82-51af-41e5-a755-5f337492ba2f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d2d0e2c04fb11432f85821ec3e5ac4b65c490b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392533"
---
# <a name="step-4-configure-the-biztalk-server-solution"></a>步骤 4：配置 BizTalk Server 解决方案
在上一步骤中，创建和部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序以 Salesforce 通知接收到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和插入本地 SQL Server 数据库的详细信息。 在此步骤中，我们将配置中的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 配置应用程序主要涉及创建对应于我们在业务流程中创建的逻辑端口的物理端口。 它还涉及将物理端口绑定到逻辑端口。 我们将执行以下步骤以配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序：  
  
- 配置请求-响应 Wcf-basichttprelay 接收位置以接收来自 Salesforce 的机会通知。  
  
- 配置请求-响应 Wcf-webhttp 发送端口用于向 Salesforce 发送查询，用于检索与收到的机会通知相关的产品详细信息。 此发送端口还从 Salesforce 接收查询响应。  
  
- 配置单向 WCF-SQL 发送端口以从 Salesforce 查询响应插入到本地 SQL Server 数据库。  
  
- 配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序将在业务流程中的逻辑端口与中创建的物理端口相关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
### <a name="to-configure-the-wcf-basichttprelay-receive-location"></a>配置 Wcf-basichttprelay 接收位置  
  
1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 展开应用程序节点并查找**SalesforceIntegration**应用程序。 在部署时创建此应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从 Visual Studio 项目。  
  
2. 展开**SalesforceIntegration**应用程序中，右键单击**接收端口**，指向**新建**，然后单击**请求-响应接收端口**. 将端口名称指定为`ReceiveOppNotification`，然后从左窗格中，单击**接收位置**。  
  
3. 在接收位置属性对话框中，指定以下值：  
  
   |||  
   |-|-|  
   |“属性”|输入`ReceiveOppNotification`。|  
   |类型|选择**Wcf-basichttprelay**|  
   |接收处理程序|Select **BizTalkServerApplication**|  
   |接收管道|选择**XMLReceive**|  
   |发送管道|选择**PassThruTransmit**|  
  
    单击**配置**针对端口类型。  
  
4. 在 Wcf-basichttprelay 传输属性对话框中，指定以下值：  
  
   1. 上**常规**选项卡上，对于**地址 (URI)**，输入`https://btssalesforce.servicebus.windows.net/notifications/opportunity`。 在这里， **btssalesforce**是命名空间中创建[步骤 1:创建服务总线 Namespace](../core/step-1-create-a-service-bus-namespace.md)。 下面是在 Salesforce 中创建工作流时指定的相同 URL 指定的 URL[步骤 2:设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)。 设置工作流在其中每次将机会的阶段设置为已结束-赢得 Salesforce 发送通知到的 URL *<https://btssalesforce.servicebus.windows.net/notifications/opportunity>*。 我们指定相同的 URL 作为此过程中接收位置配置。 启用接收位置后，在创建中继终结点 URL 指定[!INCLUDE[winazure](../includes/winazure-md.md)]。  
  
   2. 上**安全**选项卡上，指定以下内容：  
  
      -   有关**安全模式**，选择**传输**对于**中继客户端身份验证类型**，选择**无**。  
  
      -   选择**启用服务发现**复选框可将发布中的服务行为[服务注册表](http://msdn.microsoft.com/library/windowsazure/dd582704.aspx)。 指定**显示名称**该项表示与该服务发布到注册表的名称。 可以设置**发现模式**向公有或私有。 对于本教程中，设置**显示名称**到`SF Outbound Notification`并**发现模式**到**公共**。  
  
      -   在访问控制服务框下单击**编辑**。 有关**访问控制服务 STS Uri**，输入`https://btssalesforce-sb.accesscontrol.windows.net/`。 有关**颁发者名称**并**颁发者密钥**，输入中保存的值[步骤 1:创建服务总线 Namespace](../core/step-1-create-a-service-bus-namespace.md)有关**默认用户**并**默认密钥**字段。  
  
   3. 单击**确定**直到您退出所有打开的对话框。  
  
### <a name="to-configure-the-wcf-webhttp-send-port"></a>若要配置 Wcf-webhttp 发送端口  
  
1. 展开**SalesforceIntegration**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态要求响应发送端口**.  
  
2. 在发送端口属性对话框中，指定以下值：  
  
   |||  
   |-|-|  
   |“属性”|输入`SalesforceREST`。|  
   |类型|选择**的 Wcf-webhttp**|  
   |发送处理程序|Select **BizTalkServerApplication**|  
   |发送管道|选择**PassThruTransmit**|  
   |接收管道|选择**AddNamespace**单击对要配置管道的管道的省略号按钮。<br /><br /> -在**阶段 1:解码**，对于**NamespaceBase**，输入`http://BtsSalesforceIntegration.QueryResult`。 这是你在中创建的 QueryResult.xsd 架构的命名空间[步骤 3b:使用 Wcf-webhttp 适配器从 Salesforce 检索机会详细信息](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)。 当**AddNamespace**接收管道从 Salesforce 接收响应，它将此命名空间添加到响应消息。 默认情况下，来自 Salesforce 的响应消息不包括任何命名空间。<br />     有关**NamespacePrefix**，输入`sf`。<br />-在**阶段 2:反汇编**，接受默认值，然后单击**确定**。|  
  
    在发送端口属性对话框中，单击**配置**针对端口类型。  
  
3. 在 Wcf-webhttp 传输属性对话框中，指定以下值：  
  
   1. 在 **“常规”** 选项卡上，请执行下列操作：  
  
      - 有关**地址 (URI)**，输入`https://<Salesforce_instance_name>.salesforce.com/services/data/v24.0`。 必须打开 Salesforce.com 门户的地址栏中复制 https:// 与 Salesforce.com 之间的文本，可以检索 Salesforce 实例名。 例如，如果 Salesforce 门户中的 URL 是*https://*<em>na15</em>*.salesforce.com/home/home.jsp*，Salesforce 实例名是**na15**.  
  
      - 下**HTTP 方法和 URL 映射**框中，指定以下内容：  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/query?q={VAR}" />  
        </BtsHttpUrlMapping>  
        ```  
  
         以下是如何使用此设置，若要查询 Salesforce 以检索有关机会通知的详细信息，我们必须执行 GET 操作在 Salesforce REST 终结点上的 (中的指定**地址**字段) 和追加查询以检索机会详细信息。 因此，URL 应如下所示：  
  
        ```  
        https://na15.salesforce.com/services/data/v24.0/query?q=<query_string>  
        ```  
  
         我们已有作为的一部分的 Salesforce REST 终结点**地址 (URI)** 字段。 因此，作为的一部分**HTTP 方法和 URL 映射**属性，我们指定使用 GET 方法并追加 **{VAR}** 为变量。  
  
      - 在中**Variable**框中，单击**编辑**。 在此框，指定如何为值 **{VAR}** 变量推导在运行时。  
  
         在[步骤 3b:使用 Wcf-webhttp 适配器从 Salesforce 检索机会详细信息](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)，我们升级了 Query 属性，从而导致创建**PropertySchema.xsd**。 我们将使用**查询**该架构，将查询字符串传递的该元素映射到在 URL 中的 {VAR} 变量中的元素。  
  
         在变量映射对话框中，**变量**列中列出的指定更早版本，例如，变量名称**VAR**。 在中**属性名称**列中，指定具有要传递到该变量的查询字符串的已提升属性的名称。 在本教程中，该属性的名称是**查询**。 最后，对于**属性 Namespace**，指定的命名空间**PropertySchema.xsd**，这是`https://BtsSalesforceIntegration.PropertySchema`。 单击“确定” 。  
  
         ![WCF 的常规选项卡&#45;WebHttp 适配器](../core/media/bts-sf-webhttp-general.jpg "BTS_SF_WebHttp_General")  
  
   2. 上**安全**选项卡上，对于**安全模式**，选择**传输**。  
  
   3. 上**行为**选项卡上，使用你在中创建的自定义行为[步骤 3d:启用 BizTalk Server 发送和接收来自 Salesforce 的消息](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)向 Salesforce 进行身份验证。 若要使用的行为，请执行以下操作：  
  
      -   右键单击**EndpointBehavior** ，然后选择**将扩展添加**。  
  
      -   在中**选择行为扩展**对话框中，选择**Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce**。 我们将行为添加到 machine.config 时使用此行为名称。  
  
      -   选择新添加的行为，然后指定以下值：  
  
          |||  
          |-|-|  
          |consumerKey （必需）|指定你的 Salesforce 帐户的使用者密钥。 可以通过转到在中创建的连接的 Salesforce 应用程序来检索使用者密钥[步骤 2:设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)。|  
          |consumerSecret （必需）|检索使用者机密从 Salesforce 连接的应用程序中创建[步骤 2:设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)。|  
          |密码 （必需）|指定 Salesforce 帐户的密码。 若要从第三方应用程序连接到 Salesforce，必须后跟安全令牌格式密码中指定的密码。 例如，如果密码不是**密码**和令牌**XXXXXX**，则必须输入`passwordXXXXXX`。|  
          |sessionTimeout|这具有默认值为 300。|  
          |用户名 （必需）|指定 Salesforce 开发人员登录帐户。|  
  
           ![为 WCF 行为 ' 选项卡&#45;WebHttp 适配器](../core/media/bts-sf-webhttp-behavior.jpg "BTS_SF_WebHttp_Behavior")  
  
   4. 上**消息**选项卡上，在**出站消息**框中，对于**为谓词取消正文**，输入`GET`。 对于 GET 方法，这可确保没有任何消息负载中发送到 Salesforce 的请求。  
  
   5. 单击**确定**直到您退出所有打开的对话框。  
  
### <a name="to-configure-the-wcf-sql-send-port"></a>若要配置 WCF-SQL 发送端口  
  
1.  展开**SalesforceIntegration**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**.  
  
2.  在发送端口属性对话框中，指定以下值：  
  
    |||  
    |-|-|  
    |“属性”|输入`SendToSQL`。|  
    |类型|选择**WCF SQL**|  
    |发送处理程序|Select **BizTalkServerApplication**|  
    |发送管道|选择**XMLTransmit**|  
  
     在发送端口属性对话框中，单击**配置**针对端口类型。  
  
3.  在 WCF-SQL 传输属性对话框中，指定以下值：  
  
    1.  在 **“常规”** 选项卡上，请执行下列操作：  
  
        -   下`Endpoint Address`，单击**配置**。 有关**InitialCatalog**属性，指定包含必须在其中输入 Salesforce 响应中的数据的表的数据库名称。 对于本教程中，输入此值作为`Orders`。 有关**Server**属性，输入服务器名称安装 SQL Server 数据库。  
  
        -   下**SOAP 操作标头**，指定要用于插入操作**OrderDetails**表。 必须输入`TableOp/Insert/dbo/OrderDetails`。  
  
    2.  在凭据选项卡上，如果将所有内容留空适配器使用 Windows 身份验证连接到 SQL Server 数据库。 如果你想要使用任何其他形式的身份验证，可以指定相关值。  
  
    3.  单击**确定**直到您退出所有打开的对话框。  
  
### <a name="to-configure-the-biztalk-server-application"></a>若要配置 BizTalk Server 应用程序  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**SalesforceIntegration**应用程序，，然后单击**配置**。  
  
2. 在配置应用程序对话框中，选择**NotificationServiceClient**业务流程，并在右窗格中执行以下操作：  
  
   1. 对于主机，选择**BizTalkServerApplication**。  
  
   2. 映射的逻辑接收端口**SalesforceNotificationPort**到物理接收端口， **ReceiveOppNotification**。  
  
   3. 将逻辑发送端口映射**SalesforceRESTInterface**到物理发送端口**SalesforceREST**。  
  
   4. 将逻辑发送端口映射**SendToSQL**到物理发送端口**SendToSQL**。  
  
      单击“确定” 。  
  
3. 右键单击**SalesforceIntegration**应用程序，然后单击**启动**。 这将启动**NotificationServiceClient**业务流程，启用该接收位置，并启动发送端口。  
  
   在本主题中，我们完成了配置中的解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过将业务流程中的逻辑端口与物理端口相关联的管理控制台。