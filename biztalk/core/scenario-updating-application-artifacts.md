---
title: 方案：更新应用程序项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, artifacts
- updating, artifacts
- artifacts, examples
- updating, examples
- examples, updating
- artifacts, updating
ms.assetid: 76833df3-2330-48af-84d8-731028b192ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c144fcafd0800f5ac41fe1b0572f60ac895ff536
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308107"
---
# <a name="scenario-updating-application-artifacts"></a>方案：更新应用程序项目
有更新的应用程序部署到生产环境中项目的两种基本方案：  
  
- 当业务流程处理长期事务或正在等待来自要求-响应端口的响应时使用新版本更新业务流程。  
  
- 更多常规更新的情况下，当您不关心完成消息处理，如更新架构或映射使用新版本。  
  
  在一般性的更新情况下，你可能正在更新项目使用新版本，例如为了满足业务要求的更改。 相对简单，这种情况下，您可以用更新后项目覆盖原始项目。 有关所涉及的步骤的列表，请参阅[核对清单：更新 BizTalk 应用程序中的项目](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)。  
  
  第二个方案是更复杂。 在这种情况下，必须允许现有业务流程完成处理消息。 在同一时间，则必须防止现有的业务流程处理任何新消息。 相反，您希望的更新的版本的业务流程进行处理。 若要实现此目的，您部署包含到与原始版本相同的 BizTalk 应用程序已更新的业务流程的程序集，然后同时运行这两个业务流程。 （新的程序集必须具有不同的版本号比包含原始业务流程的程序集或你将无法再将它部署到同一个 BizTalk 组。）然后，停止原始业务流程，以便没有新消息路由到它，并启动更新的版本中，以便所有新消息发送给它。 原始版本完成其所有消息的处理后，你可以然后取消部署它。 有关执行这些任务的说明，请参阅[如何升级业务流程](../core/how-to-upgrade-an-orchestration.md)。  
  
  下图显示了典型的并行业务流程部署。  
  
  ![并排部署方案](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md)   
 [更新应用程序的重要注意事项](../core/important-considerations-for-updating-applications.md)