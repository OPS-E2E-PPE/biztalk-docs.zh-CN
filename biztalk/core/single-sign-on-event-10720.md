---
title: 单一登录： 事件 10720 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1878f658-e89d-499c-b61d-0a894234fa6a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa248270bd7d48699defcf00efedec3e5a545aac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971110"
---
# <a name="single-sign-on-event-10720"></a>单一登录： 事件 10720
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                   企业单一登录                                                                                                    |
| 产品版本 |                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                   |
|    事件 ID     |                                                                                                             10720                                                                                                              |
|  事件源   |                                                                                                             ENTSSO                                                                                                             |
|    组件    |                                                                                                              N\A                                                                                                               |
|  符号名称  |                                                                                                 SSO_INFO_REPLAY_RECORD_WRITTEN                                                                                                 |
|  消息正文   | 外部密码更改已成功存储在重播文件中。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> 文件名称: %4 %r<br /><br /> 记录号： %5 |

## <a name="explanation"></a>解释  
 此信息事件表示外部密码更改已成功存储在重播文件中。  

## <a name="user-action"></a>用户操作  

- 不必进行用户操作。  

  有关详细信息，请参阅下列资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
