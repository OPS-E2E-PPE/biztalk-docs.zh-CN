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
ms.openlocfilehash: 2028170edc6cd2e4414172f2be37f3c7da7ebb8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333041"
---
# <a name="how-to-view-infotip-and-tooltip"></a>如何查看信息提示和工具提示
时无需单击它可将光标移动到地图项中，屏幕提示显示与项相关的有用信息。  
  
 BizTalk 映射器使用两种类型的屏幕提示 – 信息提示和工具提示。  
  
- **信息提示**为 functoid 或链接显示。 在配置标签或注释的 functoid 或链接时，您看到在网格页上的信息提示。 此外，当属性的文本值超出**属性网格**，显示信息提示。  
  
- **工具提示**显示为网格视图中的当前对齐中部分/全部隐藏的那些架构节点。  
  
  对于链接标签保留仅前 256 个字符，并在工具提示显示全部标签。 对于 functoid，标签可以包含最多 256 个字符，注释限制为 1024年个字符。 注释的文本获取相应地截断，以显示仅前 256 个字符的注释。  
  
## <a name="prerequisites"></a>先决条件  
 若要查看工具提示，请确保 BizTalk 映射器正在运行。  
  
## <a name="to-view-the-infotip"></a>若要查看信息提示  
 当鼠标移动到 functoid 上时，信息提示将显示 functoid 名称、 functoid 标签、 functoid 注释和输入的参数有关的信息 （如果存在）。 有关**脚本**functoid，信息提示将显示前的几行代码。  
  
 链接的信息提示将显示以下信息：  
  
- 如果链接标签，设置。  
  
- **从： 源连接**。 如果源连接是架构元素，它显示元素的名称。 如果源连接是 functoid，它将显示 functoid 名称。  
  
- **： 目标连接**。 如果目标连接是架构元素，它显示元素的名称。 如果目标连接是 functoid，它将显示 functoid 名称。  
  
  如果中的字段**属性网格**文本超出显示中，将鼠标移动字段上。 信息提示将显示完整文本。  
  
  下图说明了 functoid、 信息提示链接，并**属性网格**。  
  
  ![用于 functoid、 链接和标签的信息提示](../core/media/viewing-infotips.gif "Viewing_infotips")  
  
## <a name="to-view-the-tooltip"></a>若要查看工具提示  
 当源和/或目标架构非常大时，您的映射可以跨垂直;因此可能只能看到部分架构节点。 在此类方案中，您可以看到工具提示，这些源节点上移动鼠标时。  
  
 下图显示了部分隐藏的目标架构节点的工具提示。  
  
 ![架构节点的工具提示](../core/media/viewing-tooltips.gif "Viewing_tooltips")  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射程序](../core/using-biztalk-mapper.md)