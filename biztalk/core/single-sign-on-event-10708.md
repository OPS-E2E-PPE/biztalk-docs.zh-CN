---
title: 单一登录： 事件 10708 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63675191-41cb-43fc-9355-e4ddc3f354c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b052e3545aa67b27bc94de579faedde782c0dec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003086"
---
# <a name="single-sign-on-event-10708"></a>单一登录： 事件 10708
## <a name="details"></a>详细信息  

|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                   企业单一登录                                                    |
| 产品版本 |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    事件 ID     |                                                             10708                                                              |
|  事件源   |                                                             ENTSSO                                                             |
|    组件    |                                                              N\A                                                               |
|  符号名称  |                                                    SSO_WARN_PS_NO_WIN_SYNC                                                     |
|  消息正文   | 不允许从 Windows 进行密码同步。 请检查全局标志。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户： %2 |

## <a name="explanation"></a>解释  
 此警告事件表明 Windows 请求进行密码同步并且未设置任何全局标志。 有两个标志，允许将密码发送到外部系统： sso_flag_full_sync_from_windows_to_external; 另外，允许接收来自外部系统： SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB 的密码。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  

-   使用 SSO Admin MMC 管理单元，(系统&#124;属性&#124;选项) 或命令行工具`ssomanage –enable winsync/extsync`来启用全局标志。  

## <a name="more-info"></a>详细信息

- **企业单一登录标志** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)
