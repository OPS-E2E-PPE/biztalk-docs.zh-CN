---
title: 组件 MQSeries 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, BizTalk component
- MQSeries adapters, components
- MQSeries components, MQSeries adapters
- BizTalk components
- MQSeries adapters, MQSeries component
ms.assetid: 923974cb-371d-47dc-99a7-2f7b93f60ada
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58726b6528af55da6554ff740208b3e03bdc806e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232509"
---
# <a name="components-of-the-mqseries-adapter"></a>MQSeries 适配器的组件
MQSeries 适配器使用两个组件在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 MQSeries Server for Windows 之间进行文档传输。  
  
-   **BizTalk 组件。** 将此组件与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装在同一台计算机上。 此组件与 BizTalk Server 进行通信。  
  
-   **MQSeries 组件。** 将此组件安装在 MQSeries Server for Windows 中。 MQSeries Server for Windows 在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 上运行。 此组件（称为 MQSAgent）与 IBM MQSeries Server 进行通信。  
  
    > [!NOTE]
    >  MQSeries 适配器的 MQSAgent 组件可在 MQSeries Server 5.3、CSD10 或更高版本以及 WebSphere MQSeries Server 6.0 on Windows 中运行。  
  
 下图简要介绍了该适配器的典型用法：  
  
 ![文档 MQSeries 服务器和 BizTalk 之间的流](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")  
  
 MQSeries 适配器是一种连接解决方案，使用该解决方案，您可以在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries 作为所选消息传递标准的企业中使用 MQSeries。 开发此解决方案的部分原因如下：  
  
-   适应客户对简单安装和配置以及 MQSeries 连接解决方案的要求  
  
-   支持的消息大小最大为 100 MB  
  
-   提供 MQSeries 支持  
  
-   为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供即插即用的 MQSeries 消息连接解决方案  
  
 MQSeries 适配器是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收服务套件的重要组成部分，它为各种通信协议标准提供了一组侦听器。 侦听器可以向企业应用程序集成 (EAI)、企业对企业或应用程序对应用程序集成贸易关系附加协议（例如 HTTP、FTP 或 MQSeries）。  
  
## <a name="see-also"></a>另请参阅  
 [MQSeries 适配器体系结构](../core/mqseries-adapter-architecture.md)   
 [什么是 MQSeries 适配器？](../core/what-is-the-mqseries-adapter.md)