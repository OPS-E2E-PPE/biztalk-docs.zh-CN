---
title: "MQSeries 适配器高可用性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, MQSeries adapters
- MQSeries adapters, availability
- MQSeries adapters, performance
- high availability, MQSeries adapters
ms.assetid: 4339b10b-b35d-47c0-b78a-c60207e06c8e
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c0b6486e49cb2ccddfab37271a94a4ba7a6948
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-high-availability"></a>MQSeries 适配器高可用性
在使用适配器时，可通过以下方式提高其可用性：  
  
-   设置的容错的宿主环境[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
-   对 IBM WebSphere MQ 使用 Windows 群集。  
  
 有关容错和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)和[规划你的平台，用于容错](../core/planning-your-platform-for-fault-tolerance.md)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 为确保 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries 适配器能够与远程安装的 MQSAgent 组件进行通信，请确保在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和安装了 IBM WebSphere MQ 的服务器上已启用了网络 COM+ 访问。 有关启用网络 COM + 访问的详细信息，请参阅 Microsoft 知识库文章编号 817065，"如何启用 Windows Server 2003 中的网络 COM + 访问"在可用[http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580)。  
  
 没有无需群集 MQSAgent (MQSAgent2) COM + 应用程序，用于为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries 适配器。 为确保此组件的高可用性，请在每个群集节点安装该组件。 如果该 COM+ 应用程序停止运行，则下一次从客户端中进行调用时将启动该程序。  
  
## <a name="see-also"></a>另请参阅  
 [使用 MQSeries 适配器](../core/using-the-mqseries-adapter.md)