---
title: 绑定和启动 FRR 业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, binding orchestrations
- FRR, starting orchestrations
- bindings, orchestrations
- orchestrations, bindings
ms.assetid: b74a0116-e98b-4fec-b386-710ce421a1e2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81cf116fc03a8f2d898752a077e8347fd395a4a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209053"
---
# <a name="binding-and-starting-the-frr-orchestration"></a>绑定和启动 FRR 业务流程
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]包括 FRR 业务流程为已部署的程序集 ([!INCLUDE[btsCoName](../../includes/btsconame-md.md)]。Solutions.FinancialServices.SWIFT.FrrOrchestration)。 你需要启动此业务流程。  
  
 **摘要**  
  
 若要启动 FRR 业务流程，请执行以下操作：  
  
-   通过设置到 BizTalkServerApplication 主机绑定 FrrOrchestration.FrrMain 业务流程。  
  
-   启动 FrrOrchestration.FrrMain 业务流程。  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a>若要将绑定和启动 FRR 业务流程  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，，然后**BizTalk应用程序 1**。 单击**业务流程**。  
  
2.  在业务流程窗格中，右键单击**FrrOrchestration.FrrMain**业务流程，，然后单击**属性**。  
  
3.  在业务流程属性对话框中，单击**绑定**的左窗格中。 有关**主机**，选择**BizTalkServerApplication**。 单击**应用**，然后单击**确定**。  
  
4.  在业务流程窗格中，右键单击**FrrMain**业务流程，，然后单击**启动**。