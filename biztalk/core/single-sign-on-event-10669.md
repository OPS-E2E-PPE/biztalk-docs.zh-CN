---
title: 单一登录： 事件 10669 |Microsoft Docs
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
ms.openlocfilehash: d3006b8c861ac56effa504480f2645f22f9deae8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019257"
---
# <a name="single-sign-on-event-10669"></a>单一登录： 事件 10669
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                   企业单一登录                                                                   |
| 产品版本 |                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    事件 ID     |                                                                             10669                                                                             |
|  事件源   |                                                                            ENTSSO                                                                             |
|    组件    |                                                                              N\A                                                                              |
|  符号名称  |                                                            SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED                                                            |
|  消息正文   | 无法更改 Windows 密码。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户: %3 %r<br /><br /> 错误代码： %4 |

## <a name="explanation"></a>解释  
 此警告事件表示 SSO 无法更改 Windows 密码。 SSO 将调用 Win32 函数 NetUserChangePassword 函数来更改与映射关联的 Windows 密码。 如果调用此函数失败，则系统会发出此错误消息。 错误代码将是从 NetUserChangePassword 中返回的代码。 有关详细信息，请参阅 MSDN 中此函数的文档。 失败的最可能原因是旧密码不正确，或者是新密码不满足 Windows 密码策略的要求。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  

- 验证旧密码。 如果旧密码不正确，则可以使用命令行工具或 Admin MMC 在 SSO 数据库中手动进行设置。  

- 验证新密码满足 Windows 密码策略的要求。 如果密码不符合 Windows 密码策略，则考虑使用密码筛选器。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [密码同步](../core/password-synchronization2.md)
