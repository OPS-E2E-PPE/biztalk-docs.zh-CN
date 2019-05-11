---
title: 路由业务流程执行期间发生了异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68ec8921-ba05-496e-8dcc-fd8994fcb8b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c20f6f35c6ea8bcbe4f7f3dd02fd3ff4831f4217
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359955"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-routing-orchestration"></a>路由业务流程执行期间出现异常
## <a name="details"></a>详细信息  
  
|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  产品名称   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| 产品版本 |                   [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                   |
|    事件 ID     |                                               -                                                |
|  事件源   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI     |
|    组件    |                                        批处理引擎                                         |
|  符号名称  |                                 ExceptionOccuredDuringRouting                                  |
|  消息正文   | 路由业务流程执行期间出现异常。 错误消息 = {0} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明，路由业务流程无法正确处理，每个 XML 批元素副本因为 ErrorMessage 字段中指出的错误条件。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，确定 ErrorMessage 字段中为的错误条件，解决错误，并重新提交消息。