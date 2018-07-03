---
title: 单一登录： 事件 10568 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 266fd09a-c7e6-4a69-ac1c-1834097fa393
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c94c99580b63c5dc6eede29b595435daa256115
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010246"
---
# <a name="single-sign-on-event-10568"></a>单一登录： 事件 10568
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                  企业单一登录                                                                                                  |
| 产品版本 |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                  |
|    事件 ID     |                                                                                                            10568                                                                                                            |
|  事件源   |                                                                                                           ENTSSO                                                                                                            |
|    组件    |                                                                                                             N/A                                                                                                             |
|  符号名称  |                                                                                              SSO_WARN_INVALID_APP_ADMIN_GROUP                                                                                               |
|  消息正文   | 应用程序管理员帐户无法用于应用程序更新。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 应用程序管理员: %2 %r<br /><br /> 无效帐户: %3 %r<br /><br /> 错误代码： %4 |
  
## <a name="explanation"></a>解释  
 您尝试更新的应用程序管理员帐户无效或不存在。  
  
## <a name="user-action"></a>用户操作  
 检查帐户的名称是否正确。