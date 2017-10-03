---
title: "什么是 Windows SharePoint Services Adapter？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, process flow
- Windows SharePoint Services adapters, receiving documents
- Windows SharePoint Services adapters, sending documents
- Windows SharePoint Services adapters, security
- Windows SharePoint Services adapters
- Windows SharePoint Services adapters, about Windows SharePoint Services adapters
ms.assetid: 1875ac85-46c2-4da5-ad16-8b078cb4cbd7
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a25bc378bdbb4c8bef34c3cff0140d03094faad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-windows-sharepoint-services-adapter"></a>什么是 Windows SharePoint Services Adapter？
针对 Windows SharePoint Services 的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 适配器可与 Windows SharePoint Services 和 Microsoft Office InfoPath 更紧密地集成在一起。 以下主题介绍了 Windows SharePoint Services 适配器的功能并对其工作原理进行了简要说明。  
  
## <a name="features-of-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services 适配器的功能  
 下表介绍了 Windows SharePoint Services 适配器的重要功能：  
  
-   将 BizTalk Server XML 和二进制消息发送到 SharePoint 文档库的功能。  
  
-   与 InfoPath 集成： 你可以将转换传出 BizTalk Server XML 消息，以在从 Windows SharePoint Services 站点打开时的 InfoPath 中自动打开。  
  
-   对进入 Windows SharePoint Services 的消息执行属性升级。 可以用该消息的 BizTalk Server 元数据对多达 16 个 SharePoint 列进行更新，例如业务流程实例 ID、消息 ID 或从该消息中提取的值。  
  
-   基于消息内容和 BizTalk Server 属性来生成文件名定义。  
  
-   要将文档发送到任意列表的功能 (而不是到文档库): 在这种情况下文档本身不存储在 Windows SharePoint Services，但属性提升仍发生因此将创建一个新列表项并检索的列的值从消息中。  
  
-   从任何文档库的任何视图中接收消息并使用指定文件名将其存档到指定文档库的功能。  
  
-   BizTalk Server 中的 Windows SharePoint Services 适配器属性中的升级： Windows SharePoint Services 文件信息进行消息上下文属性作为 BizTalk Server 中可用。 消息上下文属性可以访问从管道、 业务流程，等等。可以通过 WSS 访问自定义 SharePoint 列。InPropertiesXml 文档。  
  
-   完全支持动态端口： 发送适配器可以支持 （由用户在创建时定义发送端口） 的静态 URI 绑定或动态 （发送消息时由业务流程定义） 的 URI 绑定。 对于动态发送端口以及物理发送端口，所有配置信息都可以通过消息上下文属性（例如，WSS.Filename 和 WSS.ConfigTimeout）来定义。  
  
-   性能计数器  
  
## <a name="how-the-windows-sharepoint-services-adapter-works"></a>Windows SharePoint Services 适配器的工作原理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器 Windows SharePoint Services 的由三个主要组件组成：  
  
-   Windows SharePoint Services 适配器 Web 服务  
  
-   Windows SharePoint Services 接收适配器  
  
-   Windows SharePoint Services 发送适配器  
  
 在 Windows SharePoint Services 服务器上，安装了 Web Services (BTSharePointAdapterWS.asmx) 以提供对 Windows SharePoint Services 库和列表的访问。 该 Web Services 公开了从 SharePoint 库中获取、放置、删除和存档文档的方法。 接收适配器可从该 Web Services 检索文件，而发送适配器则可以向其张贴文件。  
  
 下图显示的主要组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供这些功能的 Windows SharePoint Services 的适配器。  
  
 ![](../core/media/bts-dev-adapters-wss-architecture.gif "BTS_Dev_Adapters_WSS_Architecture")  
  
### <a name="receiving-documents-from-windows-sharepoint-services"></a>从 Windows SharePoint Services 接收文档  
 接收适配器轮询 Windows SharePoint Services 文档库视图。 它对 Windows SharePoint Services 服务器调用 Web 方法，该方法使用 Windows SharePoint Services 对象模型来浏览库，签出文件，并将文件数据返回给适配器。 然后，适配器将文件提交给 BizTalk Server MessageBox，并调用另一个 Web 方法从 Windows SharePoint Services 中删除或存档文件。 为了对 Windows SharePoint Services 库中的文件进行筛选，该适配器会通过 Windows SharePoint Services 视图轮询 Windows SharePoint Services 库。  
  
 集中式（轮询）方法提供了一种简单的管理模型，在该模型中，配置工作在 BizTalk Server 上完成。 由于该方法允许对消息进行批处理，因此还提供了更优异的性能。  
  
 由于不能跨 Windows SharePoint Services、Web Services 和 BizTalk Server 提供平台级别的事务支持，因此使用签出机制来最大限度地减少与失败条件相关联的错误。 在某些情况下（即文件成功发送到 BizTalk Server MessageBox 数据库中，但无法从 Windows SharePoint Services 删除），即使文件已提交到 BizTalk Server，这些文件仍将在 Windows SharePoint Services 服务器上继续处于已签出状态。 错误将记录到 BizTalk 服务器上的事件日志中。  
  
