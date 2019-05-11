---
title: 步骤 3：测试 Solution2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30dbc7c9-3c5f-4953-b26f-5c41141c22ad
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e585019df8d6aa13374bb5648d37b10273d99cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392643"
---
# <a name="step-3-test-the-solution"></a>步骤 3：测试解决方案
![第 3 部分，共 3 步](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，测试 EAI 解决方案处理消息的方式。  
  
 **目的：** 在此步骤中，您将检查 EAIProcess 业务流程正确处理消息。 通过将示例消息放入为 EAI 应用程序指定的接收位置执行此操作。 如果 EAI 解决方案工作正常，如果 EAIProcess 业务流程从仓库请求超过 500 个货品收到一条消息之后，业务流程生成拒绝请求消息。 如果 EAIProcess 业务流程从仓库请求少于 500 个货品收到一条消息，业务流程将传递到 ERP 系统的消息。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，必须完成[步骤 2:配置并启动应用程序](../core/step-2-configure-and-start-the-application1.md)。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-test-the-eai-solution"></a>若要测试 EAI 解决方案  
  
1.  打开 Windows 资源管理器，并导航到**C:\BTSTutorials\WareHouse**。  通过安装教程文件创建此文件夹。  
  
2.  复制**RequestInstance.XML**将其粘贴到**C:\BTSTutorials\WareHouse\Request**。  
  
3.  在该文件消失后，检查**C:\BTSTutorials\ERP\Request**。  
  
4.  在 Windows 资源管理器，导航到**C:\BTSTutorials\WareHouse**。  
  
5.  复制**RequestInstance （通过限制）。XML**将其粘贴到**C:\BTSTutorials\WareHouse\Request**。  
  
6.  在该文件消失后，检查**C:\BTSTutorials\WareHouse\RequestDecline**。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 将示例消息放在 EAI 应用程序的接收位置中测试 EAI 解决方案。  
  
## <a name="see-also"></a>请参阅  
 [步骤 1：将项目部署](../core/step-1-deploy-the-projects.md)   
 [步骤 2：配置并启动应用程序](../core/step-2-configure-and-start-the-application1.md)