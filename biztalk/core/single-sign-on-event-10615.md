---
title: 单一登录：Event 10615 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5dd0041-2dfd-4fd1-97ec-f9fc719a6fcc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adece23afc79fcff2d4c0168aaee4b38819f5e50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397690"
---
# <a name="single-sign-on-event-10615"></a>单一登录：事件 10615
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                企业单一登录                                                                                                                |
| 产品版本 |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    事件 ID     |                                                                                                                          10615                                                                                                                          |
|  事件源   |                                                                                                                         ENTSSO                                                                                                                          |
|    组件    |                                                                                                                           不可用                                                                                                                           |
|  符号名称  |                                                                                                            SSO_WARN_NO_UPDATE_TICKET_TIMEOUT                                                                                                            |
|  消息正文   | 客户端用户必须是 SSO 管理员帐户的成员，才能更改 application.%r 的票证超时值<br /><br /> 客户端用户: %1 %r<br /><br /> SSO Administrators: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 错误代码： %4 |
  
## <a name="explanation"></a>解释  
 客户端用户必须是 SSO 管理员帐户的成员，才能更改应用程序的票证超时值。  
  
## <a name="user-action"></a>用户操作  
 具有系统管理员帮助您找到要进行此更改 SSO 管理员帐户的成员。