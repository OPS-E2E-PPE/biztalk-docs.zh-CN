---
title: Loopback 教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- loopbacks, tutorial
- loopback tutorial, about the loopback tutorial
- loopback tutorial
- tutorials, loopback tutorial
ms.assetid: 0f69c1f1-4039-4949-8eed-127ceabbc3cc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97714d5f7e604acbb798739fc4eb545a07968980
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010094"
---
# <a name="loopback-tutorial"></a>Loopback 教程
本教程包含详细的步骤，描述如何使用 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]来模拟一台计算机上的家庭和合作伙伴组织之间的流程实施。  
  
 在实际生产环境中，您的合作伙伴组织在远程计算机上实施流程。 本教程使用 Loopback 实用工具创建镜像贸易协议，从而在同一台计算机上模拟贸易合作伙伴。 单台计算机环回方案可用于开发和测试。 建议您不要在生产环境中使用 Loopback 实用工具。  
  
 此环回方案不支持签名消息，因此不支持不可否认性。  
  
 如果配置了证书颁发机构，并拥有供测试使用的加密私钥，那么本方案支持消息加密。  
  
 在本教程中，您可以创建本组织，合作伙伴组织和贸易协议，并使用 Loopback 实用工具创建镜像协议，然后运行示例流程来验证环回方案。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [准备教程](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [步骤 1：创建本组织](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [步骤 2：创建合作伙伴组织](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [步骤 3：编辑合作伙伴接口流程](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [步骤 4：创建贸易协议](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [步骤 5：创建镜像协议](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [步骤 6：启动业务流程](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [步骤 7：创建示例 LOB 消息](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [步骤 8：在 BTARN 数据库中查看消息](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)