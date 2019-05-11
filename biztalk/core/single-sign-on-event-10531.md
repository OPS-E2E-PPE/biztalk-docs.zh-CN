---
title: 单一登录：事件 10531 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 264941f4-7791-4a1f-a0bf-b992c9ccda64
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34767fb719ffe272720715ed1f4827979c9ff880
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262367"
---
# <a name="single-sign-on-event-10531"></a>单一登录：事件 10531
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                    企业单一登录                                                                                     |
| 产品版本 |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    事件 ID     |                                                                                              10531                                                                                               |
|  事件源   |                                                                                              ENTSSO                                                                                              |
|    组件    |                                                                                               N\A                                                                                                |
|  符号名称  |                                                                                     SSO_ERROR_GET_SECRET_OK                                                                                      |
|  消息正文   | 获取主机密 succeeded.%r 的请求<br /><br /> 密钥编号: %1 %r<br /><br /> MSID: %2 %r<br /><br /> 客户端用户: %3 %r<br /><br /> 客户端计算机: %4 %r<br /><br /> 跟踪 ID: %5 |

## <a name="explanation"></a>解释  
 此事件表示主密钥的请求已成功。  

## <a name="user-action"></a>用户操作  

- 不不需要任何用户操作。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  

- [管理主密钥](../core/managing-the-master-secret.md)
