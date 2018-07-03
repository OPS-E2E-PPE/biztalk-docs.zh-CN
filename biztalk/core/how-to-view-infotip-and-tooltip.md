---
title: 如何查看信息提示和工具提示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5621bd0a-7028-43fc-b6e8-74a528129285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 833fedbcb731971bb305c759b6f87a5a575f58e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995934"
---
# <a name="how-to-view-infotip-and-tooltip"></a>如何查看提示和工具提示
当您将光标移动到映射项上而不单击该项时，将出现一个屏幕提示，提供有关该项的有用信息。  
  
 BizTalk 映射器使用两种类型的屏幕提示 – 信息提示和工具提示。  
  
- **信息提示**为 functoid 或链接显示。 当您为 functoid 或链接配置标签或注释时，将在网格页上看到信息提示。 此外，当属性的文本值超出**属性网格**，显示信息提示。  
  
- **工具提示**显示为网格视图中的当前对齐中部分/全部隐藏的那些架构节点。  
  
  对于链接标签，仅会保留前 256 个字符，而工具提示将显示全部标签。 对于 functoid，标签最多可包含 256 个字符，注释限制在 1024 个字符。 注释的文本将相应地截断，以仅显示注释前 256 个字符。  
  
## <a name="prerequisites"></a>必要條件  
 若要查看工具提示，请确保 BizTalk 映射器正在运行。  
  
## <a name="to-view-the-infotip"></a>若要查看信息提示  
 将您将鼠标移动到 functoid 上，信息提示即会显示关于 functoid 名称、functoid 标签、functoid 注释和输入参数（如果存在）的信息。 有关**脚本**functoid，信息提示将显示前的几行代码。  
  
 链接的信息提示将显示以下信息：  
  
- 如果链接标签，设置。  
  
- **从： 源连接**。 如果源连接是架构元素，它将显示该元素的名称。 如果源连接是 functoid，则它将显示 functoid 名称。  
  
- **： 目标连接**。 如果目标连接是架构元素，它将显示该元素的名称。 如果目标连接是 functoid，则它将显示 functoid 名称。  
  
  如果中的字段**属性网格**文本超出显示中，将鼠标移动字段上。 信息提示将显示完整文本。  
  
  下图说明了 functoid、 信息提示链接，并**属性网格**。  
  
  ![用于 functoid、 链接和标签的信息提示](../core/media/viewing-infotips.gif "Viewing_infotips")  
  
## <a name="to-view-the-tooltip"></a>查看工具提示  
 如果源和/或目标架构非常大，则映射可能会纵向延伸，因此可能只能看到部分架构节点。 在这种情况下，当您将鼠标移动到这些源节点上时，可以看到工具提示。  
  
 下图显示了部分隐藏的目标架构节点的工具提示。  
  
 ![架构节点的工具提示](../core/media/viewing-tooltips.gif "Viewing_tooltips")  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器](../core/using-biztalk-mapper.md)