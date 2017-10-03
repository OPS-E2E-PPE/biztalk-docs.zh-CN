---
title: "步骤 3： 测试 Solution2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30dbc7c9-3c5f-4953-b26f-5c41141c22ad
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0e484a9f6af788775ec4ae7309965327378267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-solution"></a>步骤 3： 测试解决方案
![步骤 3 / 3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：**在此步骤中，你测试 EAI 解决方案如何处理消息。  
  
 **用途：**在此步骤中，检查 eai 进程业务流程正确处理消息。 检查方法是将示例消息放入为 EAI 应用程序指定的接收位置。 如果 EAI 解决方案工作正常，则当 EAIProcess 业务流程从仓库接收到请求多于 500 个货品的消息时，该业务流程将生成拒绝请求消息。 如果 EAIProcess 业务流程从仓库接收到请求少于 500 个货品的消息，则该业务流程会将消息传递到 ERP 系统。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前必须完成[步骤 2： 配置并启动应用程序](../core/step-2-configure-and-start-the-application1.md)。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-test-the-eai-solution"></a>测试 EAI 解决方案  
  
1.  打开 Windows 资源管理器，并导航到**C:\BTSTutorials\WareHouse**。  此文件夹是通过安装教程文件创建的。  
  
2.  复制**RequestInstance.XML**将其粘贴到**C:\BTSTutorials\WareHouse\Request**。  
  
3.  当该文件将消失时，检查**C:\BTSTutorials\ERP\Request**。  
  
4.  在 Windows 资源管理器，导航到**C:\BTSTutorials\WareHouse**。  
  
5.  复制**请求实例 （通过限制）。XML**将其粘贴到**C:\BTSTutorials\WareHouse\Request**。  
  
6.  当该文件将消失时，检查**C:\BTSTutorials\WareHouse\RequestDecline**。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 通过将示例消息放在 EAI 应用程序的接收位置中，您测试了 EAI 解决方案。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 1： 部署项目](../core/step-1-deploy-the-projects.md)   
 [步骤 2： 配置并启动应用程序](../core/step-2-configure-and-start-the-application1.md)