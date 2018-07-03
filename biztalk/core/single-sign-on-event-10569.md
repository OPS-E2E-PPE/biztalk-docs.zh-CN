---
title: 单一登录： 事件 10569 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e051a84-51c1-4e63-be55-6278a1d17c5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25665947921bb316a4d931228016eaf917b4a685
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987198"
---
# <a name="single-sign-on-event-10569"></a>单一登录： 事件 10569
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                       企业单一登录                                                                                        |
| 产品版本 |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    事件 ID     |                                                                                                 10569                                                                                                  |
|  事件源   |                                                                                                 ENTSSO                                                                                                 |
|    组件    |                                                                                                  N/A                                                                                                   |
|  符号名称  |                                                                                    SSO_WARN_NO_UPDATE_BY_APP_ADMIN                                                                                     |
|  消息正文   | 不能由应用程序管理员更改应用程序管理员帐户。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 应用程序管理员: %2 %r<br /><br /> 错误代码： %3 |
  
## <a name="explanation"></a>解释  
 不能由应用程序管理员更改应用程序管理员帐户。  
  
## <a name="user-action"></a>用户操作  
 您必须是 SSO 关联应用程序管理员或拥有更高权限，才能更改应用程序管理员帐户。