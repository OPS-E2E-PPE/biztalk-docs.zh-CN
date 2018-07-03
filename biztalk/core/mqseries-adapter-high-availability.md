---
title: MQSeries 适配器的高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, MQSeries adapters
- MQSeries adapters, availability
- MQSeries adapters, performance
- high availability, MQSeries adapters
ms.assetid: 4339b10b-b35d-47c0-b78a-c60207e06c8e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 145577ce280595ff959596cff99fd08f334e8993
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008846"
---
# <a name="mqseries-adapter-high-availability"></a>MQSeries 适配器的高可用性
在使用适配器时，可通过以下方式提高其可用性：  
  
- 设置容错宿主环境[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- 对 IBM WebSphere MQ 使用 Windows 群集。  
  
  有关容错能力的信息和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)并[规划你平台容错](../core/planning-your-platform-for-fault-tolerance.md)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
  为确保 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries 适配器能够与远程安装的 MQSAgent 组件进行通信，请确保在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和安装了 IBM WebSphere MQ 的服务器上已启用了网络 COM+ 访问。 有关启用网络 COM + 访问的详细信息，请参阅 Microsoft 知识库文章编号为 817065 的"如何在 Windows Server 2003 中，启用网络 COM + 访问"网址[ http://go.microsoft.com/fwlink/?LinkId=196580 ](http://go.microsoft.com/fwlink/?LinkId=196580)。  
  
  没有不需要群集的 MQSAgent (MQSAgent2) COM + 应用程序与一起使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries 适配器。 为确保此组件的高可用性，请在每个群集节点安装该组件。 如果该 COM+ 应用程序停止运行，则下一次从客户端中进行调用时将启动该程序。  
  
## <a name="see-also"></a>请参阅  
 [使用 MQSeries 适配器](../core/using-the-mqseries-adapter.md)