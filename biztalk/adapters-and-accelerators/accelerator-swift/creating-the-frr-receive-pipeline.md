---
title: 创建 FRR 接收管道 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, creating
- FRR, creating receive pipelines
- creating, receive pipelines
ms.assetid: 5884176b-8522-4dd3-8f93-8695858b59ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad31a69d579cf2bbe9f646fc87be1bea9f561a10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210373"
---
# <a name="creating-the-frr-receive-pipeline"></a>创建 FRR 接收管道
若要执行 FIN 响应对帐，必须创建包含 SWIFT FRR 解码器和 SWIFT FRR CorrelationSet 冲突解决程序管道组件，除了 SWIFT 反汇编程序接收管道。  
  
 **摘要**  
  
 创建具有以下阶段属性接收管道：  
  
|阶段/属性|组件/设置|  
|---------------------|------------------------|  
|拆装阶段|SWIFT 反汇编程序|  
|BRE 验证属性 （SWIFT 反汇编程序）|True|  
|XML 验证属性 （SWIFT 反汇编程序）|True|  
|SWIFT 标头架构属性 （SWIFT 反汇编程序）|（无）|  
|解码器阶段|SWIFT FRR MQSeries 解码器|  
|当事方解析阶段|SWIFT FRR 关联集冲突解决程序|  
  
### <a name="to-create-a-custom-receive-pipeline-for-frr"></a>若要为 FRR 创建自定义接收管道  
  
1.  在解决方案资源管理器的 Visual Studio 中，右键单击项目包含你[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管道，指向**添加**，然后单击**新项**。  
  
2.  在添加新项对话框中，单击**管道文件**在类别窗格中，然后选择**接收管道**在模板窗格中。  
  
3.  在**名称**框中，键入接收管道的名称，如**FRRReceivePipeline.btp**。 单击 **“添加”**。  
  
    > [!NOTE]
    >  在执行步骤 4 之前，你必须添加[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]FRR 管道组件工具箱中所述[向工具箱添加 SWIFT 管道组件](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md)。  
  
4.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**，然后单击**工具箱**。  
  
5.  从 BizTalk 管道组件工具箱窗格中，将拖动**SWIFT 反汇编程序**到**拖至此处**下面框**拆卸**暂存管道设计器中的形状。  
  
6.  与**SWIFT 反汇编程序组件**在管道设计器中，选择在**属性**，验证**BRE 验证**和**XML 验证**属性设置为**True**，和**SWIFT 标头架构**属性设置为 **（无）**。  
  
7.  在 BizTalk 管道组件工具箱中，拖动**SWIFT FRR MQSeries 解码器**到**拖至此处**下面框**解码器**暂存管道设计器中的形状。  
  
8.  从 BizTalk 管道组件工具箱窗格中，将拖动**SWIFT FRR 相关设置解析程序**到**拖至此处**下面框**ResolveParty**阶段在管道中的形状设计器。  
  
9. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**文件**，然后单击**保存所有**。