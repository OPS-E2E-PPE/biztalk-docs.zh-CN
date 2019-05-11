---
title: 单一登录：Event 10666 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 103947bb-e843-4427-a28a-1cceec90e2ae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 921f11f422e4707d81a9387cd9606c3dfd3f337d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397550"
---
# <a name="single-sign-on-event-10666"></a>单一登录：事件 10666
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                         企业单一登录                                                                          |
| 产品版本 |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                         |
|    事件 ID     |                                                                                   10666                                                                                    |
|  事件源   |                                                                                   ENTSSO                                                                                   |
|    组件    |                                                                                    N\A                                                                                     |
|  符号名称  |                                                                  SSO_INFO_DAMPED_EXTERNAL_PASSWORD_CHANGE                                                                  |
|  消息正文   | 外部密码更改被阻止 （检测为重复 discarded).%r，因而<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户： %3 |

## <a name="explanation"></a>解释  
 此信息事件表明外部密码更改已确定为不重复并丢弃。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [密码同步](../core/password-synchronization2.md)
