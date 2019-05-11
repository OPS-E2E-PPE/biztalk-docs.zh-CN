---
title: 设置 CIDX eStandards 消息交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, configuring message exchange
ms.assetid: 90468459-cef7-436b-8c0b-3a7455a091c3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6f1045e3a9562821c64e74df300ccbf9ab279d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281727"
---
# <a name="setting-up-cidx-estandards-message-exchange"></a>设置 CIDX eStandards 消息交换
本主题介绍如何设置化工数据交换 (CIDX) eStandards 消息交换。 CIDX 需要设置以下三个属性：  
  
- `Standard` 为流程配置设置中的属性**CIDX**  
  
- `Is Single Action` 为流程配置设置中的属性 `True`  
  
- `0A1 agreement` 在贸易合作伙伴协议中为属性**非 0A1**  
  
  有关 CIDX 与 RosettaNet 之间的差异的信息，请参阅[CIDX 支持](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)。  
  
### <a name="to-set-up-cidx-message-exchange"></a>若要设置 CIDX 消息交换  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2. 在中[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]。  
  
3. 右键单击**流程配置设置**，依次指向**新建**，然后单击**过程配置**。  
  
4. 在新流程配置属性对话框中，在**常规**选项卡上，对于**标准**属性中，选择**CIDX**。  
  
5. 上**活动**选项卡上，对于**是否为单一操作**属性中，选择**True**。  
  
6. 根据需要请输入其他流程配置设置。 有关这些设置的信息，请参阅中的表[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。  
  
7. 单击“确定” 。  
  
8. 右键单击**协议**，依次指向**新建**，然后单击**协议**。  
  
9. 上**常规**，**端口**，**协议**，以及**自定义属性**选项卡上，输入的各种设置的值。 有关这些设置的信息，请参阅中的表[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。  
  
10. 在新协议属性对话框中，在**常规**选项卡上，对于**0A1 协议**属性中，选择**非 0A1**。  
  
11. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)   
 [创建或编辑本组织](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)