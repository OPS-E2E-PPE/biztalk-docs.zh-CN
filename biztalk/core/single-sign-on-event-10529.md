---
title: 单一登录： 事件 10529 |Microsoft Docs
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
ms.openlocfilehash: 74bc28f01db257c06223e1b1f79268ca63e3ca49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976942"
---
# <a name="single-sign-on-event-10529"></a>单一登录： 事件 10529
## <a name="details"></a>详细信息  

|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                             企业单一登录                                             |
| 产品版本 |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    事件 ID     |                                                       10529                                                       |
|  事件源   |                                                      ENTSSO                                                       |
|    组件    |                                                        N\A                                                        |
|  符号名称  |                                            SSO_INFO_GOT_CURRENT_SECRET                                            |
|  消息正文   | 从主密钥服务器获取最新密钥。%r<br /><br /> 密钥服务器名称: %1 %r<br /><br /> MSID: %2 |

## <a name="explanation"></a>解释  
 此信息事件表明 SSO 具有主密钥服务器请求的主密钥。  

## <a name="user-action"></a>用户操作  

- 不需要用户进行任何操作。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  

- [管理主密钥](../core/managing-the-master-secret.md)
