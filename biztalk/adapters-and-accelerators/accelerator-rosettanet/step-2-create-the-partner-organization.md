---
title: 步骤 2： 创建合作伙伴组织 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- partner organization
- trading partners, partner organization
- loopback tutorial, creating partner organization
ms.assetid: 489bc961-dcb6-4610-989d-c06ba9f71b02
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3e7c8ae582f71c868f41a8ad2772e6f82d27d86
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993702"
---
# <a name="step-2-create-the-partner-organization"></a>步骤 2： 创建合作伙伴组织
在此步骤中，创建合作伙伴组织使用 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台。  

### <a name="to-create-the-partner-organization"></a>若要创建合作伙伴组织  

1. 在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开**BizTalk\<版本\>Accelerator for RosettaNet**，右键单击**合作伙伴**单击**新建**，然后单击**合作伙伴**。  

2. 在中**新合作伙伴属性**对话框框中，执行以下操作：  


   | 使用此选项 |     执行的操作      |
   |----------|---------------------|
   | **名称** |  类型**合作伙伴**。  |
   | **GBI**  | 类型**987654321**。 |


3. 在中**新合作伙伴属性**对话框中，在**联系人属性**选项卡上，执行以下操作：  


   |       使用此选项        |                执行的操作                |
   |-----------------------|------------------------------------------|
   |   **联系人姓名**    |            类型**Jane Doe**。            |
   |  **E-mail Address**   | 类型<strong>jdoe@fabrikam.com</strong>。 |
   | **电话号码**  |          类型**555-555-5555**。          |
   |    **传真号码**     |          类型**555-555-5555**。          |
   | **供应链代码** |     类型**电子元件**。      |


4. 单击**应用**，然后**确定**。  

> [!NOTE]
>  如果有加密证书，请在此处进行配置。 有关配置加密证书的信息，请参阅[管理证书](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)。  

## <a name="see-also"></a>请参阅  
 [步骤 3：编辑合作伙伴接口流程](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)