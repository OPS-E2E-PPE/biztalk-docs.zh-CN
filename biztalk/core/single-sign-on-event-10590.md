---
title: 单一登录： 事件 10590 |Microsoft Docs
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
ms.openlocfilehash: fc2ac48ecf1279c1a8347e8f1ab3bcd1367854ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006766"
---
# <a name="single-sign-on-event-10590"></a>单一登录： 事件 10590
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10590                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N/A                             |
|  符号名称  |                  SSO_ERROR_OUT_OF_SERVICE                  |
|  消息正文   |        企业单一登录正在进入脱机状态。         |
  
## <a name="explanation"></a>解释  
 通常，ENTSSO 系统每隔 30 秒检查一次 ENTSSO 数据库中的更新。 如果数据库在指定的时间内（通常是五分钟）不可用，则系统本身进入脱机状态。 在此状态下，系统将不会响应凭据请求。 但仍然可以响应某些脱机和管理活动。  
  
## <a name="user-action"></a>用户操作  
 此错误表示 ENTSSO 数据库处于脱机状态。 您应该立即调查。