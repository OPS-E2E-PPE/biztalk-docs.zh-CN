---
title: 缩减的具有信息工作者服务的体系结构 |Microsoft Docs
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
ms.assetid: ce1217bf-84a5-4888-89ba-dce85dc38340
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44c31f9fa9683d8a3a7210d324f605cb1689981c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309346"
---
# <a name="scaled-down-architecture-with-information-worker-services"></a>缩减的具有信息工作者服务的体系结构
有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 下图提供了一个示例 BizTalk Server 体系结构包括信息工作者服务，它将合并一些域与 BizTalk Server，以减少服务器和防火墙所需的数量。 此体系结构，尽管不是最分布式仍将根据其函数 BizTalk Server。  
  
 ![Scaledown Topology](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")  
  
        Scaled Down Architecture with Information Worker Services  
  
 在上图中，服务接口域和服务域中的服务器对应于 BizTalk 主机而不是物理服务器。 尽管建议在独立的计算机保持在主密钥服务器和管理工具，可具有实例的跟踪、 处理、 发送和接收多台计算机上运行的主机。 同样，外围网络中的服务器与逻辑位置相对应。  
  
 外围网络中的 SMTP、 Windows 消息队列 (也称为 MSMQ)、 文件和 SQL 服务器对应于邮件服务器、 队列、 目录或 SQL Server 分别从其 BizTalk 接收和发送主机服务接口域中接收和发送消息。  
  
 数据域中的 BAM 数据库是 BAM 主导入、 BAM 分析、 BAM 星型架构和 BAM 存档数据库。 数据域中的跟踪和分析数据库是 BizTalk Server 用于存储跟踪信息。  
  
## <a name="see-also"></a>请参阅  
 [缩减的体系结构](../core/scaled-down-architecture.md)   
 [具有信息工作者服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [设计安全的体系结构](../core/designing-a-secure-architecture.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)