---
title: 单一登录： 事件 10668 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eb3dd4d-04b5-4713-93c1-76af012d6920
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a7a3efa9ba3e9ccae3cdc39c4549a4625e5d872
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973998"
---
# <a name="single-sign-on-event-10668"></a>单一登录： 事件 10668
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                   企业单一登录                                                                                                                                                   |
| 产品版本 |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    事件 ID     |                                                                                                                                                             10668                                                                                                                                                             |
|  事件源   |                                                                                                                                                            ENTSSO                                                                                                                                                             |
|    组件    |                                                                                                                                                              N\A                                                                                                                                                              |
|  符号名称  |                                                                                                                                               SSO_WARN_NO_OLD_WINDOWS_PASSWORD                                                                                                                                                |
|  消息正文   | 不能更改 Windows 密码，因为此帐户的旧 Windows 密码不在 SSO 数据库中。%r<br /><br /> 请使用 SSO 管理工具为此 Windows 帐户设置外部凭据。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户： %3 |

## <a name="explanation"></a>解释  
 此警告事件表示密码同步不能更改 Windows 密码，因为此帐户的旧 Windows 密码不在 SSO 数据库中。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  

-   确定哪些应用程序被分配到了此适配器（事件日志消息中的名称），然后使用 SSO 管理工具来为此 Windows 帐户设置外部凭据。 必须在全部应用程序中为给定的 Windows 帐户设置外部密码。  

## <a name="more-info"></a>详细信息

- [密码同步](../core/password-synchronization2.md)  

- **密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
