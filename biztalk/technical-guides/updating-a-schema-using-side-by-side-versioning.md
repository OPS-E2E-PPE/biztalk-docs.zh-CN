---
title: "更新使用的并行版本控制的架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7360ec5-b5e9-40c7-9a7c-965fcc95ddb0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3d63b93f665e80f88e2d9e81b2337e7b198b3df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="updating-a-schema-using-side-by-side-versioning"></a>更新使用的并行版本控制的架构
你可以执行的并行使用架构的版本控制。 你可以执行以便通过将新版本的架构添加到程序集，而使现有架构 （和其版本） 升级的架构版本不变。  
  
 如果你自动增加的架构版本，则必须更新对任何管道实例和使用它的管道组件的架构的引用。 以及任何依赖于架构的业务流程，则还必须更新引用的架构 （或创建新的图） 中的映射。  
  
 如果你取消部署架构，以前版本的架构，如果可用，将处于活动状态。  
  
## <a name="schema-resolution-in-pipelines"></a>管道中的架构解析  
 如果你添加到应用程序的程序集具有与现有架构相同的消息类型的新架构包括 BizTalk 组中，管道中发生的架构解析时将使用最新的版本号的架构。 如果多个.NET 类型引用的是一种消息类型，这种混乱情况可能会导致管道执行失败。 原因在于架构查找使用的是消息类型、目标命名空间和实例的根名称。 此类型故障可能会导致任何应用程序使用相同的消息类型作为新的架构的架构中的管道。 有关架构解析的详细信息，请参阅[管道组件中的架构解析](http://go.microsoft.com/fwlink/?LinkID=154207)(http://go.microsoft.com/fwlink/?LinkID=154207) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 添加新版本的并行较旧版本的架构后，XML 反汇编程序的架构解决行为可能需要其他更改。 在某些情况下，你可能想在管道设计器的管道反汇编程序属性中于特定版本的架构的硬编码引用。 这使您可以避免 XML 反汇编程序确定要使用的消息类型动态加载的架构发现在运行时从消息 XML 内容的动态解析行为。  
  
## <a name="updating-a-schema-in-an-orchestration"></a>更新业务流程中的架构  
 当你更改与多个发送关联的架构，并接收形状中业务流程时，在可以使更改更容易通过设置每次发送与关联的消息的消息类型属性，或接收形状上的与多部分消息类型，而不是架构。 然后，你可以设置与每个形状是相同的架构相关联的消息部分的类型属性。 通过这种方式，你可以随后更改架构，通过更改的类型属性的每个消息部分，而无需更改每个形状的消息类型。 有关此过程轻松更改的详细信息，请参阅[的更好 BizTalk 编程 8 提示和技巧](http://go.microsoft.com/fwlink/?LinkId=101594)白皮书 (http://go.microsoft.com/fwlink/?LinkId=101594)。  
  
## <a name="versioning-schemas"></a>对架构的版本控制  
 BizTalk Server 采用来自包含它的程序集的最新版本的架构。 这意味着，如果你创建新的架构版本，最新版本完全替换所有以前版本的架构。 此操作在事务寿命很短时能够正常工作。 但是，业务流程管理解决方案中的事务寿命很长：订单可能需要一年时间才能完成。  
  
 为了允许使用正在使用的架构的多个版本，解决方案中的每个架构在其命名空间中都包括版本号。 BizTalk 管道确定消息类型的基于目标命名空间的消息以及架构中定义的根节点名称。 例如，订单架构的命名空间如下所示：  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 由于命名空间标识的架构和的版本编号可以包含唯一的架构的命名空间，新架构将不同于较旧版本。 因此，无需取代旧架构就可以使用新架构。  
  
 因此应提前规划这，更改架构版本可能会影响你的解决方案中的不同部分。 有关的架构版本更改效果的详细信息，请参阅[管道组件中的架构解析](http://go.microsoft.com/fwlink/?LinkID=154207)(http://go.microsoft.com/fwlink/?LinkID=154207) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 更改业务流程中的架构的版本，当使用多部分消息类型。 这样将导致更大的灵活性时版本控制架构。 使用多部分消息类型的优势的详细信息，请参阅提示 #1，"始终使用多部分消息类型，"MSDN 杂志文章中[的更好的 BizTalk 编程 8 提示和技巧](http://go.microsoft.com/fwlink/?LinkId=101594)(http://go.microsoft.com/fwlink/？LinkId = 101594)。  
  
## <a name="see-also"></a>另请参阅  
 [更新应用程序的最佳做法](../technical-guides/best-practices-for-updating-applications.md)