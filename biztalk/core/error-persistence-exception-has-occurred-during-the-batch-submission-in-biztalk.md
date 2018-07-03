---
title: 在批处理业务流程的批提交期间出现持久性异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6e832f-9d01-46e7-aaf5-2b402d509fac
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8a1277dd26fcb2036e3378f7fa6d22067a1f7e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020915"
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a>批处理业务流程的批提交过程中发生了一个持久性异常
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| 产品版本 |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    事件 ID     |                                                                                             -                                                                                              |
|  事件源   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                   |
|    组件    |                                                                                      批处理引擎                                                                                       |
|  符号名称  |                                                                                PersistenceExceptionOccured                                                                                 |
|  消息正文   | 在批处理业务流程中的批处理提交期间出现持久性异常。 批处理 Id = {0}，ErrorMessage = {1}。 请检查发送端口订阅并进行修改。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法发送批处理交换，因为该交换未订阅任何发送端口。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保发送端口订阅通过设置以下筛选器属性的发送端口的批处理： EDI。DestinationPartyName = \<PartyName\>，EDI。BatchEncodingType = EDIFACT 或 X12 以及 EDI。ToBeBatched = False。