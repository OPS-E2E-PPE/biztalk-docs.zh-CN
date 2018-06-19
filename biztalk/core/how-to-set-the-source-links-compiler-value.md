---
title: 如何将源设置链接编译器值 |Microsoft 文档
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
ms.openlocfilehash: 61a7adf74d0b186f338220a383da6b6831013312
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255829"
---
# <a name="how-to-set-the-source-links-compiler-value"></a>如何将源链接编译器值设置
你可以使用**源链接**属性用于指定如何从源节点检索值并应用于目标节点的链接。 本主题介绍了可用的选项，并介绍如何进行选择。  
  
### <a name="to-set-the-source-links-link-property"></a>设置“源链接”链接属性  
  
1.  在 BizTalk 映射器的网格页上，单击某个链接以选择该链接。  
  
     网格页中所选链接的终结点将突出显示。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，设置**源链接**属性设置为以下选项之一：  
  
    -   **复制名称。** 源架构中的节点名称用作目标架构中链接节点的值。  
  
    -   **复制文本值。** 与源架构中的节点相应的值（元素数据或属性值）用作目标架构中链接节点的值。 此选项为默认选项。 例如，`<Node>Hello<Name>Chris</Name>Barry</Node>` 的结果为“Hello”。  
  
    -   **复制文本和 Subcontent 值。** 与源架构中的记录节点相应的值、该节点所有子节点的值以及这些子节点的子节点的值（元素数据和属性值）合并为目标架构中链接节点的值。 例如，`<Node>Hello<Name>Chris</Name>Barry</Node>` 的结果为“Hello Chris Barry”。  
  
## <a name="see-also"></a>另请参阅  
 [使用链接以指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)   
 [编译器指令和链接](../core/compiler-directives-and-links.md)