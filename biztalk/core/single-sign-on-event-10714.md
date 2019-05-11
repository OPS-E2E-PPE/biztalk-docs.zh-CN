---
title: 单一登录：Event 10714 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59d8509f-cc3e-40fa-ba3d-3dcb0e73c67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 087592befd7f65241fdc413886f8245467f1e534
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397208"
---
# <a name="single-sign-on-event-10714"></a>单一登录：事件 10714
## <a name="details"></a>详细信息  

|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  产品名称   |                                     企业单一登录                                     |
| 产品版本 |                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                     |
|    事件 ID     |                                               10714                                               |
|  事件源   |                                              ENTSSO                                               |
|    组件    |                                                N\A                                                |
|  符号名称  |                             SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED                              |
|  消息正文   | 重试过期，丢弃 notification.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器： %2 |

## <a name="explanation"></a>解释  
 此警告事件表示密码同步通知重试已过期，并已丢弃通知。  

 将密码更改 （从 Windows 到外部系统) 传递到密码同步适配器，密码同步适配器确认它已成功处理密码更改。 如果在指定的时间内，密码更改不会发生，或者在更改期间会出现其他问题，是再次将密码更改传递到密码同步适配器。 这是有限的数量的时间 （最大重试），则密码更改通知将被丢弃。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 检查有相关事件的系统和应用程序事件日志。  

  有关详细信息，请参阅下列资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
