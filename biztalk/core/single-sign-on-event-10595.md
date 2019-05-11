---
title: 单一登录：Event 10595 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1517478c-7217-4e34-a5cb-ff7deea367ed
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6aecfef61ece56075c4eb0c47ba7852380d4c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397843"
---
# <a name="single-sign-on-event-10595"></a>单一登录：事件 10595
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                             企业单一登录                                                                                              |
| 产品版本 |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    事件 ID     |                                                                                                       10595                                                                                                        |
|  事件源   |                                                                                                       ENTSSO                                                                                                       |
|    组件    |                                                                                                        不可用                                                                                                         |
|  符号名称  |                                                                                           SSO_WARN_APP_INCOMPLETE_FIELDS                                                                                           |
|  消息正文   | 无法启用应用程序，因为的字段不全 application.%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 定义的字段数: %2 %r<br /><br /> 创建的字段数： %3 |
  
## <a name="explanation"></a>解释  
 在创建时应用程序在 API 级别，您指定的字段 (即用户 Id 和密码) 会定义应用程序的数目。 此外必须创建每个已定义的字段。 此警告消息列出了应用程序名称、 字段定义，数和创建的字段数。  
  
## <a name="user-action"></a>用户操作  
 确定哪些字段已定义但未创建，然后返回并创建它们。