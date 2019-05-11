---
title: 缩减的体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: e25798aa-4a1e-418c-9e0c-db964e8b5a80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 770276aceab5c0de64615f457c20d6d1945a63b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399972"
---
# <a name="scaled-down-architecture"></a>缩减的体系结构
有关完整信息的系统体系结构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 下图提供了一个示例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构，可以组合某些域与 BizTalk Server，以减少服务器数量和你的防火墙需要。 此体系结构，尽管不是最分布式仍将根据其函数 BizTalk Server。  
  
 ![缩减的体系结构](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")  
  
        Scaled Down Architecture  
  
 在上图中，服务接口域和服务域中的服务器对应于 BizTalk 主机而不是物理服务器。 尽管建议在独立的计算机保持在主密钥服务器和管理工具，可具有实例的跟踪、 处理、 发送和接收多台计算机上运行的主机。 同样，外围网络中的服务器与逻辑位置相对应。  
  
 外围网络中的 SMTP、 消息队列、 文件和 SQL 服务器对应于邮件服务器、 队列、 目录或 SQL Server 分别从其 BizTalk 接收和发送主机的处理和服务域中接收和发送消息。  
  
## <a name="see-also"></a>请参阅  
 [缩减的具有信息工作者服务的体系结构](../core/scaled-down-architecture-with-information-worker-services.md)   
 [大型分布式体系结构](../core/large-distributed-architecture.md)   
 [设计安全的体系结构](../core/designing-a-secure-architecture.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)