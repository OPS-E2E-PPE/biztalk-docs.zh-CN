---
title: 事务集标识符缺失或无效或重复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8580aab2-9fa4-43fb-b643-10621926591e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2165168f092dfb2e3b82116b1fb32153b5f4551f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324604"
---
# <a name="missing-or-invalid-or-duplicate-transaction-set-identifier"></a>事务集标识符缺失或无效或重复
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                      X12TsMissingOrInvalidTsIdentiferDescription2                      |
|  消息正文   |            事务集标识符缺失或无效或重复{0}            |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道或发送管道无法处理 X12 交换，因为事务集标识符的值（在 ST01 字段中）缺失、重复或无效。 如果文档架构没有 ST 标头和 SE 尾部，则可能会发生此错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换具有与 ST01 字段对应的值并且确保架构具有与 ST 标头和 SE 尾部对应的条目。 验证 ST01 的值是否是有效的三位文档类型的表示符。 验证 ST01 字段是否未与另一个事务集的 ST01 字段重复。