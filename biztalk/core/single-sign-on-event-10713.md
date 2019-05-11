---
title: 单一登录：Event 10713 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2da2b112-6884-4fca-a9b6-d1f65aeccd80
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00d73b759e778262bb43ffa8774fa389c8b7eead
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397227"
---
# <a name="single-sign-on-event-10713"></a>单一登录：事件 10713
## <a name="details"></a>详细信息  

|                 |                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                         企业单一登录                                                         |
| 产品版本 |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                         |
|    事件 ID     |                                                                   10713                                                                   |
|  事件源   |                                                                  ENTSSO                                                                   |
|    组件    |                                                                    N\A                                                                    |
|  符号名称  |                                                   SSO_INFO_PS_DUPLICATE_EXTERNAL_CHANGE                                                   |
|  消息正文   | 取消重复的外部密码 change.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户： %3 |

## <a name="explanation"></a>解释  
 此信息事件表明重复的外部密码更改已收到并丢弃。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
