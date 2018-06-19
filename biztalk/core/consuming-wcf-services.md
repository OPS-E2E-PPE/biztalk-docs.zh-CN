---
title: 使用 WCF 服务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- WCF services, consuming
ms.assetid: ca6c0514-c1df-43ad-8f02-df117271b0b5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fc0764295cbbc793b07757691e1f0c730a4049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237861"
---
# <a name="consuming-wcf-services"></a>使用 WCF 服务
通过使用 WCF 服务，可以将现有的 WCF 服务添加到业务流程中。 您可以将若干 WCF 服务聚合成单个业务流程。  
  
 使用 BizTalk WCF 服务使用向导，您可以从业务流程使用（调用）WCF 服务。 BizTalk WCF 服务使用向导创建使用 WCF 服务所需的端口类型和消息类型。 BizTalk WCF 服务使用向导还会创建两个绑定文件，可使用开发命令行工具或向导导入该文件，以便配置带有系统提供的绑定 WCF 适配器和 WCF-Custom 适配器的发送端口。 通过向导，您可以将 SOAP 标头与使用的 WCF 服务一起使用，更改使用的 WCF 服务的 URI，并动态设置使用的 Web Services 的 WCF。 WCF 发送适配器使用 WCF 服务和 WCF 接收位置发布 WCF 服务。  
  
 BizTalk WCF 发送适配器包括表示的预定义的 WCF 绑定的五个物理发送适配器**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**，**NetNamedPipeBinding**，和**NetMsmqBinding**。 BizTalk WCF 适配器还包括一个自定义的适配器，您可以使用该适配器随意配置发送端口的 WCF 绑定和行为信息。 有关如何配置 WCF 发送处理程序和发送端口的详细信息，请参阅操作指南主题中的每个 WCF 适配器[WCF 适配器](../core/wcf-adapters.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 WCF 服务和 WCF 时的注意事项发送适配器](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)  
  
-   [与使用的 WCF 服务的 SOAP 标头](../core/soap-headers-with-consumed-wcf-services.md)  
  
-   [配置动态发送端口使用 WCF 适配器上下文属性](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [如何通过 BizTalk WCF 服务使用向导来使用 WCF 服务](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)  
  
-   [如何处理在业务流程中的类型化的错误协定](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)  
  
-   [指定的 SOAP 操作，wcf 发送适配器](../core/specifying-soap-actions-for-wcf-send-adapters.md)