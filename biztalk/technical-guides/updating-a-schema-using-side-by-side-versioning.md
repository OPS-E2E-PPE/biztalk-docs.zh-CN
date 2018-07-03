---
title: 更新架构使用的并行版本控制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7360ec5-b5e9-40c7-9a7c-965fcc95ddb0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed0d9d3a204641ac4bccb856e62be15cc2589786
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976406"
---
# <a name="updating-a-schema-using-side-by-side-versioning"></a>更新使用的并行版本控制架构
您还可以使用架构的并行版本控制。 您执行此操作通过向程序集添加新架构版本，同时保持现有架构 （和其版本） 升级的架构版本保持不变。  
  
 如果递增的架构版本，则必须更新架构以了解任何管道实例和管道组件使用它的引用。 以及任何依赖于架构的业务流程，则还必须更新引用架构 （或创建新映射） 的映射。  
  
 如果取消部署架构的以前版本的架构，如果可用，将处于活动状态。  
  
## <a name="schema-resolution-in-pipelines"></a>在管道中的架构解析  
 如果您向应用程序中添加 BizTalk 组中包括的新架构具有与现有架构相同的消息类型的程序集，管道中发生架构解析时将使用具有最新的版本号的架构。 如果一种消息类型所引用的多个.NET 类型，此二义性可能会导致管道执行失败。 原因在于架构查找使用的是消息类型、目标命名空间和实例的根名称。 此类故障可能具有相同的消息类型作为新的架构中使用的架构的任何应用程序中的管道。 有关架构解析的详细信息，请参阅[管道组件中的架构解析](http://go.microsoft.com/fwlink/?LinkID=154207)(<http://go.microsoft.com/fwlink/?LinkID=154207>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 添加与较旧版本并行的架构的新版本后，XML 拆装器的架构解析行为可能需要其他更改。 在某些情况下，你可能想对特定版本的架构在管道设计器中的管道拆装器属性的硬编码引用。 这使您可以避免 XML 拆装器确定要使用的消息类型动态加载的架构在运行时发现从消息 XML 内容的动态解析行为。  
  
## <a name="updating-a-schema-in-an-orchestration"></a>正在更新业务流程中的架构  
 时更改架构与多个发送和接收形状在业务流程中，可以进行更改更容易通过关联与每次发送的消息将消息类型属性设置或接收形状为多部分消息类型，而不是架构。 然后，可以设置每个形状以将相同的架构与相关联的消息部分的类型属性。 通过这样一来，你随后可以更改的类型属性的每个消息部分，而无需更改每个形状的消息类型通过更改架构。 有关此过程轻松更改的详细信息，请参阅[的更好地 BizTalk 编程 8 提示和技巧](http://go.microsoft.com/fwlink/?LinkId=101594)白皮书 (http://go.microsoft.com/fwlink/?LinkId=101594)。  
  
## <a name="versioning-schemas"></a>对架构的版本控制  
 BizTalk Server 将从包含它的程序集的最新版本的架构。 这意味着，如果创建新架构版本，新版本完全替换所有以前版本的架构。 此操作在事务寿命很短时能够正常工作。 但是，业务流程管理解决方案中的事务寿命很长：订单可能需要一年时间才能完成。  
  
 为了允许使用正在使用的架构的多个版本，解决方案中的每个架构在其命名空间中都包括版本号。 BizTalk 管道确定根据目标命名空间加上在架构中定义的根节点名称的消息类型。 例如，订单架构的命名空间如下所示：  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 命名空间标识架构和版本号使包含唯一的架构的命名空间，因为新的架构将是不同于较旧版本。 因此，无需取代旧架构就可以使用新架构。  
  
 更改架构版本可以影响你的解决方案中的不同部分，因此这应提前规划。 架构版本更改的效果的详细信息，请参阅[管道组件中的架构解析](http://go.microsoft.com/fwlink/?LinkID=154207)(<http://go.microsoft.com/fwlink/?LinkID=154207>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 更改时在业务流程中的架构版本，请使用多部分消息类型。 执行此操作将导致更大的灵活性时架构版本控制。 使用多部分消息类型的优势的详细信息，请参阅提示 #1，"始终使用多部分消息类型"中的 MSDN 杂志 》 文章[提高 BizTalk 编程的 8 提示和技巧](http://go.microsoft.com/fwlink/?LinkId=101594)(http://go.microsoft.com/fwlink/?LinkId=101594)。  
  
## <a name="see-also"></a>请参阅  
 [更新应用程序的最佳做法](../technical-guides/best-practices-for-updating-applications.md)