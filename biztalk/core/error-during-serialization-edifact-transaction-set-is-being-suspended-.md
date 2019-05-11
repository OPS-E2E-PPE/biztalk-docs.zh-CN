---
title: Edifact 事务集包含在交换错误 |Microsoft Docs
description: 在序列化期间遇到错误。 以下错误被挂起的 Edifact 事务集包含在交换 （没有组）
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 368b5ad0f26b642d4d7f3575a8c7a03abac4ca0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389195"
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a>Edifact 事务集是已挂起的错误和详细信息

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                              |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                      |
| 产品版本 |                                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                  |
|    事件 ID     |                                                                                                              -                                                                                                               |
|  事件源   |                                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                    |
|    组件    |                                                                                                          EDI 引擎                                                                                                          |
|  符号名称  |                                                                                           EfactTransactionSetSendErrorWithoutGroup                                                                                           |
|  消息正文   | 在序列化期间遇到错误。 Edifact 事务集 id 为 '{0}（没有组） id 的交换中包含{1}，发送方 id{2}，接收方 id{3}以下错误被挂起： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 发送管道遇到错误，指出的错误，使用标识的事务集由于序列化传出的 EDIFACT 交换时。 请注意，事务集不在交换中组中。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，需要使用错误消息中的信息来标识事务集中的错误，然后确定问题解决方案。