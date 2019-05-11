---
title: 在序列化期间根节点未位于起始元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ea4aa6f-0f9c-4b7b-b7f6-24a5ce954048
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4403e9fb895ca05d4438f1e280d79008519918d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350676"
---
# <a name="during-serialization-root-node-is-not-placed-at-start-element"></a>在序列化期间根节点是未位于起始元素
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |             在序列化期间根节点是未位于起始元素              |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为事务集未以 ST 或 UNH 标头开头。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保每个交换中事务集开头 ST 段 （对于 X12 交换） 或 UNH 段 （对于 EDIFACT 交换），然后重新提交交换。