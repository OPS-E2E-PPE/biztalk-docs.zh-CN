---
title: 步骤 6：创建 Fabrikam 3A4 贸易合作伙伴协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: 6ccd2414-a1d4-460e-9529-65b2d30cfca6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e42c269c088d58abc3b0003bbc6a5df110e95a4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280704"
---
# <a name="step-6-creating-the-fabrikam-3a4-trading-partner-agreement"></a>步骤 6：创建 Fabrikam 3A4 贸易合作伙伴协议
在此步骤中，创建 Contoso 和 Fabrikam 使用 Microsoft® 之间的贸易合作伙伴协议[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台。 创建新的贸易合作伙伴协议为 3A4 合作伙伴接口流程 (PIP)。  

### <a name="to-start-the-btarn-management-console"></a>若要启动 BTARN 管理控制台  

- 单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。  

### <a name="to-create-the-3a4-trading-partner-agreement"></a>若要创建 3A4 贸易合作伙伴协议  

1. 在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**协议**，指向**新建**，然后单击**协议**.  

2. 在中**新协议属性**对话框中，在**常规**选项卡上，执行以下操作：  


   |         使用此选项          |                      执行的操作                       |
   |---------------------------|-------------------------------------------------------|
   |         **名称**          |           类型**Fabrikam_To_Contoso_3A4**。           |
   | **过程配置** |  选择**STD_3A4_V02.02**从下拉列表。   |
   |    **我的组织**    |     选择**Fabrikam**从下拉列表。      |
   | **合作伙伴组织**  |      选择**Contoso**从下拉列表。      |
   |     **RNIF 版本**      |     选择**V02.00.01**从下拉列表。     |
   |       **本组织角色**       | 选择**买方 （发起方）** 从下拉列表。 |
   |         **Usage**         |       选择**测试**从下拉列表。        |


3. 上**端口**选项卡上，执行以下操作：  


   |    使用此选项    |                          执行的操作                           |
   |----------------|---------------------------------------------------------------|
   | **操作 URL** | 类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。 |
   | **信号 URL** | 类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。 |
   |  **同步 URL**  | 类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。 |


4. 单击“确定” 。  

5. 右键单击**Fabrikam_To_Contoso_3A4**协议，然后单击**激活**。  

## <a name="see-also"></a>请参阅  
 [步骤 7：生成和部署 LOBWebApplication SDK 示例](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)