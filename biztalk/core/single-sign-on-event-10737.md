---
title: 单一登录： 事件 10737 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2102930b-8b1f-4d48-a14d-e8884dc7f9aa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd21b244e86c14aaf0f3af7418f1ca2ed8fbf067
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987678"
---
# <a name="single-sign-on-event-10737"></a>单一登录： 事件 10737
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                               企业单一登录                                                                                                |
| 产品版本 |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    事件 ID     |                                                                                                         10737                                                                                                          |
|  事件源   |                                                                                                         ENTSSO                                                                                                         |
|    组件    |                                                                                                          N\A                                                                                                           |
|  符号名称  |                                                                                           SSO_WARN_PS_SET_EXTERNAL_PASSWORD                                                                                            |
|  消息正文   | 更新 SSO 数据库中的外部密码失败。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户: %4 %r<br /><br /> 错误代码： %5 |

## <a name="explanation"></a>解释  
 此警告事件表示 SSO 更新 SSO 数据库中的外部密码失败。 导致该警告消息中描述的失败的原因有很多，在某些情况下，此警告可能表示配置问题，或者是在进行密码更改时删除了映射。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  

- 重试更改密码。  

- 如果更多的尝试继续失败，则使用 UI 或命令行工具来手动更改密码。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
