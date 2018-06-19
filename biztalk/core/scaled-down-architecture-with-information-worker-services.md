---
title: 按比例缩小使用信息辅助服务的体系结构 |Microsoft 文档
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
ms.openlocfilehash: 0d02558e5904bf740c09ea0db614b2189555ac75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269245"
---
# <a name="scaled-down-architecture-with-information-worker-services"></a>具有信息工作者服务的精简规模结构
有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
 下图提供了包含信息工作者服务的 BizTalk Server 示例结构，该结构将一些域与 BizTalk Server 组合在一起以减少所需的服务器和防火墙的数量。 尽管此结构不具备最强的分布式性能，但它仍然按服务器功能来分隔不同的 BizTalk Server。  
  
 ![Scaledown 拓扑](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")  
  
        Scaled Down Architecture with Information Worker Services  
  
 在上图中，服务接口和服务域中的服务器与 BizTalk 主机而不是物理服务器相对应。 虽然建议您将主密钥服务器和管理工具置于独立的计算机中，但您仍会具有与多台计算机上运行的跟踪、处理、发送和接收主机相对应的实例。 同样，外围网络中的服务器与逻辑位置相对应。  
  
 外围网络中的 SMTP 服务器、Windows 消息队列（也称为 MSMQ）服务器、文件服务器和 SQL Server 分别与邮件服务器、队列、目录或 SQL Server 相对应，服务接口和服务域中的 BizTalk 接收主机与发送主机从这些逻辑位置接收和发送消息。  
  
 数据域中的 BAM 数据库包括 BAM 主导入数据库、BAM 分析数据库、BAM 星型架构数据库和 BAM 存档数据库。 数据域中的跟踪和分析数据库就是 BizTalk Server 用于存储跟踪信息的数据库。  
  
## <a name="see-also"></a>另请参阅  
 [按比例缩小体系结构](../core/scaled-down-architecture.md)   
 [使用信息辅助服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [设计安全的体系结构](../core/designing-a-secure-architecture.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)