### <a name="sending-documents-to-windows-sharepoint-services"></a>向 Windows SharePoint Services 发送文档  
 适配器通过对 Windows SharePoint Services 服务器调用 Web 方法来向 Windows SharePoint Services 发送文档。 适配器指定 Windows SharePoint Services 站点 URL、相对于站点的文档库或列表 URL、文件或列表项名称以及要与该文件关联的升级属性。  
  
 可以将文件名设置为固定字符串，也可以设置为从文档中的 XML 数据派生的名称。 对于强制执行标准命名约定来说，派生名称会非常有用。 适配器还可以将文件的升级属性值设置为列值。 与文件名一样，升级属性值可以为固定值，也可以从文档中的 XML 数据派生。  
  
> [!IMPORTANT]
>  Windows SharePoint Services 适配器中的升级属性是与 BizTalk Server 中的升级属性或 Windows SharePoint Services 中的升级属性不同的实体。  
  
 在浏览 Windows SharePoint Services 表单库时，Windows SharePoint Services 升级属性用来使 XML 元素可见。 在将 InfoPath 表单发布到 Windows SharePoint Services 表单库时，InfoPath 会对表单库进行配置以升级关键元素，使此操作自动进行。 只有在使用 InfoPath 表单库（使用相同的 XSD 架构和 InfoPath 解决方案存储 InfoPath 表单的文档库）时，才可在 Windows SharePoint Services 中使用此功能。  
  
 将具有不同架构的文档存储在同一文档库中时，Windows SharePoint Services 适配器属性升级使用户能够将属性升级到 Windows SharePoint Services 中。  
  
 BizTalk Server 属性升级的概念与此类似，唯一不同的是属性是作为消息的属性对业务流程可见，而不是在用户界面上对最终用户可见。 此外，在将属性值保存回文档时，BizTalk Server 支持属性降级的概念。  
  
 将 Windows SharePoint Services 适配器用于 InfoPath 表单和表单库（而不是任意 XML 和文档库）时，不需要通过发送适配器设置升级属性。 相反，可以在业务流程中更改文档（通过更改消息直接进行更改，或通过将要降级的属性间接进行更改）。 Windows SharePoint Services 将会对这些值进行自动升级。  
  
## <a name="security-considerations-for-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services 适配器的安全注意事项  
 Windows SharePoint Services 适配器由子系统、运行在 Windows SharePoint Services 网站上的 BTSharePointAdapterWS Web Services 以及运行在 BizTalk Server 主机实例进程中的 BizTalk 服务器上的适配器运行时组成。 适配器运行时调用 BTSharePointAdapterWS Web Services，该 Web Services 必须具有在 Windows SharePoint Services 中执行某些任务的权限。 由于此组件作为调用方运行，因此需要向调用方授予权限。 这意味着必须进行 BizTalk 主机实例**参与者**为了能够发送和接收消息，从该站点的 SharePoint 站点上。 BTSharePointAdapterWS Web 服务可以仅由的成员调用**SharePoint 启用主机**组。 若要允许运行适配器运行时，与 Web 服务进行交互的 BizTalk 主机实例，主机实例的 Windows 帐户必须进行的成员**SharePoint 启用主机**组。 它是管理员可以添加和从使主机实例以及此组中删除帐户的责任帐户成员的 sharepoint**参与者**角色。  
  
|组件|进程标识|权限|  
|---------------|----------------------|----------------|  
|BTSharePointAdapterWS Web Services|调用方标识|调用授予 SharePoint Enabled Hosts 组的权限|  
|适配器运行时|BizTalk 主机的标识|N/A|  
|Windows SharePoint Services 对象模型|N/A|SharePoint 启用主机组必须属于**参与者**SharePoint 服务中的角色。|  
  
 BizTalk Server 安装程序 BTSharePointAdapterWS Web 服务上配置权限，以便仅的帐户，是的成员**SharePoint 启用主机**组可以访问此 Web 服务。 如果你希望主机运行 Windows SharePoint Services 适配器，管理员将需要添加到该主机与关联的 NT 组**SharePoint 启用主机**分组以及还添加**SharePoint 启用主机**组，以便 Windows SharePoint Services**参与者**角色。  
  
 对 Windows SharePoint Services 文件、列表和文档库的权限使用 Windows SharePoint Services 安全性进行限制。 消息从 Windows SharePoint Services 直接发送到 BizTalk Server 中。 适配器运行时与 Web Services 之间的通信通过 HTTP 或 HTTPS 来完成。  
  
 适配器假定 BTSharePointAdapterWS Web Services 正在使用相同的 HTTP 方案（HTTP 或 HTTPS）作为 Windows SharePoint Services 站点。 这意味着，在安全 IIS 网站上创建 Windows SharePoint Services 站点时，适配器将使用 HTTPS 与 BTSSharePointAdapterWS Web Services 进行通信，或者在没有服务器证书的 IIS 网站上创建 Windows SharePoint Services 站点时，它将使用 HTTP 与 BTSharePointAdapterWS Web Services 进行通信。  
  
## <a name="see-also"></a>另请参阅  
 [设置和部署 Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)   
 [配置 Windows SharePoint Services Adapter](../core/configuring-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services 适配器演练](../core/windows-sharepoint-services-adapter-walkthroughs.md)