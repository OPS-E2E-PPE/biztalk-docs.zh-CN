---
title: 如何匹配在映射中的架构节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 584f85d2-6198-4ef3-90d9-a322f1457d9a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a25bf295a767f34b692d54fc922fb8fe489ecc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336154"
---
# <a name="how-to-match-schema-nodes-in-a-map"></a>如何匹配在映射中的架构节点
当源或目标架构很复杂时，它可能很难将元素映射。 BizTalk 映射器引入**指示匹配**功能，它使您能够通过建议最佳匹配映射复杂架构元素。 本主题提供有关如何执行此操作的信息。  
  
> [!NOTE]
>  BizTalk 映射器建议可能的匹配架构节点。 当前仅为英语名称支持此功能。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-match-relevant-schema-nodes"></a>若要匹配相关架构节点  
  
1.  选择并右键单击的架构元素，需要知道最佳匹配项，然后依次**指示匹配**。 BizTalk 映射器突出显示最佳匹配 （仅限于 7 个），并选中最佳匹配。  
  
     或者，可以选择**指示匹配**从 BizTalk 菜单中或按 SHIFT + 空格键。  
  
     下图显示目标架构中所选节点的建议匹配。  
  
     ![暗示性映射](../core/media/suggestive-mapping.gif "Suggestive_Mapping")  
  
    > [!NOTE]
    >  按住 SHIFT 键以遍历建议匹配。  
  
2.  您现在可以执行以下操作：  
  
    -   按 ENTER 确认突出显示最佳 （如有可能） 的匹配。  
  
    -   使用向上箭头键循环按首选项顺序在突出显示匹配。  
  
        > [!NOTE]
        >  按向下箭头键可遍历到下一个最佳匹配项，并向上箭头键突出显示上一个最佳匹配项。  
  
    -   按 HOME 键返回到上匹配。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器中的增强功能](../core/using-enhanced-features-in-biztalk-mapper.md)