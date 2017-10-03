---
title: "如何创建一条新管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, warnings
- Pipeline Designer, warnings
- pipelines, creating
ms.assetid: bd95325e-1a72-4705-80f6-37ac092d11a3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83c1df14c0015ac26b99ad8f0760fe18438e8024
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-new-pipeline"></a>如何创建新管道
可以向项目添加管道模板来创建新的管道。  
  
> [!WARNING]
>  不应添加一个包含包含使用该 pipleine 组件的项目的解决方案的一个自定义管道组件的实现项目。 如果添加，则下次重新生成该解决方案时，您将收到一条错误消息，指明输出 dll 正由另一个进程使用。  
  
### <a name="to-create-a-new-pipeline"></a>创建新的管道  
  
1.  在解决方案资源管理器中，选择要在其中创建管道的项目。  
  
2.  在 **“项目”** 菜单上，单击 **“添加新项”**。  
  
3.  在**添加新项**对话框中，选择**接收管道**或**发送管道**通过一次单击它的模板。  
  
    > [!NOTE]
    >  如果您双击模板，管道将自动创建具有默认名称，将出现在**名称**字段。  
  
4.  在**名称**字段中，键入管道的名称。  
  
5.  单击 **“打开”**。  
  
     此时，新的管道将显示在解决方案资源管理器中。 设计图面将显示管道阶段和一组默认的组件。  
  
 有关将管道组件添加到管道的信息，请参阅[如何将组件添加到管道](../core/how-to-add-a-component-to-a-pipeline.md)。  
  
## <a name="see-also"></a>另请参阅  
 [如何打开管道](../core/how-to-open-a-pipeline.md)   
 [如何保存管道](../core/how-to-save-a-pipeline.md)   
 [如何使用工具箱](../core/how-to-use-the-toolbox.md)   
 [如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md)   
 [使用管道设计器中创建管道](../core/creating-pipelines-with-pipeline-designer.md)