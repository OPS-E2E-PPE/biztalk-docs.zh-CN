---
title: 解析期间遇到错误。 以下错误被挂起的 Edifact 事务集 （没有组） 的交换中包含 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 901fef68-4649-480a-997c-b061d7d069d6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fe401b82d9492590d332dcbdb7d6d59bfaf3c91
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348902"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a>解析期间遇到错误。 以下错误被挂起的 Edifact 事务集包含在交换 （没有组）
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                   |
| 产品版本 |                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                               |
|    事件 ID     |                                                                                                           -                                                                                                           |
|  事件源   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                 |
|    组件    |                                                                                                      EDI 引擎                                                                                                       |
|  符号名称  |                                                                                      EfactTransactionSetReceiveErrorWithoutGroup                                                                                      |
|  消息正文   | 解析期间遇到错误。 Edifact 事务集 id 为 '{0}（没有组） id 的交换中包含{1}，发送方 id{2}，接收方 id{3}以下错误被挂起： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道遇到错误时在交换中指出的错误，标识的事务由于分析传入的 EDIFACT 交换没有组设置。 请注意，事务集不在交换中组中。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，需要使用错误消息中的信息来标识事务集中的错误，然后确定问题解决方案产品帮助中。