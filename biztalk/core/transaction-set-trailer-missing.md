---
title: 事务集尾部缺失 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07753300-fe47-47a6-a947-6abec10c1c90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f75851b8c2b781d943611657e016775c8bce95b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279754"
---
# <a name="transaction-set-trailer-missing"></a>事务集尾部缺失
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                             X12TsTrailerMissingDescription                             |
|  消息正文   |                            事务集尾部缺失                             |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的事务集或发送管道无法处理传出的事务集，因为该事务集不包含 SE 事务集尾部（对于 X12 事务集）或 UNT 消息尾部（对于 EDIFACT 事务集）。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让事务集的发送方向事务集中添加一个 SE 事务集尾部（对于 X12 事务集）或 UNT 消息尾部（对于 EDIFACT 事务集），然后重新发送事务集。