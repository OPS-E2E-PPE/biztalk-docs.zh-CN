---
title: ESB 路线管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f78240de-34da-4751-aceb-b69d81403124
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f034c0892c7a6614bedbdd3754db1f7f3a0951d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306184"
---
# <a name="esb-itinerary-management"></a>ESB 路线管理
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] 提供两个不同选项，ESB 路线管理： 集中式的分散。 本部分讨论的每个选项的好处和风险。  
  
## <a name="decentralized-esb-policy-management"></a>分散式的 ESB 策略管理  
 在此方案中，ESB 的客户端应用程序提供内容的 ESB 路线，作为每个已提交的邮件的附件到 ESB。 该消息包含 SOAP 标头的路线的内容;管道组件接收消息时，它对消息进行解码，然后它将升级到消息上下文以进行进一步路由路线。 尽管此设计提供了机会来轻松实现传送名单模式，但完全允许客户端控制消息的流存在下列问题：  
  
- 通过允许客户端确定哪些进程应该应用到一条消息，可供选择的可用进程的详细信息是透明的 ESB 的客户端应用程序。 这种做法可能会公开给客户端从 ESB 路线的敏感信息。  
  
- 除了潜在的安全问题，从而允许客户端来管理与每个消息正在提交的路线不强制实施 ESB 路线为策略除非对于特定的客户端的实现。 因此，以强制实施路线的新版本的更改管理的成本极高，会增加每个新的特定类型的受信任的客户端应用程序。  
  
- 通过允许客户端传递整个路线并提交消息，客户端应始终为位于受信任的子系统中;否则，ESB 路线可能无法指定将不再有效的恶意的处理指令。  
  
  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] 支持处理客户端; 提交的路线但是，此选项应仅用于向后兼容性和测试目的。  
  
  有关启用客户端的路线的详细信息，请参阅[使用管道组件读取路线](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)。  
  
## <a name="centralized-esb-policy-management"></a>集中式的 ESB 策略管理  
 有一些潜在的安全性和同步问题固有与允许客户端以使用路线附加，提交消息，因此，最佳做法是管理 ESB 路线中的中央存储库作为 SQL 数据库实现，并且包含在[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]实现此目的。 通过部署到一个中心位置的路线，可以轻松地管理和修改而无需实现显著的客户端的更改，ESB 路线策略和组织可以控制消息的处理，而无需公开可能向客户端的敏感信息。  
  
 专用的管道组件可用于确定适当的 ESB 路线，以便将附加到入站消息。 此方法可用于提交基于路线的路由的消息的两个不同选项：  
  
-   使用第一个选项，客户端应用程序仍可指示非重复的 ESB 路线通过提供 SOAP 标头以及请求消息，而不是提交完整路线中的 ESB 路线的参考信息。 此信息包括 ESB 路线名称和可选版本。 在此方案中，客户端仍可以指定如何可以将消息路由，但通过公开 ESB 路线客户端应用程序的内容不存在的策略同步错误或安全遭到破坏的风险。  
  
-   第二个选项是配置了 ESB 的途径，以自动确定适当的 ESB 路线，根据内容或上下文的消息，而无需从提交客户端的任何标头信息。 这种情况下，组织可以控制的已提交的邮件流，并且不需要客户端需要注意的如何路由消息。