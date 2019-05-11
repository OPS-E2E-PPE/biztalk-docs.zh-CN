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
ms.openlocfilehash: c9dca8c7d26eb826ff6da339ae77040e5527238c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324522"
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
 此错误/警告/信息事件表明接收或发送管道不无法处理 EDIFACT 交换，因为事务集标识符 （在 UNH2.1 字段中） 的值缺失或具有无效值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换具有 UNH2.1 字段的值。 验证 UNH2.1 的值是有效的一位到 6 位文档类型指示符。