---
title: 步骤 3：编辑合作伙伴接口流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, PIPs
- PIPs, modifying
- loopback tutorial, modifying PIPs
ms.assetid: 4d03c598-8ed4-4135-9748-ede101997fd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50c276c201fca7f0aa6b8b6cf7da4e69698cba77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281110"
---
# <a name="step-3-edit-the-partner-interface-process"></a>步骤 3：编辑合作伙伴接口流程
在此步骤中，您可以编辑合作伙伴接口流程 (PIP) 配置设置，以便禁用安全传输，如果您没有在 Microsoft® Internet 信息服务 (IIS) 配置的安全套接字层 (SSL) 证书。 由于环回方案不支持传入和传出消息进行签名，必须更改要继续本教程的默认设置。 您将修改 STD_0C1_R01.02 PIP。  
  
### <a name="to-edit-the-std0c1r0102-pip"></a>若要编辑 STD_0C1_R01.02 PIP  
  
1. 在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开**BizTalk\<版本\>Accelerator for RosettaNet**，单击**流程配置设置**，右键单击**STD_0C1_R01.02**，然后单击**属性**。  
  
2. 在 STD_0C1_R01.02Properties 对话框中，在**活动**选项卡上，设置**是否要求安全传输**选项设为`False`。 仅当您在 IIS Web 服务器上没有 SSL 证书，请执行此步骤。  
  
3. 设置**要求不可否认**到`False`，将**是否要求授权**到`False`，将**和内容的不可否认**到`False`，然后单击**确定**。  
  
    这将禁用的不可否认和签名消息证书的使用。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：创建贸易协议](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)   
 [授权属性和不可否认性属性](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)