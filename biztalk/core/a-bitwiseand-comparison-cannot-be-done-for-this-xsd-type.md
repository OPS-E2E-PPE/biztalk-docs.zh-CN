---
title: "BitwiseAnd 比较无法在此 XSD 类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bc2351-c002-458a-9d35-5fdcc91c6a0e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c0f3aa2b3ae7c60f3c104daaa885ab7ae8cc7ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="a-bitwiseand-comparison-cannot-be-done-for-this-xsd-type"></a>无法为此 XSD 类型完成 BitwiseAnd 比较
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|Err_InvalidBitwiseComparision|  
|消息正文|对于此 XSD 类型，无法进行 BitwiseAnd 比较。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 在尝试决定批处理消息时无法比较上下文属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定 CSD 类型无法进行按位比较的上下文属性。