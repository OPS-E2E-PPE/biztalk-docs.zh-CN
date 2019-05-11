---
title: 单一登录：事件 11017 |Microsoft Docs
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
ms.openlocfilehash: 41b28506409bb68190f7dfe07f025d19c99dc47c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267145"
---
# <a name="single-sign-on-event-11017"></a>单一登录：事件 11017
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                               企业单一登录                                                                                                                                |
| 产品版本 |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                               |
|    事件 ID     |                                                                                                                                         11017                                                                                                                                          |
|  事件源   |                                                                                                                                         ENTSSO                                                                                                                                         |
|    组件    |                                                                                                                                          不可用                                                                                                                                           |
|  符号名称  |                                                                                                                           SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK                                                                                                                           |
|  消息正文   | 映射无效，因为 Windows 帐户不在应用程序的应用程序用户帐户。 映射已被 deleted.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 应用程序用户： %4 |
  
## <a name="explanation"></a>解释  
 指定的 Windows 帐户从来都不属于此应用程序的应用程序用户帐户或它是一次，但已更改或删除。 已删除该映射。  
  
## <a name="user-action"></a>用户操作  
 检查您的系统，密码同步帐户信息，请确保你的信息有效。 然后重新创建映射。 请注意，使用创建映射向导可降低无效映射信息的风险。