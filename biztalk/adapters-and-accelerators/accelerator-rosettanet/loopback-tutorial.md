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
ms.openlocfilehash: f96d81e59686759300e996e2f257da5afbc91ed0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283290"
---
# <a name="loopback-tutorial"></a>Loopback 教程
本教程包含详细的步骤，描述如何使用 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]来模拟一台计算机上的家庭和合作伙伴组织之间的流程实施。  
  
 在实际生产环境中，您的合作伙伴组织实现驻留在远程计算机上。 本教程使用 Loopback 实用工具创建镜像贸易协议，从而模拟贸易合作伙伴的同一计算机上。 使用单台计算机环回方案适用于开发和测试目的。 建议您不应在生产环境中使用 Loopback 实用工具。  
  
 此环回方案不支持签名消息，并因此不支持不可否认性。  
  
 如果你具有证书颁发机构配置，且具有私钥的加密可用于测试目的，这种情况下支持加密的消息。  
  
 在本教程中，您将创建本组织、 合作伙伴组织和贸易协议、 使用 Loopback 实用工具创建镜像协议，，然后运行示例流程来验证环回方案。  
  
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