---
title: 包括的事务集数目不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db958803-4667-4558-81a6-70c62d6fe8bf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb45df387dd7c06e995c2e3a2790e6cc2af68260
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263215"
---
# <a name="number-of-included-transaction-sets-do-not-match"></a>包括的事务集的数目不匹配
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                           X12FaNumberOfTsMismatchDescription                           |
|  消息正文   |                    包括的事务集的数目不匹配                    |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 X12 交换的组中的事务集数不等于组尾部中的数量（GE01 字段）。 保留交换并且出错时挂起交换时会发生这种情况。 （如果保留交换并且出错时挂起事务集或者拆分交换，则不会发布此错误消息。）  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保组尾部的 GE01 字段中的数量与交换的组中事务集的数量相同，然后重新发送交换。