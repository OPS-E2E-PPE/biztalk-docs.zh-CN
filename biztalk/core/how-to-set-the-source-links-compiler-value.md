---
title: 如何设置源链接编译器值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd1d73-78d1-468d-806a-3f6f258ee375
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb6d3a08cf1cc4f22ea339d74a1b7ca2de081a37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334220"
---
# <a name="how-to-set-the-source-links-compiler-value"></a>如何设置源链接编译器值
可以使用**源链接**属性用于指定如何从源节点检索值并将应用于目标节点的链接。 本主题介绍可用选项以及如何从中进行选择。  
  
### <a name="to-set-the-source-links-link-property"></a>若要设置源链接链接属性  
  
1. 在 BizTalk 映射器网格页上，单击链接以选择它。  
  
    突出显示的网格页中所选链接的终结点。  
  
2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，设置**源链接**属性设置为以下选项之一：  
  
   -   **复制名称。** 源架构中节点的名称用作目标架构中链接节点的值。  
  
   -   **复制文本值。** 与源架构 （元素数据或属性值） 中的节点对应的值用作目标架构中链接节点的值。 选择此选项默认值。 例如，`<Node>Hello<Name>Chris</Name>Barry</Node>`会导致"Hello"。  
  
   -   **复制文本和子内容值。** 对应于记录节点和所有子节点和及其子节点的值的值，在源架构 （元素数据和属性值） 组合作为目标架构中链接节点的值。 例如，`<Node>Hello<Name>Chris</Name>Barry</Node>`会导致"Hello Chris Barry"。  
  
## <a name="see-also"></a>请参阅  
 [使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)   
 [编译器指令和链接](../core/compiler-directives-and-links.md)