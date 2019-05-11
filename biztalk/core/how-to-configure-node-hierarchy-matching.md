---
title: 如何配置节点层次级别匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5302e194-cbc7-4d26-b25b-eb4e38abfe23
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00de1b7431fd942451d99b958746d209fcdf427d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386246"
---
# <a name="how-to-configure-node-hierarchy-matching"></a>如何配置节点层次级别匹配
当在映射中创建一个链接时，BizTalk 映射器将自动创建编译器链接以实现您绘制的链接。 **目标链接**链接的属性控制 BizTalk 映射器绘制编译器链接的方式。 本主题提供有关如何设置目标链接的信息。  
  
 **源链接**属性指定如何从源节点检索值并将应用于目标节点。 有关如何设置源链接的信息，请参阅[如何设置源链接编译器值](../core/how-to-set-the-source-links-compiler-value.md)。  
  
> [!NOTE]
>  此操作需要 BizTalk 映射器正在运行。  
  
### <a name="to-set-the-target-links-property"></a>若要设置目标链接属性  
  
1. 在映射网格页上，单击你想要设置目标链接属性的链接。  
  
2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**属性**窗口中，设置**目标链接**属性设置为以下选项之一：  
  
   -   **平展链接。** 源记录节点中的层次结构平展至目标架构中的链接到记录节点。  
  
       > [!NOTE]
       >  默认情况下，BizTalk 映射器设置**目标链接**属性设置为**平展**。  
  
   -   **匹配项的链接上而下。** 匹配节点已关闭-到-级别执行顶部。  
  
   -   **下到上匹配链接。** 匹配节点由到-级别执行从底部。  
  
## <a name="see-also"></a>请参阅  
 [节点层次级别匹配](../core/node-hierarchy-level-matching.md)   
 [编译器指令和链接](../core/compiler-directives-and-links.md)   
 [使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)