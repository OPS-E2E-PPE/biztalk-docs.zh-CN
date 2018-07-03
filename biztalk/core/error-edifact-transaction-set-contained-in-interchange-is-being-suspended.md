---
title: 在解析过程中遇到错误。 以下错误被挂起的 Edifact 事务集 （没有组） 的交换中包含 |Microsoft Docs
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
ms.openlocfilehash: c2e0d8e2b03decf2db806a08f082b7aace276a8e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006414"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a>在解析过程中遇到错误。 以下错误被挂起的 Edifact 事务集包含在交换 （没有组）
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                   |
| 产品版本 |                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                               |
|    事件 ID     |                                                                                                           -                                                                                                           |
|  事件源   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                 |
|    组件    |                                                                                                      EDI 引擎                                                                                                       |
|  符号名称  |                                                                                      EfactTransactionSetReceiveErrorWithoutGroup                                                                                      |
|  消息正文   | 在解析过程中遇到错误。 Edifact 事务集 id 为 '{0}（没有组） id 的交换中包含{1}，发送方 id{2}，接收方 id{3}以下错误被挂起： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于通过交换中标识的事务集指明的错误，在分析传入的 EDIFACT 交换（该交换没有组）时 EDI 接收管道遇到错误。 请注意，该事务集不在交换的组中。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在产品帮助中确定问题解决方案。