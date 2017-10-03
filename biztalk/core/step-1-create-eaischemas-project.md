---
title: "步骤 1： 创建 EAISchemas 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a14ee61-fa27-4f03-997e-42c34a77afee
caps.latest.revision: "55"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e73da569196d564cd9bb0886c8c7f97d94fe9614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-eaischemas-project"></a>步骤 1：创建 EAISchemas 项目
![步骤 1 5](../core/media/step-1of5.gif "Step_1of5")  
  
 **完成时间：** 5 分钟  
  
 **目标：**在此步骤中，你创建一个新[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案和项目。  
  
 **用途：** BizTalk 项目系统用于创建部分或全部[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]应用程序或业务解决方案。 这些解决方案的核心元素是 BizTalk 项目，它是可在部署程序集之前构建并生成到该程序集中的项（例如架构、业务流程、Web 消息类型、类、管道、映射和引用）的集合。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   在开始此步骤之前必须完成中的步骤[在开始本教程之前](../core/before-you-begin-the-tutorial.md)。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-create-a-new-visual-studio-solutionproject"></a>创建新的 Visual Studio 解决方案/项目  
  
1.  启动**Microsoft Visual Studio**。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。  
  
3.  在**新项目**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**已安装的模板**|单击**BizTalk 项目**，然后单击**空 BizTalk 服务器项目**。|  
    |**名称**|类型**EAISchemas**。|  
    |**位置**|类型**C:\tutorial\Lessons**。|  
    |**解决方案名称**|类型**EAISolution**。|  
    |**创建解决方案的目录**|（已选中）|  
  
4.  单击 **“确定”**。  
  
5.  在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，你在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中打开了新项目和 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 解决方案。  
  
## <a name="next-steps"></a>后续步骤  
 为库存补货请求消息创建架构。  
  
## <a name="see-also"></a>另请参阅  
 [在开始本教程之前](../core/before-you-begin-the-tutorial.md)   
 [步骤 2： 创建清单请求架构](../core/step-2-create-the-inventory-request-schema.md)   
 [步骤 3： 创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)   
 [步骤 4： 创建代码图](../core/step-4-create-the-map.md)   
 [步骤 5： 生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md)   
 [开发人员工具](../core/developer-tools.md)   
 [使用 BizTalk 项目](../core/working-with-biztalk-projects.md)