---
title: 单一登录： 事件 10706 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73db77e-5bb6-431c-a8ca-5682d7ab3d6a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9e56600b86856af6a9cdb14fd2a902b047e84b5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022451"
---
# <a name="single-sign-on-event-10706"></a>单一登录： 事件 10706
## <a name="details"></a>详细信息  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                 企业单一登录                                                 |
| 产品版本 |                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                 |
|    事件 ID     |                                                           10706                                                           |
|  事件源   |                                                          ENTSSO                                                           |
|    组件    |                                                            N\A                                                            |
|  符号名称  |                                                SSO_WARN_PS_NO_GLOBAL_SYNC                                                 |
|  消息正文   | 组适配器要求全局标志允许密码同步。 请检查全局标志。%r<br /><br /> 适配器： %1 |

## <a name="explanation"></a>解释  
 此警告事件表示，外部密码同步适配器请求密码同步，并且未设置全局标记。 有两个标志，允许将密码发送到外部系统： sso_flag_full_sync_from_windows_to_external; 另外，允许接收来自外部系统： SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB 的密码。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  

-   使用 SSO Admin MMC 管理单元，(系统&#124;属性&#124;选项) 或命令行工具`ssomanage –enable winsync/extsync`来启用全局标志。  

## <a name="more-info"></a>详细信息

- **企业单一登录标志** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)
