---
title: 单一登录：Event 10529 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ed70e0-8458-4736-883f-a4536f094dc0
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 204e5d2ff2093b5980176d1696fd9bd45b892023
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262425"
---
# <a name="single-sign-on-event-10529"></a>单一登录：事件 10529
## <a name="details"></a>详细信息  

|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                             企业单一登录                                             |
| 产品版本 |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    事件 ID     |                                                       10529                                                       |
|  事件源   |                                                      ENTSSO                                                       |
|    组件    |                                                        N\A                                                        |
|  符号名称  |                                            SSO_INFO_GOT_CURRENT_SECRET                                            |
|  消息正文   | 已从主 server.%r 获得当前密钥<br /><br /> 密钥服务器名称: %1 %r<br /><br /> MSID: %2 |

## <a name="explanation"></a>解释  
 此信息事件表明 SSO 已从主密钥服务器请求的主密钥。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  

- [管理主密钥](../core/managing-the-master-secret.md)
