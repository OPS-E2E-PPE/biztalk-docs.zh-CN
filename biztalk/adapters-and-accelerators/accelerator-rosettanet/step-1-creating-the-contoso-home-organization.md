---
title: 第 1 步：创建 Contoso 本组织 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating home organizations
- creating, home organizations
- home organizations, creating
ms.assetid: 0e7a53b9-ae59-4cd1-88bd-0ada7e65acba
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3893d582a85708190f1f030b06187fcd8f152bd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281593"
---
# <a name="step-1-creating-the-contoso-home-organization"></a>第 1 步：创建 Contoso 本组织
在此步骤中，使用 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台创建 Contoso 本组织。  

### <a name="to-start-the-btarn-management-console"></a>若要启动 BTARN 管理控制台  

- 在 Contoso 计算机上，单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。  

### <a name="to-create-the-home-organization"></a>若要创建本组织  

1. 在中[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**本组织**，指向**新建**，然后单击**本组织**。  

2. 在新本组织属性对话框中，在**常规**选项卡上，执行以下操作：  


   |               使用此选项               |                                                                              执行的操作                                                                               |
   |--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |               **名称**               |                                                                           类型**CONTOSO**。                                                                           |
   |               **GBI**                | 类型**123456789**。 **注意：** 如果已在同一计算机上运行 Loopback 教程，将需要输入除"123456789"不同的 GBI 值。 |
   | **本组织分类** |                                                           选择**制造商**从下拉列表。                                                            |


3. 单击**联系人属性**选项卡，然后再执行以下操作：  


   |       使用此选项        |               执行的操作                |
   |-----------------------|-----------------------------------------|
   |   **联系人姓名**    |           类型**John Doe**。            |
   |  **E-mail Address**   | 类型<strong>jdoe@contoso.com</strong>。 |
   | **电话号码**  |         类型**555-555-5555**。          |
   |    **传真号码**     |         类型**555-555-5555**。          |
   | **供应链代码** |     类型**电子元件**。     |


4. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [步骤 2：创建 Fabrikam 合作伙伴组织](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-fabrikam-partner-organization.md)