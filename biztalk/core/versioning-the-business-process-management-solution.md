---
title: 版本控制业务流程管理解决方案 |Microsoft 文档
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
ms.openlocfilehash: af8afd3666a35b827ff25b243c1bfb4c81262273
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288645"
---
# <a name="versioning-the-business-process-management-solution"></a>版本控制业务流程管理解决方案
业务流程管理解决方案的设计使您可以根据需要替换阶段。 该设计还提供了架构版本控制的更简易方法。  
  
 有关将业务流程划分为阶段的信息，请参阅[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
> [!NOTE]
>  解决方案的元素高度依赖于消息结构。 更改消息结构将需要对业务流程进行大量更改。  
  
 有关更新中部署的解决方案和指引，用于编写脚本的程序集来处理更新的常规说明，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。  
  
## <a name="adding-replacing-or-removing-stages"></a>添加、替换或删除阶段  
 订单处理阶段业务流程包含两种类型的代码： 实现业务流程和提供的基础结构，以便它可以运行解决方案中的代码的代码。 在这两个阶段业务流程， **CableOrder1**和**CableOrder2**，业务进程代码组形状内部标记为"业务处理。"  
  
 创建新阶段最简单的方法是复制其中一个阶段，使用您的代码替换“业务处理”组中的代码，并保留基础结构代码不变。  
  
> [!NOTE]
>  **CableOrder2** orchestration 具有两个"业务处理"组，第二解决更新历史记录发送形状。 发送形状是有效发送作用域的组成部分。 (有关详细信息，请参阅"提高性能与嵌套作用域"中[OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)。)由于组形状不能与作用域形状的组成部分重叠，因此第二个组被标记，以指示它是业务流程代码的一部分。  
  
 必须按新业务流程在序列中的编号来设置其筛选器表达式。 **OrderManager**假定阶段数字开头和增加一个用于每个后续阶段 （1、 2、 3...）。 若要筛选第三个阶段，则应将筛选器表达式设置为：  
  
 `(Microsoft.Samples.BizTalk.SouthridgeVidoe.Schemas.Stage == 3)`  
  
 解决方案使用 BAM API 来跟踪解决方案中的事件，包括订单处理阶段。 第一个阶段将启动 BAM 活动；最后一个阶段则结束该活动。 如果有异常，则解决方案中的处理程序将结束所涉及的 BAM 活动。 BAM 将不连续的操作有效地重新组装成连续的视图，以便进行监视。  
  
## <a name="changing-configuration"></a>更改配置  
 如果所做更改增加或减少了阶段数，则必须更改存储在企业单一登录 (SSO) 密钥存储区中的配置信息。  
  
 如果你尚未部署应用程序，则可以修改的配置设置**TotalStages** CreateSouthridgeVideoApplication.cmd 脚本文件中。 在部署期间运行该脚本时，该值将发生更改。  
  
 如果已经部署应用程序，则可以通过运行命令行实用工具 BTSScnSSOApplicationConfig（位于 SDK\Common\SsoApplicationConfig 文件夹中）来更改值。 若要将阶段的总数设置为三，请使用以下命令行：  
  
 `BTSScnSSOApplicationConfig -set SouthRidgeVideo.CableOrder ConfigProperties TotalStages 3`  
  
 由于解决方案会缓存配置值，因此必须等到刷新间隔过后，新值才能生效。  
  
## <a name="versioning-schemas"></a>对架构的版本控制  
 BizTalk 从包含它的最新版本的程序集中获取架构。 这意味着，如果创建新版本的架构，则它会完全替换所有以前版本的架构。 此操作在事务寿命很短时能够正常工作。 但是，业务流程管理解决方案中的事务寿命很长：订单可能需要一年时间才能完成。  
  
 为了允许使用正在使用的架构的多个版本，解决方案中的每个架构在其命名空间中都包括版本号。 例如，订单架构的命名空间如下所示：  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 由于命名空间标识架构，并且通过包括版本号使命名空间对于架构来说是唯一的，新的架构有别于旧版本。 因此，无需取代旧架构就可以使用新架构。  
  
## <a name="see-also"></a>另请参阅  
 [开发一个业务流程管理解决方案](../core/developing-a-business-process-management-solution.md)