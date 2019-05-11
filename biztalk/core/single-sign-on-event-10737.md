---
title: 单一登录：Event 10737 | Microsoft Docs
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
ms.openlocfilehash: 522eac1a2a70b1518f35c58d82ede99d6a402af0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270929"
---
# <a name="single-sign-on-event-10737"></a>单一登录：事件 10737
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                               企业单一登录                                                                                                |
| 产品版本 |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    事件 ID     |                                                                                                         10737                                                                                                          |
|  事件源   |                                                                                                         ENTSSO                                                                                                         |
|    组件    |                                                                                                          N\A                                                                                                           |
|  符号名称  |                                                                                           SSO_WARN_PS_SET_EXTERNAL_PASSWORD                                                                                            |
|  消息正文   | 更新 SSO database.%r 中的外部密码失败<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户: %4 %r<br /><br /> 错误代码： %5 |

## <a name="explanation"></a>解释  
 此警告事件表示 SSO 更新 SSO 数据库中的外部密码失败。 有各种可能的原因的指示警告消息; 中失败在某些情况下，此警告可能表示存在配置问题，或映射可能已被删除时密码更改的过程中。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 重试更改密码。  

- 如果更多的尝试仍失败，请使用 UI 或命令行工具手动将密码更改。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
