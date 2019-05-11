---
title: 步骤 9：验证并生成映射项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, maps
- message enrichment tutorial, maps
- maps, building
- maps, validating
ms.assetid: 10716b0b-702c-48bb-85a9-d58d8f33b68b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f41cc3bbe235dfda75563d94ae0173737a58c75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286639"
---
# <a name="step-9-validate-and-build-the-map-project"></a>步骤 9：验证并生成映射项目
在此步骤中，使用**验证映射**命令，以确定是否映射包含任何内部不一致，或存在会妨碍其为映射架构有效地使用其他问题。 你还生成项目以生成包含你创建的资源 （架构和映射） 的程序集。 这还可确保到目前为止完成的工作中没有任何编译错误。  
  
### <a name="to-validate-the-map-project"></a>若要验证映射项目  
  
1.  在解决方案资源管理器中右键单击**DoorbellMap.btm**映射，然后依次**验证映射**。  
  
2.  确保在输出窗口中显示一条成功消息。 因为不映射到目标架构中的所有可用元素，则可能出现一些警告。  
  
     如果不显示任何成功消息，进行故障排除映射项目。  
  
### <a name="to-build-the-map-project"></a>若要生成映射项目  
  
- 在解决方案资源管理器中右键单击**BTAHL7 项目**，然后单击**生成**。 确保在输出窗口中显示一条成功消息。  
  
   如果不显示任何成功消息，进行故障排除映射项目。  
  
  请继续执行[步骤 10:创建一个业务流程](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)