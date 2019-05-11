---
title: 如何使用工具箱 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipeline components, deleting from toolbox
- pipeline components, Pipeline Designer
- pipeline components, adding to toolbox
- Pipeline Designer, toolbox
- pipelines, creating
ms.assetid: 7a60c590-1a38-46fe-addf-0aa2c8b63cf9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2990cdf576f1678078da564932542081512d09dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383181"
---
# <a name="how-to-use-the-toolbox"></a>如何使用工具箱
通过将组件 （形状） 从工具箱拖动到设计图面创建的管道。 管道设计器可帮助你通过在创建过程上放置某些限制组装有效的管道。 您只能选择适用于要创建的管道类型的工具箱组件。 例如，接收管道将显示解码器、 拆装器和验证为有效的工具箱组件，而编码器和组装器将被禁用 （灰显）。  
  
 此外，阶段可以接受有效的组件。 例如，不能将编码器组件拖至组装阶段。 将组件拖放有效放置位置附近，会出现一个箭头，指示该组件可的插入的位置。  
  
 如果是有效的组件拖到某一阶段的处于折叠状态，将鼠标悬停几秒钟以展开它，然后将组件放入阶段的阶段。  
  
 将自定义组件添加到管道设计器中的工具箱是类似于标准 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]过程。  
  
 **开始和结束形状**  
  
 **启动**并**最终**形状显示为在所有管道上的项目符号。 它们提供设计图面上，为 visual 的组织。 没有仅各项之一，并且它们都不能添加也不能删除。 **启动**并**最终**形状并显示在工具箱中。  
  
### <a name="to-add-a-pipeline-component-to-the-toolbox"></a>若要向工具箱添加管道组件  
  
1.  在 **“工具”** 菜单上，单击 **“选择工具箱项”**。  
  
     -或-  
  
     右键单击工具箱，然后单击**选择项**。  
  
2.  在中**自定义工具箱**对话框中，单击**BizTalk 管道组件**选项卡。  
  
     对话框中显示兼容管道组件。 可以通过单击顶部的对话框的选项卡在类别间进行导航。  
  
3.  选择你想要添加到工具箱的组件。  
  
4.  单击“确定” 。 该组件将出现在**BizTalk 管道组件**工具箱选项卡中的。  
  
### <a name="to-remove-a-pipeline-component-from-the-toolbox"></a>若要从工具箱中删除的管道组件  
  
-   打开**自定义工具箱**对话框 （如在前面的过程中），然后清除要删除的组件。  
  
     即使已从工具箱将保持已注册组件。  
  
## <a name="see-also"></a>请参阅  
 [如何创建新的管道](../core/how-to-create-a-new-pipeline.md)   
 [如何打开管道](../core/how-to-open-a-pipeline.md)   
 [如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md)   
 [使用管道设计器创建管道](../core/creating-pipelines-with-pipeline-designer.md)