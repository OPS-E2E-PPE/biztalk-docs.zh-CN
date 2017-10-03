---
title: "节点层次结构级别匹配 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Field nodes
- BizTalk Mapper, processing
- Record node
- BizTalk Mapper, compiler directives
- destination schemas, matching nodes
- source schemas, matching nodes
- maps, links
- Target Links property
- BizTalk Mapper, links
- compiler directives, matching schema nodes
- compiler directives, flattening source hierarchies
- maps, processing
ms.assetid: 5ba1ac77-0e70-4c58-9b8c-1b379dbbb3bd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b2d0c363abfefb9e3d0eb8abfb332c59539bb67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="node-hierarchy-level-matching"></a>节点层次结构级别匹配
BizTalk 映射程序使您能够配置链接属性可控制编译器如何匹配源和目标架构之间的节点层次结构。 在从源架构中的字段创建链接到目标架构中的字段上时，BizTalk 映射程序会自动添加编译器链接。 这些编译器链接取决于你选择的匹配。  
  
 当显示的网格页中选择一个链接时，其中一个属性显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口是**目标链接**属性。 您可以为映射中的各个链接选择以下可能的值：  
  
-   **平展链接。** 使用此值可将所有源层次平展至目标架构节点中的父记录。  
  
-   **匹配链接上而下。** 使用此值可从架构顶部到架构底部匹配节点级别。  
  
-   **匹配链接从下往上。** 使用此值可从架构底部到架构顶部匹配节点级别。  
  
## <a name="flatten-links"></a>平展链接  
 在此模式下，所有源层次都将平展至目标节点中的父记录。 在第一种情况下，源架构比目标架构更为复杂。 在第二种情况下，目标架构更为复杂。  
  
 ![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")  
平展链接  
  
 ![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")  
平展链接，第二种情况  
  
## <a name="match-links-top-down"></a>匹配链接自上而下  
 此模式将从上到下对级别进行匹配。 在第一种情况下，源架构比目标架构更为复杂。 在第二种情况下，目标架构更为复杂。  
  
 ![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")  
自上而下匹配  
  
 ![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")  
自上而下匹配，第二个用例  
  
## <a name="match-links-bottom-up"></a>匹配链接自下而上  
 此模式匹配从下至上级别到另一个级别。 在第一种情况下，源架构比目标架构更为复杂。 在第二种情况下，目标架构更为复杂。  
  
 ![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")  
自下而上匹配  
  
 ![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")  
自下而上匹配，第二个用例  
  
## <a name="how-biztalk-mapper-processes-link-types"></a>BizTalk 映射程序如何处理链接类型  
 因为你可以设置**目标链接**到不同的值不同的链接的属性，BizTalk 映射程序需要一种方式，若要解决的不同设置，在它们可能发生冲突。  
  
 例如，如果从链接的使用 flatten 编译器指令、 自上而下的编译器指令和自下而上的编译器指令**字段**节点**字段**中目标架构，并将这些节点节点共享同一个父**记录**节点，BizTalk 映射程序忽略冲突的自顶向下和自下而上的编译器指令，并将所有的链接，就像它们被设置为平展编译器指令。  
  
 下表显示如何 BizTalk 映射程序处理指向**字段**中相同的节点**记录**目标架构中的节点上的设置基于**目标链接**在同一个链接的属性**记录**节点。  
  
|平展|自上而下|自下而上|结果|  
|-------------|---------------|----------------|------------|  
|0 或更多|1 或更多|1 或更多|BizTalk 映射程序将所有的链接，就像它们被设置为平展编译器指令。|  
|1 或更多|1 或更多|0|BizTalk 映射程序将所有的链接，就像它们被设置为自上而下的编译器指令。|  
|1 或更多|0|1 或更多|BizTalk 映射程序将所有的链接，就像它们被设置为自下而上的编译器指令。|  
  
 自顶向下和自下而上的编译器指令将优先于 flatten 编译器指令，但相互抵消两者都存在。  
  
## <a name="see-also"></a>另请参阅  
 [大容量复制 Functoid](../core/mass-copy-functoid.md)   
 [如何将源链接编译器值设置](../core/how-to-set-the-source-links-compiler-value.md)   
 [编译地图](../core/compiling-maps.md)