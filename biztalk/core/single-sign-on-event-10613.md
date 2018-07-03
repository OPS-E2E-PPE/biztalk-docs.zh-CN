---
title: 单一登录： 事件 10613 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a87ca19-24a0-4cf8-984f-2f70d7b5018c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 250f113e0cd60b417cee29d32f8e61fbf38632dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023803"
---
# <a name="single-sign-on-event-10613"></a>单一登录： 事件 10613
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                   企业单一登录                                                    |
| 产品版本 |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    事件 ID     |                                                             10613                                                              |
|  事件源   |                                                             ENTSSO                                                             |
|    组件    |                                                              N/A                                                               |
|  符号名称  |                                                     SSO_ERROR_RPC_CALLBACK                                                     |
|  消息正文   | SSO 服务器访问被拒绝。%r<br /><br /> 客户端用户: %1 %r<br /><br /> RPC 调用信息: %2: %3 %r<br /><br /> 错误代码： %4 |
  
## <a name="explanation"></a>解释  
 从客户端到 SSO 服务器的调用已作出，但未被接受。 这可能是由许多不同原因引起的，例如协议不正确或客户端没有足够的安全权限。  
  
## <a name="user-action"></a>用户操作  
 请注意此消息中的信息和事件日志中的任何相关信息，请与 Microsoft 产品支持服务联系。