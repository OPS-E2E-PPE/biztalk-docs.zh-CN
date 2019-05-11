---
title: 单一登录：Event 11013 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 450836dc-ddeb-4423-9966-69ad173f2c87
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9a59bb13c413489f3b950409fe886c7ddc2e0d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267294"
---
# <a name="single-sign-on-event-11013"></a>单一登录：事件 11013
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                      |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                      企业单一登录                                                                                       |
| 产品版本 |                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                      |
|    事件 ID     |                                                                                                11013                                                                                                 |
|  事件源   |                                                                                                ENTSSO                                                                                                |
|    组件    |                                                                                                 不可用                                                                                                  |
|  符号名称  |                                                                                        SSO_WARN_NOT_APP_USER                                                                                         |
|  消息正文   | 客户端用户不是应用程序用户 account.%r 的成员<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户： %2\\%3 %r<br /><br /> 应用程序名称: %4 %r<br /><br /> 应用程序用户： %5 |
  
## <a name="explanation"></a>解释  
 客户端用户不是应用程序用户帐户的成员。 审核级别设置为高时，才会显示此警告。  
  
## <a name="user-action"></a>用户操作  
 若要纠正这种情况，您必须使客户端用户应用程序用户帐户的成员。 若要停止在将来出现此警告消息，则可以降低审核级别。