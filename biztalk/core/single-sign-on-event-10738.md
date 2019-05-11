---
title: 单一登录：Event 10738 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f3fbe55-d158-4f00-8c21-798b3bf5f19b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c2262db4fe30670576acfbfbd5ee05d5090558b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291762"
---
# <a name="single-sign-on-event-10738"></a>单一登录：事件 10738
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                    企业单一登录                                                                     |
| 产品版本 |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                    |
|    事件 ID     |                                                                              10738                                                                               |
|  事件源   |                                                                              ENTSSO                                                                              |
|    组件    |                                                                               N\A                                                                                |
|  符号名称  |                                                             SSO_INFO_PS_SET_WINDOWS_PASSWORD_ADAPTER                                                             |
|  消息正文   | SSO database.%r 中已成功更新 Windows 密码<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户： %3\\%4 |

## <a name="explanation"></a>解释  
 此信息事件表明 SSO 数据库中已成功更新 Windows 密码。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
