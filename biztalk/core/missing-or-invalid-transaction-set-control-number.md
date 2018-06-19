---
title: 缺少或无效的事务集控制编号 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6064b974-e8cd-4486-abc2-010afe0d956e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e9448c9be2cd05c7f7d8c18c13730933c1b5824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262989"
---
# <a name="missing-or-invalid-transaction-set-control-number"></a>事务集控制编号缺失或无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12TsMissingOrInvalidTsControlNumberDescription|  
|消息正文|事务集控制编号缺失或无效|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道或发送管道无法处理交换，因为事务集控制编号的值（在 ST02 字段中）缺失或无效。 事务集控制编号必须为字母数字值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
1.  确保每个事务集具有一个事务集控制编号。  
  
2.  确保每个事务集控制编号是字母数字值。