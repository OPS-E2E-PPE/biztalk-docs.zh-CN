---
title: "如何开发相互依赖的业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5464096e-66d8-48de-bc02-c754c5cfbada
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93f8d086a60487e144b02c01a393eb6f10a63b40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-develop-interdependent-orchestrations"></a>如何开发相互依赖的业务流程
你可以使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]开发一套提供相互依赖 Web 服务的业务流程。 当必须引用数据类型和/或业务流程从中调用它们中的端口的业务流程时，会发生此情况。 这种方案的示例的特征如下：  
  
-   具有两个或多个业务流程。  
  
-   第一个业务流程 (Orch1) 使用单向 Web 服务调用调用第二个业务流程 (Orch2)。  
  
-   Orch2 响应回 Orch1 与 Web 服务调用。  
  
 有关此类型的项目的一个示例，请参阅[教程 2： 采购订单过程](http://msdn.microsoft.com/library/a324ef1b-39b3-49ab-9719-a13f526cb467)。  
  
### <a name="to-develop-two-interdependent-orchestrations-orch1-and-orch2"></a>若要开发 Orch1 和 Orch2 的两个相互依赖业务流程  
  
1.  使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建具有接收端口将作为 Web 服务公开 Orch1 的部分版本。  
  
2.  编译 Orch1。  
  
3.  运行 Web 服务发布向导并发布该端口。  
  
4.  使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、 创建和完成所有 Orch2，使用 Orch1 的 web 服务。  
  
5.  编译 Orch2。  
  
6.  运行 Web 服务发布向导并发布端口。  
  
7.  完成 Orch1，使用 Orch2 的 web 服务根据需要。  
  
8.  重新编译 Orch1。  
  
9. 部署 Orch1 和 Orch2。  
  
## <a name="see-also"></a>另请参阅  
 [如何使用发布向导的 BizTalk Web 服务发布作为 Web 服务业务流程](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)