---
title: 在 BizTalk Server 中的使用逻辑应用适配器 |Microsoft Docs
description: 安装和配置来创建接收端口、 接收位置，以及 BizTalk Server 中的发送端口的逻辑应用适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72f2a5ac-a1f6-4bdb-8c29-8267ede75b17
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e13756fb6310b73f8e7fb88c336bdf2a7bbc1372
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972822"
---
# <a name="logic-app-adapter"></a>逻辑应用适配器

## <a name="overview"></a>概述
BizTalk Server 使用逻辑应用适配器来接收消息从 Azure 逻辑应用，或将消息发送到 Azure 逻辑应用。 

在 Azure 中，我们将创建一个逻辑应用。 此逻辑应用使用 BizTalk 连接器来连接到 BizTalk Server 创建的接收位置。 本主题假定你已具备一定的 Azure 逻辑应用。 如果您熟悉逻辑应用，我们建议[学习有关它们的详细信息](https://azure.microsoft.com/documentation/articles/app-service-logic-what-are-logic-apps/)，，甚至[创建逻辑应用](https://azure.microsoft.com/documentation/articles/app-service-logic-create-a-logic-app/)。

在本主题中，我们列出逻辑应用从 BizTalk Server 中接收消息的步骤。 逻辑应用将另一种方法，将消息发送到 BizTalk Server。 在接收端使用在 IIS 中的应用程序来处理与 Azure 服务的通信。 如果 BizTalk Server 在本地，还会在 BizTalk Server 上安装数据网关和在 Azure 中创建网关。 

如果 Azure 虚拟机 (VM) 上安装 BizTalk Server，则您可以选择公开 VM 作为 HTTP 终结点 （您获取的 URL），或不会将其作为 HTTP 终结点进行公开。 如果将其公开，您不需要使用网关。 在逻辑应用中，可以在 BizTalk 连接器中输入你的 URL。 如果不公开 VM (没有 URL)，然后您需要使用网关。 本主题中列出这些步骤。

我们还展示如何将消息从 BizTalk Server 发送到 Azure 逻辑应用。 逻辑应用将另一种方法，从 BizTalk Server 接收消息。 正如您将看到在本主题中，在发送端是非常简单。

使用本主题创建接收位置和发送端口使用逻辑应用适配器。 可以使用本地 （已加入域） BizTalk Server 中或运行 BizTalk Server 的 Azure 虚拟机中的逻辑应用适配器。 

## <a name="requirements"></a>要求

- 若要登录到 Azure 门户中，并创建一个逻辑应用，一个 Azure 订阅。
- 可选。 若要将测试消息发送到逻辑应用，安装 HTTP 测试工具，如[Fiddler](http://www.telerik.com/fiddler)或[Postman](https://www.getpostman.com/)。 如果使用另一种方法来将消息发送到逻辑应用，你无需使用这些工具。 

## <a name="receive-messages-from-a-logic-app"></a>从逻辑应用接收消息

有几个步骤所涉及的 BizTalk Server 从逻辑应用接收消息。 本部分列出了这些步骤。 可能的用户界面中 Azure 更改，因此某些步骤可能无法完全按照列出它。 

#### <a name="prerequisites"></a>必要條件

- 如果 BizTalk Server，在本地安装和配置[的本地数据网关](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-install/)为逻辑应用。 然后，在 Azure 中，[创建数据网关资源](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-connection/)连接到 BizTalk Server。
- 如果 VM 未公开 HTTP 终结点为 Azure VM 上安装 BizTalk Server，然后安装和配置[的本地数据网关](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-install/)为逻辑应用。 然后，在 Azure 中，[创建数据网关资源](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-connection/)连接到 BizTalk Server。
- 如果在 Azure VM 上安装 BizTalk Server，并且 VM 公开为 HTTP 终结点，然后该网关不是需要或者使用。 

### <a name="step-1-install-the-logic-app-adapter"></a>步骤 1： 安装逻辑应用适配器

逻辑应用适配器是一个单独的下载，并且不包含 BizTalk Server 安装。 

> [!IMPORTANT] 
> 若要下载 LogicAppAdapter.iso:
> 
> 1. 转到[逻辑应用的 Microsoft BizTalk Server 适配器](https://www.microsoft.com/download/details.aspx?id=54287)，并保存。 
> 2. 打开 LogicAppAdapter.iso，并运行**逻辑应用 Adapter.msi**文件来安装。

1. 在 BizTalk 服务器上，下载并安装逻辑应用适配器。 

2. 双击选择**逻辑应用 Adapter.msi**安装。 接受许可协议，并**安装**。
3. **完成**安装，d 重启**BizTalkServerApplication**并**BizTalkServerIsolatedHost**主机实例。

安装后，你具有：

- 逻辑应用适配器添加到 BizTalk 管理。
- 发送处理程序创建，并使用 BizTalkServerApplication 主机。
- 接收处理程序将创建为 WCF 服务，并使用 BizTalkServerIsolatedHost 主机。
- `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter`文件夹创建，并包括两个服务： 管理和 ReceiveService。 

    **管理**逻辑应用中的 BizTalk 连接器用于连接到 BizTalk Server 使用数据网关。 此管理服务允许 BizTalk Server 以便接收来自 Azure 逻辑应用使用数据网关的消息。 在 BizTalk 接收端仅使用此服务。 它不使用发送方。

    **ReceiveService**输入接收位置时 BizTalk 连接器中的逻辑应用中使用。 **ReceiveService**负责从逻辑应用发送的消息。 在 BizTalk 接收端仅使用此服务。 它不使用发送方。


### <a name="step-2-create-the-iis-applications"></a>步骤 2： 创建 IIS 应用程序

IIS 应用程序使用的管理和 ReceiveService 服务。

你可以运行使用新的应用程序池或现有的应用程序池的 IIS 应用程序。 应用程序池的标识要求运行 BizTalk 服务，如 BizTalk Application Users 和 BizTalk Isolated Host Users 组的帐户所在的组的成员身份。  

> [!TIP] 
> 如果创建新的应用程序池，然后保持默认.NET CLR 版本，并托管的管道。 请记住，选择已与你的 BizTalk 服务帐户所在的 BizTalk 组的成员身份的标识 （高级设置）。 

#### <a name="create-the-management-iis-application"></a>创建管理 IIS 应用程序
此 IIS 应用程序的 URL 由 BizTalk 连接器 （在逻辑应用） 用于在 BizTalk Server 上使用数据网关。

1. 打开 Internet 信息服务 (IIS) 管理器。
2. 右键单击**Default Web Site**，并**添加应用程序**。 在此新的应用程序： 

    1. 输入**别名**（名称） 为应用程序，例如**IISLogicApp**。 
    2. **选择**应用程序池。
    3. 设置**物理路径**到`C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter\Management`。 
    3. **测试设置**以确认应用程序池标识，将传递身份验证和授权测试。

3. 单击“确定”保存更改。
4. 打开 web 浏览器并转到`http://localhost/YourApplicationAlias/schemas?api-version=2016-10-26`，如`http://localhost/IISLogicApp/Schemas?api-version=2016-10-26`。 是架构显示的列表，或系统将提示您打开/保存`schemas.json`。 实际结果取决于在 web 浏览器。 如果这两个命令发生，则可能缺少应用程序池标识到 BizTalk 组的成员身份。

#### <a name="create-the-biztalk-receiveservice-iis-application"></a>创建 BizTalk ReceiveService IIS 应用程序
由 BizTalk 连接器 （在逻辑应用） 使用此 IIS 应用程序的 URL 时选择接收位置。 

1. 打开 Internet 信息服务 (IIS) 管理器。
2. 右键单击**Default Web Site**，并**添加应用程序**。 在此新的应用程序： 

    1. 输入**别名**（名称） 为应用程序，例如**ReceiveWCFService**。 
    2. **选择**为以前的 IIS 应用程序的相同应用程序池。
    3. 设置**物理路径**到`C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter\ReceiveService`。 
    3. **测试设置**以确认应用程序池标识，将传递身份验证和授权测试。

3. 单击“确定”保存更改。


### <a name="step-3-create-a-logic-app"></a>步骤 3： 创建逻辑应用

1. 在中[Azure 门户](https://portal.azure.com)，创建新的逻辑应用。
2. 添加**收到 HTTP 请求时**触发器。
3. 添加**BizTalk Server-从 JSON 准备消息**操作。 
4. **可选**： 选择**通过本地数据网关连接**，并输入以下命令： 

    | “属性” | Description |
   | --- | --- |
    | BizTalk 服务器 URL | BizTalk 管理 IIS 应用程序 URL 中输入完全限定的域名 (FQDN)。 例如，输入`http://BizTalkServerName.corp.contoso.com/IISLogicApp/`。 |
    | 身份验证类型 | 选择**Windows**。 |
   | 用户名 | 输入 IIS 应用程序池的标识。 |
   | Password | 输入 IIS 应用程序池的密码。 |
   | 网关 | 选择你创建的网关。 |

    > [!TIP] 
    > 请记住，数据网关是仅需要：
    > - 您使用的本地 BizTalk Server
    > - 使用 BizTalk Server Azure 虚拟机*和*VM 未公开为 HTTP 终结点 (没有 URL)

5. 选择“创建”。 
6. 配置操作。 有关**正文**，选择 HTTP 正文输出。 有关**架构**，选择你想要使用的架构。 

    > [!NOTE] 
    > 此步骤假定你熟悉架构在 BizTalk 中，并知道所需的架构。 如果您不能确定，然后部署 HelloWorld SDK 示例、 更新及其项目以使用逻辑应用适配器，并使用其架构和示例消息。 

7. 添加新的步骤，并选择**BizTalk Server-发送消息**操作。 有关**接收位置**，从下拉列表中，选择 URL 或输入 ReceiveService IIS 应用程序 URL 的完全限定的域名 (FQDN)。 例如，输入`http://BizTalkServerName.corp.contoso.com/ReceiveWCFService/Service1.svc`。

    > [!TIP] 
    > 在创建接收位置时，此确切的 URL 还中输入将接收位置传输属性作为**公共地址**（常规选项卡）。

    有关**正文**，从以前的 BizTalk Server 操作中选择正文输出。 

8. **保存**所做的更改。 

保存时，HTTP 请求触发器会自动创建一个 URL。 复制此 URL;在需要**步骤 5： 将消息发送**。

### <a name="step-4-create-a-receive-port-and-a-receive-location"></a>步骤 4： 创建接收端口和接收位置

> [!NOTE] 
> 而不是创建您自己的接收端口和接收位置，可以将部署 HelloWorld SDK 示例。 更新为使用逻辑应用适配器的项目。 
 
本部分列出了创建自己的项目的步骤。 

1. 在 BizTalk Server 管理中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开要为应用程序运行接收位置。 例如，展开**BizTalk Application 1**。
2. 右击选择**接收端口**，选择**新建**，然后选择**单向接收端口**。
3. 在接收端口属性中，输入以下信息：  

    | 使用此选项 | 执行的操作 |
    | --- | --- |
    | **名称** | 输入接收端口的名称。 例如，输入**LAReceivePort**。 |
    | **身份验证** | 选项： <br/><ul><li>无身份验证： 默认值。 禁用身份验证。</li><li>身份验证失败时删除消息： 启用身份验证，但若要删除未经验证的消息。</li><li>身份验证失败时保留消息： 单击此选项可启用身份验证并保留未经验证的消息。 </li></ul>|
    | **为失败消息启用路由功能** | 将路由到某个订阅应用程序的处理失败的任何消息 （例如其他接收端口或业务流程计划）。 取消选中此选项可挂起失败的消息并将生成一个否定确认 (NACK)。 默认值为清除此复选框。 有关详细信息，请参阅[如何为接收端口的失败消息启用路由](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md)。|

4. 选择**接收位置**，然后选择**新建**。 
5. 输入**名称**的接收位置。 例如，输入**LAReceiveLoc**。
6. 有关**类型**，选择**逻辑应用**从列表中，然后选择**配置按钮**。 
7. 在中**常规**选项卡上，配置用于逻辑应用的终结点地址：

    | 使用此选项 | 执行的操作 |
    | --- | --- |
    | **地址 (URI)** | 必需的。 输入 BizTalk ReceiveService IIS 应用程序 URL (`/YourIISApp2Name/Service1.svc`)。 例如，输入`/ReceiveWCFService/Service1.svc`。 |
    | **公用地址** | 必需的。 输入`http://<your fully qualified machine name>/YourIISApp2Name/Service1.svc`。 例如，输入`http://btsProd.northamerica.corp.contoso.com/ReceiveWCFService/Service1.svc`。 <br/><br/>逻辑应用中的接收位置中还列出了此确切的 URL。|

8. **可选**。 在中**绑定**选项卡上，配置任何超时和编码相关的基础的 Wcf-webhttp 绑定的属性。 当处理大型消息时，这些属性是很有帮助。

    | 使用此选项 | 执行的操作 |
    | --- | --- |
    | 打开超时 | 输入为完成信道打开操作应该花费的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 <br/><br/>默认值：00:01:00<br/>最大值： 23:59:59 |
    | 发送超时 |输入为完成发送操作应该花费的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 如果你使用请求-响应接收端口，此值指定完成，整个交互的时间跨度，即使客户端返回一条大消息。 <br/><br/>默认值：00:01:00<br/>最大值： 23:59:59|
    | 关闭超时 | 输入为完成信道关闭操作应该花费的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 <br/><br/>默认值：00:01:00<br/>最大值： 23:59:59 |
    | 已接收消息的最大字节数 | 以字节为单位的消息包括标头，以在网络上接收输入的最大大小。 消息的大小受为每个消息分配的内存量。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。 <br/><br/>默认值：65536<br/>最大值：2147483647|
    | 最大并行调用数 | 输入对单个服务实例的并发调用数。 超出此限制的调用将在队列中排队。 将此值设置为 0 等效于将它设置为 Int32.MaxValue。 <br/><br/>默认值为 200。|

9. **可选**。 在中**安全**选项卡上，配置任何安全属性。 出于开发目的，您可以选择无：

    | 使用此选项 | 执行的操作 |
    | --- | --- |
    | 安全模式 | 选项：  <br/><br/><ul><li>None： 不保护消息在传输过程。</li><li>传输： 使用 HTTPS 传输提供安全性。 使用 HTTPS 对 SOAP 消息进行保护。 若要使用此模式下，必须设置了安全套接字层 (SSL) 在 Internet 信息服务 (IIS)。 </li><li>TransportCredentialOnly： 默认值。 </li></ul> |
    | 传输客户端凭据类型 | 使用客户端身份验证时，请选择凭据类型。 选项：  <br/><br/><ul><li>None： 无身份验证发生在传输级别。</li><li>Basic： 使用基本身份验证以通过网络以纯文本格式发送用户名和密码。 你必须创建与凭据对应的域或本地用户帐户。</li><li>摘要： 使用摘要式身份验证，以通过网络发送密码哈希值。 仅适用于具有运行 Windows Server 操作系统身份验证的域控制器的域。 你必须创建与客户端凭据对应的域或本地用户帐户。</li><li>Ntlm： 默认值。 客户端将发送凭据而不将密码发送到此接收位置。 你必须创建与客户端凭据对应的域或本地用户帐户。</li><li>Windows: Windows 集成身份验证协商 Kerberos 或 NTLM，则首选使用 Kerberos 域是否存在。 若要使用 Kerberos，务必让客户端使用服务主体名称 (SPN) 标识服务。 你必须创建与客户端凭据对应的域或本地用户帐户。</li><li>证书： 使用客户端证书。 CA 证书链的客户端 X.509 证书必须安装在此计算机的受信任的根证书颁发机构证书存储，以便客户端进行身份验证与此接收位置。</li><li>InheritedFromHost</li></ul> |
    | 使用单一登录 | |


10. **可选**。 在中**消息**选项卡上，使用**出站 HTTP 标头**属性添加任何自定义标头，并使用其他属性来帮助进行错误： 

    | 使用此选项 | 执行的操作 |
    | --- | --- |
    |出站 HTTP 标头 | 输入所需响应消息上标记任何 HTTP 标头。 | 
    | 失败时禁用位置 | 入站的处理由于接收管道故障或路由故障而失败时禁用接收位置。 默认值为未选中状态。|
    | 失败时挂起请求消息 | 入站的处理由于接收管道故障或路由故障而失败时挂起请求消息。 默认值为未选中状态。|
    | 在错误中包括异常详细信息 | 出现错误时，返回任何 SOAP 错误以帮助调试。 默认值为未选中状态。|

[管理接收位置](../core/managing-receive-locations.md)介绍的其他属性。 

### <a name="step-5-send-a-message"></a>步骤 5： 将发送一条消息

1. 打开 Fiddler 或 Postman （或为所需的任意）。
2. 粘贴请求触发器从逻辑应用的 URL。 在步骤 3 中复制此 URL。 
3. 选择**POST**作为 HTTP 谓词，并将设置**内容类型**标头与`application/json`。 在正文中，粘贴以下 JSON:  

    ```json
    {“hello”:”world”}
    ```

4. 由于这是对 BizTalk 的单向调用，结果应为 HTTP 202。 如果使用的 HelloWorld SDK 示例，请转到您的 BizTalk server。 在发送文件夹中可能有一个文件。 


## <a name="send-messages-to-a-logic-app"></a>将消息发送到逻辑应用

### <a name="step-1-install-the-logic-apps-adapter"></a>步骤 1： 安装逻辑应用适配器

逻辑应用适配器是一个单独的下载，并且不包含 BizTalk Server 安装。

1. 转到[逻辑应用的 Microsoft BizTalk Server 适配器](https://www.microsoft.com/download/details.aspx?id=54287)，并保存。 
2. 打开 LogicAppAdapter.iso，并运行**逻辑应用 Adapter.msi**文件来安装。
3. **完成**安装和重启**BizTalkServerApplication**并**BizTalkServerIsolatedHost**主机实例。

安装后，你具有：

- 逻辑应用适配器添加到 BizTalk 管理
- 发送处理程序创建，并使用 BizTalkServerApplication 主机。
- 接收处理程序将创建为 WCF 服务，并使用 BizTalkServerIsolatedHost 主机。
- `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter`文件夹创建，并包括两个服务： 管理和 ReceiveService。 这些服务不用于将消息发送到逻辑应用。 


### <a name="step-2-create-a-logic-app"></a>步骤 2： 创建逻辑应用

1. 在中[Azure 门户](https://portal.azure.com)，创建新的逻辑应用。
2. 添加**收到 HTTP 请求时**触发器
3. 添加**Office 365 Outlook-发送电子邮件**操作。 有关**到**地址，请输入你的 Office 365 地址。 有关**使用者**，输入`Sending from BizTalk`。 有关**正文**，选择*正文*的输出**收到 HTTP 请求时**触发器。 
4. 逻辑应用看起来类似于： 

    ![LogicAppExample](../core/media/logicappexample.gif)

5. 复制 HTTP POST URL 自动创建时保存逻辑应用;您需要在下一步中的此 URL。 您可能需要关闭并重新打开该逻辑应用可以看到的 URL。  


### <a name="step-3-create-a-send-port"></a>步骤 3： 创建一个发送端口

对于 BizTalk Server 将消息发送到逻辑应用中，逻辑应用必须具有**手动**触发，例如**手动-HTTP 请求时收到**。 

1. 在 BizTalk Server 管理中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开要为应用程序运行发送端口。 例如，展开**BizTalk Application 1**。
2. 右击选择**发送端口**，选择**新建**，然后选择**静态单向发送端口**。
3. 输入**名称**发送端口。 例如，输入**LASendPort**。
4. 有关**类型**，选择**逻辑应用**从列表中，然后选择**配置**按钮。 
5. 在中**常规**选项卡上，配置**回调 URI**的逻辑应用触发器。 完成这项工作的方法有两种： 

    **选项 1** ： 将粘贴在上一步中复制的 HTTP POST URL**触发器 (回调 URI)** 属性。 此外可以复制 URI 使用以下步骤：  
  
   1. 在中[Azure 门户](https://portal.azure.com)，逻辑应用设计器 （编辑模式下） 中打开逻辑应用。 
   2. 选择**HTTP 请求时收到**卡片，并将复制**URL**。 
   3. 在您的发送端口，将在此 URL 粘贴**触发器 (回调 URI)** 属性。

      > [!TIP] 
      > 您的管理 Api 还可用于获取此 URI。

      **选项 2** ： 如果你不知道为触发器的回调 URI，选择**配置**，并登录到 Azure。 然后，使用下拉列表选择您**订阅**，**资源组**，**逻辑应用**，以及**触发器**。
 
6. **可选**。 在中**绑定**选项卡上，配置任何超时和编码相关的基础的 Wcf-webhttp 绑定的属性。 当处理大型消息时，这些属性是很有帮助。

    | 使用此选项 | 执行的操作 |
    | --- | --- |
    | 打开超时 | 输入为完成信道打开操作应该花费的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 <br/><br/>默认值：00:01:00<br/>最大值： 23:59:59 |
    | 发送超时 |输入为完成发送操作应该花费的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 如果你使用请求-响应接收端口，此值指定完成，整个交互的时间跨度，即使客户端返回一条大消息。 <br/><br/>默认值：00:01:00<br/>最大值： 23:59:59|
    | 关闭超时 | 输入为完成信道关闭操作应该花费的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 <br/><br/>默认值：00:01:00<br/>最大值： 23:59:59 |
    | 已接收消息的最大字节数 | 以字节为单位的消息包括标头，以在网络上接收输入的最大大小。 消息的大小受为每个消息分配的内存量。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。 <br/><br/>逻辑 appa 适配器利用[WebHttpBinding 类](https://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.aspx)在缓冲的传输模式下，与终结点进行通信。 对于缓冲的传输模式中， [WebHttpBinding.MaxBufferSize](https://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.maxbuffersize.aspx)属性也始终等于此属性的值。  <br/><br/>默认值：65536<br/>最大值：2147483647 |


7. **可选**。 在中**消息**选项卡上，使用**出站 HTTP 标头**要对传出消息添加任何自定义标头属性。 
8. 选择**确定**以保存配置。 

[管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)介绍其他发送端口属性。 

### <a name="step-4-send-some-messages"></a>步骤 4： 将一些消息发送

您可以创建一个接收端口和使用文件适配器接收位置。 请确保已启用逻辑应用。

1. 创建接收端口，如*FileSendPort*，
2. 创建接收位置，并设置的属性类似于：  

    | “属性” | 示例输入 |
    | --- | --- |
   | 接收文件夹 | C:\temp\In\ |
   | 文件掩码 | *.txt |
   | 管道 | PassThruReceive |

3. 在您创建的发送端口，将**筛选器**到：

    | “属性” | 运算符 | ReplTest1 |
    | --- | --- | --- |
    | BTS.ReceivePortName |  == | *FileSendPort* |

4. 使用以下文本创建一个文本文件 (文件名.txt)。 使用此文本文件作为您的示例消息： 

    ```
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

5. 将您的示例消息 (文件名.txt) 复制到接收文件夹。 发送端口将.txt 文件发送到逻辑应用使用你输入的 URI。 逻辑应用接收文件。 如果使用 Office 365 Outlook 连接器，你*到*电子邮件地址应接收电子邮件中的，使用示例消息。

## <a name="next"></a>Next
[逻辑应用有哪些？](https://azure.microsoft.com/documentation/articles/app-service-logic-what-are-logic-apps/)  

[创建逻辑应用](https://azure.microsoft.com/documentation/articles/app-service-logic-create-a-logic-app/)

[在 BizTalk Server 中使用适配器](../core/using-adapters.md)