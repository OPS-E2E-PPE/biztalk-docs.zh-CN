---
title: 步骤 10： 创建业务流程 |Microsoft 文档
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
ms.openlocfilehash: cfc554a6f3c94a077b34ae79a36b8e484eadcd5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206565"
---
# <a name="step-10-create-an-orchestration"></a>步骤 10： 创建业务流程
在此步骤中，你可以使用 Orchestration 设计器创建业务流程来表示检索其他患者的详细信息，以完全填充 ADT_A04 消息的业务流程。 使用业务流程设计器，选择表示此业务流程的操作所需的业务流程形状。 在更高版本的练习中，你提供其他信息以配置形状，以便它们可以正常工作。  
  
> [!NOTE]
>  在以下步骤中创建业务流程只能在本教程的上下文中。 为了使业务流程能够正常工作，它需要的程序集引用、 映射和其他使用本教程时创建的项目。  
  
### <a name="to-create-an-orchestration"></a>若要创建业务流程  
  
1.  在解决方案资源管理器，右键单击**BTAHL7 项目**，指向**添加**，然后单击**新项**。  
  
2.  在**添加新项**对话框中，在**类别**窗格中，单击**Orchestration 文件**。  
  
3.  在**模板**窗格中，单击**BizTalk 业务流程**。  
  
4.  在**名称**字段中，键入**门铃 Orchestration.odx** (请注意，单词之间没有空格**门铃**和**Orchestration**) 作为业务流程的名称，然后单击**添加**若要创建新的业务流程文件。  
  
5.  在**视图**菜单上，单击**工具箱**。  
  
6.  在**工具箱**窗格中，拖动**接收**形状变为设计视图图面，然后将其放置在标记为的区域上**从工具箱中删除形状**。  
  
7.  在 （在你的屏幕的右下方） 的属性窗口中，单击**名称**属性并键入**DoorbellReceive**作为名称的**接收**形状，，然后按**输入**。  
  
8.  在属性窗口中，更改**激活**属性**True**。  
  
9. 拖动**转换**从工具箱形状并将其放正下方**DoorbellReceive**形状。  
  
10. 在 （在你的屏幕的右下方） 的属性窗口中，单击**名称**属性可以更改的名称**转换**形状变为**DoorbellTransform**，然后按**输入**。  
  
11. 在**工具箱**窗格中，拖动**消息分配**形状变为设计视图图面，然后将其放置在直接下方区域上**ConstructMessage_1**形状。  
  
12. 在业务流程设计视图图面中，单击**MessageAssignment_1**形状，然后在**属性**窗格中，单击**名称**，然后键入新名称**DoorbellFinalTransform**，然后按**Enter**。  
  
13. 拖动**发送**从工具箱形状并将其放连接线正下方**DoorbellFinalTransform**形状。  
  
14. 在 （在你的屏幕的右下方） 的属性窗口中，单击**名称**属性可以更改的名称**发送**形状变为**DoorbellSend**，然后按**输入**。  
  
 继续执行[步骤 11： 创建业务流程变量](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息扩充教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)