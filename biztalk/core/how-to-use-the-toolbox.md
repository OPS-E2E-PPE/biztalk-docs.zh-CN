---
title: "如何使用工具箱 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipeline components, deleting from toolbox
- pipeline components, Pipeline Designer
- pipeline components, adding to toolbox
- Pipeline Designer, toolbox
- pipelines, creating
ms.assetid: 7a60c590-1a38-46fe-addf-0aa2c8b63cf9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3965a063aebcc932f07937fd19c3998412591ea1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-toolbox"></a>如何使用工具箱
您可以通过将组件（形状）从工具箱拖至设计图面来创建管道。 使用管道设计器，可以通过对创建过程进行特定限制来组装有效的管道。 您只能选择适用于要创建的管道类型的工具箱组件。 例如，对于接收管道，解码器、拆装器和验证器将显示为有效的工具箱组件，而编码器和组装器将处于禁用状态（呈灰色）。  
  
 此外，阶段只接受有效的组件。 例如，不能将编码器组件拖至组装阶段。 将组件拖至有效放置位置的附近时，将显示一个箭头，用于指示该组件可插入到的位置。  
  
 如果将有效组件拖至已折叠的阶段，则可在该阶段上将鼠标悬停几秒钟以展开该阶段，然后即可将组件放入该阶段中。  
  
 向管道设计器的工具箱中添加自定义组件的过程类似于 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 标准过程。  
  
 **开始和结束形状**  
  
 **启动**和**结束**形状显示为所有管道中的项目符号。 这些形状显示在设计图面上只是为了直观地进行组织。 每个形状只有一个，既不能添加，也不能删除。 **启动**和**结束**形状不会出现在工具箱中。  
  
### <a name="to-add-a-pipeline-component-to-the-toolbox"></a>向工具箱添加管道组件  
  
1.  在 **“工具”** 菜单上，单击 **“选择工具箱项”**。  
  
     -或者-  
  
     右键单击工具箱，然后单击**选择项**。  
  
2.  在**自定义工具箱**对话框中，单击**BizTalk 管道组件**选项卡。  
  
     此时，将出现一个显示兼容管道组件的对话框。 您可以通过单击该对话框顶部的各个选项卡来浏览不同的类别。  
  
3.  选择要添加到工具箱的组件。  
  
4.  单击 **“确定”**。 该组件将出现在**BizTalk 管道组件**工具箱选项卡中的。  
  
### <a name="to-remove-a-pipeline-component-from-the-toolbox"></a>从工具箱中删除管道组件  
  
-   打开**自定义工具箱**（如前面的过程中） 的对话框中，然后清除要删除的组件。  
  
     从工具箱中删除后，组件仍会保持为已注册状态。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建一条新管道](../core/how-to-create-a-new-pipeline.md)   
 [如何打开管道](../core/how-to-open-a-pipeline.md)   
 [如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md)   
 [使用管道设计器中创建管道](../core/creating-pipelines-with-pipeline-designer.md)