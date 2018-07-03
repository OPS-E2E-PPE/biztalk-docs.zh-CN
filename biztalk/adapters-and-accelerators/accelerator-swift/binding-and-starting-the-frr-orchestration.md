---
title: 绑定和启动 FRR 业务流程 |Microsoft Docs
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
ms.openlocfilehash: b01386cedbd25148e5ea0ce2ac44fb56e9fe3d03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987438"
---
# <a name="binding-and-starting-the-frr-orchestration"></a>绑定和启动 FRR 业务流程
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 包括 FRR 业务流程，作为部署的程序集 (Microsoft。Solutions.FinancialServices.SWIFT.FrrOrchestration)。 您需要启动此业务流程。  
  
 **摘要**  
  
 若要启动 FRR 业务流程，请执行以下操作：  
  
-   通过设置到 BizTalkServerApplication 主机绑定 FrrOrchestration.FrrMain 业务流程。  
  
-   启动 FrrOrchestration.FrrMain 业务流程。  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a>绑定和启动 FRR 业务流程  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，然后**BizTalk应用程序 1**。 单击**业务流程**。  
  
2.  在业务流程窗格中，右键单击**FrrOrchestration.FrrMain**业务流程，并单击**属性**。  
  
3.  在业务流程属性对话框中，单击**绑定**的左窗格中。 有关**主机**，选择**BizTalkServerApplication**。 单击**Apply**，然后单击**确定**。  
  
4.  在业务流程窗格中，右键单击**FrrMain**业务流程，并单击**启动**。