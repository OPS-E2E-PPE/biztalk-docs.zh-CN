---
title: "步骤 5： 生成 EAISchemas 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c20cd368-7446-4861-8d71-5bc25ce408a2
caps.latest.revision: "41"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394d9df78f7064df8501ed43149bd26793533c47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-build-the-eaischemas-project"></a>步骤 5：生成 EAISchemas 项目
![步骤 5 5](../core/media/step-5of5.gif "Step_5of5")  
  
 **完成时间：** 6 だ 牧  
  
 **目标：**在此步骤中，您将编译 EAISchemas 项目。  
  
 **用途：** Microsoft BizTalk Server 和.NET Framework 的最重要方面是，所有的 BizTalk Server 项目; 地图、 架构、 业务流程和管道，可以编译成.NET 程序集。 此设计的两个最重要含义是：这些程序集必须具有强名称，为此它们还需遵守 .NET 版本控制规则。 其主要含义是：根据特定版本的其他 .NET 项目或程序集（包括 BizTalk 项目）生成 BizTalk 项目后，该 BizTalk 项目将继续使用该版本，直到根据更高的版本重新生成该 BizTalk 项目。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   在开始此步骤之前，必须完成以下步骤：  
  
    -   [步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)  
  
    -   [步骤 2： 创建清单请求架构](../core/step-2-create-the-inventory-request-schema.md) 
  
    -   [步骤 3： 创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)  
  
    -   [步骤 4： 创建代码图](../core/step-4-create-the-map.md)  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-build-the-eaischemas-project"></a>若要生成 EAISchemas 项目  
  
1.  在解决方案资源管理器，右键单击**EAISchemas**，然后单击**生成**。  
  
     屏幕底部应显示：  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，为生成程序集文件 (DLL)，您需要构建 EAISchemas 项目。  
  
## <a name="next-steps"></a>后续步骤  
 创建针对中批准条件库存补货请求消息的内容的计算结果的业务流程[第 2 课： 定义业务流程](../core/lesson-2-define-the-business-process.md)。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)   
 [步骤 2： 创建清单请求架构](../core/step-2-create-the-inventory-request-schema.md)   
 [步骤 3： 创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)   
 [步骤 4： 创建代码图](../core/step-4-create-the-map.md)