---
title: 步骤 3： 编辑合作伙伴接口流程 |Microsoft Docs
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
ms.openlocfilehash: a3b5b6d2f6b0fcbf13ab521bc318eda54ece55f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003606"
---
# <a name="step-3-edit-the-partner-interface-process"></a>步骤 3： 编辑合作伙伴接口流程
在此步骤中，您可以编辑合作伙伴接口流程 (PIP) 配置设置，以便禁用安全传输，如果您没有在 Microsoft® Internet 信息服务 (IIS) 配置的安全套接字层 (SSL) 证书。 由于环回方案不支持对传入消息和传出消息签名，为了继续完成教程，你必须更改默认设置。 你将修改 STD_0C1_R01.02 PIP。  
  
### <a name="to-edit-the-std0c1r0102-pip"></a>编辑 STD_0C1_R01.02 PIP  
  
1. 在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开**BizTalk\<版本\>Accelerator for RosettaNet**，单击**流程配置设置**，右键单击**STD_0C1_R01.02**，然后单击**属性**。  
  
2. 在 STD_0C1_R01.02Properties 对话框中，在**活动**选项卡上，设置**是否要求安全传输**选项设为`False`。 请只在 IIS Web 服务器上没有 SSL 证书的情况下执行此步骤。  
  
3. 设置**要求不可否认**到`False`，将**是否要求授权**到`False`，将**和内容的不可否认**到`False`，然后单击**确定**。  
  
    此操作禁用“不可否认性”，也禁止了签名消息证书的使用。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4： 创建贸易协议](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)   
 [授权属性和不可否认性属性](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)