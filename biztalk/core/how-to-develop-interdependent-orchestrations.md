---
title: 如何开发相互依赖的业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5464096e-66d8-48de-bc02-c754c5cfbada
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f069b6017ef5d740e3c6cb24b3e7877deef924c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385228"
---
# <a name="how-to-develop-interdependent-orchestrations"></a>如何开发相互依赖的业务流程
可以使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]开发一组具有相互依赖的 Web 服务的业务流程。 当有引用数据类型和/或从其调用它们的业务流程中的端口的业务流程时，会发生此情况。 这种情况下的示例是具有以下特征：  
  
- 有两个或多个业务流程。  
  
- 第一个业务流程 (Orch1) 使用一个单向 Web 服务调用调用第二个业务流程 (Orch2)。  
  
- Orch2 响应回 Orch1 的 Web 服务调用。  
  
  此类型的项目的一个示例，请参阅[教程 2:采购订单处理](http://msdn.microsoft.com/library/a324ef1b-39b3-49ab-9719-a13f526cb467)。  
  
### <a name="to-develop-two-interdependent-orchestrations-orch1-and-orch2"></a>若要开发 Orch1 和 Orch2 的两个相互依赖业务流程  
  
1. 使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建具有将作为 Web 服务公开的接收端口 Orch1 的部分版本。  
  
2. 编译 Orch1。  
  
3. 运行 Web Services 发布向导并发布端口。  
  
4. 使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、 创建和完成所有 Orch2，使用 Orch1 的 web 服务。  
  
5. 编译 Orch2。  
  
6. 运行 Web Services 发布向导并发布端口。  
  
7. 完成 Orch1，使用 Orch2 的 web 服务根据需要。  
  
8. 重新编译 Orch1。  
  
9. 部署 Orch1 和 Orch2。  
  
## <a name="see-also"></a>请参阅  
 [如何使用 BizTalk Web Services 发布向导业务流程发布为 Web 服务](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)