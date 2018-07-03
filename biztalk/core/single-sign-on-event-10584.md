---
title: 单一登录： 事件 10584 |Microsoft Docs
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
ms.openlocfilehash: 0188f09ab94bd14df0dbe3fee0b91341cd9eb087
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996718"
---
# <a name="single-sign-on-event-10584"></a>单一登录： 事件 10584
## <a name="details"></a>详细信息  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  产品名称   |                   企业单一登录                    |
| 产品版本 |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    事件 ID     |                             10584                              |
|  事件源   |                             ENTSSO                             |
|    组件    |                              N/A                               |
|  符号名称  |                   SSO_WARN_NO_IMPERSONATION                    |
|  消息正文   | 无法模拟客户端。%r<br /><br /> 错误代码： %1 |
  
## <a name="explanation"></a>解释  
 模拟客户端是 ENTSSO 系统为验证客户端的标识而执行的操作。 当系统无法模拟客户端时，可能发生了以下三种情况之一。 客户端可能尝试执行一个常见操作，客户端可能尝试渗入系统安全，或客户端应用程序可能被设计为阻止模拟。  
  
## <a name="user-action"></a>用户操作  
 找到该客户端应用程序，确定其尝试执行的操作，以及其是否阻止模拟。