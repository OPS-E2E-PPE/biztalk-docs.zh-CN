---
title: 事务集控制编号缺失或无效 |Microsoft Docs
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
ms.openlocfilehash: 14b8a05a636be08e605d8d2a5bae98748fd3dbb7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971678"
---
# <a name="missing-or-invalid-transaction-set-control-number"></a>事务集控制编号缺失或无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                    X12TsMissingOrInvalidTsControlNumberDescription                     |
|  消息正文   |                   事务集控制编号缺失或无效                    |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道或发送管道无法处理交换，因为事务集控制编号的值（在 ST02 字段中）缺失或无效。 事务集控制编号必须为字母数字值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
1.  确保每个事务集具有一个事务集控制编号。  
  
2.  确保每个事务集控制编号是字母数字值。