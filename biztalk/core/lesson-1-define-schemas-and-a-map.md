---
title: 第 1 课： 定义架构和映射 |Microsoft Docs
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
ms.openlocfilehash: b1e017239fc70186660812ea941fe11209506b1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980366"
---
# <a name="lesson-1-define-schemas-and-a-map"></a>第 1 课：定义架构和映射
在本课中，您将在企业应用程序集成 (EAI) 解决方案中创建并生成第一个项目。 此项目包含两个消息架构和一个映射。  
  
 在 EAI 解决方案中，仓库系统将向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送库存补货请求消息以进行处理。 在本课中，您将创建以下项：  
  
- EAI 解决方案，用来容纳项目。  
  
- 项目，用来容纳架构和映射。  
  
- 仓库向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送的库存补货请求消息的架构。  
  
- 在请求遭到拒绝时仓库接收的消息的架构。  
  
- 映射，用来重新格式化请求消息以创建请求拒绝消息。  
  
  在开始之前生成项目的最后[第 2 课： 定义业务流程](../core/lesson-2-define-the-business-process.md)。 在第 2 课中，您将创建路由消息并根据批准条件评估库存补货请求消息内容的业务流程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)  
  
-   [步骤 2：创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md)  
  
-   [步骤 3：创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)  
  
-   [步骤 4：创建映射](../core/step-4-create-the-map.md)  
  
-   [步骤 5：生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md)  
  
## <a name="see-also"></a>请参阅  
 [开始本教程之前](../core/before-you-begin-the-tutorial.md)   
 [第 2 课： 定义业务流程](../core/lesson-2-define-the-business-process.md)   
 [第 3 课：部署解决方案](../core/lesson-3-deploy-the-solution.md)