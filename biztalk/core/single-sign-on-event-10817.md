---
title: 单一登录：Event 10817 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c4f05181db88c58a5e29857cbe2ce80bb3ab369
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396106"
---
# <a name="single-sign-on-event-10817"></a>单一登录：事件 10817
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10817                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            不可用                             |
|  符号名称  |              ENTSSO_E_NOTIFICATION_NOT_FOUND               |
|  消息正文   |         找不到指定的通知。          |
  
## <a name="explanation"></a>解释  
 密码更改所指定的通知找不到 GUID。  
  
## <a name="user-action"></a>用户操作  
 请参阅此密码同步适配器，以确定相应的通知 GUID 的配置。