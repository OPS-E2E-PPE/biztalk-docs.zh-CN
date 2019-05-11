---
title: 版本控制业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, process management solutions
- process management solution tutorial, modifying
- process management solution tutorial, versioning
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 501b2162-821f-44e1-87c0-8628cc5bd9c3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f3b030ed67745e37b9808d888a5f0df07e57bba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393748"
---
# <a name="versioning-the-business-process-management-solution"></a>版本控制业务流程管理解决方案
设计业务流程管理解决方案是使您可以根据需要替换阶段。 设计还提供了更简单的方法的架构版本控制。  
  
 有关将业务流程划分成阶段的信息，请参阅[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
> [!NOTE]
>  该解决方案中的元素都高度依赖于消息结构。 更改消息结构需要向业务流程的重大更改。  
  
 有关更新已部署的解决方案和编写脚本的指南中的程序集来处理更新的常规说明，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。  
  
## <a name="adding-replacing-or-removing-stages"></a>添加、 替换或删除阶段  
 订单处理阶段业务流程包含两种类型的代码： 代码实现的业务流程和提供的基础结构，以便它可以在解决方案中进行操作的代码。 在这两个阶段业务流程**CableOrder1**并**CableOrder2**，业务流程代码组形状内标记为"业务处理"。  
  
 若要创建新的阶段的最简单方法是复制其中一个阶段，在"业务处理"组中的代码替换为你的代码，并保留基础结构代码保持不变。  
  
> [!NOTE]
>  **CableOrder2**业务流程具有两个"业务处理"组，第二个围绕更新历史发送形状。 发送形状是有效发送作用域的一部分。 (详细信息，请参阅"使用嵌套作用域提高性能"中[在 OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)。)组形状不能重叠作用域形状的一部分，因为第二个组被标记，以指示它是业务流程代码的一部分。  
  
 必须为它的数字序列中新的业务流程上设置筛选器表达式。 **OrderManager**假定阶段编号一开始，并增加另一个用于每个后续阶段 （1、 2、 3...）。 若要筛选的第三个阶段，将设置为以下筛选器表达式：  
  
 `(Microsoft.Samples.BizTalk.SouthridgeVidoe.Schemas.Stage == 3)`  
  
 该解决方案使用 BAM API 来跟踪解决方案，包括订单处理阶段中的事件。 第一个阶段将启动 BAM 活动中;最后一个阶段则结束。 如果那里异常，该解决方案中的处理程序结束所涉及的 BAM 活动。 BAM 有效地重新组装成连续的视图用于监视不连续的操作。  
  
## <a name="changing-configuration"></a>更改配置  
 如果所做的更改增加或减少阶段数，则必须更改存储在企业单一登录 (SSO) 密钥存储区中的配置信息。  
  
 如果尚未部署应用程序，则可以修改的配置设置**TotalStages** CreateSouthridgeVideoApplication.cmd 脚本文件中。 在部署期间运行该脚本时，会更改值。  
  
 如果你已部署应用程序，您可以通过在位于 SDK\Common\SsoApplicationConfig 文件夹中运行命令行实用工具 BTSScnSSOApplicationConfig，更改值。 若要设置为三个阶段的总数目，将使用以下命令行：  
  
 `BTSScnSSOApplicationConfig -set SouthRidgeVideo.CableOrder ConfigProperties TotalStages 3`  
  
 由于解决方案会缓存配置值，你必须等待，直到刷新间隔过后才会生效的新值。  
  
## <a name="versioning-schemas"></a>架构版本控制  
 BizTalk 需要来自包含它的程序集的最新版本的架构。 这意味着，如果创建新架构版本完全替换所有以前版本的架构。 这适用于事务的生存期较短。 但是，业务流程管理解决方案中的事务寿命很长： 订单可能需要一年时间才能完成。  
  
 若要允许使用正在使用的架构的多个版本的可能性，解决方案中的每个架构包括其命名空间中的版本号。 例如，订单架构的命名空间是按如下所示：  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 命名空间标识架构和版本号使包含唯一的架构的命名空间，因为新的架构将是不同于较旧版本。 因此，新的架构可以使用而无需取代旧架构。  
  
## <a name="see-also"></a>请参阅  
 [开发业务流程管理解决方案](../core/developing-a-business-process-management-solution.md)