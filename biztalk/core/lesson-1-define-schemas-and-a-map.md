---
title: 第 1 课：定义架构和映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial, creating solutions
ms.assetid: 4fe7720d-722e-4fa0-a556-477fc66ffa12
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02069f45a537a645dc0c3948e13d1f9208a8e5b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380772"
---
# <a name="lesson-1-define-schemas-and-a-map"></a>第 1 课：定义架构和映射
在本课程中，将创建和构建企业应用程序集成 (EAI) 解决方案中的第一个项目。 该项目包含两个消息架构和映射。  
  
 在 EAI 解决方案中，仓库系统将发送到库存补货请求消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行处理。 在本课中，您将创建以下各项：  
  
- EAI 解决方案中，若要保存项目。  
  
- 项目，用来容纳架构和映射。  
  
- 由仓库发送给消息的架构，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到库存补货请求。  
  
- 在请求遭到拒绝时仓库接收的消息架构。  
  
- 映射，用来重新格式化请求消息创建请求拒绝消息。  
  
  在开始之前生成项目的最后[第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)。 第 2 课中创建路由消息并根据批准条件的库存补货请求消息的内容的计算结果的业务流程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)  
  
-   [步骤 2：创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md)  
  
-   [步骤 3：创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)  
  
-   [步骤 4：创建映射](../core/step-4-create-the-map.md)  
  
-   [步骤 5：生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md)  
  
## <a name="see-also"></a>请参阅  
 [开始本教程之前](../core/before-you-begin-the-tutorial.md)   
 [第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)   
 [第 3 课：部署解决方案](../core/lesson-3-deploy-the-solution.md)