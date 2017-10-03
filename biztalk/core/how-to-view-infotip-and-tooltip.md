---
title: "如何查看信息提示和工具提示 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5621bd0a-7028-43fc-b6e8-74a528129285
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06aba645f94b87e0a7951d9c8264056262a12a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-infotip-and-tooltip"></a>如何查看提示和工具提示
当您将光标移动到映射项上而不单击该项时，将出现一个屏幕提示，提供有关该项的有用信息。  
  
 BizTalk 映射器使用两种类型的屏幕提示 – 信息提示和工具提示。  
  
-   **Infotips** functoid 或链接都显示出来。 当您为 functoid 或链接配置标签或注释时，将在网格页上看到信息提示。 此外，超过时属性的文本值的显示**属性网格**，显示信息提示。  
  
-   **工具提示**显示在网格视图中的当前对齐方式从部分/完全隐藏这些架构节点。  
  
 对于链接标签，仅会保留前 256 个字符，而工具提示将显示全部标签。 对于 functoid，标签最多可包含 256 个字符，注释限制在 1024 个字符。 注释的文本将相应地截断，以仅显示注释前 256 个字符。  
  
## <a name="prerequisites"></a>先决条件  
 若要查看工具提示，请确保 BizTalk 映射器正在运行。  
  
## <a name="to-view-the-infotip"></a>若要查看的信息提示  
 将您将鼠标移动到 functoid 上，信息提示即会显示关于 functoid 名称、functoid 标签、functoid 注释和输入参数（如果存在）的信息。 有关**脚本**functoid，信息提示显示代码的前几行。  
  
 链接的信息提示将显示以下信息：  
  
-   如果链接标签，设置。  
  
-   **从： 源连接**。 如果源连接是架构元素，它将显示该元素的名称。 如果源连接是 functoid，则它将显示 functoid 名称。  
  
-   **目标机构： 目标连接**。 如果目标连接是架构元素，它将显示该元素的名称。 如果目标连接是 functoid，则它将显示 functoid 名称。  
  
 如果中的字段**属性网格**具有超过显示中，文本的字段上移动鼠标。 信息提示将显示完整文本。  
  
 下图说明了与 functoid infotips 链接，与**属性网格**。  
  
 ![有关 functoid、 链接和标签 Infotips](../core/media/viewing-infotips.gif "Viewing_infotips")  
  
## <a name="to-view-the-tooltip"></a>查看工具提示  
 如果源和/或目标架构非常大，则映射可能会纵向延伸，因此可能只能看到部分架构节点。 在这种情况下，当您将鼠标移动到这些源节点上时，可以看到工具提示。  
  
 下图显示了部分隐藏的目标架构节点的工具提示。  
  
 ![到架构节点的工具提示](../core/media/viewing-tooltips.gif "Viewing_tooltips")  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk 映射程序](../core/using-biztalk-mapper.md)