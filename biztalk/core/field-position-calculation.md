---
title: 字段位置计算 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e315f09-f2c9-49cc-8d2f-0f4f2d48fd45
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55c58f532ea64300518667d677d2248f5c1c2b6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246069"
---
# <a name="field-position-calculation"></a>字段位置计算

## <a name="overview"></a>概述
当你使用**位置长度**和**位置偏移量**属性**Field 元素**和**字段特性**中的节点你架构在平面文件消息中, 定义的位置记录布局**启动位置**和**长度**列**平面文件**选项卡中BizTalk 编辑器的计算的起始位置和长度，分别显示相关字段，并记录。  
  
> [!NOTE]
>  **平面文件**选项卡会显示作为备用选项卡式视图与 XSD 视图 BizTalk 编辑器中，当你配置了平面文件扩展使用**架构编辑器扩展**属性**架构**节点。 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 通常，特定字段的起始位置*N*是上一个字段的起始位置加上的上一个字段，以及你为字段指定的 （位置） 偏移量长度*N*.  
  
 在 Microsoft 中的所有字段的位置计算[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是，将自动执行，在快速，无需执行的命令 （如在以前版本的 BizTalk Server 需要）。  
  
## <a name="see-also"></a>另请参阅  
-  [位置记录注意事项](../core/positional-record-considerations.md)   
-  **位置的长度 （的平面文件架构的节点属性）** 和**位置偏移量 （的平面文件架构的节点属性）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]