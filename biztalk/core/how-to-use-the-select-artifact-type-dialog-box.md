---
title: "如何使用选择项目类型对话框中 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Select Artifact Type dialog box
- artifacts, Select Artifact Type dialog box
- Orchestration Designer, items
ms.assetid: f0f767f1-4130-4ff0-a898-a089343ee71f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88167cbeb5c8c6bb0a62030e64f4ed3d91a9d1aa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-select-artifact-type-dialog-box"></a>如何使用选择项目类型对话框
*项*用于在业务流程设计器中配置的业务流程的元素。 项的例子包括架构、映射、管道、端口类型和多部分消息类型。 开发业务流程及其构成部分（例如，端口形状、转换形状和消息）时，您可能需要引用某些项，这些项不位于当前业务流程，而是位于当前项目或者已编译到 BizTalk Server 程序集的其他项目中。 你使用**选择项目类型**对话框中，以查找并配置业务流程中的某个元素时，然后指定项。  
  
 **选择项目类型**从 Orchestration 设计器中的多个位置对话框才可用。 你可以选择\<从引用的程序集选择\>下拉列表中显示配置选项; 单击此文本将打开**选择项目类型**对话框。  
  
 必须先选择要配置的元素，然后才可以选择项。  
  
 你可以使用**选择项目类型**以下特定用途的对话框中：  
  
|操作|用途|  
|------------|-------------|  
|选择管道|为直接（早期）绑定配置端口时，针对管道属性选择管道。|  
|选择映射|选择一个映射，以便与使用**转换**形状。|  
|选择一个架构|创建多部分消息类型时，在项目中选择架构。|  
|选择端口类型|创建端口时引用现有端口类型。|  
|选择多部分消息类型|创建消息时引用现有的多部分类型。|  
|选择 .NET 类型|创建变量或消息时引用现有的 .NET 类型。|  
  
 **引用窗格**  
  
 引用窗格中的**选择项目类型**对话框中将显示在当前项目和其他可用的程序集的引用。 若要在此窗格中选择某个引用，请单击该引用。 若要展开此窗格中的容器 (如**程序集**容器)，单击它旁边的加号 （+）。  
  
 **项窗格**  
  
 项窗格中的**选择项目类型**对话框中显示引用窗格中当前选定的引用中包含的项。 项窗格中有两个列，**项**和**限定名称**，其中显示当前引用中的项目的信息。  
  
### <a name="to-use-the-select-artifact-type-dialog-box"></a>使用“选择项目类型”对话框  
  
1.  展开**引用**的左窗格中的节点。 该窗格显示了可用的项目和程序集。  
  
2.  展开**程序集**节点。 将列出一个或多个程序集，例如 SYSTEM.DLL 和 MICROSOFT.BIZTALK.PIPELINES.DLL。  
  
3.  单击程序集。 如果程序集包含项，则这些项将显示在右侧窗格中。 项的限定名将显示在右侧窗格的右侧列中。  
  
    > [!NOTE]
    >  如果当前项目包含项，则可以单击该项目来查看其项并选择其中一项。  
  
4.  若要在右窗格中选择一个项，单击它，然后单击**确定**退出**选择项目类型**对话框。 这将会指定该项作为所选元素的类型。 若要关闭**选择项目类型**对话框中没有选择和分配某一项，请单击**取消**。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程形状](../core/orchestration-shapes.md)   
 [如何将形状添加到业务流程](../core/how-to-add-shapes-to-orchestrations.md)   
 [如何将参数添加到业务流程](../core/how-to-add-parameters-to-orchestrations.md)