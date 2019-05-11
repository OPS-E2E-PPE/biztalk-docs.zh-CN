---
title: 单一登录：Event 10710 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 469dc407-be7a-45a1-bcf5-2ba7060a19e2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62c43785a276ce33412b509af7a034697caab9f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397256"
---
# <a name="single-sign-on-event-10710"></a>单一登录：事件 10710
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                          企业单一登录                                                                          |
| 产品版本 |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                          |
|    事件 ID     |                                                                                    10710                                                                                    |
|  事件源   |                                                                                   ENTSSO                                                                                    |
|    组件    |                                                                                     N\A                                                                                     |
|  符号名称  |                                                                        SSO_INFO_PS_WIN_CHANGE_DAMPED                                                                        |
|  消息正文   | Windows 密码更改被阻止 （检测为重复 discarded).%r，因而<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 客户端用户： %3 |

## <a name="explanation"></a>解释  
 此信息事件表明 Windows 密码更改已被丢弃，因为它被检测为重复。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
