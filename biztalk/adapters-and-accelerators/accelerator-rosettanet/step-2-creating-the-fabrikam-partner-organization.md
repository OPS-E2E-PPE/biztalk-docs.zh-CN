---
title: 步骤 2： 创建 Fabrikam 合作伙伴组织 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trading partners
- double action tutorial, creating partner organizations
- trading partners, partner organization
ms.assetid: 4d2ddc4c-2275-4faf-9a36-8a912cc06527
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5634b1394a7c390dfddbcf3b893e2496e20a08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004358"
---
# <a name="step-2-creating-the-fabrikam-partner-organization"></a>步骤 2： 创建 Fabrikam 合作伙伴组织
在此步骤中，使用 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台创建新的贸易合作伙伴。 此教程中的贸易合作伙伴为 Fabrikam 组织。  

### <a name="to-start-the-btarn-management-console"></a>启动 BTARN 管理控制台  

- 在 Contoso 计算机上，单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后依次**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。  

### <a name="to-create-fabrikam-as-a-trading-partner"></a>创建 Fabrikam 作为贸易合作伙伴  

1. 在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**合作伙伴**，指向**新建**，然后单击**合作伙伴**.  

2. 在新合作伙伴属性对话框中，在**常规**选项卡上，执行以下操作<strong>:</strong>  


   |          使用此选项          |                                                                              执行的操作                                                                               |
   |----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |          **名称**          |                                                                          类型**FABRIKAM**。                                                                           |
   |          **GBI**           | 类型**987654321**。 **注意：** 如果同一台计算机上运行 Loopback 教程，必须输入除"987654321"不同的 GBI 值。 |
   | **合作伙伴分类** |                                                              选择**购物者**从下拉列表。                                                              |
   | **签名证书**  |                                                  选择**Fabrikam 签名 [指纹]** 从下拉列表。                                                  |
   | **加密证书** |                                                 选择**Fabrikam 加密 [指纹]** 从下拉列表。                                                  |


3. 单击**联系人属性**选项卡，然后再执行以下操作：  


   |       使用此选项        |                执行的操作                |
   |-----------------------|------------------------------------------|
   |   **联系人姓名**    |            类型**Jane Doe**。            |
   |  **E-mail Address**   | 类型<strong>jdoe@fabrikam.com</strong>。 |
   | **电话号码**  |          类型**555-555-5555**。          |
   |    **传真号码**     |          类型**555-555-5555**。          |
   | **供应链代码** |     类型**电子元件**。      |


4. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [步骤 3：创建 Contoso 0C2 贸易合作伙伴协议](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-contoso-0c2-trading-partner-agreement.md)