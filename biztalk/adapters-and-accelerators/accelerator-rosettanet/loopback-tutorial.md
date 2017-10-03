---
title: "环回教程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- loopbacks, tutorial
- loopback tutorial, about the loopback tutorial
- loopback tutorial
- tutorials, loopback tutorial
ms.assetid: 0f69c1f1-4039-4949-8eed-127ceabbc3cc
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3b013eb65320dc36dd1319d7332e45ed54b2444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="loopback-tutorial"></a>环回教程
本教程包含详细的步骤说明，描述如何使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 在一台计算机上模拟本组织与合作伙伴组织之间的流程实施情况。  
  
 在实际生产环境中，您的合作伙伴组织在远程计算机上实施流程。 本教程使用 Loopback 实用工具创建镜像贸易协议，从而在同一台计算机上模拟贸易合作伙伴。 单台计算机环回方案可用于开发和测试。 建议您不要在生产环境中使用 Loopback 实用工具。  
  
 此环回方案不支持签名消息，因此不支持不可否认性。  
  
 如果配置了证书颁发机构，并拥有供测试使用的加密私钥，那么本方案支持消息加密。  
  
 在本教程中，您可以创建本组织，合作伙伴组织和贸易协议，并使用 Loopback 实用工具创建镜像协议，然后运行示例流程来验证环回方案。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为教程做准备](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [步骤 1： 创建主组织](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [步骤 2： 创建伙伴组织](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [步骤 3： 编辑合作伙伴接口过程](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [步骤 4： 创建贸易协议](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [步骤 5： 创建镜像协议](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [步骤 6： 启动业务流程](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [步骤 7： 创建示例 LOB 消息](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [BTARN 数据库中的步骤 8： 查看消息](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)