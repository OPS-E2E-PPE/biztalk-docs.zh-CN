---
title: 单一登录：Event 10555 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9c663-4aa8-4ca5-be63-d4461a2a8517
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6522295b1f6efe3be224739ff1adfe6316abaf7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398855"
---
# <a name="single-sign-on-event-10555"></a>单一登录：事件 10555
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10555                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            不可用                             |
|  符号名称  |          SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED           |
|  消息正文   | Denied.%r 访问密钥服务器<br /><br /> 客户端用户： %1 |
  
## <a name="explanation"></a>解释  
 一条消息已发送到服务器但回复受到阻止。 原因可能是多种不同原因，例如协议不正确或服务器上没有足够的安全权限。  
  
## <a name="user-action"></a>用户操作  
 请注意错误日志中的信息，请与产品支持服务联系。