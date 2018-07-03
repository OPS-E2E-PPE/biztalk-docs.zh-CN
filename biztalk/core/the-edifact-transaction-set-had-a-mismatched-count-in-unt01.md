---
title: Edifact 事务集在 UNT01 中有不匹配的计数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2859274-78e8-4e16-92b7-c143da6da421
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717260f8e45298c19756707ed042b97ab6e207fb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016044"
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a>EDIFACT 事务集在 UNT01 中的计数不匹配
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| 产品版本 |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    事件 ID     |                                                                  -                                                                  |
|  事件源   |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                        |
|    组件    |                                                             EDI 引擎                                                              |
|  符号名称  |                                                      EfactUnhUntCountMismatch                                                       |
|  消息正文   | Edifact 事务集在 UNT01 中的计数不匹配。 UNT01 为{0}，而它应该已{1}。 此错误已纠正。 |
  
## <a name="explanation"></a>解释  
 此警告表明 UNT01 字段（为段计数）与事务集中的段数不匹配。 UNT01 的值被更改或已损坏，或者在确定计数之后添加或删除了段。 发送管道将 UNT01 字段重置为正确的段数，然后发送交换。  
  
## <a name="user-action"></a>用户操作  
 不需要用户进行任何操作。