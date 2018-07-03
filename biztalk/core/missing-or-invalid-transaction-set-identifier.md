---
title: 事务集标识符缺失或无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 282c8128-7d23-44e2-bf44-e90e52cb5fb1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f0444468b7f7ff52b38bcd8db01a6bded5ed0a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009926"
---
# <a name="missing-or-invalid-transaction-set-identifier"></a>事务集标识符缺失或无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                     EfactTsMissingOrInvalidTsIdentiferDescription                      |
|  消息正文   |                     事务集标识符缺失或无效                      |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道或发送管道无法处理 EDIFACT 交换，因为事务集标识符的值（在 UNH2.1 字段中）缺失或无效。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换具有 UNH2.1 字段的值。 验证 UNH2.1 的值是否是有效的 1 位到 6 位文档类型的表示符。