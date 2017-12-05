---
title: "在批次提交数据封闭在批处理的业务流程期间出现持久性异常 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf6e832f-9d01-46e7-aaf5-2b402d509fac
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c01e77ab46b1ef23b15bc8e288ff7f151d1563cb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a>批处理业务流程的批提交过程中发生了一个持久性异常
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|批处理引擎|  
|符号名称|PersistenceExceptionOccured|  
|消息正文|在批处理业务流程中的批处理提交期间出现持久性异常。 批 Id = {0}，ErrorMessage = {1}。 请检查发送端口订阅并进行修改。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法发送批处理交换，因为该交换未订阅任何发送端口。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保订阅到批次的发送端口通过设置发送端口的以下筛选器属性： EDI。DestinationPartyName = \<PartyName\>，EDI。BatchEncodingType = EDIFACT 或 X12，和 EDI。ToBeBatched = False。