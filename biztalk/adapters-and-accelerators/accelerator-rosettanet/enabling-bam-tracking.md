---
title: 启用 BAM 跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM tracking, enabling
- BAM tracking, disabling
ms.assetid: 3fee3315-fba7-4eea-89f3-6a061b450bb8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3098fa81b9fa88c884eb556a31481ac1ac57c51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283764"
---
# <a name="enabling-bam-tracking"></a>启用 BAM 跟踪
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 支持增强了使用 BizTalk 活动监视 (BAM) 跟踪。 BTARN 配置的全局属性的一部分启用跟踪。 启用跟踪后[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]跟踪所有协议的所有消息。 默认情况下，启用跟踪。  
  
 有关跟踪的详细信息，请参阅[增强跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)。  
  
### <a name="to-enable-or-disable-bam-tracking"></a>若要启用或禁用 BAM 跟踪  
  
1. 单击**启动**，依次指向**程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2. 右键单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]节点在作用域窗格中，然后单击**属性**。  
  
3. 在中**全局属性**对话框中，选择**启用 BAM 跟踪**启用跟踪，或清除此选项以禁用它。  
  
> [!IMPORTANT]
>  每当你更改了启用标志启用或禁用跟踪，您必须重新启动公用流程和 HTTP 适配器运行在其的所有服务。 这包括主机服务和独立主机服务。  
  
## <a name="see-also"></a>请参阅  
 [管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md)   
 [增强的跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)   
 [管理 BTARN 配置](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)