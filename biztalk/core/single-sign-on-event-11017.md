---
title: 单一登录： 事件 11017 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a4f7264-18aa-4eca-97c9-d5fd7e90e2cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e0883abfd3bc86f6e41fd11e0feafa79b080b13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024187"
---
# <a name="single-sign-on-event-11017"></a>单一登录： 事件 11017
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                               企业单一登录                                                                                                                                |
| 产品版本 |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                               |
|    事件 ID     |                                                                                                                                         11017                                                                                                                                          |
|  事件源   |                                                                                                                                         ENTSSO                                                                                                                                         |
|    组件    |                                                                                                                                          N/A                                                                                                                                           |
|  符号名称  |                                                                                                                           SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK                                                                                                                           |
|  消息正文   | 由于 Windows 帐户不属于应用程序的应用程序用户帐户而导致映射无效。 已删除该映射。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 应用程序用户： %4 |
  
## <a name="explanation"></a>解释  
 指定的 Windows 帐户不是此应用程序的应用程序用户帐户的一部分，或者曾经是应用程序用户帐户的一部分，但已更改或删除。 已删除该映射。  
  
## <a name="user-action"></a>用户操作  
 检查系统的密码同步帐户信息，并确保您的信息有效。 然后重新创建映射。 请注意，使用创建映射向导可降低无效映射信息的风险。