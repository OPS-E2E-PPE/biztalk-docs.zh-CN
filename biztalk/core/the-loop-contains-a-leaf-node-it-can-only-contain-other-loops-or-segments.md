---
title: "循环包含叶节点。 它只能包含其他循环或段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a0ee5e6-519d-4c95-8681-de5a37741d56
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d03349389fb108d434cce67afc5be13fd2a3d513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-loop-contains-a-leaf-node-it-can-only-contain-other-loops-or-segments"></a>循环包含叶节点。 它只能包含其他循环或段
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|SchemaCode125ELoopContainsLeafNode|  
|消息正文|循环包含叶节点。 它只能包含其他循环或段|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示接收管道无法处理传入的交换，因为文档架构不符合该交换。 在这种情况下，循环包含 childless 叶节点，而其他循环或段可能仅包含循环，则指定的架构。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，具有交换修复循环的发送方，以便其不包含叶节点，然后重新发送该交换。