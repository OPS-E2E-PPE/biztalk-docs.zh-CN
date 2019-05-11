---
title: 在序列化期间遇到错误。 以下错误被挂起事务集功能组中包含的 X12 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49b13038-2637-4435-91e9-d6fe2b80ca7a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beed40e2a019b957f13435a344e5a00831443a33
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348951"
---
# <a name="error-encountered-during-serialization-the-x12-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>在序列化期间遇到错误。 X12 事务集功能组中包含以下错误被挂起
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                             |
| 产品版本 |                                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                         |
|    事件 ID     |                                                                                                                     -                                                                                                                      |
|  事件源   |                                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                           |
|    组件    |                                                                                                                 EDI 引擎                                                                                                                 |
|  符号名称  |                                                                                                         X12TransactionSetSendError                                                                                                         |
|  消息正文   | 在序列化期间遇到错误。 X12 事务集 id 为 '{0}功能组 id 中包含{1}，交换中包含的 id{2}，发送方 id{3}，接收方 id{4}以下错误被挂起： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 发送管道遇到错误，在序列化传出的 X12 交换由于指出的错误与标识的事务集。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，需要使用错误消息中的信息来标识事务集中的错误，然后确定问题解决方案产品帮助中。