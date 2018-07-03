---
title: 步骤 5： 创建镜像协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, mirror agreements
- loopback tutorial, creating mirror agreements
- agreements, mirror agreements
ms.assetid: 6aa70b1e-7d38-49f7-9d5f-f008cbe3df66
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fde79b9ee5cdbb5cd34440aa59e79e842f79b0b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006462"
---
# <a name="step-5-create-a-mirror-agreement"></a>步骤 5： 创建镜像协议
在此步骤中，将使用 Loopback 实用工具在你配置了本组织的计算机上创建模拟贸易合作伙伴的镜像协议。 Loopback 实用工具是一个命令行工具。  
  
### <a name="to-create-a-mirror-agreement-using-the-loopback-utility"></a>使用 Loopback 实用工具创建镜像协议  
  
1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 在命令提示符处，转到\<*驱动器*\>: \Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK。 键入以下命令，然后按**Enter**:  
  
   ```  
   Loopback /enable HOME  
   ```  
  
3. 在步骤 2 中执行的命令完成后，在命令提示符处，键入以下命令，然后按**Enter**:  
  
   ```  
   Loopback /mirror "Trade Agreement"   
   ```  
  
   Loopback 实用工具会为本组织（发起方）自动创建发送端口，并为合作伙伴组织自动创建镜像贸易协议。 合作伙伴使用两个新的发送端口与本组织进行通信。  
  
> [!NOTE]
>  在每次更新原始贸易协议时，都必须重新反映贸易协议。  
  
## <a name="see-also"></a>请参阅  
 [步骤 6：启动业务流程](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)
