---
title: 单一登录：Event 10568 | Microsoft Docs
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
ms.openlocfilehash: 52d5ec7ece58816afd10e44e2bf83d53a35895e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398770"
---
# <a name="single-sign-on-event-10568"></a>单一登录：事件 10568
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                  企业单一登录                                                                                                  |
| 产品版本 |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                  |
|    事件 ID     |                                                                                                            10568                                                                                                            |
|  事件源   |                                                                                                           ENTSSO                                                                                                            |
|    组件    |                                                                                                             不可用                                                                                                             |
|  符号名称  |                                                                                              SSO_WARN_INVALID_APP_ADMIN_GROUP                                                                                               |
|  消息正文   | 应用程序管理员帐户不是有效的应用程序 update.%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 应用程序管理员: %2 %r<br /><br /> 无效帐户: %3 %r<br /><br /> 错误代码： %4 |
  
## <a name="explanation"></a>解释  
 已尝试更新的应用程序管理员帐户无效或不存在。  
  
## <a name="user-action"></a>用户操作  
 检查帐户的名称正确。