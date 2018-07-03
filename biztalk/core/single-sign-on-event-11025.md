---
title: 单一登录： 事件 11025 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df5a733b-3c95-409c-8485-bf3f7feb3c50
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd8c25dc80669b4524c7e9ce848e4b0e28f773f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015894"
---
# <a name="single-sign-on-event-11025"></a>单一登录： 事件 11025
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                 企业单一登录                                                                                                  |
| 产品版本 |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                 |
|    事件 ID     |                                                                                                           11025                                                                                                            |
|  事件源   |                                                                                                           ENTSSO                                                                                                           |
|    组件    |                                                                                                            N/A                                                                                                             |
|  符号名称  |                                                                                            SSO_WARN_INVALID_APP_TICKET_TIMEOUT                                                                                             |
|  消息正文   | 票证超时值对应用程序更新无效。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 票证超时： %2 分钟 %r<br /><br /> 最大票证超时： %3 分钟 %r<br /><br /> 错误代码： %4 |
  
## <a name="explanation"></a>解释  
 票证超时值无效。  
  
## <a name="user-action"></a>用户操作  
 票证超时值的详细信息，请参阅[SSO 关联应用程序](../core/sso-affiliate-applications.md)。