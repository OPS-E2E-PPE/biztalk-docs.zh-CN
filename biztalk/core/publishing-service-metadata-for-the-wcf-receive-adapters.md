---
title: "用于 WCF 接收适配器发布服务元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4df09e8f-e0c9-41c5-bd71-13bb0e96cd97
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6962ec3068694223bd6ca214d2d7500e0d5316
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="publishing-service-metadata-for-the-wcf-receive-adapters"></a>为 WCF 发布服务元数据接收适配器
可以使用 BizTalk WCF 服务发布向导来创建为现有 WCF 接收位置发布服务元数据的 WCF 服务。 若要从已发布的元数据文档生成客户端服务模型代码可以使用服务模型元数据实用工具 (SvcUtil.exe) 包含在 Windows 软件开发工具包 (SDK) 和.NET Framework 运行时组件。  
  
> [!NOTE]
>  在发布服务元数据的 WCF 适配器之前，必须创建 WCF 接收位置使用 BizTalk 管理控制台或 BizTalk Server 附带 BTSTask 命令行工具。 有关如何创建 WCF 的详细信息接收位置，请参阅中的每个 WCF 适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。  
  
## <a name="iis-versions"></a>IIS 版本
  
 发布服务元数据的 WCF 服务可以正在运行随操作系统附带的 IIS 版本。
  
-   **IIS**提供的高级的进程模型。 已发布的 BizTalk WCF 服务必须在 ASP.NET 兼容模式中运行。 用于 WCF 接收适配器，通过在 IIS 中的 Web 应用程序发布的服务元数据可通过 HTTP 传输进行访问。  
  
## <a name="publish-service-metadata-for-the-wcf-receive-locations"></a>为 WCF 接收位置发布服务元数据
  
 若要为 WCF 接收位置发布服务元数据，您必须使用 BizTalk WCF 服务发布向导来创建一个 Web 应用程序，以承载提供服务元数据的 WCF 服务。 这样便允许调用接收位置，就像 WCF 服务一样。  BizTalk WCF 服务发布向导会在已创建的 Web 应用程序的根文件夹中生成下列文件：  
  
|文件|文件夹|Description|  
|----------|------------|-----------------|  
|WCF 服务（.svc 文件）|\|为 WCF 发布服务元数据的 WCF 服务接收位置。 WCF 服务发布使用 HTTP/GET 请求进行检索的服务元数据。|  
|Web.config|\|ASP.NET 配置文件，包含 ASP.NET Web 应用程序行为、 已发布的 WCF 服务行为、 元数据终结点和特定于 BizTalk 的设置信息。 该向导将生成 Web.config 时**httpGetEnabled**属性 **\<serviceMetadata\>** 元素设置为**true**。 您可以使用元数据导入工具（如 SvcUtil.exe）生成在开发环境中调用此服务所需的客户端代码。 发布元数据的地址是 WCF 服务的终结点地址加上 **？ wsdl** 查询字符串。 **注意︰**  由 BizTalk WCF 发布向导生成的默认元数据绑定不安全，它允许匿名访问元数据。 服务元数据中包含有关服务的详细说明，可能会有意或无意地包含敏感信息。 为了防止服务元数据受到未经授权的访问，可以修改 Web.config，使其针对元数据终结点使用安全绑定。|  
|ServiceDescription.xml|\|XML 文件中描述的已发布的 WCF 服务协定包括的消息类型。|  
|BizTalk 架构（.xsd 文件）|\App_Data|XML 架构，用在 WCF 接收位置中并可定义 XML 实例消息的结构。|  
|SchemaIndex.xml|\App_Data|XML 文件，指示用在 WCF 接收位置中的 XML 架构文件。|  
|Serialization.xsd|\App_Data|通过导出 XML 架构[DataContractSerializer](https://msdn.microsoft.com/library/system.runtime.serialization.datacontractserializer.aspx)有关类型、 元素和命名空间中, 属性 http://schemas.microsoft.com/2003/10/Serialization/。|  
|BindingInfo.xml|\App_Data\Temp|BizTalk 绑定文件，可将其通过开发命令行工具或向导导入，以配置接收位置。 已发布的 WCF 服务在运行时不使用此文件和 Temp 文件夹。|  
|WcfServiceDescription.xml|\App_Data\Temp|XML 文件，概述与 BizTalk WCF 服务发布向导一起用来创建此 Web 应用程序的设置。 已发布的 WCF 服务在运行时不使用此文件和 Temp 文件夹。|  
  
## <a name="next-steps"></a>后续步骤
  
-   [使用 BizTalk WCF 服务发布向导为基于内容的路由的 WCF 接收位置发布服务元数据](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md)  
  
-   [使用 BizTalk WCF 服务发布向导为已绑定到业务流程端口的 WCF 接收位置发布服务元数据](../core/publish-receive-location-service-metadata-biztalk-wcf-service-publishing-wizard.md)  
  
## <a name="see-also"></a>另请参阅  
 [演练：通过 WCF-NetMsmq 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)