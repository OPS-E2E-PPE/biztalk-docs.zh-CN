---
title: "步骤 1： 向解决方案添加 EAIOrchestration 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9aa0d9-2075-4c7e-8baf-1ecd2721859a
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3b8e2b9c197e01ed695311c67bc79cf5056c4d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a>步骤 1：向解决方案中添加 EAIOrchestration 项目
![步骤 1 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **完成时间：** 5 分钟  
  
 **目标：**在此步骤中，你可以将第二个项目添加到 EAI 解决方案。 然后再向该新项目添加业务流程。  
  
 **用途：**创建业务流程单独的项目。 当多个人员使用一个解决方案时，这样做很有帮助。 您可以使用该新业务流程自动执行本课中的业务程序。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   在开始此步骤之前必须完成[第 1 课： 定义架构和映射](../core/lesson-1-define-schemas-and-a-map.md)。  
  
## <a name="procedures"></a>过程  
 如果您关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]窗口中，按照中的过程后，"以打开 Visual Studio 项目"[步骤 2： 创建清单请求架构](../core/step-2-create-the-inventory-request-schema.md)以将其打开。  
  
#### <a name="to-add-another-project-to-your-solution"></a>向解决方案添加另一项目  
  
1.  从 Visual Studio 中，在**文件**菜单上，指向**添加**，然后单击**新项目**。  
  
2.  在**新项目**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**已安装的模板**|单击**BizTalk 项目**，然后单击**空 BizTalk 服务器项目**。|  
    |**名称**|键入 `EAIOrchestration`。|  
    |**位置**|键入 `C:\BTSTutorials\EAISolution`。|  
  
3.  单击 **“确定”**。  
  
#### <a name="to-add-an-orchestration"></a>添加业务流程  
  
1.  在解决方案资源管理器，右键单击**EAIOrchestration**，指向**添加**，然后单击**新项**。  
  
2.  在**添加新项-EAIOrchestration**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**已安装的模板**|单击**Orchestration 文件**，然后单击**BizTalk 业务流程**。|  
    |**名称**|类型**EAIProcess.odx**。|  
  
3.  单击 **“添加”**。  
  
     此时，将打开业务流程设计器。 下图显示了包含 EAIProcess 业务流程的业务流程设计器：  
  
     ![新的业务流程](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，您向 EAI 解决方案添加了另一项目。 然后又向该新项目添加了业务流程。  
  
## <a name="next-steps"></a>后续步骤  
 定义中的业务流程[步骤 2： 定义业务流程](../core/step-2-define-the-business-process.md)。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2： 定义的业务流程](../core/step-2-define-the-business-process.md)   
 [步骤 3： 将端口添加到业务流程](../core/step-3-add-ports-to-the-orchestration.md)   
 [步骤 4： 生成 EAIOrchestration 项目](../core/step-4-build-the-eaiorchestration-project.md)