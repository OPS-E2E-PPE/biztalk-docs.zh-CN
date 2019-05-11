---
title: 单一登录：Event 10547 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be25cdc9-d6c1-488d-9ead-877a2454c3d1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8ec8133a6d2456e2cdafca56ae956f6be1d31a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243428"
---
# <a name="single-sign-on-event-10547"></a>单一登录：事件 10547
## <a name="details"></a>详细信息  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  产品名称   |                         企业单一登录                         |
| 产品版本 |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    事件 ID     |                                   10547                                   |
|  事件源   |                                  ENTSSO                                   |
|    组件    |                                    CO                                     |
|  符号名称  |                          SSO_WARN_UPDATE_FAILED                           |
|  消息正文   | 未能重新加密过程中更新 SSO 数据库中的凭据 |

## <a name="explanation"></a>解释  
 此警告事件表示没有可以使用新的加密结果更新凭据。 当更改主密钥时，通过生成新密钥或还原旧密钥，重新加密对 SSO 数据库进行解密使用旧密钥加密的所有密钥和使用新密钥重新加密。 如果凭据已删除，因为它们是在重新加密的过程中，会发生此事件。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 等待一小段延迟; 后进行另一个重新加密如果未自动放弃，重新启动 SSO 服务，这将触发新的重新加密，如果需要。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [了解 SSO](../core/understanding-sso.md)
