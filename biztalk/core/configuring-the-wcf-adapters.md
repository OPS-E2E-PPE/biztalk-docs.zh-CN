---
title: 配置 WCF 适配器 |Microsoft Docs
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
ms.openlocfilehash: d3dbe2541a85879f21d6d2393280933d8335dac0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355132"
---
# <a name="configuring-the-wcf-adapters"></a>配置 WCF 适配器
BizTalk 适配器的 Windows Communication Foundation (WCF) 允许[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与基于 WCF 的应用程序进行通信。 BizTalk WCF 适配器包括五个物理适配器，分别表示 WCF 预定义绑定 —**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**， **NetNamedPipeBinding**，并**NetMsmqBinding**。 预定义绑定的 WCF 适配器提供以便您可以轻松配置大多数应用程序要求所需的信息。  
  
 BizTalk WCF 适配器还包括两个适配器，您可以自由地配置 WCF 绑定和行为信息的接收位置和发送端口。  
  
 所有 WCF 适配器提供相似的传输属性对话框，发送端口和接收位置。 但是，配置 WCF 适配器的具体的任务因物理适配器。 与适配器绑定，比如安装证书，不能直接相关的任务是相同的所有 WCF 适配器。 本部分讨论所有 WCF 适配器都共有的任务。 有关每个适配器不同的任务的信息，请参阅中的适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)  
  
-   [WCF 适配器的安全建议](../core/wcf-adapters-security-recommendations.md)  
  
-   [安装用于 WCF 适配器的证书](../core/installing-certificates-for-the-wcf-adapters.md)  
  
-   [指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [如何启用 WCF 适配器的 WCF 扩展点](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)  
  
-   [WCF 适配器性能计数器](../core/wcf-adapters-performance-counters.md)  
  
-   [WCF 适配器的单一登录支持](../core/single-sign-on-support-for-the-wcf-adapters.md)  
  
## <a name="see-also"></a>请参阅  
 [WCF 适配器](../core/wcf-adapters.md)