---
title: 接收适配器发布 WCF 服务和 WCF 时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF adapters, best practices
- WCF adapters, receive adapters
- WCF services, publishing
- best practices, WCF adapters
ms.assetid: 797b7ffd-534c-4f09-9738-fb17b208bc96
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa7a36d9e38463ea9be43b6be1520d7b6732ef5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354696"
---
# <a name="considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters"></a>接收适配器发布 WCF 服务和 WCF 时的注意事项
本主题提供发布 WCF 服务通过 WCF 接收适配器时应考虑的信息。  使用 WCF 适配器发布服务可由 WCF 客户端调用，就像典型的 WCF 服务。  
  
## <a name="in-process-hosting"></a>进程内托管  
 托管中的接收位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程空间，btsntsvc.exe，可简化的开发和部署的好处。 此外，它会创建比在以充分利用高可用性和负载均衡的功能的 IIS 中承载的更多主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  在外进行托管的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 IIS 中的过程是指[对于独立 WCF 接收适配器配置 IIS](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)。  
  
## <a name="set-the-isoneway-property-of-wcf-services-published-with-the-wcf-adapters-except-for-the-wcf-netmsmq-receive-adapter-to-false"></a>使用 WCF 适配器为 false （对于 Wcf-netmsmq 接收适配器除外） 发布的 WCF 服务的 IsOneWay 属性设置  
 **System.ServiceModel.OperationContractAttribute.IsOneWay**通过 WCF 适配器发布的 WCF 服务属性，接收的适配器设置为使用 Wcf-netmsmq 发布的服务除外 **，则返回 true** -设置为**false**甚至对于单向接收位置。 如果**IsOneWay**属性设置为**false**，甚至是返回的方法**void**生成答复消息。 在这种情况下，基础结构创建，并会发送空消息来向调用方指示该方法已返回。 使用此方法使基础结构以发送由服务操作返回到客户端引发的异常。  
  
 若要在其中使用通过 WCF 适配器 （对于 Wcf-netmsmq 接收适配器除外） 发布的 WCF 服务**IsOneWay**是**false**，则**IsOneWay**属性客户端必须设置为**false** ，如下所示：  
  
```  
[ServiceContract(Namespace="Microsoft.WCF.Documentation")]  
  public interface ISampleService{  
    [OperationContract(IsOneWay=false, ReplyAction="*",Action="…"]  
    string SampleMethod(string msg);  
}  
```  
  
> [!NOTE]
>  因为默认值**IsOneWay**属性是**false**，无需在代码中指定该属性。  
  
## <a name="the-replyaction-property-of-the-operationcontractattribute-on-the-client-side-should-be-set-to--an-asterisk-when-consuming-wcf-services-published-with-one-way-receive-locations"></a>在客户端上 OperationContractAttribute 的 ReplyAction 属性应设置为"*"（星号） 时使用 WCF 服务发布使用单向接收位置  
 **System.ServiceModel.OperationContractAttribute.ReplyAction**的属性**System.ServiceModel.OperationContractAttribute**可以在客户端上用于指定的值从 WCF 服务的响应消息的 SOAP 操作。  
  
 除了指定答复消息的操作标头的特定值 (这是一个答复时通知客户端以及要采取的操作)，还可以指定字符串"*"（星号）。 在客户端应用程序中指定星号可指示客户端不验证该服务将发送的响应消息中的答复操作。  
  
 使用 WCF 服务发布的单向接收位置，代理方法 WCF 服务必须返回**void**，在这种情况下代理方法希望 WCF 服务会发送空消息来向调用方指示，该方法已返回。 为代理方法能够收到这则空消息， **ReplyAction**的属性**OperationContractAttribute**应设置为"*"（星号），如下所示：  
  
```  
[ServiceContract(Namespace="Microsoft.WCF.Documentation")]  
  public interface ISampleService{  
    [OperationContract(IsOneWay=false, ReplyAction="*",Action="…"]  
    string SampleMethod(string msg);  
}  
```  
  
