---
title: 在序列化期间遇到错误。 以下错误被挂起的 Edifact 事务集功能组中包含 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b76086-334b-45fb-85f8-82e3335daac4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c89d4300d54bc7e524f9f33aea4689a6cdc4bc27
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007654"
---
# <a name="error-encountered-during-serialization-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>在序列化期间遇到错误。 功能组中包含的 EDIFACT 事务集由于以下错误被挂起
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                               |
| 产品版本 |                                                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                           |
|    事件 ID     |                                                                                                                       -                                                                                                                        |
|  事件源   |                                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                             |
|    组件    |                                                                                                                   EDI 引擎                                                                                                                   |
|  符号名称  |                                                                                                          EfactTransactionSetSendError                                                                                                          |
|  消息正文   | 在序列化期间遇到错误。 Edifact 事务集 id 为 '{0}功能组 id 中包含{1}，交换中包含的 id{2}，发送方 id{3}，接收方 id{4}以下错误被挂起： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于通过标识的事务集指明的错误，在序列化传出的 EDIFACT 交换期间 EDI 发送管道遇到错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在产品帮助中确定问题解决方案。