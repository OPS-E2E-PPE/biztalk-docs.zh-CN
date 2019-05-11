---
title: 使用 WCF 服务 |Microsoft Docs
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
ms.openlocfilehash: 0969fb98cbf9ea79f4e32138d795b6b4de81f513
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354622"
---
# <a name="consuming-wcf-services"></a>使用 WCF 服务
使用 WCF 服务，可将现有的 WCF 服务添加到您的业务流程。 可以将若干 WCF 服务聚合成单个业务流程。  
  
 您可以通过使用 BizTalk WCF 服务使用向导从您的业务流程使用 （调用） WCF 服务。 BizTalk WCF 服务使用向导创建端口类型和消息类型所需使用 WCF 服务。 BizTalk WCF 服务使用向导还会创建两个可开发命令行工具或向导以使用系统提供的绑定 WCF 适配器和 Wcf-custom 适配器配置发送端口导入的绑定文件。 该向导允许你结合使用的 WCF 服务使用 SOAP 标头、 更改使用的 WCF 服务的 URI 而动态设置使用的 Web 服务的 WCF。 WCF 发送适配器使用 WCF 服务和 WCF 接收位置发布 WCF 服务。  
  
 BizTalk WCF 发送适配器包括五个物理发送适配器，分别表示 WCF 预定义绑定**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**，**NetNamedPipeBinding**，并**NetMsmqBinding**。 BizTalk WCF 适配器还包括使您能够随意配置 WCF 绑定和行为信息的发送端口的自定义适配器。 有关如何配置 WCF 发送处理程序和发送端口的详细信息，请参阅中每个 WCF 适配器的操作指南主题[WCF 适配器](../core/wcf-adapters.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [通过 WCF 发送适配器使用 WCF 服务时的注意事项](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)  
  
-   [SOAP 标头与使用的 WCF 服务](../core/soap-headers-with-consumed-wcf-services.md)  
  
-   [使用 WCF 适配器上下文属性配置动态发送端口](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [如何使用 BizTalk WCF 服务使用向导来使用 WCF 服务](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)  
  
-   [如何处理业务流程中的类型化的错误协定](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)  
  
-   [为 WCF 发送适配器指定 SOAP 操作](../core/specifying-soap-actions-for-wcf-send-adapters.md)