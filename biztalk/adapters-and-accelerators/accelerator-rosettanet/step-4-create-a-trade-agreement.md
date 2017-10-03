---
title: "步骤 4： 创建贸易协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, trade agreeements
- loopback tutorial, creating trade agreements
- agreements, creating
ms.assetid: 9bcb80b1-fefc-4f1c-ae03-fb736cdfd524
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b94acad2b71694223b0566f86edfcfa86610099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-a-trade-agreement"></a>步骤 4： 创建贸易协议
在此步骤中，将使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理控制台创建本组织与合作伙伴组织之间的贸易协议。  
  
### <a name="to-create-a-trade-agreement"></a>若要创建贸易协议  
  
1.  在 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开**BizTalk\<版本 > Accelerator for RosettaNet**，右键单击**协议**，单击**新**，然后单击**协议**。  
  
2.  在**新协议属性**对话框中，在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**贸易协议**。|  
    |**过程配置**|选择**STD_0C1_R01.02**从下拉列表。|  
    |**我的组织**|选择**主页**从下拉列表。|  
    |**伙伴组织**|选择**合作伙伴**从下拉列表。|  
    |**主角色**|选择**发起程序**从下拉列表。|  
  
3.  在**新协议属性**对话框中，在**端口**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**操作 URL**|类型**http://localhost/BTARNApp/RNIFReceive.aspx**。|  
    |**信号 URL**|类型**http://localhost/BTARNApp/RNIFReceive.aspx**。|  
    |**同步 URL**|留空。 同步合作伙伴接口流程 (PIP) 不需要同步 URL。|  
  
4.  单击**应用**，然后单击**确定**。  
  
 创建完贸易协议之后，你必须激活该协议。  
  
### <a name="to-activate-the-trade-agreement"></a>激活贸易协议  
  
-   在[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，单击**协议**，右键单击**贸易协议**在结果窗格中，然后单击**激活**.  
  
## <a name="see-also"></a>另请参阅  
 [步骤 5： 创建镜像协议](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)