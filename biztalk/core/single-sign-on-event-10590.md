---
title: 单一登录：Event 10590 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd8c3804-5c84-403f-881b-e4b101c2323a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21e9ed1ffdee369ccb357cb7b7f20424cb61b474
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271034"
---
# <a name="single-sign-on-event-10590"></a>单一登录：事件 10590
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10590                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            不可用                             |
|  符号名称  |                  SSO_ERROR_OUT_OF_SERVICE                  |
|  消息正文   |        企业单一登录正在进入脱机状态。         |
  
## <a name="explanation"></a>解释  
 ENTSSO 系统通常会会每隔 30 秒检查 ENTSSO 数据库上的更新。 如果指定的时间 （通常为 5 分钟），数据库将不可用，则系统本身进入脱机。 在此状态下，系统将不响应凭据请求。 仍有可能某些脱机和管理活动。  
  
## <a name="user-action"></a>用户操作  
 此错误表示 ENTSSO 数据库处于脱机状态。 应立即调查。