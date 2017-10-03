---
title: "管道模板 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, templates
- Pipeline Designer, templates
- send pipelines, templates
- receive pipelines, templates
ms.assetid: b9779159-e49d-47fb-aa1c-06be5d604c67
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6af41d3c23c889b7a7e9bd2529adc80bc7bcd2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="pipeline-templates"></a>管道模板
除了默认管道，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含两个管道模板： 接收管道模板和发送管道模板。 从 BizTalk 项目中 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，你可以通过管道模板添加到你的项目**添加新项**命令**项目**菜单。 每个模板都有一个关联的策略文件，该文件用于确定管道的阶段并指示管道中允许使用的管道组件。 虽然无法重排策略文件中的阶段，但可以使用管道设计器重排阶段中的组件。  
  
 策略文件指定以下内容：  
  
-   阶段的顺序。  
  
-   每个阶段允许使用的组件数。  
  
-   各个阶段的执行模式。  
  
 管道模板的策略文件存储在 *\<BizTalk Server 安装目录 >*\Developer Tools\Pipeline 策略文件。 不要修改策略文件。 若要更改管道，请打开管道模板，然后使用管道设计器修改该管道。 有关使用管道设计器的详细信息，请参阅[使用管道设计器](../core/using-pipeline-designer.md)。  
  
 空管道模板文件存储在 *\<BizTalk Server 安装目录 >*\Developer Tools\BizTalkProjectItems 中,，名为 BTSReceivePipeline.btp 和 BTSTransmitPipeline.btp。 文件名称扩展.btp 指示该文件是一种 BizTalk Server 管道，并且可以在管道设计器中编辑。  
  
## <a name="see-also"></a>另请参阅  
 [类型的管道](../core/types-of-pipelines.md)   
 [类型的管道组件](../core/types-of-pipeline-components.md)   
 [默认管道](../core/default-pipelines.md)   
 [管道组件](../core/pipeline-components.md)   
 [有关管道、 阶段和组件](../core/about-pipelines-stages-and-components.md)