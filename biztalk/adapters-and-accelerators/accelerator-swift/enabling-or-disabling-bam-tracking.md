---
title: "启用或禁用 BAM 跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, BAM tracking
- BAM tracking
ms.assetid: 07896fab-88a0-4759-8547-16edcd1eebc0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1132c41e9a017e42139d988d1588f79d7d3afaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-or-disabling-bam-tracking"></a>启用或禁用 BAM 跟踪
你可以启用或禁用 BAM 跟踪任何时候，即使在消息修复和新的传输进程的进程中的事务。 但是，如果你禁用 BAM 跟踪进程事务时，BAM 数据可能不完整的这些事务。 如果发生这种情况，历史记录表将仍然包含所有实例的准确的数据。  
  
 有关启用或禁用 BAM 跟踪 A4SWIFT 组件配置过程的一部分的信息，请参阅[设置 A4SWIFT 属性](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)。  
  
### <a name="to-enable-or-disable-bam-tracking"></a>若要启用或禁用 BAM 跟踪  
  
1.  在配置文件的 Web 客户端中，右键单击**BizTalk Accelerator for SWIFT**在控制台树中，然后单击**属性**。  
  
2.  在全局属性对话框中，禁用通过取消选择跟踪的 BAM**启用 BAM 跟踪**，或启用 BAM 跟踪通过选择它。  
  
3.  单击 **“确定”**。  
  
4.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，，然后**平台设置**。 单击**托管实例**。  
  
5.  在细节窗格中，右键单击主机实例，然后单击**重新启动**。  
  
## <a name="see-also"></a>另请参阅  
 [设置 A4SWIFT 属性](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)