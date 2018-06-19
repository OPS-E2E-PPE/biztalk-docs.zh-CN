---
title: Doctype 无效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67233aae-65c0-4689-a4b3-60a48132343a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fec7dc4f2dfed0c8e8b8fcde13593d4e29997f7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239141"
---
# <a name="doctype-is-invalid"></a>Doctype 无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|DocTypeInvalidFormat|  
|消息正文|Doctype {0} 无效。 无法确定一个或多个命名空间、版本或事务集 ID|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道无法处理传入的交换，因为未正确发现架构。  
  
 对于 X12，目标命名空间是在“EDI 属性”对话框的“X12 交换处理属性”页的“启用自定义事务集定义”网格中确定的。 消息中的 GS02 和 ST01 值必须与某行网格中的相应值匹配，才能正确标识目标命名空间。 用于事务集的架构名称是通过将传入事务集中的版本（GS08 的前 5 个字符）和 doctype (ST01) 添加到指定的目标命名空间来创建的。  
  
 对于 EDIFACT，目标命名空间是在“EDI 属性”对话框的“EDIFACT 交换处理属性”页的“启用自定义事务集定义”网格中确定的。 消息中的 UNH2.1、UNH2.2、UNH2.3、UNH2.5、UNG2.1 和 UNG2.2 值必须与某行网格中的对应值匹配，才能正确标识目标命名空间。 通过向所标识的目标命名空间中添加传入的事务集的 UNH2.2 中的消息版本号、UNH2.3 中的消息发行版号以及 UNH2.1 中的消息类型来创建将用于事务集的架构的名称。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行，如下所示：  
  
1.  确保事务集的架构的命名空间能够由“EDI 属性”对话框的“交换处理属性”页的“启用自定义事务集定义”网格中的某一行正确标识。 否则，请更改网格中的相应值。  
  
2.  如果命名空间已正确标识，则确定用于标识架构的值是否正确。 对于 X12，这些值是传入事务集中的版本（GS08 的前 5 个字符）和 doctype (ST01)。 对于 EDIFACT，它们是传入的事务集的 UNH2.2 中的消息版本号、UNH2.3 中的消息发行版号以及 UNH2.1 中的消息类型。 如果这些值不正确，则让事务集的发送方更改这些字段的值，然后重新发送消息。