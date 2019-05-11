---
title: 单一登录：Event 11016 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3963b706-168d-438d-a068-637f8a6b7b0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01bf4d34a68680b391e49b465e44138fca81b210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267072"
---
# <a name="single-sign-on-event-11016"></a>单一登录：事件 11016
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                   企业单一登录                                                                                                                                                                    |
| 产品版本 |                                                                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                   |
|    事件 ID     |                                                                                                                                                                             11016                                                                                                                                                                              |
|  事件源   |                                                                                                                                                                             ENTSSO                                                                                                                                                                             |
|    组件    |                                                                                                                                                                              不可用                                                                                                                                                                               |
|  符号名称  |                                                                                                                                                                RPC 扩展错误信息 %r                                                                                                                                                                |
|  消息正文   | %1%r<br /><br /> 错误代码： %2<br /><br /> AuthzInitializeContextFromSid 函数失败，出现 ERROR_ACCESS_DENIED。 这意味着 SSO 服务器下运行的服务帐户没有足够的权限来检查 Active Directory 中的组成员身份。 请检查您的文档详细介绍了如何修复此 problem.%r |
  
## <a name="explanation"></a>解释  
 SSO 服务器下运行的服务帐户没有足够的权限来检查 Active Directory 中的组成员身份。  
  
## <a name="user-action"></a>用户操作  
 请参阅[SSO 服务器](../core/sso-server.md)SSO 文档中。