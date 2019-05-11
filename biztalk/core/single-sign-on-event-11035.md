---
title: 单一登录：事件 11035 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d551083c-a897-4a76-a40c-2254d3a3e52e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39b07359061b7e855e8ea53abee64ef567668395
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395243"
---
# <a name="single-sign-on-event-11035"></a>单一登录：事件 11035
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                               企业单一登录                                                                                                                                                |
| 产品版本 |                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                               |
|    事件 ID     |                                                                                                                                                         11035                                                                                                                                                          |
|  事件源   |                                                                                                                                                         ENTSSO                                                                                                                                                         |
|    组件    |                                                                                                                                                          不可用                                                                                                                                                           |
|  符号名称  |                                                                                                                                           SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER                                                                                                                                            |
|  消息正文   | Windows 密码更改。 此 Windows 帐户的映射已检测到但被忽略，因为 application.%r 未配置密码同步<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 应用程序: %3 %r<br /><br /> 外部帐户: %4 %r<br /><br /> 客户端用户： %5 |
  
## <a name="explanation"></a>解释  
 已检测到此 Windows 帐户的映射，但被忽略，因为没有为此应用程序配置密码同步。  
  
## <a name="user-action"></a>用户操作  
 有关配置密码同步的信息，请参阅[密码同步](../core/password-synchronization2.md)。