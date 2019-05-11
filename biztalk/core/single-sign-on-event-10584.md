---
title: 单一登录：Event 10584 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9377d-b4fd-48a6-961a-3629b3db644a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 478d33b1ef00930617a32f18dc7cf942210e0162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395255"
---
# <a name="single-sign-on-event-10584"></a>单一登录：事件 10584
## <a name="details"></a>详细信息  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  产品名称   |                   企业单一登录                    |
| 产品版本 |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    事件 ID     |                             10584                              |
|  事件源   |                             ENTSSO                             |
|    组件    |                              不可用                               |
|  符号名称  |                   SSO_WARN_NO_IMPERSONATION                    |
|  消息正文   | 无法模拟 client.%r<br /><br /> 错误代码： %1 |
  
## <a name="explanation"></a>解释  
 模拟客户端是 ENTSSO 系统执行的操作以验证客户端的标识。 当系统无法模拟客户端时，以下三种情况可能会发生。 客户端可能尝试执行一个常见操作、 客户端可能尝试渗入系统安全，或客户端应用程序可能被设计为阻止模拟。  
  
## <a name="user-action"></a>用户操作  
 找到客户端应用程序，并确定它正尝试执行操作，以及它阻止模拟。