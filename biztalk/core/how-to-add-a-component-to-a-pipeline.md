---
title: 如何向管道添加组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, components
ms.assetid: 6b1dbeab-6acc-46d7-8ddd-79b79da3591c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65db8b09dfcb7f1821746ffb5716e5f1e3f3e1dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387396"
---
# <a name="how-to-add-a-component-to-a-pipeline"></a>如何向管道添加组件
通过从工具箱拖动到设计图面可将组件添加到管道中。  
  
### <a name="to-add-a-component-to-a-pipeline"></a>若要向管道添加组件  
  
- 在工具箱中，管道将组件拖放到**放到此处 ！** 在设计图面上的框。  
  
  下图显示了如何在管道设计图面了管道。 此管道包含两个阶段，即组装阶段和编码阶段。 XML 组装器管道组件已添加到组装阶段中，但编码阶段仍然为空，因为它仍显示**放到此处 ！** 指示可以向阶段添加管道组件。  
  
  ![阶段和 BizTalk 管道中的组件](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")  
  说明了阶段和 BizTalk 管道中的组件。  
  
> [!NOTE]
>  管道组件只能放在设计图面上的特定位置。 仅可以在其中之有阶段关联的阶段中删除管道组件。 带有贯穿线的圆形旁边会显示指针不能放置管道组件。 显示一个箭头，并且设计图面上的部分将突出显示可以放置管道组件的位置。  
  
## <a name="see-also"></a>请参阅  
 [如何创建新的管道](../core/how-to-create-a-new-pipeline.md)   
 [如何打开管道](../core/how-to-open-a-pipeline.md)   
 [如何使用工具箱](../core/how-to-use-the-toolbox.md)   
 [如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md)   
 [使用管道设计器创建管道](../core/creating-pipelines-with-pipeline-designer.md)