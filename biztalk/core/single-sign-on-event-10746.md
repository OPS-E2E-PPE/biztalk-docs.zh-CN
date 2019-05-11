---
title: 单一登录：Event 10746 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8189120b-923a-4c88-937e-f06565bcac56
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19bef7a20062761f1d019b786bd96581b302bec4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395495"
---
# <a name="single-sign-on-event-10746"></a>单一登录：事件 10746
## <a name="details"></a>详细信息  

|                 |                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                           企业单一登录                                                           |
| 产品版本 |                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                           |
|    事件 ID     |                                                                     10746                                                                     |
|  事件源   |                                                                    ENTSSO                                                                     |
|    组件    |                                                                      N\A                                                                      |
|  符号名称  |                                                           SSO_WARN_PASSWORD_EXPIRED                                                           |
|  消息正文   | 外部帐户的密码已 expired.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户： %3 |

## <a name="explanation"></a>解释  
 此警告事件表明外部帐户的密码已过期。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请检查系统和应用程序事件日志中的关联错误。    

## <a name="more-info"></a>详细信息
有关详细信息，请参阅下列资源：  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  

- [密码同步](../core/password-synchronization2.md)
