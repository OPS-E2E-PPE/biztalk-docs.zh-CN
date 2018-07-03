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
ms.openlocfilehash: 1eb785793b865e36c5b37bd6b32199ab3e34f5d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009574"
---
# <a name="how-to-configure-node-hierarchy-matching"></a>如何配置节点层次级别匹配
在映射中创建链接时，BizTalk 映射器会自动创建编译器链接以实现您绘制的链接。 **目标链接**链接的属性控制 BizTalk 映射器绘制编译器链接的方式。 本主题提供有关如何设置目标链接的信息。  
  
 **源链接**属性指定如何从源节点检索值并将应用于目标节点。 有关如何设置源链接的信息，请参阅[如何设置源链接编译器值](../core/how-to-set-the-source-links-compiler-value.md)。  
  
> [!NOTE]
>  此操作要求 BizTalk 映射器处于运行状态。  
  
### <a name="to-set-the-target-links-property"></a>设置“目标链接”属性  
  
1. 在映射网格页上，单击您要设置目标链接属性的链接。  
  
2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**属性**窗口中，设置**目标链接**属性设置为以下选项之一：  
  
   -   **平展链接。** 源记录节点中的层次将平展至目标架构中所链接到的记录节点。  
  
       > [!NOTE]
       >  默认情况下，BizTalk 映射器设置**目标链接**属性设置为**平展**。  
  
   -   **匹配项的链接上而下。** 从上向下按级别执行节点匹配。  
  
   -   **下到上匹配链接。** 从下向上按级别执行节点匹配。  
  
## <a name="see-also"></a>请参阅  
 [节点层次级别匹配](../core/node-hierarchy-level-matching.md)   
 [编译器指令和链接](../core/compiler-directives-and-links.md)   
 [使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)