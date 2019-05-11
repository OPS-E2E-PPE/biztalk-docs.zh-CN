---
title: 与 BatchId 关联的协议未启用或已过期。 批处理不能继续 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d92cb07-7646-42b3-90a8-18acbcd145cd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee993aeab2f3edc6ef092cea38acfc86a3dc2574
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346792"
---
# <a name="the-agreement-associated-with-batchid-is-not-enabled-or-has-expired-batching-cannot-continue"></a>与 BatchId 关联的协议未启用或已过期。 批处理无法继续
## <a name="details"></a>详细信息  
  
|                 |                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------|
|  产品名称   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| 产品版本 |                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    事件 ID     |                                                 -                                                  |
|  事件源   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI       |
|    组件    |                                             EDI 引擎                                             |
|  符号名称  |                                    ErrorBatchAgreementDisabled                                     |
|  消息正文   | 与 BatchId 关联的协议{0}未启用或已过期。 批处理不能继续。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法启动批处理或无法处理批处理消息，因为协议已过期。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保所包含协议的“协议”属性中存在具有给定 Id 的批处理并且确保其开始和结束日期落在协议的开始和结束日期之内。 还要确保启用该协议。