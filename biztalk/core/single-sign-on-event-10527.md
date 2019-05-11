---
title: 单一登录：Event 10527 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40995ad8-9f74-4e96-863d-427e23025ba1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57f5ac8452d96e3af54ff4d5cfc21f6664435bc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262503"
---
# <a name="single-sign-on-event-10527"></a>单一登录：事件 10527
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                      企业单一登录                                                                                      |
| 产品版本 |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                      |
|    事件 ID     |                                                                                                10527                                                                                                |
|  事件源   |                                                                                               ENTSSO                                                                                                |
|    组件    |                                                                                                  0                                                                                                  |
|  符号名称  |                                                                                     SSO_ERROR_GET_SECRET_FAILED                                                                                     |
|  消息正文   | 获取主机密 failed.%r 的请求<br /><br /> 密钥编号: %1 %r<br /><br /> 客户端用户: %2 %r<br /><br /> 客户端计算机: %3 %r<br /><br /> 跟踪 ID: %4 %r<br /><br /> 错误代码： %5 |

## <a name="explanation"></a>解释  
 此错误事件表示获取主密钥的请求已失败。 在这些情况下应该有相关的邮件应用程序事件日志中。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查应用程序事件日志关联的事件或错误。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  

- [管理主密钥](../core/managing-the-master-secret.md)
