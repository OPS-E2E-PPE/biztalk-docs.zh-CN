---
title: 可接受 Edifact 事务集控制编号已达到来宾设置的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3924a18c-87bc-4727-b7cd-598d3e5ade2a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c539b6a3380001927f02bf3d828b707a7807cf4f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388722"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-guest-settings"></a>已达到来宾设置的可接受 Edifact 事务集控制编号最大限制
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                 |
| 产品版本 |                                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                             |
|    事件 ID     |                                                                                                         -                                                                                                          |
|  事件源   |                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                               |
|    组件    |                                                                                                     EDI 引擎                                                                                                     |
|  符号名称  |                                                                                            GlobalEdifactUnhNumberError                                                                                             |
|  消息正文   | 已达到来宾设置的可接受 Edifact 事务集控制编号最大限制。 导航到全局配置接收方角色屏幕、 合作伙伴协议管理器中的字段 UNH 1 可重置计数器 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道不无法处理传出的交换，因为在全局设置中，特别是字段 UNH1.2 中的参考编号指定的 UNH1 字段中的事务集控制编号已超过允许的最大值。 组控制编号的最大值取决于 UNH1 中三个字段的值。 最大字符数是 14 个字段 UNH1.2，13 个 UNH1.1 中的前缀和 UNH1.3 中的后缀的 13 和 14 个所有三个字段的组合中的参考编号。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按照如下方式重置事务集控制编号的参考编号字段 (UNH1.2)：  
  
1.  在 EDI 全局属性对话框中，打开 UNH 段定义页。  
  
2.  单击与 UNH1 字段关联的“编辑”字段。  
  
3.  将组控制编号 （UNH1.2 中的参考编号） 的中间字段设置为新值中，以便该字段具有可接受的位数。