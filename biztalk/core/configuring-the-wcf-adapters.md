---
title: 配置 WCF 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- NetTcpBinding [WCF adapters]
- configuring [WCF adapters]
- WCF adapters, pre-defined bindings
- configuring [WCF adapters], about configuring WCF adapters
- WsHttpBinding [WCF adapters]
- BasicHttpBinding [WCF adapters]
- NetNamedPipeBinding [WCF adapters]
- NetMsmqBinding [WCF adapters]
- bindings, pre-defined [WCF adapters]
- WCF adapters, configuring
ms.assetid: af01e2d4-303d-407a-b853-dd90b0246a8a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dde69bb5b2014a20509778e27230840e47c0b36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233157"
---
# <a name="configuring-the-wcf-adapters"></a>配置 WCF 适配器
用于 Windows Communication Foundation (WCF) 的 BizTalk 适配器允许 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与基于 WCF 的应用程序通信。 BizTalk WCF 适配器包括表示的预定义的 WCF 绑定的五个物理适配器-**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**， **NetNamedPipeBinding**，和**NetMsmqBinding**。 通过用于预定义绑定的 WCF 适配器，您可以轻松配置大多数应用程序要求的必需信息。  
  
 BizTalk WCF 适配器还包括用于随意配置接收位置和发送端口的 WCF 绑定和行为信息的两个适配器。  
  
 所有 WCF 适配器都为发送端口和接收位置提供相似的传输属性对话框。 不过，配置 WCF 适配器的具体任务因物理适配器而异。 就不与适配器绑定直接相关的任务而言，比如安装证书，对于所有 WCF 适配器都是相同的。 本部分讨论的是所有 WCF 适配器共有的任务。 有关为每个适配器与不同的任务的信息，请参阅中的适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)  
  
-   [WCF 适配器安全建议](../core/wcf-adapters-security-recommendations.md)  
  
-   [将证书安装适用于这些 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)  
  
-   [为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [如何启用与 WCF 适配器 WCF 扩展点](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)  
  
-   [WCF 适配器性能计数器](../core/wcf-adapters-performance-counters.md)  
  
-   [WCF 适配器的的单一登录支持](../core/single-sign-on-support-for-the-wcf-adapters.md)  
  
## <a name="see-also"></a>另请参阅  
 [WCF 适配器](../core/wcf-adapters.md)