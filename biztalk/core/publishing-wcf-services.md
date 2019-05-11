---
title: 发布 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cc57665a8f57fde0d1ea410c0bad4454cb1a7a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398360"
---
# <a name="publish-wcf-services"></a>发布 WCF 服务
业务流程可以作为 BizTalk Server 将调用的 WCF 客户端中的 WCF 服务发布。  
  
## <a name="publish-wcf-services-with-the-isolated-wcf-adapters"></a>发布独立 WCF 适配器的 WCF 的服务 
  
 创建并如 Wcf-basichttp 适配器的独立的 WCF 适配器、 Wcf-wshttp 适配器和 Wcf-customisolated 适配器使用 BizTalk WCF 服务发布向导发布 WCF 服务。 这将创建一个接收位置，作为进程外应用程序在 IIS 中存在。  
  
 通过独立 WCF 适配器发布 WCF 服务之前，应具有托管 WCF 服务如何了解在 Internet 信息服务 (IIS)。  
  
## <a name="publish-service-metadata-for-the-wcf-receive-locations"></a>为 WCF 接收位置发布服务元数据
  
 对于已发布的 WCF 接收位置使用 BizTalk WCF 服务发布向导创建服务元数据。 若要从已发布元数据文档生成服务模型客户端代码可以使用 Windows 软件开发工具包 (SDK) 和.NET Framework 运行时组件中包含的服务模型元数据实用工具工具 (SvcUtil.exe)。  
  
> [!IMPORTANT]
>  运行 BizTalk WCF 服务发布向导之前，必须启用 WCF 服务。 有关启用你的系统的 WCF 服务的详细信息，请参阅[配置 IIS 以实现独立 WCF 接收适配器](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)。  
  
## <a name="next-steps"></a>后续步骤
  
-   [通过独立 WCF 接收适配器发布 WCF 服务](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [为 WCF 接收适配器发布服务元数据](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [通过 WCF 接收适配器发布 WCF 服务时的注意事项](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [SOAP 标头与已发布的 WCF 服务](../core/soap-headers-with-published-wcf-services.md)  
  
-   [从发布为 WCF 服务的业务流程引发错误异常](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)