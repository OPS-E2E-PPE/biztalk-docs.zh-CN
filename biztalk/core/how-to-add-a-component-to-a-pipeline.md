---
title: "如何将组件添加到管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: pipelines, components
ms.assetid: 6b1dbeab-6acc-46d7-8ddd-79b79da3591c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a9f11f03e818ae1067bc22027822bfeef202260
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-component-to-a-pipeline"></a>如何将组件添加到管道
通过将组件从工具箱拖至设计图面可以向管道添加组件。  
  
### <a name="to-add-a-component-to-a-pipeline"></a>若要将组件添加到管道  
  
-   在工具箱中，将管道组件拖放到**拖至此处 ！** 在设计图面上的框。  
  
 下图显示如何管道设计图面阐释管道。 此管道有两个阶段，即组装阶段和编码阶段。 XML 汇编程序管道组件已添加到组装阶段中，但因为它仍将显示编码阶段是仍为空，**拖至此处 ！** 若要指示管道组件，可以添加到的阶段。  
  
 ![阶段和 BizTalk 管道中的组件](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")  
BizTalk 管道中的阶段和组件说明图  
  
> [!NOTE]
>  管道组件仅在设计图面上的特定位置中删除。 管道组件只能放在与之有阶段关联的阶段中。 如果指针旁出现一个带有贯穿线的圆圈，则表示指针处不能放置管道组件。 如果出现一个箭头，并且突出显示了设计图面部分，则表示该处可以放置管道组件。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建一条新管道](../core/how-to-create-a-new-pipeline.md)   
 [如何打开管道](../core/how-to-open-a-pipeline.md)   
 [如何使用工具箱](../core/how-to-use-the-toolbox.md)   
 [如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md)   
 [使用管道设计器中创建管道](../core/creating-pipelines-with-pipeline-designer.md)