---
title: 单一登录：Event 10533 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31abd828-5f10-43f7-b99e-f3195250130c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ce83b8d2c7ff6973900088dcb0c0028e31f0e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262313"
---
# <a name="single-sign-on-event-10533"></a>单一登录：事件 10533
## <a name="details"></a>详细信息  

|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                             企业单一登录                                             |
| 产品版本 |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    事件 ID     |                                                       10533                                                       |
|  事件源   |                                                      ENTSSO                                                       |
|    组件    |                                                        N\A                                                        |
|  符号名称  |                                            SSO_INFO_GOT_CURRENT_SECRET                                            |
|  消息正文   | 已从主 server.%r 获得当前密钥<br /><br /> 密钥服务器名称: %1 %r<br /><br /> MSID: %2 |

## <a name="explanation"></a>解释  
 此信息事件表明 SSO 具有当前的主密钥。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  

- [管理主密钥](../core/managing-the-master-secret.md)
