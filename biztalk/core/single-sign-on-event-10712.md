---
title: 单一登录：Event 10712 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f890bf20-dfb5-48b9-be6b-de29131a1955
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ebc91d0c7d7f55bdbf9f86b570f50023a963107
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397219"
---
# <a name="single-sign-on-event-10712"></a>单一登录：事件 10712
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                             企业单一登录                                                                              |
| 产品版本 |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    事件 ID     |                                                                                       10712                                                                                        |
|  事件源   |                                                                                       ENTSSO                                                                                       |
|    组件    |                                                                                        N\A                                                                                         |
|  符号名称  |                                                                          SSO_WARN_PS_NOTIFICATION_TOO_OLD                                                                          |
|  消息正文   | 通知被丢弃，因为它太 old.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 通知类型: %3 %r<br /><br /> 其他数据： %4 |

## <a name="explanation"></a>解释  
 此警告事件表示密码同步通知被丢弃，因为它太旧。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
