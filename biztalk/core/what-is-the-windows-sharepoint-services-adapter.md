---
title: 什么是 Windows SharePoint Services 适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4949188ec1bed73fa663a7cfb87e7c3bdad6265
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242917"
---
# <a name="what-is-the-windows-sharepoint-services-adapter"></a>什么是 Windows SharePoint Services 适配器？
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于 Windows SharePoint Services 适配器提供了与 Windows SharePoint Services 和 Microsoft Office InfoPath 更紧密的集成。 以下主题介绍的功能和 Windows SharePoint Services 适配器的工作原理的概述。  
  
## <a name="features-of-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services 适配器的功能  
 以下列表描述了 Windows SharePoint Services 适配器的重要功能：  
  
-   若要将 BizTalk Server XML 和二进制消息发送到 SharePoint 文档库功能。  
  
-   与 InfoPath 集成：你可以转换传出 BizTalk Server XML 消息，以在从 Windows SharePoint Services 站点打开时的 InfoPath 中自动打开。  
  
-   转到 Windows SharePoint Services 的消息的属性升级。 最多 16 个 SharePoint 列可以使用类似于消息的业务流程实例 ID、 消息 ID 或从消息中提取的值的 BizTalk Server 元数据进行更新。  
  
-   文件名称定义将基于消息内容和 BizTalk Server 属性。  
  
-   要将文档发送到任意列表的功能 (而不是向文档库):在这种情况下文档本身不存储在 Windows SharePoint Services，但这样将创建一个新列表项和从消息中检索的列的值，仍会执行属性升级。  
  
-   能够从任何文档库的任意视图中接收消息并将其存档到指定的文档库使用指定的文件名。  
  
-   升级 BizTalk Server 中的 Windows SharePoint Services 适配器属性：Windows SharePoint Services 文件信息可在 BizTalk Server 中作为消息上下文属性。 可以从管道、 业务流程等访问消息上下文属性。可以通过 WSS 访问自定义 SharePoint 列。InPropertiesXml 文档。  
  
-   完全支持动态端口：发送适配器可以支持静态 URI 绑定 （创建发送端口时由用户定义） 或动态 URI 绑定 （发送消息时由业务流程定义）。 可以通过消息上下文属性，如 WSS 定义的所有配置信息。文件名和 WSS。ConfigTimeout，对于动态发送端口，以及物理发送端口。  
  
-   性能计数器  
  
## <a name="how-the-windows-sharepoint-services-adapter-works"></a>Windows SharePoint Services 适配器的工作原理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器由三个主要组件组成：  
  
- Windows SharePoint Services 适配器 Web services  
  
- Windows SharePoint Services 接收适配器  
  
- Windows SharePoint Services 发送适配器  
  
  在 Windows SharePoint Services 服务器上安装 Web 服务 (BTSharePointAdapterWS.asmx) 以提供对 Windows SharePoint Services 库和列表访问。 Web 服务公开 get、 put、 删除和存档来自 SharePoint 库的文档的方法。 接收适配器检索文件从 Web 服务和向其发送适配器张贴文件。  
  
  下图显示的主要组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于提供这些功能的 Windows SharePoint Services 适配器。  
  
  ![](../core/media/bts-dev-adapters-wss-architecture.gif "BTS_Dev_Adapters_WSS_Architecture")  
  
### <a name="receiving-documents-from-windows-sharepoint-services"></a>从 Windows SharePoint Services 接收文档  
 接收适配器轮询 Windows SharePoint Services 文档库视图。 它对使用 Windows SharePoint Services 对象模型来浏览库、 签出文件并将文件数据返回到适配器的 Windows SharePoint Services 服务器调用 Web 方法。 然后，该适配器提交至 BizTalk Server MessageBox，并调用另一个 Web 方法，删除或存档的文件从 Windows SharePoint Services。 若要筛选的 Windows SharePoint Services 库中的文件，适配器轮询 Windows SharePoint Services 库通过 Windows SharePoint Services 视图。  
  
 集中式 （轮询） 方法提供了简单的管理模型，其中在 BizTalk server 进行配置。 因为，它允许批处理的消息，它还提供更好的性能。  
  
 由于 Windows SharePoint Services、 Web 服务和 BizTalk Server 跨平台级别的事务支持不可用，因此使用签出机制来最大程度减少与失败条件相关联的错误。 在某些情况下 （即文件成功发送到 BizTalk Server MessageBox 数据库但不能从 Windows SharePoint Services 删除），文件将保持签出 Windows SharePoint Services 服务器上，即使它们是提交到 BizTalk Server。 错误将记录到 BizTalk 服务器上的事件日志。  
  
