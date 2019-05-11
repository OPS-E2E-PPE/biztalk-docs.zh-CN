---
title: 事务集控制编号不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c4b0c3f-f3be-4c2c-8719-8e40aa7122b9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3081249fba97e9bf478c8435952c8e5c5ecb914
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279939"
---
# <a name="transaction-set-control-number-mismatch"></a>事务集控制编号不匹配
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                         X12TsControlNumberMismatchDescription                          |
|  消息正文   |                        事务集控制编号不匹配                         |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道拒绝传入事务集，因为事务集的 SE02 字段中包含的控制编号与 ST02 字段中的控制编号不匹配。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让发送方的事务集更改为与 ST02 字段中的控制编号相同所拒绝的事务集的 SE02 字段中的控制编号，然后重新发送交换。