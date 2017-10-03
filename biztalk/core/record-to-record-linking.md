---
title: "记录移动链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a3fa4d7-5689-4f55-af1b-369defa37037
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac6abc3d27ad3ee2f135e3ff5c8c1749fcae5f4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="record-to-record-linking"></a>到记录链接

## <a name="overview"></a>概述
在 Microsoft 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可以使用 BizTalk 映射程序多个之间创建链接的源和目标架构在同一时间类似部分。 在以前版本的 BizTalk Server 中，只能一次一个地分别创建此类链接。 有两种不同类型的记录将链接，在正被链接，，如下所示的源和目标架构记录的结构的相似性的程度上基于每个适用于不同方案的：  
  
-   **链接的结构。** 如果源架构和目标架构中所链接记录的结构相同或非常相似，则使用结构链接。  
  
-   **名称匹配链接。** 如果源架构和目标架构中链接的记录也具有相似结构，并具有匹配的记录和字段名称，但结构性异常多于结构链接的可处理量，则使用名称匹配链接。  
  
    > [!NOTE]
    >  记录的链接将应用于链接仅在使用配置的值复制**源链接**属性。  
  
## <a name="record-to-record-linking-structure-links"></a>记录的链接： 结构链接  
 如果源架构和目标架构中要链接的记录具有相同或几乎完全相同的结构，请使用结构链接。  
  
 如果架构的结构完全相同，则只需在每个架构的根节点处添加一个链接。 在快捷菜单中，选择所需的链接模式。  
  
 如果架构中特定记录的结构完全相同，则只需在这两个架构的这些记录间添加一个链接。 在快捷菜单中，选择所需的链接模式。  
  
 有关如何配置记录到记录的信息作为使用任一结构链接链接或名称匹配链接，请参阅[自动链接记录](../core/how-to-link-records-automatically.md)。  
  
> [!NOTE]
>  结构链接是记录到记录的链接的默认类型。  
  
## <a name="record-to-record-linking-name-matching-links"></a>记录的链接： 名称匹配的链接  
 如果源架构和目标架构中要链接的记录结构非常相似但又不完全相同，请使用名称匹配链接。 例如，源架构或目标架构在要链接的节点中可能比另一个架构具有更多的从属记录或字段。  
  
 若要创建具有几乎匹配的结构，包括整个架构 （如果适用），你源和目标架构的部分之间的名称匹配链接创建从子层次结构的父节点发起和结束在另一台的链接子层次结构的父节点。 在快捷菜单中，选择所需的模式。 链接这些节点后，将自动为源架构和目标架构中具有相同名称以及相同子结构的所有从属记录和字段创建链接。  
  
 有关如何配置记录到记录的信息作为使用任一结构链接链接或名称匹配链接，请参阅[自动链接记录](../core/how-to-link-records-automatically.md)。  
  
## <a name="see-also"></a>另请参阅  
 [自动将记录的链接](../core/how-to-link-records-automatically.md)   
 [编辑链接属性](../core/how-to-edit-link-properties.md)