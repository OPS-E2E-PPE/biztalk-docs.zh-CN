---
title: 单一登录： 事件 10747 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63ae1ab4-0f4e-45a7-83c1-31b8037e4dd7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6303d7dd39c2168d67d206401bdf8d2c30f5d21
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993910"
---
# <a name="single-sign-on-event-10747"></a>单一登录： 事件 10747
## <a name="details"></a>详细信息  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                       企业单一登录                                                        |
| 产品版本 |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    事件 ID     |                                                                 10747                                                                  |
|  事件源   |                                                                  N\A                                                                   |
|    组件    |                                                                  N\A                                                                   |
|  符号名称  |                                                     SSO_ERROR_UNKNOWN_NOTIFICATION                                                     |
|  消息正文   | 收到未知通知类型。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 通知类型： %3 |

## <a name="explanation"></a>解释  
 此错误事件表明 SSO 服务检测到具有无效通知类型的内部错误。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查系统和应用程序事件日志中的相关事件。  

  有关详细信息，请参阅下列资源：  

- [使用 SSO](../core/using-sso.md)
