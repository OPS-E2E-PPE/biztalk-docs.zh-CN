---
title: 如何强调映射项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2732b36-ca57-4566-ba26-da27a3082f32
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6bb03969a044c6a474f5d2d1c1e5e1a5067cf81
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-emphasize-map-items"></a>如何强调映射项
在 BizTalk 映射器中，当您选择一个映射项目时，都会强调所有相关的链接和 functoids。 这在具有许多链接的映射中非常有用，因为识别关系和相关架构项比较困难。  
  
 当你选择一个链接、functoid 或一个架构元素时，BizTalk 映射器会强调相关关系和架构元素。 对于已选择的映射项，所有的传入链接和传出链接（递归方式）将以粗体突出显示，并且所有其他映射项目将显示为灰色。以下屏幕快照将已选择的映射项用粗体和彩色显示，而其他映射项目则显示更亮些。  
  
> [!NOTE]
>  在此上下文中，相关关系意思是直接或间接链接到已选择映射项目的所有链接、functoid 或结构元素。  
  
 ![强调地图项](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")  
  
## <a name="prerequisites"></a>必要條件  
 此操作要求 BizTalk 映射器处于运行状态。  
  
## <a name="to-emphasize-a-map-item"></a>若要强调地图项  
  
-   单击一个映射项（链接、functoid 或架构元素）。 您可以查看到当前网格页中与已选择映射项有关的其他链接和 functoid（包括架构节点）都是突出显示。  
  
     有时，对于已选择的节点，可能在其他网格页中存在关系。 在此种情况下，BizTalk 映射器强调当前网格页中的实例，并且突出显示页面选项卡（存在已选择节点的其他相关关系）。  
  
## <a name="see-also"></a>另请参阅  
 [在 BizTalk 映射程序中使用增强的功能](../core/using-enhanced-features-in-biztalk-mapper.md)