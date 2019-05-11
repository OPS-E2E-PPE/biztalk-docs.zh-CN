---
title: 单一登录：Event 10558 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7161e732fc95aa2fb62ee2ba5e8f188266804206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398824"
---
# <a name="single-sign-on-event-10558"></a>单一登录：事件 10558
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                  企业单一登录                                                                                   |
| 产品版本 |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    事件 ID     |                                                                                            10558                                                                                             |
|  事件源   |                                                                                            ENTSSO                                                                                            |
|    组件    |                                                                                             不可用                                                                                              |
|  符号名称  |                                                                                  SSO_WARN_USER_OWN_MAPPINGS                                                                                  |
|  消息正文   | 仅允许应用程序用户控制其自己 mappings.%r<br /><br /> 域名: %1 %r<br /><br /> 用户名: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 客户端用户： %4 |
  
## <a name="explanation"></a>解释  
 已尝试通过应用程序用户控制其他用户的映射。 这不是允许。  
  
## <a name="user-action"></a>用户操作  
 仅可通过特定映射应用程序用户控制的映射。