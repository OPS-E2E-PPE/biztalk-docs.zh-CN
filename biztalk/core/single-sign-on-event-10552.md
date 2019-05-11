---
title: 单一登录：Event 10552 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f85ae0b3-d8f8-4341-8bd3-423e85402d58
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 744ecbd42d4a62fd72b792e7491f3f127ebf14f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398897"
---
# <a name="single-sign-on-event-10552"></a>单一登录：事件 10552
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10552                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            不可用                             |
|  符号名称  |          SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED          |
|  消息正文   |              映射服务器访问 denied.%r               |
  
## <a name="explanation"></a>解释  
 调用对映射服务器进行从客户端，但未被接受。 原因可能是多种不同原因，例如协议不正确或客户端上没有足够的安全权限。  
  
## <a name="user-action"></a>用户操作  
 请注意错误日志中的信息，请与产品支持服务联系。