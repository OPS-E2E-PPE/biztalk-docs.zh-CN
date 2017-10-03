---
title: "设置向上 CIDX eStandards 消息交换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: CIDX, configuring message exchange
ms.assetid: 90468459-cef7-436b-8c0b-3a7455a091c3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c4606dfc4b912d884a997bb65acb26cb4352448
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-up-cidx-estandards-message-exchange"></a>设置向上 CIDX eStandards 消息交换
本主题介绍如何设置筛选数据交换 (CIDX) eStandards 消息交换。 CIDX 需要设置以下三个属性：  
  
-   `Standard`中的过程配置设置应用到属性**CIDX**  
  
-   流程配置设置中设置为 `True` 的 `Is Single Action` 属性  
  
-   `0A1 agreement`属性在贸易合作伙伴协议到**非 0A1**  
  
 有关 CIDX 和 RosettaNet 之间的差异的信息，请参阅[CIDX 支持](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)。  
  
### <a name="to-set-up-cidx-message-exchange"></a>若要设置 CIDX 消息交换  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2.  在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台中，展开 [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]。  
  
3.  右键单击**过程配置设置**，指向**新建**，然后单击**过程配置**。  
  
4.  在新进程配置属性对话框中，在**常规**选项卡上，为**标准**属性中，选择**CIDX**。  
  
5.  上**活动**选项卡上，为**是否为单一操作**属性中，选择**True**。  
  
6.  根据需要请输入其他过程配置设置。 有关这些设置的信息，请参阅中的表[如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。  
  
7.  单击 **“确定”**。  
  
8.  右键单击**协议**，指向**新建**，然后单击**协议**。  
  
9. 上**常规**，**端口**，**协议**，和**自定义属性**选项卡上，输入的各种设置的值。 有关这些设置的信息，请参阅中的表[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。  
  
10. 在新的协议属性对话框中，在**常规**选项卡上，为**0A1 协议**属性中，选择**非 0A1**。  
  
11. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)   
 [创建或编辑主组织](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)