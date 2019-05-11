---
title: 单一登录：Event 10785 | Microsoft Docs
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
ms.openlocfilehash: fed42624f0efc2c4ae2d13c35d48ca47a87e35cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278017"
---
# <a name="single-sign-on-event-10785"></a>单一登录：事件 10785
## <a name="details"></a>详细信息  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  产品名称   |                   企业单一登录                    |
| 产品版本 |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    事件 ID     |                             10785                              |
|  事件源   |                             ENTSSO                             |
|    组件    |                              不可用                               |
|  符号名称  |                       ENTSSO_E_DB_ACCESS                       |
|  消息正文   | 尝试访问 SSO 数据库时出错。 |
  
## <a name="explanation"></a>解释  
 ENTSSO 数据库可能处于脱机状态。  
  
## <a name="user-action"></a>用户操作  
 具有系统管理员检查 ENTSSO 服务器上的事件日志。