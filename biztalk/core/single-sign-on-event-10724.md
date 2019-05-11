---
title: 单一登录：Event 10724 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 022a6f73-a24b-4058-91a5-b831f6875409
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5494af19164c6c2621196ccd481d8510be58794
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303310"
---
# <a name="single-sign-on-event-10724"></a>单一登录：事件 10724
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                     企业单一登录                                                                                      |
| 产品版本 |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    事件 ID     |                                                                                               10724                                                                                                |
|  事件源   |                                                                                               ENTSSO                                                                                               |
|    组件    |                                                                                                N\A                                                                                                 |
|  符号名称  |                                                                                    SSO_ERROR_REPLAY_SECURITY_2                                                                                     |
|  消息正文   | 已从其原始 value.%r 更改重播或进度文件的安全性<br /><br /> 文件名称: %1 %r<br /><br /> 当前文件安全性: %2 %r<br /><br /> 原始文件安全性： %3 |

## <a name="explanation"></a>解释  
 此错误事件表示已更改的重播或进度文件的安全性。  

 重播文件存储在重播文件目录。 默认情况下，SSO 服务帐户用于创建重播文件和重播文件目录。 没有进行了更改的安全配置的重播文件和重播文件目录创建以来，SSO 会验证。 如果在不同帐户创建重播文件目录时，密码同步尝试在该目录中创建重播文件时，可以返回此错误。 强烈建议用户不要更改重播文件和重播文件目录的任何安全配置。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查用于创建重播文件的帐户权限。 这通常是 SSO 系统帐户。  

  有关详细信息，请参阅下列资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
