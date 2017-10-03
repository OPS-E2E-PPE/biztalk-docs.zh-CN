---
title: "步骤 6： 创建 Contoso 3A4 贸易合作伙伴协议 |Microsoft 文档"
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
ms.assetid: a20e40d8-7e3b-4930-8921-056ffddd08ea
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e2a5513d9df725ca1f67cec728dffad552047f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-creating-the-contoso-3a4-trading-partner-agreement"></a>步骤 6： 创建 Contoso 3A4 贸易合作伙伴协议
在此步骤中，将使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理控制台创建 Contoso 和 Fabrikam 之间的贸易合作伙伴协议， 并为 3A4 合作伙伴接口流程 (PIP) 创建新的贸易合作伙伴协议。  
  
### <a name="to-start-the-btarn-management-console"></a>启动 BTARN 管理控制台  
  
-   单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本 > Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。  
  
### <a name="to-create-the-3a4-trading-partner-agreement"></a>创建 3A4 贸易合作伙伴协议  
  
1.  在 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**协议**，指向**新建**，然后单击**协议**.  
  
2.  在新的协议属性对话框中，在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**Fabrikam_To_Contoso_3A4**。|  
    |**过程配置**|选择**STD_3A4_V02.02**从下拉列表。|  
    |**我的组织**|选择**Contoso**从下拉列表。|  
    |**伙伴组织**|选择**Fabrikam**从下拉列表。|  
    |**RNIF 版本**|选择**V02.00.01**从下拉列表。|  
    |**主角色**|选择**Seller （响应方）**从下拉列表。|  
    |**用法**|选择**测试**从下拉列表。|  
  
3.  上**端口**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**操作 URL**|类型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
    |**信号 URL**|类型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
    |**同步 URL**|类型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
  
4.  单击 **“确定”**。  
  
5.  右键单击**Fabrikam_To_Contoso_3A4**协议，然后单击**激活**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 7： 构建和部署 DoubleAction SDK 示例](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-doubleaction-sdk-sample.md)