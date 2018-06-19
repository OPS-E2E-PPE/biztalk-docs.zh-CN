---
title: 发布 WCF 服务 |Microsoft 文档
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
ms.openlocfilehash: 00136b64d5feaf552f77b92b3ad4442da4e447cc
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710236"
---
# <a name="publish-wcf-services"></a>发布 WCF 服务
业务流程可以作为由 WCF 客户端调用的 BizTalk Server 中的 WCF 服务发布。  
  
## <a name="publish-wcf-services-with-the-isolated-wcf-adapters"></a>发布具有独立的 WCF 适配器的 WCF 服务 
  
 通过使用针对独立 WCF 适配器（WCF-BasicHttp 适配器、WCF-WSHttp 适配器和 WCF-CustomIsolated 适配器）的 BizTalk WCF 服务发布向导，可以创建并发布 WCF 服务。 这将创建一个接收位置，作为 IIS 中进程外应用程序存在。  
  
 在使用独立 WCF 适配器发布 WCF 服务之前，您应当了解如何在 Internet 信息服务 (IIS) 中承载 WCF 服务。  
  
## <a name="publish-service-metadata-for-the-wcf-receive-locations"></a>为 WCF 接收位置发布服务元数据
  
 通过使用 BizTalk WCF 服务发布向导，可以为已发布的 WCF 接收位置创建服务元数据。 若要从已发布的元数据文档生成服务模型客户端代码可以使用服务模型元数据实用工具 (SvcUtil.exe) 包含在 Windows 软件开发工具包 (SDK) 和.NET Framework 运行时组件。  
  
> [!IMPORTANT]
>  在运行 BizTalk WCF 服务发布向导之前，必须先启用 WCF 服务。 有关启用你的系统的 WCF 服务的详细信息，请参阅[将 IIS 配置为独立的 WCF 接收适配器](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)。  
  
## <a name="next-steps"></a>后续步骤
  
-   [通过独立 WCF 接收适配器发布 WCF 服务](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [为 WCF 接收适配器发布服务元数据](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [通过 WCF 接收适配器发布 WCF 服务时的注意事项](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [SOAP 标头与已发布的 WCF 服务](../core/soap-headers-with-published-wcf-services.md)  
  
-   [从发布为 WCF 服务的业务流程引发错误异常](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)