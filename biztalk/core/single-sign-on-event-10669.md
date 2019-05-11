---
title: 单一登录：Event 10669 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e88a583d-7385-42dd-841e-aa2d2215dd69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d0a9ab77f528060be25616eb8d80072402957a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397531"
---
# <a name="single-sign-on-event-10669"></a>单一登录：事件 10669
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                   企业单一登录                                                                   |
| 产品版本 |                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    事件 ID     |                                                                             10669                                                                             |
|  事件源   |                                                                            ENTSSO                                                                             |
|    组件    |                                                                              N\A                                                                              |
|  符号名称  |                                                            SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED                                                            |
|  消息正文   | 更改 Windows password.%r 失败<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户: %3 %r<br /><br /> 错误代码： %4 |

## <a name="explanation"></a>解释  
 此警告事件表示 SSO 无法更改 Windows 密码。 SSO 将调用 Win32 函数 NetUserChangePassword 函数来更改与映射关联的 Windows 密码。 如果该函数会此错误消息发出。 错误代码将是从 NetUserChangePassword 中返回。 请参阅 MSDN 中此函数的详细信息的文档。 最有可能导致失败的原因是旧密码不正确，或新的密码不满足 Windows 密码策略要求。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

- 验证旧密码。 如果旧密码不正确，则可以使用命令行工具或 Admin MMC 在 SSO 数据库中手动设置。  

- 验证新的密码符合 Windows 密码策略要求。 如果密码不符合 Windows 密码策略，则请考虑使用密码筛选器。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [密码同步](../core/password-synchronization2.md)
