---
title: 确认生成失败，因为已达到全局设置的 Edifact 事务集控制编号的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6adc02d7-ebc4-4da0-a19a-3a423d63499d
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2c0c6d5fe8d8296bcd8c23dfa6986b8e7acb60a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349064"
---
# <a name="acknowledgement-generation-has-failed-as-maximum-limit-of-edifact-transaction-set-control-number-has-been-reached-for-global-settings"></a>确认生成失败，因为已达到全局设置的 Edifact 事务集控制编号的最大限制
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                     |
| 产品版本 |                                                                                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                                 |
|    事件 ID     |                                                                                                                             -                                                                                                                             |
|  事件源   |                                                                                                                    BizTalk Server EDI                                                                                                                     |
|    组件    |                                                                                                                        EDI 引擎                                                                                                                         |
|  符号名称  |                                                                                                                             -                                                                                                                             |
|  消息正文   | 无法生成确认，因为“来宾”设置已达到可接受的 Edifact 事务集控制编号的最大限制。 导航到“全局”配置发送方角色屏幕、合作伙伴协议管理器中的字段 UNH 1 可重置计数器。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法生成对 EDIFACT 交换的确认，因为在确认的事务集参考编号 (UNH1) 中输入的控制编号大于 UNH1 所允许的最大值。 在这种情况下，BizTalk Server 使用 EDI 全局属性来创建确认。  
  
 事务集参考编号的最大值取决于用于参考编号的位数。 参考编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请将“UNG 和 UNH 段定义”页的事务集参考编号 (UNH1) 的参考编号字段 (UNH1.2) 重置为低于最大限制的值。 在 BizTalk Server 管理控制台的 EDI 全局属性对话框中设置此属性。