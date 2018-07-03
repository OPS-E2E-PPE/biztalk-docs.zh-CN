---
title: 单一登录： 事件 10652 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7fe452-bcec-4722-8ec6-78d4fe462a0a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2e27c678f2c031c642107cd770566f92d7ca708
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985742"
---
# <a name="single-sign-on-event-10652"></a>单一登录： 事件 10652
## <a name="details"></a>详细信息  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  产品名称   |                         企业单一登录                         |
| 产品版本 |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    事件 ID     |                                   10652                                   |
|  事件源   |                                  ENTSSO                                   |
|    组件    |                                    N\A                                    |
|  符号名称  |                   SSO_ERROR_PASSWORD_SYNC_START_FAILED                    |
|  消息正文   | 密码同步服务初始化失败。%r<br /><br /> 错误代码： %1 |

## <a name="explanation"></a>解释  
 此错误事件表示，由于发生异常，密码同步服务无法启动。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查应用程序和系统事件日志，以了解 ENTSSO 或其他服务的相关错误。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [密码同步](../core/password-synchronization2.md)
