---
title: 步骤 10： 创建业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, creating
- creating, orchestrations
- message enrichment tutorial, orchestrations
ms.assetid: 10f5cf3d-4a34-4c80-89d1-c390552cfc09
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e896b5a5723b84cfc94d735aa51b8bee848b41b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989774"
---
# <a name="step-10-create-an-orchestration"></a>步骤 10： 创建业务流程
在此步骤中，使用业务流程设计器来创建用于表示检索其他患者的详细信息，以完全填充 ADT_A04 消息的业务流程的业务流程。 使用业务流程设计器，则选择表示此业务流程的操作所需的业务流程形状。 在更高版本的练习中，您提供其他信息以配置的形状，以便它们可以正常运行。  
  
> [!NOTE]
>  以下步骤中创建的业务流程仅适用于本教程的上下文。 为了使业务流程才能正常工作，它需要的程序集引用、 映射和使用本教程时创建的其他项目。  
  
### <a name="to-create-an-orchestration"></a>若要创建一个业务流程  
  
1. 在解决方案资源管理器中右键单击**BTAHL7 项目**，依次指向**添加**，然后单击**新项**。  
  
2. 在中**添加新项**对话框中**类别**窗格中，单击**业务流程文件**。  
  
3. 在中**模板**窗格中，单击**BizTalk 业务流程**。  
  
4. 在中**名称**字段中，键入**门铃 Orchestration.odx** (请注意，单词之间没有空格**门铃**并**业务流程**) 作为业务流程名称，然后单击**添加**创建新的业务流程文件。  
  
5. 在中**视图**菜单上，单击**工具箱**。  
  
6. 在**工具箱**窗格中，拖动**接收**到设计视图图面上形状并将其放在标记为区域**从工具箱中删除形状**。  
  
7. 在属性窗口 （在屏幕的底部） 中，单击**名称**属性，然后键入**DoorbellReceive**的名称作为**接收**形状，，然后按**输入**。  
  
8. 在属性窗口中更改**激活**属性设置为**True**。  
  
9. 拖动**转换**形状从工具箱拖放直接**DoorbellReceive**形状。  
  
10. 在属性窗口 （在屏幕的底部） 中，单击**名称**要更改的名称属性**转换**形状变为**DoorbellTransform**，然后按**输入**。  
  
11. 在中**工具箱**窗格中，拖动**消息赋值**到设计视图图面上形状并将其放在下方的区域上**ConstructMessage_1**形状。  
  
12. 在业务流程设计视图图面上，单击**MessageAssignment_1**形状，然后在**属性**窗格中，单击**名称**并键入新名称**DoorbellFinalTransform**，然后按**Enter**。  
  
13. 拖动**发送**从工具箱形状，然后将其放在下方的连接线上**DoorbellFinalTransform**形状。  
  
14. 在属性窗口 （在屏幕的底部） 中，单击**名称**要更改的名称属性**发送**形状变为**DoorbellSend**，然后按**输入**。  
  
    请继续执行[步骤 11： 创建业务流程变量](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)