---
title: "发布使用 WCF 的 WCF 服务时的注意事项接收适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF adapters, best practices
- WCF adapters, receive adapters
- WCF services, publishing
- best practices, WCF adapters
ms.assetid: 797b7ffd-534c-4f09-9738-fb17b208bc96
caps.latest.revision: "34"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30175e7966d565306c45820f1a6c2e22e4611876
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters"></a>通过 WCF 接收适配器发布 WCF 服务时的注意事项
本主题提供在通过 WCF 接收适配器发布 WCF 服务时应当注意的信息。  如果使用 WCF 适配器发布服务，会允许该服务由 WCF 客户端调用，就像该服务是一个典型的 WCF 服务一样。  
  
## <a name="in-process-hosting"></a>进程内托管  
 如果在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程空间 btsntsvc.exe 内托管接收位置，可以简化开发和部署过程。 此外，它比在 IIS 中托管能够创建更多的主机实例，从而能够利用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的高可用性和负载平衡功能。  有关托管外部信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 IIS 中的过程是指[将 IIS 配置为独立的 WCF 接收适配器](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)。  
  
## <a name="set-the-isoneway-property-of-wcf-services-published-with-the-wcf-adapters-except-for-the-wcf-netmsmq-receive-adapter-to-false"></a>将 WCF 适配器（WCF-NetMsmq 接收适配器除外）发布的 WCF 服务的 IsOneWay 属性设置为 false  
 **System.ServiceModel.OperationContractAttribute.IsOneWay** 属性的 WCF 服务发布与 WCF 适配器-除外发布与 WCF NetMsmq 服务接收的适配器设置为 **true** -设置为 **false** 甚至为单向接收位置。 如果 **IsOneWay** 属性设置为 **false**, ，即使返回方法 **void** 导致答复消息。 在这种情况下，基础结构将创建并发送一则空消息，向调用方指明该方法已返回。 使用此方法，基础结构可以向客户端回发服务操作引发的异常。  
  
 若要在其中使用 WCF 服务使用 （除了对于 WCF NetMsmq 收到适配器） 的 WCF 适配器发布 **IsOneWay** 是 **false**, 、 **IsOneWay** 客户端上的属性必须设置为 **false** ，如下所示︰  
  
```  
[ServiceContract(Namespace="Microsoft.WCF.Documentation")]  
  public interface ISampleService{  
    [OperationContract(IsOneWay=false, ReplyAction="*",Action="…"]  
    string SampleMethod(string msg);  
}  
```  
  
> [!NOTE]
>  因为的默认值 **IsOneWay** 属性是 **false**, ，则不需要在代码中指定属性。  
  
## <a name="the-replyaction-property-of-the-operationcontractattribute-on-the-client-side-should-be-set-to--an-asterisk-when-consuming-wcf-services-published-with-one-way-receive-locations"></a>在使用通过单向接收位置发布的 WCF 服务时，客户端上 OperationContractAttribute 的 ReplyAction 属性应当设置为“*”（星号）  
 **System.ServiceModel.OperationContractAttribute.ReplyAction** 属性 **System.ServiceModel.OperationContractAttribute** 可以在客户端上用于指定从 WCF 服务的响应消息的 SOAP 操作值。  
  
 除了为答复消息的操作头指定特定值以外（以通知客户端这是一个答复，以及要执行的操作），还可以指定字符串“*”（星号）。 在客户端应用程序中指定星号即指示客户端不验证服务所发送的响应消息中的答复操作。  
  
 使用 WCF 服务发布的单向接收位置，代理方法的 WCF 服务必须返回 **void**, ，在这种情况下的代理方法需要 WCF 服务将发送一条空消息以向调用方指示该方法已返回。 要接收此空消息的代理方法 **ReplyAction** 属性 **OperationContractAttribute** 应设置为"*"（星号），如下所示︰  
  
```  
[ServiceContract(Namespace="Microsoft.WCF.Documentation")]  
  public interface ISampleService{  
    [OperationContract(IsOneWay=false, ReplyAction="*",Action="…"]  
    string SampleMethod(string msg);  
}  
```  
  
