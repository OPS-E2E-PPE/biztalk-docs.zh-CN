---
title: 单一登录： 事件 11016 |Microsoft Docs
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
ms.openlocfilehash: 96f39cba26da1b3e03c7259643c3dcf2704bbdf3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974510"
---
# <a name="single-sign-on-event-11016"></a>单一登录： 事件 11016
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                   企业单一登录                                                                                                                                                                    |
| 产品版本 |                                                                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                   |
|    事件 ID     |                                                                                                                                                                             11016                                                                                                                                                                              |
|  事件源   |                                                                                                                                                                             ENTSSO                                                                                                                                                                             |
|    组件    |                                                                                                                                                                              N/A                                                                                                                                                                               |
|  符号名称  |                                                                                                                                                                RPC EXTENDED ERROR INFORMATION%r                                                                                                                                                                |
|  消息正文   | %1%r<br /><br /> 错误代码： %2<br /><br /> AuthzInitializeContextFromSid 函数失败，错误消息为 ERROR_ACCESS_DENIED。 这表示运行 SSO 服务器的服务帐户没有足够的权限在 Active Directory 中检查组成员身份。 请查看您的文档，了解有关如何解决此问题的详细信息。%r |
  
## <a name="explanation"></a>解释  
 运行 SSO 服务器的服务帐户没有足够的权限在 Active Directory 中检查组成员身份。  
  
## <a name="user-action"></a>用户操作  
 请参阅[SSO 服务器](../core/sso-server.md)SSO 文档中。