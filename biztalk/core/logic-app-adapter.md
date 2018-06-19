---
title: BizTalk Server 中的使用逻辑应用适配器 |Microsoft 文档
description: 安装和配置来创建接收端口、 接收位置，以及在 BizTalk Server 发送端口的 Logic Apps 适配器
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
ms.openlocfilehash: faa43c187df7a8eb9fccd2f02f23f16e86b97ce0
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
ms.locfileid: "22266709"
---
# <a name="logic-app-adapter"></a>逻辑应用适配器

## <a name="overview"></a>概述
BizTalk Server 使用 Logic Apps 适配器接收消息从 Azure 逻辑应用程序，或将消息发送到 Azure 逻辑应用程序。 

在 Azure 中，我们将创建逻辑应用。 此逻辑应用程序使用 BizTalk 连接器连接到你创建 BizTalk 服务器接收位置。 本主题假定你已具备一定的 Azure 逻辑应用。 如果你熟悉逻辑应用，我们建议 [学习更多相关信息](https://azure.microsoft.com/documentation/articles/app-service-logic-what-are-logic-apps/), ，，甚至 [创建你自己的逻辑应用](https://azure.microsoft.com/documentation/articles/app-service-logic-create-a-logic-app/)。

在本主题中，我们将列出的步骤以在 BizTalk Server 中的一条消息接收逻辑应用。 逻辑应用将另一种方法，将消息发送到 BizTalk Server。 接收方使用在 IIS 中的应用程序来处理向 Azure 服务的通信。 如果 BizTalk 服务器本地，还会在 BizTalk Server 中，安装数据网关和在 Azure 中创建网关。 

如果 Azure 虚拟机 (VM) 上安装 BizTalk Server，则你可以选择将 VM 公开为 HTTP 终结点 （你获取的 URL），或不会将其作为 HTTP 终结点进行公开。 如果不将其公开，你不需要使用网关。 逻辑应用程序中，可以在 BizTalk 连接器中输入你的 URL。 如果不公开 VM (没有 URL)，然后你需要使用网关。 此主题中列出这些步骤。

此外，我们展示如何将消息从 BizTalk Server 发送到 Azure 逻辑应用程序。 逻辑应用，将另一种方法，从 BizTalk Server 接收消息。 你将会看到此主题中，发送方将非常简单。

使用本主题创建接收位置和使用 Logic Apps 适配器发送端口。 你可以使用本地 （加入到你的域） BizTalk Server 中或运行 BizTalk Server 的 Azure 虚拟机中的 LogicApp 适配器。 

## <a name="requirements"></a>要求

- 一个 Azure 订阅来登录到 Azure 门户中，和创建逻辑应用。
- 可选。 若要向逻辑应用程序发送一条测试消息，安装 HTTP 测试工具，如 [Fiddler](http://www.telerik.com/fiddler) 或 [Postman](https://www.getpostman.com/)。 如果你使用另一种方法将消息发送到逻辑应用，你无需使用这些工具。 

## <a name="receive-messages-from-a-logic-app"></a>从逻辑应用接收消息

有几个步骤所涉及的 BizTalk Server 逻辑应用从接收消息。 本部分列出了这些步骤。 它是 Azure 的更改，因此某些步骤中的用户界面可能不会完全按列出。 

#### <a name="prerequisites"></a>先决条件

- 如果 BizTalk Server，在本地安装和配置 [本地数据网关](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-install/) 对于 Logic Apps。 然后，在 Azure 中， [创建数据网关资源](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-connection/) 连接到你的 BizTalk Server。
- 如果 BizTalk 服务器安装在 Azure VM，并且虚拟机未公开为 HTTP 终结点，然后安装和配置 [本地数据网关](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-install/) 对于 Logic Apps。 然后，在 Azure 中， [创建数据网关资源](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-connection/) 连接到你的 BizTalk Server。
- 如果 BizTalk 服务器安装在 Azure VM，并且作为 HTTP 终结点公开 VM，然后网关不是需要或使用。 

### <a name="step-1-install-the-logic-app-adapter"></a>步骤 1︰ 安装逻辑应用适配器

逻辑应用适配器为单独下载，而且不包含与 BizTalk Server 安装。 

> [!IMPORTANT] 
> 若要下载 LogicAppAdapter.iso:
> 
> 1. 转到 [对于 Logic Apps 的 Microsoft BizTalk Server 适配器](https://www.microsoft.com/download/details.aspx?id=54287), ，并保存。 
> 2. 打开 LogicAppAdapter.iso，并运行 **LogicApp Adapter.msi** 文件来安装。

1. 在 BizTalk 服务器上，下载并安装逻辑应用适配器。 

2. 双击选择 **LogicApp Adapter.msi** 安装。 接受许可协议，和 **安装**。
3. **完成** 安装、 d 重启 **BizTalkServerApplication** 和 **BizTalkServerIsolatedHost** 托管实例。

安装完成后，你具有下列项目︰

- LogicApp 适配器添加到 BizTalk 管理。
- 发送处理程序会创建，并使用 BizTalkServerApplication 主机。
- 接收处理程序创建为 WCF 服务，并使用 BizTalkServerIsolatedHost 主机。
- `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter`文件夹会创建，并包括两个服务： 管理和 ReceiveService。 

    **管理**逻辑应用中的 BizTalk 连接器用于连接到 BizTalk Server 使用的数据网关。 此管理服务允许 BizTalk Server 从 Azure 逻辑应用使用数据网关接收消息。 在 BizTalk 接收端仅使用此服务。 它不使用发送方。

    **ReceiveService**逻辑应用中的 BizTalk 连接器时输入接收位置使用。 **ReceiveService**负责从逻辑应用程序发送消息。 在 BizTalk 接收端仅使用此服务。 它不使用发送方。


### <a name="step-2-create-the-iis-applications"></a>步骤 2︰ 创建 IIS 应用程序

IIS 应用程序使用的管理和 ReceiveService 服务。

你可以运行使用新的应用程序池或现有的应用程序池的 IIS 应用程序。 应用程序池的标识需要运行 BizTalk 服务，例如 BizTalk 应用程序用户和 BizTalk 隔离主机用户组的帐户在同一组的成员身份。  

> [!TIP] 
> 如果你创建新的应用程序池，然后保留默认的.NET CLR 版本和托管的管道。 请记住，选择具有相同的 BizTalk 组作为你的 BizTalk 服务帐户的成员身份的标识 （高级设置）。 

#### <a name="create-the-management-iis-application"></a>创建管理 IIS 应用程序
此 IIS 应用程序的 URL 由 BizTalk 连接器 （在逻辑应用程序） 用于使用 BizTalk Server 上的数据网关。

1. 打开 Internet Information Services (IIS) 管理器。
2. 右键单击 **Default Web Site**, ，和 **添加应用程序**。 在此新的应用程序︰ 

    1. 输入 **别名** （名称） 为应用程序，如 **IISLogicApp**。 
    2. **选择** 应用程序池。
    3. 设置**物理路径**到`C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter\Management`。 
    3. **测试设置** 以确认应用程序池标识，将传递身份验证和授权测试。

3. 选择 **确定** 以保存所做的更改。
4. 打开 web 浏览器，并转到`http://localhost/YourApplicationAlias/schemas?api-version=2016-10-26`，如`http://localhost/IISLogicApp/Schemas?api-version=2016-10-26`。 是架构显示的列表，或系统会提示打开/保存 `schemas.json`。 实际结果取决于你的 web 浏览器。 如果两种情况均发生，则可能缺少应用程序池标识的 BizTalk 组的成员身份。

#### <a name="create-the-biztalk-receiveservice-iis-application"></a>创建 BizTalk ReceiveService IIS 应用程序
此 IIS 应用程序的 URL 由 （中你逻辑的应用） 的 BizTalk 连接器时，你选择接收位置。 

1. 打开 Internet Information Services (IIS) 管理器。
2. 右键单击 **Default Web Site**, ，和 **添加应用程序**。 在此新的应用程序︰ 

    1. 输入 **别名** （名称） 为应用程序，如 **ReceiveWCFService**。 
    2. **选择** 与以前的 IIS 应用程序相同的应用程序池。
    3. 设置**物理路径**到`C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter\ReceiveService`。 
    3. **测试设置** 以确认应用程序池标识，将传递身份验证和授权测试。

3. 选择 **确定** 以保存所做的更改。


### <a name="step-3-create-a-logic-app"></a>步骤 3︰ 创建逻辑应用

1. 在 [Azure 门户](https://portal.azure.com), ，创建新的逻辑应用。
2. 添加 **收到时 HTTP 请求** 触发器。
3. 添加 **BizTalk Server-准备从 JSON 消息** 操作。 
4. **可选**︰ 选择 **通过本地数据网关的连接**, ，并输入以下︰ 

    | 属性 | Description |
   | --- | --- |
    | BizTalk 服务器 URL | 输入 BizTalk 中的管理 IIS 应用程序 URL 的完全限定的域名 (FQDN)。 例如，输入`http://BizTalkServerName.corp.contoso.com/IISLogicApp/`。 |
    | 身份验证类型 | 选择 **Windows**。 |
   | 用户名 | 输入 IIS 应用程序池标识。 |
   | 密码 | 输入 IIS 应用程序池的密码。 |
   | 网关 | 选择你创建的网关。 |

    > [!TIP] 
    > 请记住，数据网关是仅需的如果︰
    > - 你使用本地 BizTalk Server
    > - 你正在使用 BizTalk Server Azure 虚拟机 *和* VM 不公开为 HTTP 终结点 (没有 URL)

5. 选择“创建”。 
6. 配置操作。 有关 **正文**, ，选择 HTTP 正文输出。 有关 **架构**, ，选择你想要使用的架构。 

    > [!NOTE] 
    > 此步骤假定你熟悉 BizTalk 中的架构，并知道所需的架构。 如果你不确定，然后部署 HelloWorld SDK 示例，更新其项目以使用逻辑应用适配器，并使用其架构和示例的消息。 

7. 添加一个新的步骤，并选择 **BizTalk Server-发送的消息** 操作。 有关**接收位置**，从下拉列表中，选择的 URL 或输入 ReceiveService IIS 应用程序 URL 的完全限定的域名 (FQDN)。 例如，输入`http://BizTalkServerName.corp.contoso.com/ReceiveWCFService/Service1.svc`。

    > [!TIP] 
    > 当创建接收位置时，在此确切的 URL，还将在作为接收位置传输属性中输入 **公共地址** （常规选项卡）。

    有关 **正文**, ，从之前的 BizTalk Server 操作选择正文输出。 

8. **保存** 所做的更改。 

保存时，HTTP 请求触发器将自动创建一个 URL。 复制此 URL;你需要在 **步骤 5︰ 将消息发送**。

### <a name="step-4-create-a-receive-port-and-a-receive-location"></a>步骤 4︰ 创建一个接收端口和接收位置

> [!NOTE] 
> 而不是创建您自己接收端口和接收位置，你可以将部署 HelloWorld SDK 示例。 更新项目以使用 Logic Apps 适配器。 
 
本部分列出的步骤来创建你自己的项目。 

1. 在 BizTalk Server 管理中，展开 **BizTalk Server 管理**, ，展开 **BizTalk 组**, ，展开 **应用程序**, ，然后展开你要运行接收位置的应用程序。 例如，展开 **BizTalk 应用程序 1**。
2. 右-选择 **接收端口**, ，选择 **新建**, ，然后选择 **单向接收端口**。
3. 在接收端口属性中，输入以下信息︰  

    | 使用此选项 | 動作 |
    | --- | --- |
    | **名称** | 输入接收端口的名称。 例如，输入 **LAReceivePort**。 |
    | **身份验证** | 选项： <br/><ul><li>无身份验证︰ 默认值。 禁用身份验证。</li><li>丢弃的消息，如果身份验证失败︰ 启用身份验证，但若要删除未经身份验证的消息。</li><li>保留消息，如果身份验证失败︰ 单击此选项以启用身份验证并保留未经身份验证的消息。 </li></ul>|
    | **启用路由失败消息** | 将路由失败对订阅应用程序处理的任何消息 （例如另一个接收端口或业务流程计划）。 取消选中此选项可挂起失败的消息并生成否定确认 (NACK)。 默认值为清除此复选框。 有关详细信息，请参阅[如何启用路由失败消息为接收端口](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md)。|

4. 选择 **接收位置**, ，然后选择 **新建**。 
5. 输入 **名称** 接收位置。 例如，输入 **LAReceiveLoc**。
6. 有关 **类型**, ，选择 **LogicApp** 从该列表中，并选择 **配置按钮**。 
7. 在 **常规** 选项卡上配置逻辑应用的终结点地址︰

    | 使用此选项 | 動作 |
    | --- | --- |
    | **地址 (URI)** | 必需的。 输入 BizTalk ReceiveService IIS 应用程序 URL (`/YourIISApp2Name/Service1.svc`)。 例如，输入`/ReceiveWCFService/Service1.svc`。 |
    | **公共地址** | 必需的。 输入 `http://<your fully qualified machine name>/YourIISApp2Name/Service1.svc`。 例如，输入 `http://btsProd.northamerica.corp.contoso.com/ReceiveWCFService/Service1.svc`。 <br/><br/>接收位置你逻辑的应用程序中还列出了此确切的 URL。|

8. **可选**。 在 **绑定** 选项卡上，配置任何超时和编码相关的基础的 WCF WebHttp 绑定的属性。 处理大消息时，这些属性是很有帮助。

    | 使用此选项 | 执行的操作 |
    | --- | --- |
    | 打开超时 | 输入它时应采取通道打开操作完成的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 <br/><br/>默认值：00:01:00<br/>最大值︰ 23:59:59 |
    | 发送超时时 |输入为完成发送操作也会花费的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 如果你使用请求-响应接收端口，此值指定的时间范围进行整个交互，从而完成，即使客户端返回一个大的消息。 <br/><br/>默认值：00:01:00<br/>最大值︰ 23:59:59|
    | 关闭超时 | 输入它时应采取通道关闭操作完成的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 <br/><br/>默认值：00:01:00<br/>最大值︰ 23:59:59 |
    | 已接收消息的最大字节数 | 以字节为单位，包括消息头的消息，以在网络上接收输入的最大大小。 消息的大小受为每个消息分配的内存量。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。 <br/><br/>預設值：65536<br/>最大值：2147483647|
    | 最大并行调用数 | 输入到单个服务实例的并发调用数。 超出此限制的调用将在队列中排队。 将此值设置为 0 与将其设置为 Int32.MaxValue 等效。 <br/><br/>默认值为 200。|

9. **可选**。 在 **安全** 选项卡上配置的任何安全属性。 对于开发目的，你可以选择一个︰

    | 使用此选项 | 执行的操作 |
    | --- | --- |
    | 安全模式 | 选项：  <br/><br/><ul><li>None︰ 不保护消息在传输过程。</li><li>传输︰ 使用 HTTPS 传输提供安全性。 使用 HTTPS 对 SOAP 消息进行保护。 若要使用此模式下，你必须设置了安全套接字层 (SSL) 在 Internet 信息服务 (IIS)。 </li><li>TransportCredentialOnly︰ 默认值。 </li></ul> |
    | 传输客户端凭据类型 | 使用客户端身份验证时，请选择凭据类型。 选项：  <br/><br/><ul><li>None︰ 无身份验证发生在传输级别。</li><li>Basic︰ 使用基本身份验证来通过网络以纯文本格式发送用户名和密码。 你必须创建与凭据对应的域或本地用户帐户。</li><li>Digest︰ 使用摘要式身份验证，以通过网络哈希值的形式发送密码。 仅适用于具有运行 Windows Server 操作系统身份验证的域控制器的域。 你必须创建与客户端凭据对应的域或本地用户帐户。</li><li>Ntlm︰ 默认值。 客户端发送的凭据不发送到此密码的情况下接收位置。 你必须创建与客户端凭据对应的域或本地用户帐户。</li><li>Windows: Windows 集成身份验证协商 Kerberos 或 NTLM，如果存在域，则使用 Kerberos。 若要使用 Kerberos，务必使客户端使用服务主体名称 (SPN) 标识的服务。 你必须创建与客户端凭据对应的域或本地用户帐户。</li><li>证书︰ 使用客户端证书。 CA 证书链，以便客户端可以对此进行身份验证必须在此计算机的受信任根证书颁发机构证书存储中安装客户端 X.509 证书对接收位置。</li><li>InheritedFromHost</li></ul> |
    | 使用单一登录 | |


10. **可选**。 在 **消息** 选项卡上，使用 **出站 HTTP 标头** 属性添加任何自定义标头，并使用其他属性来帮助进行故障︰ 

    | 使用此选项 | 执行的操作 |
    | --- | --- |
    |出站 HTTP 标头 | 输入所需标记在响应消息上任何 HTTP 标头。 | 
    | 失败时禁用位置 | 如果由于接收管道故障，还是路由故障而失败的入站的处理，请禁用接收位置。 默认值为未选中状态。|
    | 失败时挂起请求消息 | 如果由于接收管道故障，还是路由故障而失败的入站的处理，将挂起的请求消息。 默认值为未选中状态。|
    | 在错误中包括异常详细信息 | 发生错误时，返回以帮助调试任何 SOAP 错误。 默认值为未选中状态。|

[管理接收位置](../core/managing-receive-locations.md)介绍其他属性。 

### <a name="step-5-send-a-message"></a>步骤 5︰ 将发送一条消息

1. 打开 Fiddler 或 Postman （或为你希望的任何内容）。
2. 粘贴请求触发器从逻辑应用程序的 URL。 你在步骤 3 中复制此 URL。 
3. 选择 **POST** 作为 HTTP 谓词，并将设置 **content-type** 标头到 `application/json`。 在正文中，粘贴以下 JSON:  

    ```json
    {“hello”:”world”}
    ```

4. 由于这是单向调用 BizTalk，结果应为 HTTP 202。 如果你使用 HelloWorld SDK 示例，请转到 BizTalk server。 在你发送文件夹中可能是一个文件。 


## <a name="send-messages-to-a-logic-app"></a>将消息发送到逻辑应用

### <a name="step-1-install-the-logic-apps-adapter"></a>步骤 1︰ 安装 Logic Apps 适配器

Logic Apps 适配器是一个单独的下载，而且不包含与 BizTalk Server 安装。

1. 转到 [对于 Logic Apps 的 Microsoft BizTalk Server 适配器](https://www.microsoft.com/download/details.aspx?id=54287), ，并保存。 
2. 打开 LogicAppAdapter.iso，并运行 **LogicApp Adapter.msi** 文件来安装。
3. **完成** 安装和重新启动 **BizTalkServerApplication** 和 **BizTalkServerIsolatedHost** 托管实例。

安装完成后，你具有下列项目︰

- LogicApp 适配器添加到 BizTalk 管理
- 发送处理程序会创建，并使用 BizTalkServerApplication 主机。
- 接收处理程序创建为 WCF 服务，并使用 BizTalkServerIsolatedHost 主机。
- `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter`文件夹会创建，并包括两个服务： 管理和 ReceiveService。 这些服务不用于将消息发送到逻辑应用。 


### <a name="step-2-create-a-logic-app"></a>步骤 2︰ 创建逻辑应用

1. 在 [Azure 门户](https://portal.azure.com), ，创建新的逻辑应用。
2. 添加 **收到时 HTTP 请求** 触发器
3. 添加 **Office 365 Outlook 的电子邮件发送** 操作。 有关 **到** 地址，输入你的 Office 365 地址。 有关 **主题**, ，输入 `Sending from BizTalk`。 有关 **正文**, ，选择 *正文* 输出从 **收到时 HTTP 请求** 触发器。 
4. 逻辑应用的显示效果类似于︰ 

    ![LogicAppExample](../core/media/logicappexample.gif)

5. 复制时保存逻辑应用程序; 自动创建的 HTTP POST URL你需要在下一步此 URL。 你可能需要关闭并重新打开逻辑应用，使看到的 URL。  


### <a name="step-3-create-a-send-port"></a>步骤 3︰ 创建发送端口

对于 BizTalk Server 中将消息发送到逻辑应用，必须具有逻辑应用 **手动** 触发，如 **收到手动-当 HTTP 请求**。 

1. 在 BizTalk Server 管理中，展开 **BizTalk Server 管理**, ，展开 **BizTalk 组**, ，展开 **应用程序**, ，然后展开你要运行发送端口的应用程序。 例如，展开 **BizTalk 应用程序 1**。
2. 右-选择 **发送端口**, ，选择 **新建**, ，然后选择 **静态单向发送端口**。
3. 输入 **名称** 发送端口。 例如，输入 **LASendPort**。
4. 有关 **类型**, ，选择 **LogicApp** 从该列表中，并选择 **配置** 按钮。 
5. 在 **常规** 选项卡上，配置 **回调 URI** 你逻辑应用触发。 完成这项工作的方法有两种： 

    **选项 1** ︰ 粘贴你在前一步骤中复制的 HTTP POST URL **触发器 (回调 URI)** 属性。 您还可以将复制的 URI 使用以下步骤︰  
  
      1. 在 [Azure 门户](https://portal.azure.com), ，在逻辑应用设计器 （编辑模式） 中打开逻辑应用程序。 
      2. 选择 **收到时 HTTP 请求** 卡，并将复制 **URL**。 
      3. 在你发送端口，将在此 URL 粘贴 **触发器 (回调 URI)** 属性。

    > [!TIP] 
    > 你的管理 Api 还可用于获取此 URI。

    **选项 2** ︰ 如果你不知道你触发器的回调 URI，则选择 **配置**, ，和登录到 Azure。 然后，使用下拉列表选择你 **订阅**, ，**资源组**, ，**逻辑应用**, ，和 **触发器**。
 
6. **可选**。 在 **绑定** 选项卡上，配置任何超时和编码相关的基础的 WCF WebHttp 绑定的属性。 处理大消息时，这些属性是很有帮助。

    | 使用此选项 | 执行的操作 |
    | --- | --- |
    | 打开超时 | 输入它时应采取通道打开操作完成的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 <br/><br/>默认值：00:01:00<br/>最大值︰ 23:59:59 |
    | 发送超时时 |输入为完成发送操作也会花费的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 如果你使用请求-响应接收端口，此值指定的时间范围进行整个交互，从而完成，即使客户端返回一个大的消息。 <br/><br/>默认值：00:01:00<br/>最大值︰ 23:59:59|
    | 关闭超时 | 输入它时应采取通道关闭操作完成的时间间隔。 此值应大于或等于 System.TimeSpan.Zero。 <br/><br/>默认值：00:01:00<br/>最大值︰ 23:59:59 |
    | 已接收消息的最大字节数 | 以字节为单位，包括消息头的消息，以在网络上接收输入的最大大小。 消息的大小受为每个消息分配的内存量。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。 <br/><br/>逻辑 appa 适配器利用 [WebHttpBinding 类](https://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.aspx) 在缓冲的传输模式中与终结点进行通信。 对于缓冲的传输模式中， [WebHttpBinding.MaxBufferSize](https://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.maxbuffersize.aspx) 属性也始终等于此属性的值。  <br/><br/>默认值：65536<br/>最大值：2147483647 |


7. **可选**。 在 **消息** 选项卡上，使用 **出站 HTTP 标头** 属性来对传出消息中添加任何自定义标头。 
8. 选择 **确定** 以保存配置。 

[管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)介绍其他发送端口属性。 

### <a name="step-4-send-some-messages"></a>步骤 4︰ 发送某些消息

你可以创建接收端口和接收位置使用了文件适配器。 请确保启用逻辑应用。

1. 创建接收端口，如 *FileSendPort*,，
2. 创建一个接收位置，并设置的属性类似于︰  

    | 属性 | 示例输入 |
    | --- | --- |
   | 接收文件夹 | C:\temp\In\ |
   | 文件掩码 | *.txt |
   | 管道 | PassThruReceive |

3. 在你创建的发送端口，集中 **筛选器** 到︰

    | 属性 | 运算符 | “值” |
    | --- | --- | --- |
    | BTS.ReceivePortName |  == | *FileSendPort* |

4. 创建具有以下文本的文本文件 (FileName.txt)。 使用此文本文件作为示例消息︰ 

    ```
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

5. 将你的示例消息 (FileName.txt) 复制到接收文件夹中。 发送端口将.txt 文件发送到逻辑应用，使用你输入的 URI。 逻辑应用接收文件。 如果你使用 Office 365 Outlook 连接器，你 *到* 电子邮件地址应收到电子邮件，使用的示例消息。

## <a name="next"></a>Next
[逻辑应用有哪些？](https://azure.microsoft.com/documentation/articles/app-service-logic-what-are-logic-apps/)  

[创建逻辑应用](https://azure.microsoft.com/documentation/articles/app-service-logic-create-a-logic-app/)

[BizTalk Server 中使用适配器](../core/using-adapters.md)