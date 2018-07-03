---
title: 单一登录： 事件 10817 |Microsoft Docs
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
ms.openlocfilehash: 7e42873f0b56c43a7c997a2476ba2b15148d4639
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979190"
---
# <a name="single-sign-on-event-10817"></a>单一登录： 事件 10817
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10817                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N/A                             |
|  符号名称  |              ENTSSO_E_NOTIFICATION_NOT_FOUND               |
|  消息正文   |         找不到指定的通知。          |
  
## <a name="explanation"></a>解释  
 无法找到密码更改所指定的通知 GUID。  
  
## <a name="user-action"></a>用户操作  
 查看此密码同步适配器的配置来确定与通知相应的 GUID。