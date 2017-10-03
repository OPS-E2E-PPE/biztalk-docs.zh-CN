---
title: "ESB 路线管理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f78240de-34da-4751-aceb-b69d81403124
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fb7c2566cbd445ea305089033935427b82046bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="esb-itinerary-management"></a>ESB 路线管理
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供有关 ESB 路线管理两个不同的选项： 集中式分散。 本部分讨论每个这些选项的好处和风险。  
  
## <a name="decentralized-esb-policy-management"></a>分散式的 ESB 策略管理  
 在此方案中，ESB 客户端应用程序提供内容的 ESB 路线到 ESB 作为每个已提交的邮件的附件中。 该消息包含具有路线的内容; 的 SOAP 标头当管道组件收到消息时，它对消息进行解码，然后它会将升级到进一步的路由的消息上下文路线。 尽管此设计提供机会来轻松地实现路由滑动模式，完全允许客户端可以控制的消息流提供以下挑战：  
  
-   通过允许客户端确定哪些进程应该应用到一条消息，可供选择的可用进程的详细信息是透明的 ESB 客户端应用程序。 这种做法可能无法公开从 ESB 路线到客户端的敏感信息。  
  
-   除了潜在的安全问题，从而使客户端管理的正在提交的每个邮件路线不强制实施 ESB 路线为策略除非它为特定的客户端实现。 因此，为强制路线的新版本的更改管理的费用的极高，会增加每个新的特定类型的受信任的客户端应用程序。  
  
-   通过允许客户端将与已提交的邮件整个路线，客户端应始终为位于受信任的子系统中;否则，ESB 路线可能无法指定将不再有效的恶意的处理指令。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]处理提交的客户端，则路线的支持但是，应仅使用此选项，以向后兼容并供用于测试用途。  
  
 有关启用客户端路线的详细信息，请参阅[使用管道组件读取一条路线](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)。  
  
## <a name="centralized-esb-policy-management"></a>集中式的 ESB 策略管理  
 有潜在的安全性和同步问题固有与允许客户端与路线附加，提交消息，因此，最佳做法是管理中的中央存储库作为 SQL 数据库实现，并包含在ESB路线[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]为此目的。 通过部署到一个中心位置路线，可以轻松地管理和修改而无需实现显著的客户端更改 ESB 路线策略和组织可以控制消息的处理，而无需公开可能向客户端的敏感信息。  
  
 专用的管道组件可用于确定适当的 ESB 路线，若要将附加到入站消息。 此方法提供了用于提交路线基于路由的消息的两个不同的选项：  
  
-   客户端应用程序使用的第一个选项，可以仍指示多不同的 ESB 路线通过提供的 SOAP 标头以及请求消息，而不是提交完成路线中的 ESB 路线引用信息。 此信息包括 ESB 路线名称和可选的版本。 在此方案中，客户端仍可以指定如何可以路由消息，但是不不存在任何策略同步错误或安全会危害的风险的公开 ESB 路线客户端应用程序的内容。  
  
-   第二个选项是配置 ESB 入口就能够自动确定适当的 ESB 路线，基于内容或上下文的消息，而无需提交的客户端中任何标头信息。 这种情况下，组织可以控制的已提交的邮件流和无需进行客户端需要注意的消息传送方式。