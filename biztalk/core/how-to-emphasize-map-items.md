---
title: 如何强调映射项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2732b36-ca57-4566-ba26-da27a3082f32
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5be500ad36b27848733863ffde1a648d42c7db17
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385150"
---
# <a name="how-to-emphasize-map-items"></a>如何强调映射项
在 BizTalk 映射器中，在选择地图项中，所有相关的链接和 functoid 的强调程度。 这可在映射中许多链接，其中很难识别关系和相关的架构项。  
  
 当选择链接、 functoid 或架构元素时，BizTalk 映射器强调相关的关系和架构元素。 对于选定的映射项中，所有中突出显示的传入链接和传出链接 （递归） 粗体和所有其他映射项目将灰显。下面的屏幕截图显示选定的映射项以粗体显示，并显示较浅的颜色和其他映射项目。  
  
> [!NOTE]
>  在此上下文中，相关的关系意思是直接或间接地链接到选定的映射项的所有链接、 functoid 或架构元素。  
  
 ![强调映射项](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")  
  
## <a name="prerequisites"></a>先决条件  
 此操作需要 BizTalk 映射器正在运行。  
  
## <a name="to-emphasize-a-map-item"></a>若要强调映射项  
  
-   单击一个映射项 （链接、 functoid 或架构元素）。 您可以看到突出显示所有其他链接和 functoid （包括架构节点） 与当前网格页中选定的映射项相关联。  
  
     有时，对于所选节点，可能有其他网格页中存在的关系。 在这种情况下，BizTalk 映射器强调当前网格页中的实例，并还会突出显示与所选节点的其他相关的关系所在的页选项卡。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器中的增强功能](../core/using-enhanced-features-in-biztalk-mapper.md)