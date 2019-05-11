---
title: 第 1 步：向解决方案中添加 EAIOrchestration 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9aa0d9-2075-4c7e-8baf-1ecd2721859a
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df384829c19f24b71bec1726a260f185ea583463
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392943"
---
# <a name="step-1-add-eaiorchestration-project-to-the-solution"></a>第 1 步：向解决方案中添加 EAIOrchestration 项目
![步骤 1，共 4 步](../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，您向 EAI 解决方案添加第二个项目。 然后，将业务流程添加到新的项目。  
  
 **目的：** 创建一个单独的项目的业务流程。 当有多个人员使用一种解决方案时，这非常有用。 使用新的业务流程自动业务流程执行本课程中。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   在开始此步骤之前，必须完成[第 1 课：定义架构和映射](../core/lesson-1-define-schemas-and-a-map.md)。  
  
## <a name="procedures"></a>过程  
 如果已关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]窗口中，按照中的"打开 Visual Studio 项目"过程[步骤 2:创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md)以将其打开。  
  
#### <a name="to-add-another-project-to-your-solution"></a>若要将另一个项目添加到你的解决方案  
  
1.  Visual Studio 中，从上**文件**菜单，依次指向**添加**，然后单击**新项目**。  
  
2.  在中**新的项目**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**已安装的模板**|单击**BizTalk 项目**，然后单击**空的 BizTalk Server 项目**。|  
    |**名称**|键入 `EAIOrchestration`。|  
    |**位置**|键入 `C:\BTSTutorials\EAISolution`。|  
  
3.  单击“确定” 。  
  
#### <a name="to-add-an-orchestration"></a>若要添加业务流程  
  
1.  在解决方案资源管理器中右键单击**EAIOrchestration**，依次指向**添加**，然后单击**新项**。  
  
2.  在中**添加新项-EAIOrchestration**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**已安装的模板**|单击**业务流程文件**，然后单击**BizTalk 业务流程**。|  
    |**名称**|类型**EAIProcess.odx**。|  
  
3.  单击 **“添加”**。  
  
     业务流程设计器随即打开。 下图显示了包含 EAIProcess 业务流程的业务流程设计器。  
  
     ![新的业务流程](../core/media/tut1-eaiprocess.gif "Tut1_EAIProcess")  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，您向 EAI 解决方案添加第二个项目。 然后向该新项目添加业务流程。  
  
## <a name="next-steps"></a>后续步骤  
 定义业务流程中的[步骤 2:定义业务流程](../core/step-2-define-the-business-process.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2：定义业务流程](../core/step-2-define-the-business-process.md)   
 [步骤 3：向业务流程添加端口](../core/step-3-add-ports-to-the-orchestration.md)   
 [步骤 4：生成 EAIOrchestration 项目](../core/step-4-build-the-eaiorchestration-project.md)