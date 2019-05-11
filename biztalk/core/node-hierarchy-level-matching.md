---
title: 节点层次级别匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 016a02be9634c86c03ac0a5532caf49a59a26c7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323562"
---
# <a name="node-hierarchy-level-matching"></a>节点层次级别匹配
BizTalk 映射器，您可以配置要控制编译器如何匹配节点层次结构的源和目标架构之间的链接属性。 从源架构中的字段创建链接到目标架构中的字段上时，BizTalk 映射器会自动添加编译器链接。 这些编译器链接取决于您选择的匹配。  
  
 当在显示的网格页中选择一个链接时，其中一个属性显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口是**目标链接**属性。 您可以在地图中选择以下可能值为每个链接：  
  
-   **平展链接。** 此值用于平展至目标架构节点中的父记录的所有源层次结构。  
  
-   **匹配项的链接上而下。** 使用此值可匹配节点级别从架构顶部到架构底部。  
  
-   **下到上匹配链接。** 使用此值可匹配节点级别从架构底部到架构顶部。  
  
## <a name="flatten-links"></a>平展链接  
 在此模式下，所有源层次都将都平展至目标节点的父记录。 在第一种情况下，源架构是比目标架构更为复杂。 在第二种情况下，目标架构是更复杂。  
  
 ![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")  
平展链接  
  
 ![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")  
平展链接，第二种情况  
  
## <a name="match-links-top-down"></a>匹配项的链接上而下  
 此模式下从上到下匹配级别的。 在第一种情况下，源架构是比目标架构更为复杂。 在第二种情况下，目标架构是更复杂。  
  
 ![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")  
自上而下的匹配  
  
 ![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")  
自上而下的匹配，第二个用例  
  
## <a name="match-links-bottom-up"></a>匹配项的链接下到上  
 此模式下从下到上匹配级别的。 在第一种情况下，源架构是比目标架构更为复杂。 在第二种情况下，目标架构是更复杂。  
  
 ![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")  
自下而上的匹配  
  
 ![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")  
自下而上的匹配，第二个用例  
  
## <a name="how-biztalk-mapper-processes-link-types"></a>BizTalk 映射器如何处理链接类型  
 因为可以设置**目标链接**属性设置为不同的值不同的链接，BizTalk 映射器需要一种方法时可能发生的冲突解决不同的设置。  
  
 例如，如果从链接使用平展编译器指令、 自上而下的编译器指令和下到上编译器指令**字段**到节点**字段**中目标架构中，并将这些节点节点共享同一个父**记录**节点，BizTalk 映射器将忽略自上而下和自下而上的编译器指令冲突并将所有链接视为它们设置为平展编译器指令。  
  
 下表显示了 BizTalk 映射器如何处理指向**字段**中相同的节点**记录**上的设置基于目标架构中的节点**目标链接**在同一链接的属性**记录**节点。  
  
|平展|自上而下的|自下而上的|结果|  
|-------------|---------------|----------------|------------|  
|0 或更多|一个或多个|一个或多个|BizTalk 映射器将所有链接视为它们设置为平展编译器指令。|  
|一个或多个|一个或多个|0|BizTalk 映射器将所有链接视为它们设置为上到下编译器指令。|  
|一个或多个|0|一个或多个|BizTalk 映射器将所有链接视为它们设置为下到上编译器指令。|  
  
 自上而下和自下而上的编译器指令优先于平展编译器指令，但相互抵消两者都存在。  
  
## <a name="see-also"></a>请参阅  
 [批量复制 Functoid](../core/mass-copy-functoid.md)   
 [如何设置源链接编译器值](../core/how-to-set-the-source-links-compiler-value.md)   
 [编译映射](../core/compiling-maps.md)