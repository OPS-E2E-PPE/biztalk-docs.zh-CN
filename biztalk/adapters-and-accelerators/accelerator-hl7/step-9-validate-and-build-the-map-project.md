---
title: 步骤 9： 验证并生成映射项目 |Microsoft 文档
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
ms.openlocfilehash: c1eb4580a9c89534204e492aebdd21988a6ce0e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206469"
---
# <a name="step-9-validate-and-build-the-map-project"></a>步骤 9： 验证并生成映射项目
在此步骤中，你使用**验证映射**以确定映射是否包含任何内部不一致，或者具有其他问题，防止将其用于有效地映射架构的命令。 你也会生成此项目以生成该程序集包含你创建的资源 （架构和映射）。 这还可以确保到目前为止完成的工作中没有编译错误。  
  
### <a name="to-validate-the-map-project"></a>若要验证映射项目  
  
1.  在解决方案资源管理器，右键单击**DoorbellMap.btm**映射，并依次**验证映射**。  
  
2.  确保在输出窗口中显示一条成功消息。 由于不映射到目标架构中的所有可用元素，因此，可能显示某些警告。  
  
     如果不显示任何成功消息，请检查映射项目。  
  
### <a name="to-build-the-map-project"></a>若要生成映射项目  
  
-   在解决方案资源管理器，右键单击**BTAHL7 项目**，然后单击**生成**。 确保在输出窗口中显示一条成功消息。  
  
     如果不显示任何成功消息，请检查映射项目。  
  
 继续执行[步骤 10： 创建业务流程](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息扩充教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)