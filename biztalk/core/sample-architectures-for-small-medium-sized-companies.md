---
title: 对于小型示例体系结构&amp;的中小型公司 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
ms.assetid: fc8c2fdd-bcb1-481c-b351-03092dd48540
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81bde6f78cad46e0c1346ec1ca705f44014d4cb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271070"
---
# <a name="sample-architectures-for-small-amp-medium-sized-companies"></a>对于小型示例体系结构&amp;中等规模的公司
本部分提供示例体系结构来部署 Microsoft BizTalk Server，如果想要帮助保护在小型或中型公司中的资产。 尽管这些结构鼓励实施深度防御和服务分隔来最小化攻击的影响，它们假定的硬件、 软件和通常也适用于大型公司的人力资源的数量。  
  
 但是，小型和中型公司 （或具有小型 BizTalk Server 部署的大型公司） 还应关注如何保护其环境。 我们了解了公司如何部署或计划部署后其[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，则我们将派生平衡可用资源与最大可能安全性的小型和中型公司的示例体系结构。 您应使用本部分中的信息来帮助你规划您自己的部署。 评估您的业务需求和资产后你可能决定在不同的体系结构上的 BizTalk Server 部署。  
  
 若要使其更轻松地查看您的体系结构的外观，本部分提供示例体系结构是基于各种可能在环境中使用的适配器。 下图显示您的拓扑的组件是独立于适配器的并在适配器上的哪些组件依赖您在 BizTalk Server 环境中使用。  
  
 我们还检查根据一些可以使用与 BizTalk Server 适配器的使用方案。 若要帮助您规划和设计您自己的体系结构，我们提供此示例结构的威胁模型分析。 此分析，您可以深入地了解可能会影响你的公司，具体取决于使用与你的合作伙伴进行通信的适配器的潜在安全问题。  
  
 虽然本部分提供信息以帮助您设计安全部署的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，以增加您还应该考虑确保环境中的服务器之间的通信的环境中的安全性。  
  
> [!IMPORTANT]
>  本部分假设不使用业务活动监视 (BAM)。 此功能需要额外的安全注意事项。 中对此进行讨论[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
> [!NOTE]
>  有关本文档中未说明的适配器的详细信息，请参阅 BizTalk Server 开发人员中心 ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420)。)  
  
## <a name="in-this-section"></a>本节内容  
  
-   [示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)  
  
-   [示例体系结构：HTTP 和 SOAP 适配器](../core/sample-architecture-http-and-soap-adapters.md)  
  
-   [示例体系结构：BizTalk 消息队列](../core/sample-architecture-biztalk-message-queuing.md)  
  
-   [示例体系结构：FTP Adapter](../core/sample-architecture-ftp-adapter.md)  
  
-   [示例体系结构：文件适配器](../core/sample-architecture-file-adapter.md)