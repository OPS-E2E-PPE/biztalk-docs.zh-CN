---
title: "步骤 3： 创建 Contoso 0 C 2 贸易合作伙伴协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- agreements, creating
- creating, agreements
- double action tutorial, creating agreements
ms.assetid: b4267faa-5f10-4294-9890-169f1d5ad8f7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac1279232849620c7ca35be5e95ccf1fe6d08c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-creating-the-contoso-0c2-trading-partner-agreement"></a>步骤 3： 创建 Contoso 0 C 2 贸易合作伙伴协议
在此步骤中，将使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理控制台创建 Contoso 和 Fabrikam 之间的贸易合作伙伴协议， 并为 0C2 合作伙伴接口流程 (PIP) 创建新的贸易合作伙伴协议。  
  
### <a name="to-start-the-btarn-management-console"></a>启动 BTARN 管理控制台  
  
-   单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。  
  
### <a name="to-create-the-0c2-trading-partner-agreement"></a>创建 0C2 贸易合作伙伴协议  
  
1.  在 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**协议**，单击**新建**，然后单击**协议**.  
  
2.  在新的协议属性对话框中，在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**Fabrikam_To_Contoso_0C2**。|  
    |**过程配置**|选择**STD_0C2_R01.02**从下拉列表。|  
    |**我的组织**|选择**Contoso**从下拉列表。|  
    |**伙伴组织**|选择**Fabrikam**从下拉列表。|  
    |**RNIF 版本**|选择**V02.00.01**从下拉列表。|  
    |**主角色**|选择**响应方 （响应方）**从下拉列表。|  
    |**用法**|选择**测试**从下拉列表。|  
  
3.  单击**端口**选项卡，然后执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**操作 URL**|类型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
    |**信号 URL**|类型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
    |**同步 URL**|类型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
  
4.  单击 **“确定”**。  
  
5.  右键单击**Fabrikam_To_Contoso_0C2**协议，，然后单击**激活**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4：创建 Contoso 0C4 贸易合作伙伴协议](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-contoso-0c4-trading-partner-agreement.md)