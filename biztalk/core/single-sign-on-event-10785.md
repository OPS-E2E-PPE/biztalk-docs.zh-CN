---
title: 单一登录： 事件 10785 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4f4a2ad-a378-4806-ba16-d2872c4773f1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96194f9ab4a057301e9c0a20d4c222f730e70bfb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991510"
---
# <a name="single-sign-on-event-10785"></a>单一登录： 事件 10785
## <a name="details"></a>详细信息  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  产品名称   |                   企业单一登录                    |
| 产品版本 |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    事件 ID     |                             10785                              |
|  事件源   |                             ENTSSO                             |
|    组件    |                              N/A                               |
|  符号名称  |                       ENTSSO_E_DB_ACCESS                       |
|  消息正文   | 尝试访问 SSO 数据库时出错。 |
  
## <a name="explanation"></a>解释  
 ENTSSO 数据库可能处于脱机状态。  
  
## <a name="user-action"></a>用户操作  
 请系统管理员检查 ENTSSO 服务器上的事件日志。