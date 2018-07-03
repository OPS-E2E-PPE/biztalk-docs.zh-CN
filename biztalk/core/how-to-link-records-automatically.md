---
title: 如何自动链接记录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc2926c7-07c2-45d1-afde-d3f894f6b88d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77d4c703a890398516ccbb9a9b4d1fafff22a8f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018160"
---
# <a name="how-to-link-records-automatically"></a>如何自动链接记录
当您在源架构和目标架构的两个记录元素之间创建链接时，BizTalk 映射器会通过快捷菜单为您提供实时帮助。 本主题提供了有关如何使用快捷菜单执行链接操作的信息。  
  
 可以按以下方式自动创建记录到记录的链接：  
  
- **直接链接。** 使用该技术，BizTalk 映射器会将来自源架构的记录链接到目标架构中所选定的记录。  
  
- **按结构链接。** 使用此方法，BizTalk 映射器尝试匹配**记录**并**字段**中的节点**记录**这些结构根据要链接的节点**记录**节点，而不管这些结构中的相应节点的名称。  
  
- **按名称进行链接。** 使用此方法，BizTalk 映射器尝试匹配**记录**并**字段**中的节点**记录**的名称根据要链接的节点在相应节点，而不管其结构**记录**要链接的节点。  
  
- **大容量复制。** **批量复制**functoid，映射可使用包含的架构**任何**并**anyAttribute**元素。 有关 BizTalk 映射器中可用 functoid 的信息，请参阅[使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)。  
  
  要使用快捷菜单，连接必须来自子层次结构母节点，并且必须终止于另一个子层次结构母节点。 快捷菜单可帮助确定应当在两个架构节点之间创建哪种类型的链接。 以下是在快捷菜单上的可用选项的列表。  
  
|映射来源|映射到|链接行为|  
|--------------|------------|-------------------|  
|字段|字段|直接链接|  
|录制|字段|直接链接|  
|字段|录制|直接链接|  
|录制|录制|此时将出现快捷菜单|  
  
## <a name="prerequisites"></a>必要條件  
 这些操作需要 BizTalk 映射器正在运行。  
  
### <a name="to-link-the-record-elements-directly"></a>若要直接链接记录元素，请执行以下操作：  
  
1.  通过鼠标拖动源架构中的子层次结构母节点，然后将其放到目标架构中的子层次结构母节点。  
  
2.  在快捷菜单上，单击**直接链接**。 下表显示了从所选的源节点到目标节点中出现的直接链接。  
  
     ![从源节点到目标节点的直接链接](../core/media/linkrecordelements-directly.gif "Linkrecordelements_directly")  
  
    > [!IMPORTANT]
    >  您可以将源架构中子层次结构母节点中的直接链接，置于目标架构中的非子层次结构母节点中。 下表显示了作为源架构中母节点的“Root”到作为目标架构中子“Root”的“Record1”的直接链接。  
  
     ![直接链接记录元素](../core/media/linkrecordelements-directly2.gif "Linkrecordelements_directly2")  
  
### <a name="to-link-the-record-elements-by-structure"></a>若要通过结构链接记录元素，请执行以下操作：  
  
1.  通过鼠标拖动源架构中的子层次结构母节点，然后将其放到目标架构中的子层次结构母节点。  
  
2.  在快捷菜单上，单击**按结构链接**。 BizTalk 映射器会匹配**记录**并**字段**中的节点**记录**这些结构根据要链接的节点**记录**节点，而不管这些结构中的相应节点的名称。  
  
     ![链接记录元素&#95;结构](../core/media/linkrecordelements-bystructure.gif "Linkrecordelements_bystructure")  
  
    > [!IMPORTANT]
    >  当您尝试通过结构将源架构中的子层次结构母节点链接到目标架构中的非子层次结构母节点，BizTalk 映射器会将源母节点的子项分别映射到目标母节点的子项。 下图显示了通过结构进行链接。  
  
     ![按结构链接记录元素](../core/media/linkrecordelements-bystructure2.gif "Linkrecordelements_bystructure2")  
  
### <a name="to-link-the-record-elements-by-name"></a>若要通过名称链接记录元素，请执行以下操作：  
  
1.  通过鼠标拖动源架构中的子层次结构母节点，然后将其放到目标架构中的子层次结构母节点。  
  
2.  在快捷菜单上，单击**按名称链接**。 BizTalk 映射器将尝试匹配**记录**并**字段**中的节点**记录**根据相应节点，而不考虑的名称要链接的节点其结构，在**记录**要链接的节点。  
  
     ![按名称链接记录元素](../core/media/linkrecordelements-byname.gif "Linkrecordelements_byname")  
  
    > [!IMPORTANT]
    >  您可以将源架构中子层次结构母节点中的直接链接，链接到目标架构中的非子层次结构母节点。 BizTalk 映射器会匹配源节点的子项名称和目标节点的子项名称 如果它找到了完全相同的子项，则会在各自的子项之间建立链接。 下图说明了这一概念。  
  
## <a name="to-link-using-a-mass-copy-functoid"></a>要使用一个批量复制 functoid 链接  
 **批量复制**functoid，映射可使用包含的架构**任何**并**anyAttribute**元素。 实际上，这些元素是 XML 架构定义语言为匹配未知结构或属性而提供的通配符。  
  
 除了处理未知结构的数据**批量复制**functoid，您可以简化架构开发： 需详细指定仅将处理的架构部分。  
  
 ![按批量复制 functoid 链接记录元素](../core/media/linkrecordelements-masscopyfunctoid.gif "Linkrecordelements_MassCopyfunctoid")  
  
 有关详细信息**批量复制**functoid，请参阅[批量复制 Functoid](../core/mass-copy-functoid.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)   
 [如何向映射添加批量复制 Functoid](../core/how-to-add-mass-copy-functoids-to-a-map.md)