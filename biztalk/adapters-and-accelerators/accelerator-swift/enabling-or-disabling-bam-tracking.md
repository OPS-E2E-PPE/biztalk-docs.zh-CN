---
title: 启用或禁用 BAM 跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, BAM tracking
- BAM tracking
ms.assetid: 07896fab-88a0-4759-8547-16edcd1eebc0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f44f8d6add5eed56182a68b881e4019e2ca214a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377982"
---
# <a name="enabling-or-disabling-bam-tracking"></a>启用或禁用 BAM 跟踪
您可以启用或禁用 BAM 跟踪在任何时候，即使在消息修复和新的传输过程具有正在处理的事务。 但是，如果您禁用 BAM 跟踪过程中执行事务时，BAM 数据可能不完整的这些事务。 如果发生这种情况，历史记录表仍将包含所有实例的准确的数据。  
  
 有关启用或禁用 BAM 跟踪 A4SWIFT 组件配置过程的一部分的信息，请参阅[设置 A4SWIFT 属性](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)。  
  
### <a name="to-enable-or-disable-bam-tracking"></a>若要启用或禁用 BAM 跟踪  
  
1.  在配置文件 Web 客户端中，右键单击**BizTalk Accelerator for SWIFT**在控制台树中，然后单击**属性**。  
  
2.  在全局属性对话框中，禁用 BAM 跟踪通过取消选中**启用 BAM 跟踪**，或启用 BAM 跟踪通过选择它。  
  
3.  单击“确定” 。  
  
4.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，然后**平台设置**。 单击**托管实例**。  
  
5.  在详细信息窗格中，右键单击该主机实例，然后依次**重新启动**。  
  
## <a name="see-also"></a>请参阅  
 [设置 A4SWIFT 属性](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)