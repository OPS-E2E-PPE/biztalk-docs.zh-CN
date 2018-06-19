---
title: 方案： 更新应用程序项目 |Microsoft 文档
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
ms.openlocfilehash: e95e6a66fb0e6bccc1fcc2fb4a7664538e50d3e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269533"
---
# <a name="scenario-updating-application-artifacts"></a>方案： 更新应用程序项目
存在以下两个在已部署到生产环境的应用程序中更新项目的基本情况：  
  
-   在某一业务流程处理长期事务或正在等待来自要求-响应端口的响应时，通过新版本更新该业务流程。  
  
-   在您并不关心消息处理是否完成时，例如使用新版本更新架构或映射，这是更一般性的更新情况。  
  
 在一般性的更新情况中，您可能在用新版本更新某一项目，例如为了满足业务要求变化。 此情况相对简单，并且您可以用更新后的项目覆盖原始项目。 涉及的步骤列表，请参阅[清单： 更新 BizTalk 应用程序中的项目](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)。  
  
 第二种情况更为复杂。 在此情况中，您必须允许现有业务流程完成对消息的处理。 同时，您必须避免现有业务流程处理任何新消息。 而是应该让业务流程的已更新版本进行处理。 为此，您将包含已更新业务流程的程序集部署到与原始版本相同的 BizTalk 应用程序中，然后同时运行这两个业务流程。 （新的程序集必须与包含原始业务流程的程序集具有不同版本，否则，您将不能将它部署到同一 BizTalk 组中。）然后，您将停止原始业务流程，以便没有新消息传送给该业务流程；再启动更新后的版本，以便将所有新消息都发送给它。 在原始版本完成其所有消息的处理后，您可以取消对它的部署。 有关执行这些任务的说明，请参阅[如何升级业务流程](../core/how-to-upgrade-an-orchestration.md)。  
  
 下图显示了典型的并行业务流程部署方案。  
  
 ![并排部署方案](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md)   
 [更新应用程序的重要注意事项](../core/important-considerations-for-updating-applications.md)