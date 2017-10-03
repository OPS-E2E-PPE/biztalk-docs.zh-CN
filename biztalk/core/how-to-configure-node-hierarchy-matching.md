---
title: "如何配置匹配的节点层次结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5302e194-cbc7-4d26-b25b-eb4e38abfe23
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d29a794db6f34d7e8251c32bbf428b3a336601fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-node-hierarchy-matching"></a>如何配置匹配的节点层次结构
在映射中创建链接时，BizTalk 映射器会自动创建编译器链接以实现您绘制的链接。 **目标链接**链接的属性控制 BizTalk 映射程序如何绘制编译器链接。 本主题提供有关如何设置目标链接的信息。  
  
 **源链接**属性指定如何从源节点检索值并应用于目标节点。 有关如何将源链接设置的信息，请参阅[如何将源链接编译器值设置](../core/how-to-set-the-source-links-compiler-value.md)。  
  
> [!NOTE]
>  此操作要求 BizTalk 映射器处于运行状态。  
  
### <a name="to-set-the-target-links-property"></a>设置“目标链接”属性  
  
1.  在映射网格页上，单击您要设置目标链接属性的链接。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**属性**窗口中，设置**目标链接**属性设置为以下选项之一：  
  
    -   **平展链接。** 源记录节点中的层次将平展至目标架构中所链接到的记录节点。  
  
        > [!NOTE]
        >  默认情况下，BizTalk 映射程序将设置**目标链接**属性**Flatten**。  
  
    -   **匹配链接上而下。** 从上向下按级别执行节点匹配。  
  
    -   **匹配链接从下往上。** 从下向上按级别执行节点匹配。  
  
## <a name="see-also"></a>另请参阅  
 [节点层次结构级别匹配](../core/node-hierarchy-level-matching.md)   
 [编译器指令和链接](../core/compiler-directives-and-links.md)   
 [使用链接以指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)