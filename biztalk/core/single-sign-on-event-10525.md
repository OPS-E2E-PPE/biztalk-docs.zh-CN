---
title: 单一登录： 事件 10525 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cba8ef4-4e48-44a7-b791-bab7dc4b9cc0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae350ce6b1688d908dedb3961007401300d8d2fc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968190"
---
# <a name="single-sign-on-event-10525"></a>单一登录： 事件 10525
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                      企业单一登录                                                                       |
| 产品版本 |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    事件 ID     |                                                                                10525                                                                                 |
|  事件源   |                                                                                ENTSSO                                                                                |
|    组件    |                                                                                 N\A                                                                                  |
|  符号名称  |                                                                     SSO_INFO_GENERATE_SECRET_OK                                                                      |
|  消息正文   | 新的主密钥已成功 generated.%r<br /><br /> MSID: %1 %r<br /><br /> 客户端用户: %2 %r<br /><br /> 客户端计算机: %3 %r<br /><br /> 跟踪 ID: %4 |

## <a name="explanation"></a>解释  
 此信息事件表示已成功生成新主密钥。  

## <a name="user-action"></a>用户操作  

- 不需要用户进行任何操作。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  

- [管理主密钥](../core/managing-the-master-secret.md)
