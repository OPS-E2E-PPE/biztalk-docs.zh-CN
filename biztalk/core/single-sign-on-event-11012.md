---
title: 单一登录： 事件 11012 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 252bedc8-8dc3-4962-b078-465f9b064ead
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28f78d834e57a85e05de143612d376b77ebed799
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988006"
---
# <a name="single-sign-on-event-11012"></a>单一登录： 事件 11012
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                               企业单一登录                                                                                                |
| 产品版本 |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    事件 ID     |                                                                                                         11012                                                                                                          |
|  事件源   |                                                                                                         ENTSSO                                                                                                         |
|    组件    |                                                                                                          N/A                                                                                                           |
|  符号名称  |                                                                                           SSO_WARN_NOT_APP_ADMIN_ADMIN_SAME                                                                                            |
|  消息正文   | 客户端用户不是应用程序管理员帐户的成员。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户： %2\\%3 %r<br /><br /> 应用程序名称: %4 %r<br /><br /> 应用程序管理员： %5 |
  
## <a name="explanation"></a>解释  
 客户端用户不是应用程序管理员帐户的成员。 只有当审核级别设置为高时，才会出现此警告。  
  
## <a name="user-action"></a>用户操作  
 若要修复此情形，您必须使客户端用户成为应用程序管理员帐户的成员。 若要阻止以后出现此警告，您可以降低审核级别。