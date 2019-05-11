---
title: 单一登录：Event 10522 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd634a57-01dc-44bd-bcf9-668689db7b77
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac9347492793170faed39be91f2925e0ffdc1cdc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393024"
---
# <a name="single-sign-on-event-10522"></a>单一登录：事件 10522
## <a name="details"></a>详细信息  

|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  产品名称   |                                   企业单一登录                                   |
| 产品版本 |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    事件 ID     |                                             10522                                             |
|  事件源   |                                            ENTSSO                                             |
|    组件    |                                              N\A                                              |
|  符号名称  |                                      SSO_ERROR_REENCRYPT                                      |
|  消息正文   | SSO 数据库重新加密失败。 将在重试 %1 minutes.%r<br /><br /> 错误代码： %2 |

## <a name="explanation"></a>解释  
 此错误事件表示 SSO 数据库重新加密失败。 SSO 服务启动时在主服务器上，的首先就是检查是否有任何内容仍使用之前的主密钥加密的 SSO 数据库中。 如果找到任何内容，它会解密 （使用上一个密钥） 此信息并重新对它使用当前的主密钥进行加密。 如果出于任何原因，此过程失败，会发出此事件消息。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查错误代码，以确定错误的根本原因可能是什么。 这可能是网络或数据库问题。 如果它是间歇性的则不需要操作，因为将一小段延迟后再次尝试重新加密。 如果此问题不是间歇性的停止 SSO 服务，并尝试解决此问题。 一旦问题解决后，然后重启 SSO 服务，则重新启动 SSO 服务将自动执行重新加密。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何显示 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)  

- [主密钥服务器](../core/master-secret-server.md)