> [!NOTE]
>  不需要设置**ReplyAction**属性设置为"\*"（星号） 对于 Wcf-netmsmq 适配器，因为 Wcf-netmsmq 适配器要求 WCF 客户端可以设置**IsOneWay**属性 **，则返回 true**。  
  
## <a name="an-isolated-host-instance-can-run-only-one-adapter"></a>一个独立的主机实例运行只有一个适配器  
 一个独立的主机实例运行只有一个适配器。 如果用一个独立主机配置多个独立适配器，如 HTTP、 SOAP 和 WCF 适配器的接收处理程序，则必须创建多个应用程序池，每个适配器的一个应用程序池。 有关 biztalk 独立主机的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。  
  
## <a name="use-the-template----content-specified-by-template-option-when-sending-non-xml-content-as-response-messages"></a>作为响应消息发送非 XML 内容时使用"模板-内容由模板指定"选项  
 使用 WCF 适配器**正文--BizTalk 响应消息正文**（默认值） 选项不允许发送字符数据和位图图像等非 XML 消息。 可以使用**模板-由模板指定的内容**WCF 适配器能够发送非 XML 消息的选项。 有关如何使用模板的详细信息，请参阅[指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  
  
## <a name="setting-up-the-permissions-for-a-wcf-service-published-with-the-wcf-service-publishing-wizard"></a>设置 WCF 服务的权限使用 WCF 服务发布向导发布  
 使用 ASP.NET 应用程序使用 WCF 服务发布向导在创建时[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]平台，可能会出现与 WCF 服务调用期间访问 Dll 相关的错误。 这些错误通常与默认值的问题[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]和[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]安全。 有关这些错误的详细信息，请参阅 Microsoft 帮助和支持文章名为"，收到 'System.IO.FileNotFoundException' 错误时在客户端应用程序调用 Web 服务"帮助和支持网站上在[ http://go.microsoft.com/fwlink/?LinkId=43659](http://go.microsoft.com/fwlink/?LinkId=43659).  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 需要运行 WCF 服务的过程授予适当的权限是否为在进程内主机或独立主机运行服务。 下[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]和[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]独立主机的默认 Windows 组是 Isolated Host Users 组，因此为 Isolated Host Users 组添加权限应当能够解决此问题。  
  
#### <a name="to-add-the-permissions-to-the-isolated-host-users-group"></a>若要将权限添加到 Isolated Host Users 组  
  
1.  在 Microsoft Windows 资源管理器，找到 %windir%\temp 目录。  
  
2.  右键单击 windir%\temp，然后依次**属性**。  
  
3.  在中**属性**对话框中，单击**安全**选项卡。  
  
4.  单击**外**，选择**Isolated Host Users 组**，然后单击**确定**。  
  
## <a name="setting-up-the-permissions-for-a-wcf-receive-location-with-the-wcf-netmsmq-adapter"></a>设置权限的 wcf 接收位置使用 Wcf-netmsmq 适配器  
 当使用 NetMsmqBinding 的 WCF 客户端向通过 Wcf-netmsmq 适配器发布的 WCF 服务发送一条消息时，它解决了到目标队列，这是由服务的队列管理器管理的队列消息。 在客户端上的队列管理器将消息发送至传输 （或传出） 队列。 传输队列是客户端队列管理器中，用于存储传输到目标队列的消息队列。  
  
 服务的队列管理器接受定址到目标队列拥有并存储消息的消息。 然后，服务可进行请求以便读取来自目标队列，队列管理器将消息传递给该服务。 出于此原因，承载接收位置的 BizTalk 主机实例的服务帐户应具有从目标队列中读取的权限。  
  
## <a name="use-an-empty-body-path-expression-to-receive-a-soap-message-with-character-data-in-the-content-of-the-soap-body-element"></a>使用空的正文路径表达式接收字符数据的 SOAP 消息的 SOAP Body 元素内容中  
 为了使 WCF 接收适配器从传入响应消息的 soap 内容中有字符数据创建 BizTalk 消息**正文**元素，如下面的示例中所示，应该将**正文路径表达式**文本框留空**消息**WCF 适配器传输属性对话框中的选项卡。  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      ...  
    </s:Header>  
    <s:Body>Contoso</s:Body>  
</s:Envelope>  
```  
  
 如果选择**信封**或**正文**选项时，适配器无法创建 BizTalk 消息，从前面的传入消息。 消息未挂起，因为在入站 SOAP 封送处理中失败的消息不会挂起。 详细了解如何在使用的正文路径表达式**消息**选项卡上，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  
  
> [!NOTE]
>  通过配置 btsntsvc.exe.config 文件来，可以在 Windows SDK 中使用的 TraceViewer 工具 (SvcTraceViewer.exe)。 有关 Windows SDK 的详细信息，请参阅"什么是 Windows SDK 中的新增功能"处[ http://go.microsoft.com/fwlink/?LinkId=75219 ](http://go.microsoft.com/fwlink/?LinkId=75219)。 有关 TraceViewer 工具的详细信息，请参阅"TraceViewer 工具 (SvcTraceViewer.exe)"在[ http://go.microsoft.com/fwlink/?LinkId=75218 ](http://go.microsoft.com/fwlink/?LinkId=75218)。  
  
## <a name="using-schemas-that-reference-other-schemas"></a>使用引用其他架构的架构  
 可以使用**重新定义**，**包括**，并**导入**元素时架构变得大而复杂，或当架构表示不同类型的实例消息具有共同某些部分。 它可用于将较小的架构合并到最终定义的计划与贸易合作伙伴交换的实例消息结构的架构。 可以使用 BizTalk WCF 服务发布向导将这些架构发布为 WCF 服务。  
  
 应使用 BizTalk WCF 服务使用向导来创建使用从 BizTalk 项目的 WCF 服务所需的 BizTalk 项目。 如果你想要使用.NET 应用程序中的 WCF 服务，应使用服务模型元数据实用工具工具 (Svcutil.exe) 来创建 WCF 服务的代理类。 有关如何使用引用其他架构的架构的详细信息，请参阅[，使用其他架构](../core/schemas-that-use-other-schemas.md)并[如何创建，使用其他架构](../core/how-to-create-schemas-that-use-other-schemas.md)。 有关 Svcutil.exe 的详细信息，请参阅"服务模型元数据实用工具工具 (Svcutil.exe) 在" [ http://go.microsoft.com/fwlink/?LinkID=74696 ](http://go.microsoft.com/fwlink/?LinkID=74696)。  
  
 下表显示了限制，并需要了解使用时的注意事项发布 WCF 服务与使用其他架构的架构。  
  
|XML 架构元素|使用 WCF 服务使用 BizTalk WCF 服务发布向导发布|使用由.NET 应用程序承载的 WCF 服务|  
|------------------------|-------------------------------------------------------------------------------------|--------------------------------------------------------|  
|\<import\>|使用 BizTalk WCF 服务使用向导和 Svcutil.exe 支持|使用 BizTalk WCF 服务使用向导和 Svcutil.exe 支持|  
|\<include\>|支持这两个 BizTalk WCF 服务使用向导和 Svcutil.exe**注意：** 创建代理类时，Svcutil.exe 可能会引发一条警告消息。|支持这两个 BizTalk WCF 服务使用向导和 Svcutil.exe**注意：** 创建代理类时，Svcutil.exe 可能会引发一条警告消息。|  
|\<redefine\>|-支持使用 BizTalk WCF 服务使用向导<br />-有限的支持由 Svcutil.exe**注意：** Svcutil.exe 具有相同的限制**重新定义**元素的 xsd.exe 具有。|支持这两个 BizTalk WCF 服务使用向导和 Svcutil.exe**注意：** 创建代理类时，Svcutil.exe 可能会引发一条警告消息。|  
  
> [!NOTE]
>  与使用的架构创建对已发布的 BizTalk WCF 服务的代理类时，Svcutil.exe 可能会引发一条警告消息**包括**并**重新定义**元素。 例如，"全局元素已声明。"  
  
## <a name="ensure-that-an-in-process-wcf-receive-location-is-not-disabled-after-you-change-the-computer-name-part-in-its-service-endpoint-address"></a>请确保在更改其服务终结点地址中的计算机名部分之后未禁用进程内 WCF 接收位置  
 如果更改中的计算机名称部分**地址 (URI)** 文本框中的进程内运行 WCF 接收位置，我们建议使用 BizTalk 管理控制台来检查是否仍在运行接收位置。 例如，如果你更改服务终结点地址使用的 Wcf-nettcp 接收适配器，请**net.tcp://\<**<em>您的计算机名称</em>**\>/samplepath**到**net.tcp://localhost/samplepath**，可能会禁用该接收位置与**Service.InvalidOperationException**。 如果仅中的计算机名称部分服务终结点地址更改而无需修改路径部分，请确保未禁用接收位置，并启用它，如有必要。  
  
## <a name="set-the-appropriate-msdtc-security-configuration-options-on-client-computers-communicating-with-remote-wcf-receive-locations-through-a-transaction-protocol"></a>设置相应的 MSDTC 安全配置选项与远程 WCF 进行通信的客户端计算机上接收位置通过事务协议  
 Wcf-nettcp、 Wcf-wshttp 和 Wcf-netnamedpipe 接收适配器可以参与事务性协调进程使用 WCF 客户端管理的**WS-AtomicTransaction**和**OleTransaction**事务协议。 消息可以传输到目标接收位置和删除从 MessageBox 数据库在事务上下文中使用的事务协议。  
  
 为与远程 WCF 接收位置使用的事务协议，必须适当地配置 MSDTC**的安全配置**WCF 客户端计算机上的选项。 下表列出了所需的值的选项，可在 MSDTC**的安全配置**对话框：  
  
|配置选项|默认值|推荐值|  
|--------------------------|-------------------|-----------------------|  
|网络 DTC 访问|禁用|Enabled|  
|允许出站|禁用|Enabled|  
|要求进行相互身份验证|Enabled|如果相应的远程接收位置都运行 Windows Server 2003 SP1 或 SP2，并且配置为包含已启用**要求相互身份验证**。|  
|要求对呼叫方进行身份验证|禁用|如果运行 MSDTC 的群集上，启用。|  
  
 应用这些更改后，您必须重新启动 MSDTC 服务。  
  
 若要访问 MSDTC**的安全配置**对话框框中，请执行以下步骤：  
  
1.  单击**启动**，单击**运行**，然后键入**dcomcnfg**以启动**组件服务**管理控制台。  
  
2.  展开**组件服务**，展开**计算机**，右键单击**我的电脑**，然后单击**属性**。  
  
3.  在中**我的电脑属性**对话框中，单击**MSDTC**选项卡，然后依次**安全配置**以显示**安全配置**对话框。  
  
## <a name="explanation-of-the-soap-wrapper-when-using-the-biztalk-wcf-service-publishing-wizard"></a>使用 BizTalk WCF 服务发布向导时 SOAP 包装的说明  
 当业务流程公开为[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]服务通过使用[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]生成服务发布向导，一个包装器。 此包装器使用的端口将消息发送 XML 消息中的方法名称。 此包装是 Microsoft SOAP 信封的默认值。 它允许[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]包装 WCF 消息由适配器传输到的终结点中的多个部分组成的 SOAP 消息。  
  
 最佳做法是，发送方应使用包装和接收方应，或发送方不应使用一个包装器和接收方应接收原始[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]消息。 无法提前预知使用包装是否会导致之间发送和接收到的内容不兼容性问题。