---
title: 步骤 5：创建 Contoso 3A2 贸易合作伙伴协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, creating
- creating, agreements
- double action tutorial, creating agreements
ms.assetid: 5c602c9c-22bd-450f-bb14-6848b1414c03
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a243ee66927d5a969a353f9fa9e5aaef3a8744c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280882"
---
# <a name="step-5-creating-the-contoso-3a2-trading-partner-agreement"></a>步骤 5：创建 Contoso 3A2 贸易合作伙伴协议
在此步骤中，创建 Contoso 和 Fabrikam 使用 Microsoft® 之间的贸易合作伙伴协议[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台。 创建新的贸易合作伙伴协议为 3A2 合作伙伴接口流程 (PIP)。  

### <a name="to-start-the-btarn-management-console"></a>若要启动 BTARN 管理控制台  

- 单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。  

### <a name="to-create-the-3a2-trading-partner-agreement"></a>若要创建 3A2 贸易合作伙伴协议  

1. 在中 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**协议**，指向**新建**，然后单击**协议**.  

2. 在中**新协议属性**对话框中，在**常规**选项卡上，执行以下操作：  


   |         使用此选项          |                            执行的操作                            |
   |---------------------------|------------------------------------------------------------------|
   |         **名称**          |                类型**Fabrikam_To_Contoso_3A2**。                 |
   | **过程配置** |      选择**STD_3A2_R02.00.00A**从下拉列表。      |
   |    **我的组织**    |           选择**Contoso**从下拉列表。            |
   | **合作伙伴组织**  |           选择**Fabrikam**从下拉列表。           |
   |     **RNIF 版本**      |          选择**V02.00.01**从下拉列表。           |
   |       **本组织角色**       | 选择**产品供应商 （响应方）** 从下拉列表。 |
   |         **Usage**         |             选择**测试**从下拉列表。             |


3. 单击**端口**选项卡，然后再执行以下操作：  


   |    使用此选项    |                          执行的操作                           |
   |----------------|---------------------------------------------------------------|
   | **操作 URL** | Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |
   | **信号 URL** | Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |
   |  **同步 URL**  | Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |


4. 单击“确定”  。  

5. 右键单击**Fabrikam_To_Contoso_3A2**协议，，然后单击**激活**。  

## <a name="see-also"></a>请参阅  
 [步骤 6：创建 Contoso 3A4 贸易合作伙伴协议](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-contoso-3a4-trading-partner-agreement.md)