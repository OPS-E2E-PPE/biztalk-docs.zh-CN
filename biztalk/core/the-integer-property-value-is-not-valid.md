---
title: "整数属性值不是有效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31d4e9a7-4336-40f1-997a-9f79d86b26d2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acbb350d9dd8fe77e42bb7e8b3cdf4617c87a2f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-integer-property-value-is-not-valid"></a>integer 属性值无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|Err_InvalidInteger|  
|消息正文|integer 属性值无效。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 在尝试决定是否批处理消息时无法比较上下文属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定 XSD 类型为 integer 且值无效的上下文属性。