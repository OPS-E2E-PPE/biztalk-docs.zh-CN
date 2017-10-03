---
title: "查找启动元素时，发现结束元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7690744-a795-47cc-bc66-a0314a4cc320
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dacaa096b15a6f2969ed56b5bac2138876a6095
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a>查找 Start 元素时发现一个 End 元素
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EndElementFoundWhenLookingForStartElement|  
|消息正文|名为 {0} EndElement 时，发现，寻找与名称 {1}，在深度 {2} StartElement|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法处理传入的 XML 消息（分析后）或传出的 XML 消息（序列化前），因为 XML 消息未通过验证。 XML 消息不包含标头或数据元素的结束标记。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请向 XML 消息中添加相应的结束标记或尾部，然后重新发送消息。