> [!NOTE]
>  不需要设置 **ReplyAction** 属性设置为"\*"（星号） 对于 WCF NetMsmq 适配器，因为 WCF NetMsmq 适配器需要 WCF 客户端可以设置 **IsOneWay** 属性 **true**。  
  
## <a name="an-isolated-host-instance-can-run-only-one-adapter"></a>一个独立主机实例只能运行一个适配器  
 一个独立主机实例只能运行一个适配器。 如果用一个独立主机配置多个独立适配器（如 HTTP、SOAP 和 WCF 适配器）的接收处理程序，则必须创建多个应用程序池，每个适配器对应一个应用程序池。 有关 BizTalk 隔离主机的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。  
  
## <a name="use-the-template----content-specified-by-template-option-when-sending-non-xml-content-as-response-messages"></a>在发送 XML 内容作为响应消息时使用“模板 - 由模板指定的内容”选项  
 使用 WCF 适配器 **正文--BizTalk 响应消息正文** （默认值） 选项不允许进行发送非 XML 消息，如字符数据和位图图像。 你可以使用 **模板--由模板指定内容** 发送非 XML 消息的 WCF 适配器的选项。 有关如何使用模板的详细信息，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  
  
## <a name="setting-up-the-permissions-for-a-wcf-service-published-with-the-wcf-service-publishing-wizard"></a>为通过 WCF 服务发布向导发布的 WCF 服务设置权限  
 在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 平台上使用通过 WCF 服务发布向导创建的 ASP.NET 应用程序时，在调用 WCF 服务期间可能会出现与访问 DLL 相关的错误。 通常这些错误与默认的 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 和 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 安全问题有关。 有关这些错误的详细信息，请参阅 Microsoft 帮助和支持文章调用"你收到"System.IO.FileNotFoundException"错误时客户端应用程序调用 Web 服务"帮助和支持 Web 站点上在 [http://go.microsoft.com/fwlink/?LinkId=43659](http://go.microsoft.com/fwlink/?LinkId=43659)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 要求：无论 WCF 服务是在进程内主机上运行还是在独立主机上运行，运行该服务的进程都必须被授予适当的权限。 在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 和 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 中，独立主机的默认 Windows 组是 Isolated Host Users 组，因此为 Isolated Host Users 组添加权限应当能够解决此问题。  
  
#### <a name="to-add-the-permissions-to-the-isolated-host-users-group"></a>为 Isolated Host Users 组添加权限  
  
1.  在 Microsoft Windows 资源管理器中，找到 %windir%\temp 目录。  
  
2.  右键单击 %windir%\temp，然后单击 **属性**。  
  
3.  在 **属性** 对话框中，单击 **安全** 选项卡。  
  
4.  单击 **添加**, ，选择 **隔离主机用户组**, ，然后单击 **确定**。  
  
## <a name="setting-up-the-permissions-for-a-wcf-receive-location-with-the-wcf-netmsmq-adapter"></a>为带有 WCF-NetMsmq 适配器的 WCF 接收位置设置权限  
 当使用 NetMsmqBinding 的 WCF 客户端向通过 WCF-NetMsmq 适配器发布的 WCF 服务发送消息时，它会将消息发送到目标队列（也就是由服务的队列管理器管理的队列）。 客户端上的队列管理器会将该消息发送到传输（或传出）队列。 传输队列是客户端队列管理器上的一个队列，用来存储要传输到目标队列的消息。  
  
 服务的队列管理器接受发送到它所拥有的目标队列的消息，并存储这些消息。 然后，服务会请求从目标队列读取消息，而队列管理器会将这些消息传送给该服务。 因此，承载接收位置的 BizTalk 主机实例的服务帐户应当具有从目标队列进行读取的权限。  
  
## <a name="use-an-empty-body-path-expression-to-receive-a-soap-message-with-character-data-in-the-content-of-the-soap-body-element"></a>使用空的正文路径表达式接收在 SOAP Body 元素内容中有字符数据的 SOAP 消息  
 对于 WCF 收到适配器，以从传入的响应消息的 SOAP 内容中的字符数据与创建 BizTalk 消息 **正文** 元素，如下面的示例中所示应将其保留 **正文路径表达式** 文本框上空 **消息** WCF 适配器传输属性对话框中的选项卡。  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      ...  
    </s:Header>  
    <s:Body>Contoso</s:Body>  
</s:Envelope>  
```  
  
 如果你选择 **信封** 或 **正文** 选项，该适配器无法创建 BizTalk 消息，从以前的传入消息。 该消息不会挂起，因为在入站 SOAP 封送处理中失败的消息不会挂起。 有关如何使用正文路径表达式上**消息**选项卡上，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  
  
> [!NOTE]
>  可以通过配置 BTSNTSvc.exe.config 文件来使用 Windows SDK 中的 TraceViewer 工具 (SvcTraceViewer.exe)。 有关 Windows SDK 的详细信息，请参阅"什么是 Windows SDK 中的新增功能"网址 [http://go.microsoft.com/fwlink/?LinkId=75219](http://go.microsoft.com/fwlink/?LinkId=75219)。 有关 TraceViewer 工具的详细信息，请参阅"TraceViewer 工具 (SvcTraceViewer.exe)"在 [http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218)。  
  
## <a name="using-schemas-that-reference-other-schemas"></a>使用引用其他架构的架构  
 你可以使用 **重新定义**, ，**包括**, ，和 **导入** 元素时你的架构变得大而复杂，或当表示你不同类型的实例消息的架构的共同点某些部分。 可能有必要将较小的架构组合成新的架构，这个新的架构可以最终定义要与贸易合作伙伴进行交换的实例消息的结构。 可使用 BizTalk WCF 服务发布向导将这些架构发布为 WCF 服务。  
  
 应当使用 BizTalk WCF 服务使用向导创建从 BizTalk 项目使用 WCF 服务所必需的 BizTalk 项目。 如果要从 .NET 应用程序使用 WCF 服务，应当使用服务模型元数据实用工具 (Svcutil.exe) 为 WCF 服务创建代理类。 有关如何使用引用其他架构的架构的详细信息，请参阅[架构，使用其他架构](../core/schemas-that-use-other-schemas.md)和[如何创建架构，使用其他架构](../core/how-to-create-schemas-that-use-other-schemas.md)。 Svcutil.exe 有关的详细信息，请参阅"服务模型元数据实用工具 (Svcutil.exe)"在 [http://go.microsoft.com/fwlink/?LinkID=74696](http://go.microsoft.com/fwlink/?LinkID=74696)。  
  
 下表显示了在使用已发布的、其架构使用其他架构的 WCF 服务时，需要了解的限制和注意事项。  
  
|XML 架构元素|使用通过 BizTalk WCF 服务发布向导发布的 WCF 服务|使用由 .NET 应用程序承载的 WCF 服务|  
|------------------------|-------------------------------------------------------------------------------------|--------------------------------------------------------|  
|\<import\>|BizTalk WCF 服务使用向导和 Svcutil.exe 均支持|BizTalk WCF 服务使用向导和 Svcutil.exe 均支持|  
|\<include\>|BizTalk WCF 服务使用向导和 Svcutil.exe 支持 **注意︰**  创建代理类时，Svcutil.exe 可能会引发一条警告消息。|BizTalk WCF 服务使用向导和 Svcutil.exe 支持 **注意︰**  创建代理类时，Svcutil.exe 可能会引发一条警告消息。|  
|\<redefine\>|支持与使用向导的 BizTalk WCF 服务<br />-有限的支持由 Svcutil.exe **注意︰**  Svcutil.exe 具有的相同限制 **重新定义** 作为 XSD.exe 的元素。|BizTalk WCF 服务使用向导和 Svcutil.exe 支持 **注意︰**  创建代理类时，Svcutil.exe 可能会引发一条警告消息。|  
  
> [!NOTE]
>  使用使用的架构创建针对发布的 BizTalk WCF 服务的代理类时，Svcutil.exe 可能会引发一条警告消息 **包括** 和 **重新定义** 元素。 例如，“The global element has already been declared.”（此全局元素已声明。）  
  
## <a name="ensure-that-an-in-process-wcf-receive-location-is-not-disabled-after-you-change-the-computer-name-part-in-its-service-endpoint-address"></a>在更改了服务终结点地址中的计算机名部分之后，请确保相应的进程内 WCF 接收位置未被禁用。  
 如果更改中的计算机名称部分 **地址 (URI)** 文本框中的运行中进程 WCF 接收位置，我们建议，使用 BizTalk 管理控制台来检查是否仍在运行接收位置。 例如，如果你更改使用 WCF NetTcp 的服务终结点地址将接收适配器， **net.tcp://\<***您的计算机名称***\>/samplepath**到**net.tcp://localhost/samplepath**，接收位置可能与禁用**Service.InvalidOperationException**。 如果只更改服务终结点地址中的计算机名部分，而不修改路径部分，则请确保接收位置未被禁用，如有必要请启用它。  
  
## <a name="set-the-appropriate-msdtc-security-configuration-options-on-client-computers-communicating-with-remote-wcf-receive-locations-through-a-transaction-protocol"></a>在通过事务协议与远程 WCF 接收位置进行通信的客户端计算机上设置相应的 MSDTC 安全配置选项  
 WCF NetTcp、 WCF WSHttp 和 WCF NetNamedPipe 接收适配器可以参与到使用 WCF 客户端管理的事务协调流程 **Ws-atomictransaction** 和 **OleTransaction** 事务协议。 可以在事务性上下文中使用事务协议将消息传输到目标接收位置并将其从 MessageBox 数据库中删除。  
  
 与远程通信 WCF 接收位置使用的事务协议，你必须相应地配置 MSDTC **安全配置** WCF 客户端计算机上的选项。 下表列出所需的值的选项，可以在 MSDTC **安全配置** 对话框中︰  
  
|配置选项|默认值|推荐值|  
|--------------------------|-------------------|-----------------------|  
|网络 DTC 访问|Disabled|已启用|  
|允许出站|Disabled|已启用|  
|要求进行相互身份验证|Enabled|如果相应的远程接收位置运行的 Windows Server 2003 SP1 或 SP2，并且配置为包含启用 **相互身份验证所需**。|  
|要求对呼叫方进行身份验证|禁用|运行 MSDTC 的群集上启用。|  
  
 在应用这些更改之后，必须重新启动 MSDTC 服务。  
  
 若要访问 MSDTC **安全配置** 对话框框中，执行以下步骤︰  
  
1.  单击 **启动**, ，单击 **运行**, ，和类型 **dcomcnfg** 以启动 **组件服务** 管理控制台。  
  
2.  展开 **组件服务**, ，展开 **计算机**, ，右键单击 **我的电脑**, ，然后单击 **属性**。  
  
3.  在 **我的电脑属性** 对话框中，单击 **MSDTC** 选项卡上，并依次 **安全配置** 以显示 **安全配置** 对话框。  
  
## <a name="explanation-of-the-soap-wrapper-when-using-the-biztalk-wcf-service-publishing-wizard"></a>使用 BizTalk WCF 服务发布向导时 SOAP 包装的说明  
 当使用 [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 服务发布向导将业务流程作为 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务发布时，会生成一个包装。 包装将使用消息发送到的 XML 消息端口的方法名称。 此包装是 Microsoft SOAP 信封的默认值。 它允许 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 包装 WCF 消息中通过适配器传输到终节点的多部分 SOAP 消息。  
  
 作为最佳实践，发送方应使用包装，接收方应接收消息，或者，发送方不使用包装，接收方应接收原始 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 消息。 无法提前预知使用包装是否会导致发送和接收内容之间的不兼容问题。