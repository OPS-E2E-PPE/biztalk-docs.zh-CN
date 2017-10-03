---
title: "为 WCF 发布服务元数据接收适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF services, publishing
ms.assetid: 4df09e8f-e0c9-41c5-bd71-13bb0e96cd97
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d922c0acecf81a96b0e40cebf739e7b56c5ffd3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-service-metadata-for-the-wcf-receive-adapters"></a>为 WCF 发布服务元数据接收适配器
可以使用 BizTalk WCF 服务发布向导来创建为现有 WCF 接收位置发布服务元数据的 WCF 服务。 若要从已发布的元数据文档生成客户端服务模型代码可以使用服务模型元数据实用工具 (SvcUtil.exe) 中包含[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]软件开发工具包 (SDK)，为[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]和[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]运行时组件。  
  
> [!NOTE]
>  在发布服务元数据的 WCF 适配器之前，必须创建 WCF 使用 BizTalk 管理控制台或包含的 BTSTask 命令行工具接收位置[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关如何创建 WCF 的详细信息接收位置，请参阅中的每个 WCF 适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。  
  
 **版本的 IIS**  
  
 发布服务元数据的 WCF 服务可以在下列操作系统中如下版本的 Internet 信息服务 (IIS) 上运行：  
  
-   **在 Windows Vista、 Windows Server 2008 SP2 和 Windows Server 2008 R2 的 IIS 7.0/7.5 中。** IIS 7.0/7.5 提供与 IIS 6.0 相同的高级过程模型。 发布的 BizTalk WCF 服务必须在 IIS 7.0/7.5 的 ASP.NET 兼容模式下运行。 用于 WCF 接收适配器发布的 Web 应用程序在 IIS 7.0/7.5 中的服务元数据可通过 HTTP 传输进行访问。  
  
 **为 WCF 接收位置发布服务元数据**  
  
 若要为 WCF 接收位置发布服务元数据，您必须使用 BizTalk WCF 服务发布向导来创建一个 Web 应用程序，以承载提供服务元数据的 WCF 服务。 这样便允许调用接收位置，就像 WCF 服务一样。  BizTalk WCF 服务发布向导会在已创建的 Web 应用程序的根文件夹中生成下列文件：  
  
|文件|文件夹|Description|  
|----------|------------|-----------------|  
|WCF 服务（.svc 文件）|\|WCF 服务，为 WCF 接收位置发布服务元数据。 WCF 服务发布使用 HTTP/GET 请求进行检索的服务元数据。|  
|Web.config|\|ASP.NET 配置文件，其中包含有关 ASP.NET Web 应用程序行为、已发布 WCF 服务行为、元数据终结点和 BizTalk 特有设置的信息。 该向导将生成 Web.config 时**httpGetEnabled**属性 **\<serviceMetadata >**元素设置为**true**。 您可以使用元数据导入工具（如 SvcUtil.exe）生成在开发环境中调用此服务所需的客户端代码。 从该处发布元数据的地址是 WCF 服务的终结点地址加上**？ wsdl**查询字符串。 **注意：**由 BizTalk WCF 发布向导生成的默认元数据绑定不安全，它允许匿名访问元数据。 服务元数据中包含有关服务的详细说明，可能会有意或无意地包含敏感信息。 为了防止服务元数据受到未经授权的访问，可以修改 Web.config，使其针对元数据终结点使用安全绑定。|  
|ServiceDescription.xml|\|用于描述包含消息类型的已发布 WCF 服务约定的 XML 文件。|  
|BizTalk 架构（.xsd 文件）|\App_Data|XML 架构，用在 WCF 接收位置中并可定义 XML 实例消息的结构。|  
|SchemaIndex.xml|\App_Data|XML 文件，指示用在 WCF 接收位置中的 XML 架构文件。|  
|Serialization.xsd|\App_Data|通过导出 XML 架构[DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722)有关类型、 元素和命名空间中, 属性 http://schemas.microsoft.com/2003/10/Serialization/。|  
|BindingInfo.xml|\App_Data\Temp|BizTalk 绑定文件，可将其通过开发命令行工具或向导导入，以配置接收位置。 已发布的 WCF 服务在运行时不使用此文件和 Temp 文件夹。|  
|WcfServiceDescription.xml|\App_Data\Temp|XML 文件，概述与 BizTalk WCF 服务发布向导一起用来创建此 Web 应用程序的设置。 已发布的 WCF 服务在运行时不使用此文件和 Temp 文件夹。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何使用发布向导的 BizTalk WCF 服务的 WCF 接收位置用于基于内容的路由发布服务元数据](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md)  
  
-   [如何使用发布向导的 BizTalk WCF 服务的 WCF 接收位置发布服务元数据绑定到业务流程端口](../core/publish-receive-location-service-metadata-biztalk-wcf-service-publishing-wizard.md)  
  
## <a name="see-also"></a>另请参阅  
 [演练： 使用 WCF NetMsmq 适配器的 WCF 服务发布](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)