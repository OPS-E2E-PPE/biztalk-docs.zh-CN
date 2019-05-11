---
title: 大型分布式具有信息工作者服务的体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- architecture, large distributions
ms.assetid: 92f2d55c-3f51-42ca-99ef-60b23464691e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54bb036868202c153fef2405a6f26d977e823b40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328932"
---
# <a name="large-distributed-architecture-with-information-worker-services"></a>具有信息工作者服务的大型分布式体系结构
有关如何设计 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 业务活动监视 (BAM) 为信息工作者提供了可见性的业务流程和与合作伙伴进行直接通信。 这提供了一组不同的保护这些服务的要求。 信息工作者有可能不在数据域和公司域中有帐户和所需访问服务接口域对某些 BizTalk Server 生成的数据的访问权限。  
  
 下图显示了包括 BAM 的分布式的 BizTalk Server 体系结构。  
  
 ![分布式体系结构](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")  
具有信息工作者服务的分布式的 BizTalk Server 体系结构  
  
 中所示的结构相比[大型分布式体系结构](../core/large-distributed-architecture.md)，信息工作者服务的分布式的结构包含了其他信息工作者服务，例如 BAM 门户。 信息工作者服务容器包括以下服务器和服务：  
  
-   BAM 门户服务器。 业务最终用户使用 BAM 门户来访问 BAM 数据库，以便监视关键性能指标 (Kpi) 测量进度的业务目标，以及有关其业务流程的其他信息。 此服务器还具有 BAM 查询 Web 服务和 BAM 管理 Web 服务。  
  
-   用于 BAM 的 SQL Server: BAM 主导入数据库、 BAM 存档数据库、 BAM 星型架构数据库和 BAM 分析数据库。  
  
## <a name="see-also"></a>请参阅  
 [大型分布式体系结构](../core/large-distributed-architecture.md)   
 [缩减的具有信息工作者服务的体系结构](../core/scaled-down-architecture-with-information-worker-services.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)