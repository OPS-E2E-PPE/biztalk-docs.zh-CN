---
title: 对于小型示例体系结构&amp;中等规模的公司 |Microsoft 文档
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
ms.openlocfilehash: 0fa7911b7b2da942d559f2c85ad32e896c79d174
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269549"
---
# <a name="sample-architectures-for-small-amp-medium-sized-companies"></a>对于小型示例体系结构&amp;中等规模的公司
本部分介绍了部署 Microsoft BizTalk Server 以帮助保护中小型公司内的资产的示例结构。 尽管这些结构鼓励实施深度防御和服务分隔来最大限度地降低攻击的影响，但其假定的硬件、软件和人力资源的数量通常也适用于大型公司。  
  
 不过，中小型公司（或者具有小规模 BizTalk Server 部署的大型公司）还应关注如何保护其环境。 我们查看公司如何部署或计划部署后其[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，则我们将派生平衡与最大限度的安全性的可用资源的小型和中型公司的示例体系结构。 使用本部分中的信息将有助于您规划您自己的部署。 在评估您的业务需求和资产后，您也可能决定为 BizTalk Server 部署采用其他结构。  
  
 为了更方便地展示结构的外观，本部分根据您可能在环境中使用的各种适配器提供了不同的示例结构。 这些图中显示了拓扑结构的哪些组件与适配器无关，以及哪些组件需要依赖 BizTalk Server 环境中所使用的适配器。  
  
 我们还根据可与 BizTalk Server 一起使用的一些适配器来划分不同的使用方案。 为帮助您规划和设计自己的结构，我们对此示例结构进行了威胁模型分析。 通过此分析，您可以更深入地了解可能会影响您的公司的潜在安全问题。根据您与合作伙伴进行通信所用的适配器的不同，这些问题也会有所不同。  
  
 虽然本部分提供信息来帮助你设计的安全部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，来提高您还应考虑保护环境中的服务器之间的通信的环境中的安全性。  
  
> [!IMPORTANT]
>  本部分假定您没有使用业务活动监视 (BAM)。 使用该功能还需要遵循其他安全注意事项。 对此进行讨论[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
> [!NOTE]
>  有关在本文档中未涉及的适配器的详细信息，请参阅 BizTalk Server 开发人员中心 ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420)。)  
  
## <a name="in-this-section"></a>本节内容  
  
-   [示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)  
  
-   [示例体系结构： HTTP 和 SOAP 适配器](../core/sample-architecture-http-and-soap-adapters.md)  
  
-   [示例体系结构： BizTalk 消息队列](../core/sample-architecture-biztalk-message-queuing.md)  
  
-   [示例体系结构： FTP 适配器](../core/sample-architecture-ftp-adapter.md)  
  
-   [示例体系结构： 文件适配器](../core/sample-architecture-file-adapter.md)