---
title: 步骤 5：生成 EAISchemas 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20cd368-7446-4861-8d71-5bc25ce408a2
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b82d7b4d322464cb873e47e0e15e57c6f68f51d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244303"
---
# <a name="step-5-build-the-eaischemas-project"></a>步骤 5：生成 EAISchemas 项目
![步骤 5，共 5](../core/media/step-5of5.gif "Step_5of5")  
  
 **若要完成的时间：** 6 分钟  
  
 **目标：** 在此步骤中，您将编译 EAISchemas 项目。  
  
 **目的：** Microsoft BizTalk Server 和.NET Framework 的最重要方面是，所有 BizTalk Server 项目;映射、 架构、 业务流程和管道，获取编译到.NET 程序集。 这种设计的两个最重要的意义是，这些程序集必须具有强名称，并且正因为如此，它们还需遵守.NET 版本控制规则。 其主要含义是，一次生成的其他.NET 项目或程序集 （包括 BizTalk 项目） 的特定版本的 BizTalk 项目，将继续使用该版本，直到它已针对较新版本重新生成。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   开始此步骤之前，必须完成以下步骤：  
  
    -   [步骤 1：创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)  
  
    -   [步骤 2：创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md) 
  
    -   [步骤 3：创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)  
  
    -   [步骤 4：创建映射](../core/step-4-create-the-map.md)  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-build-the-eaischemas-project"></a>若要生成 EAISchemas 项目  
  
1.  在解决方案资源管理器中右键单击**EAISchemas**，然后单击**生成**。  
  
     在屏幕底部应显示：  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，您需要构建 EAISchemas 项目以生成程序集文件 (DLL)。  
  
## <a name="next-steps"></a>后续步骤  
 创建计算结果根据批准条件中的库存补货请求消息的内容的业务流程[第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 1：创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)   
 [步骤 2：创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md)   
 [步骤 3：创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)   
 [步骤 4：创建映射](../core/step-4-create-the-map.md)