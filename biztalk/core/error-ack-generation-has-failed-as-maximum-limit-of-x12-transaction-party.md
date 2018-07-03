---
title: 错误确认生成失败，因为最大限制的 X12 事务方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c78a7cef-24ae-4d09-9043-2f53c301302d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9bc40d87e879b1ec6c23d2db0f2dfb466e6f38
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012382"
---
# <a name="error-ack-generation-has-failed-as-maximum-limit-of-x12-transaction-party"></a>错误确认生成失败，因为最大限制的 X12 事务参与方
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                          |
| 产品版本 |                                                                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                      |
|    事件 ID     |                                                                                                                  -                                                                                                                  |
|  事件源   |                                                                                                         BizTalk Server EDI                                                                                                          |
|    组件    |                                                                                                             EDI 引擎                                                                                                              |
|  符号名称  |                                                                                                                  -                                                                                                                  |
|  消息正文   | 确认生成失败，因为的可接受 X12 事务集控制编号已达到参与方的最大限制{0}。 导航到发送方角色屏幕中的“参与方”、合作伙伴协议管理器中的字段 ST 2 可重置计数器 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法生成对 X12 交换的确认，因为在确认的事务集控制编号 (ST2) 中输入的控制编号大于 ST2 所允许的最大值。 在这种情况下，BizTalk Server 使用 EDI 参与方属性来创建确认。  
  
 事务集控制编号的最大值取决于用于控制编号的位数。 所有三个字段的最大长度是 9；前缀和后缀字段的最大长度是 8。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请将“GS 和 ST 段定义”页的事务集控制编号 (ST2) 的控制编号字段 (ST2.2) 重置为低于最大限制的值。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的“EDI 全局属性”对话框中设置此属性。