---
title: 单一登录：Event 10556 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66661a77-e8b0-4972-a3bc-4bb717967699
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30e2f3f8e76f5b2b18aca176dfee1d77c7b1ff1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398827"
---
# <a name="single-sign-on-event-10556"></a>单一登录：事件 10556
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                             企业单一登录                                                                                                                             |
| 产品版本 |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                             |
|    事件 ID     |                                                                                                                                       10556                                                                                                                                       |
|  事件源   |                                                                                                                                      ENTSSO                                                                                                                                       |
|    组件    |                                                                                                                                        不可用                                                                                                                                        |
|  符号名称  |                                                                                                                            SSO_WARN_INVALID_GROUP_USER                                                                                                                            |
|  消息正文   | 为组应用程序指定的映射不是有效的。 映射必须指定一个 application.%r 应用程序用户帐户<br /><br /> 域名: %1 %r<br /><br /> 用户名: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 应用程序用户： %4 |
  
## <a name="explanation"></a>解释  
 映射不是有效的。  
  
## <a name="user-action"></a>用户操作  
 检查映射指定为此应用程序的应用程序用户帐户之一。