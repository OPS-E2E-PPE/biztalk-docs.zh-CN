---
title: 单一登录：Event 10735 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31c791c6-1901-4441-b329-ed75833cb83e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3e7752733a437f3526af7d5ac2790d2ffac64fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291780"
---
# <a name="single-sign-on-event-10735"></a>单一登录：事件 10735
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                             企业单一登录                                                                                                              |
| 产品版本 |                                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    事件 ID     |                                                                                                                       10735                                                                                                                        |
|  事件源   |                                                                                                                       ENTSSO                                                                                                                       |
|    组件    |                                                                                                                        N\A                                                                                                                         |
|  符号名称  |                                                                                                              SSO_WARN_PS_APP_DISABLED                                                                                                              |
|  消息正文   | 外部密码更改。 密码未更改外部帐户因为应用程序被 disabled.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户： %4 |

## <a name="explanation"></a>解释  
 此警告事件表示，密码未更改外部帐户因为应用程序已被禁用。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 启用关联应用程序  

  有关详细信息，请参阅下列资源：  

- [如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)  

- [密码同步](../core/password-synchronization2.md)
