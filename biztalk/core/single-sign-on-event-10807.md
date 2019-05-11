---
title: 单一登录：Event 10807 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 882c01c6-70db-4986-9f4b-f08335424250
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 774769a952436729e3a32c5aeaf9d3d8eb98243c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267524"
---
# <a name="single-sign-on-event-10807"></a>单一登录：事件 10807
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10807                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            不可用                             |
|  符号名称  |        ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS         |
|  消息正文   |            未确认的通知太多。             |
  
## <a name="explanation"></a>解释  
 密码更改通知每次发送、 接收一条确认消息。 在这种情况下，已超过未确认通知的限制。  
  
## <a name="user-action"></a>用户操作  
 检查密码同步适配器。