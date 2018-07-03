---
title: 单一登录： 事件 10661 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3418f37-770d-4021-9341-5dbe99689da6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b52ec67069951bcda3dee54da96e33ca5145e9e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998854"
---
# <a name="single-sign-on-event-10661"></a>单一登录： 事件 10661
## <a name="details"></a>详细信息  

|                 |                                                                                     |
|-----------------|-------------------------------------------------------------------------------------|
|  产品名称   |                              企业单一登录                              |
| 产品版本 |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    事件 ID     |                                        10661                                        |
|  事件源   |                                       ENTSSO                                        |
|    组件    |                                         N\A                                         |
|  符号名称  |                    SSO_ERROR_PASSWORD_SYNC_WINDOWS_START_FAILED                     |
|  消息正文   | Windows 的密码同步（从 PCNS）启动失败。%r<br /><br /> 错误代码： %1 |

## <a name="explanation"></a>解释  
 此错误事件表示无法启动 Windows 的密码同步。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

-   检查相关事件的应用程序和系统事件日志。  

-   验证适配器配置属性。  

## <a name="more-info"></a>详细信息

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)  

- **企业单一登录的用户界面帮助** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
