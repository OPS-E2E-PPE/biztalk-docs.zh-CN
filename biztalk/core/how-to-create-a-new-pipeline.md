---
title: 如何创建新的管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, warnings
- Pipeline Designer, warnings
- pipelines, creating
ms.assetid: bd95325e-1a72-4705-80f6-37ac092d11a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 908c0eebecaf005e22194584f9a1d1e7fafa4daf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970230"
---
# <a name="how-to-create-a-new-pipeline"></a>如何创建新管道
可以向项目添加管道模板来创建新的管道。  
  
> [!WARNING]
>  不应添加到包含使用该管道组件的项目的解决方案的自定义管道组件的实现包含一个项目。 如果添加，则下次重新生成该解决方案时，您将收到一条错误消息，指明输出 dll 正由另一个进程使用。  
  
### <a name="to-create-a-new-pipeline"></a>创建新的管道  
  
1. 在解决方案资源管理器中，选择要在其中创建管道的项目。  
  
2. 在 **“项目”** 菜单上，单击 **“添加新项”**。  
  
3. 在中**添加新项**对话框中，选择**接收管道**或**发送管道**通过一次单击模板。  
  
   > [!NOTE]
   >  如果双击模板，该管道将自动创建具有默认名称，将出现在**名称**字段。  
  
4. 在中**名称**字段中，键入管道的名称。  
  
5. 单击 **“打开”**。  
  
    此时，新的管道将显示在解决方案资源管理器中。 设计图面将显示管道阶段和一组默认的组件。  
  
   有关向管道添加管道组件的信息，请参阅[如何将组件添加到管道](../core/how-to-add-a-component-to-a-pipeline.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何打开管道](../core/how-to-open-a-pipeline.md)   
 [如何保存管道](../core/how-to-save-a-pipeline.md)   
 [如何使用工具箱](../core/how-to-use-the-toolbox.md)   
 [如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md)   
 [使用管道设计器创建管道](../core/creating-pipelines-with-pipeline-designer.md)