---
title: 单一登录：事件 10569 |Microsoft Docs
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
ms.openlocfilehash: 21e3c6e7650e61af9811cd58542a7a4d2b6204af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398755"
---
# <a name="single-sign-on-event-10569"></a>单一登录：事件 10569
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                       企业单一登录                                                                                        |
| 产品版本 |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    事件 ID     |                                                                                                 10569                                                                                                  |
|  事件源   |                                                                                                 ENTSSO                                                                                                 |
|    组件    |                                                                                                  不可用                                                                                                   |
|  符号名称  |                                                                                    SSO_WARN_NO_UPDATE_BY_APP_ADMIN                                                                                     |
|  消息正文   | 应用程序 Administrator.%r 不能更改应用程序管理员帐户<br /><br /> 应用程序名称: %1 %r<br /><br /> 应用程序管理员: %2 %r<br /><br /> 错误代码： %3 |
  
## <a name="explanation"></a>解释  
 不能由应用程序管理员更改应用程序管理员帐户。  
  
## <a name="user-action"></a>用户操作  
 您必须是一个 SSO 关联应用程序管理员或更高版本来更改应用程序管理员帐户。