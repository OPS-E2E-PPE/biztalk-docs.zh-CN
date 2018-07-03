---
title: 单一登录： 事件 10553 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0da8faf-8127-4d2e-a2ef-e5af20aff34f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0103305692cfb978820cd94e9a42a3b384f5ba4d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013454"
---
# <a name="single-sign-on-event-10553"></a>单一登录： 事件 10553
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10553                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N/A                             |
|  符号名称  |           SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED           |
|  消息正文   |               管理服务器访问被拒绝。%r                |
  
## <a name="explanation"></a>解释  
 发出了一个从客户端到管理服务器的调用，但是该调用未被接受。 这可能是由许多不同原因引起的，例如协议不正确或客户端没有足够的安全权限。  
  
## <a name="user-action"></a>用户操作  
 请记录下错误日志中的信息，然后与产品支持服务部门联系。