### <a name="sending-documents-to-windows-sharepoint-services"></a>将文档发送到 Windows SharePoint Services  
 适配器通过调用 Windows SharePoint Services 服务器上的 Web 方法向 Windows SharePoint Services 发送文档。 适配器指定 Windows SharePoint Services 站点 URL、 文档库或列表 URL 相对于站点、 文件或列表项名称和已升级属性将与文件相关联。  
  
 可以设置的文件的名称为固定字符串或从文档中的 XML 数据派生的名称。 派生名称可以是强制执行标准命名约定非常有用。 适配器还可以设置已提升属性值对该文件作为列的值。 使用文件名，如升级的属性值可以修复或可从文档中的 XML 数据。  
  
> [!IMPORTANT]
>  中的 Windows SharePoint Services 适配器的升级的属性是比 BizTalk Server 中的升级的属性或 Windows SharePoint Services 中的升级的属性不同的实体。  
  
 Windows SharePoint Services 升级属性用于浏览 Windows SharePoint Services 表单库时使 XML 元素可见。 当 InfoPath 窗体发布到 Windows SharePoint Services 表单库中时，InfoPath 窗体将库配置以升级关键元素，使此操作自动。 仅当使用 InfoPath 表单库 （存储使用相同的 XSD 架构和 InfoPath 解决方案的 InfoPath 窗体的文档库） 时，此功能是 Windows SharePoint Services 中可用。  
  
 Windows SharePoint Services 适配器属性升级使用户能够将属性提升到 Windows SharePoint Services 时具有不同架构的文档存储在同一个文档库。  
  
 BizTalk Server 属性升级是类似的概念，仅，业务流程作为消息的属性而不属于最终用户 UI 上的属性被设置可见。 此外，BizTalk Server 支持属性降级的概念，属性值保存回文档时。  
  
 使用时的 Windows SharePoint Services 适配器与 InfoPath 窗体和窗体库 （而不是任意 XML 和文档库），您不需要设置发送适配器通过升级的属性。 相反，文档可以在业务流程内更改 （通过更改消息直接或间接通过属性将降级）。 值将由 Windows SharePoint Services 会自动升级。  
  
## <a name="security-considerations-for-the-windows-sharepoint-services-adapter"></a>有关 Windows SharePoint Services 适配器的安全注意事项  
 Windows SharePoint Services 适配器由子系统、 运行 Windows SharePoint Services Web 站点的 BTSharePointAdapterWS Web 服务和 BizTalk Server 主机实例进程在 BizTalk server 上运行的适配器运行时组成。 适配器运行时调用 BTSharePointAdapterWS Web 服务，其必须具有权限才能执行某些任务在 Windows SharePoint Services 内部。 由于此组件作为调用方运行，需要向调用方授予权限。 这意味着 BizTalk 主机实例必须成为**参与者**为了能够发送和接收消息，从该站点的 SharePoint 站点上。 可以仅由的成员调用 BTSharePointAdapterWS Web 服务**SharePoint Enabled Hosts**组。 若要允许运行适配器运行时，与 Web 服务进行交互的 BizTalk 主机实例，主机实例 Windows 帐户必须进行的成员**SharePoint Enabled Hosts**组。 它是负责的管理员来添加和删除帐户从该组也使主机实例帐户隶属于 SharePoint**参与者**角色。  
  
|组件|进程标识|权限|  
|---------------|----------------------|----------------|  
|BTSharePointAdapterWS Web 服务|调用方标识|调用授予 SharePoint Enabled Hosts 组的权限|  
|适配器运行时|BizTalk 主机的标识|不可用|  
|Windows SharePoint Services 对象模型|不可用|SharePoint Enabled Hosts 组必须属于**参与者**SharePoint Services 中的角色。|  
  
 BizTalk Server 安装 BTSharePointAdapterWS Web 服务上配置权限，以便只有帐户，是的成员**SharePoint Enabled Hosts**一组可访问此 Web 服务。 如果你想要运行的 Windows SharePoint Services 适配器的主机，管理员将需要添加到该主机与关联的 NT 组**SharePoint Enabled Hosts**组并添加**SharePoint Enabled Hosts**组，以便 Windows SharePoint Services**参与者**角色。  
  
 对 Windows SharePoint Services 文件、 列表和文档库的权限是使用 Windows SharePoint Services 安全限制。 直接在 BizTalk Server 从 Windows SharePoint Services 发送消息。 适配器运行时和 Web 服务之间的通信是通过 HTTP 或 HTTPS。  
  
 适配器假定 BTSharePointAdapterWS Web 服务作为 Windows SharePoint Services 站点使用相同的 HTTP 方案 （HTTP 或 HTTPS）。 这意味着该适配器将使用 HTTPS 与 BTSSharePointAdapterWS Web 服务通信，Windows SharePoint Services 站点创建安全的 IIS Web 站点，或它将使用 HTTP 与 BTSharePointAdapterWS Web 进行通信时服务时在没有服务器证书的 IIS 网站上创建 Windows SharePoint Services 站点。  
  
## <a name="see-also"></a>请参阅  
 [设置和部署 Windows SharePoint Services 适配器](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)   
 [配置 Windows SharePoint Services 适配器](../core/configuring-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services 适配器演练](../core/windows-sharepoint-services-adapter-walkthroughs.md)