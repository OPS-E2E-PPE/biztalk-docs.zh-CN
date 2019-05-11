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
ms.openlocfilehash: 428704c78c3d6b615f0272927b03fb57aa66d91b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298794"
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a>Edifact 事务集在 UNT01 中有计数不匹配
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| 产品版本 |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    事件 ID     |                                                                  -                                                                  |
|  事件源   |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                        |
|    组件    |                                                             EDI 引擎                                                              |
|  符号名称  |                                                      EfactUnhUntCountMismatch                                                       |
|  消息正文   | Edifact 事务集在 UNT01 中有计数不匹配。 UNT01 为{0}，而它应该已{1}。 已纠正。 |
  
## <a name="explanation"></a>解释  
 此警告表明 UNT01 字段，它是段计数，没有与事务集中的段数不匹配。 UNT01 的值已更改或损坏，或者添加或删除后确定计数段。 发送管道将 UNT01 字段重置为正确数量的段，，然后发送交换。  
  
## <a name="user-action"></a>用户操作  
 不不需要任何用户操作。