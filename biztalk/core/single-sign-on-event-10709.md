---
title: 单一登录：Event 10709 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98e86890-88dd-49f0-bb2c-1234507e8be5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4f69e2226ab304e9d6b23ead1c9e2b84ffa9fb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397247"
---
# <a name="single-sign-on-event-10709"></a>单一登录：事件 10709
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                  企业单一登录                                                                                                                   |
| 产品版本 |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    事件 ID     |                                                                                                                            10709                                                                                                                             |
|  事件源   |                                                                                                                            ENTSSO                                                                                                                            |
|    组件    |                                                                                                                             N\A                                                                                                                              |
|  符号名称  |                                                                                                                SSO_WARN_PS_PCNS_ACCESS_DENIED                                                                                                                |
|  消息正文   | 从 PCNS 的 Windows 密码更改将仅接受来自域控制器中访问 domain.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户: %2 %r<br /><br /> 访问域: %3 %r<br /><br /> 访问 Sid: %4 %r<br /><br /> 错误代码： %5 |

## <a name="explanation"></a>解释  
 此警告事件表明 Windows 密码更改已在 ENTSSO 服务器域之外的服务器上收到来自密码更改通知服务 (PCNS)。 Windows 密码更改将仅接受来自 ENTSSO 服务器所在域中的域控制器。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- ENTSSO 服务器配置为 PCNS 位于同一域中。  

  有关详细信息，请参阅下列资源：  

- [密码同步](../core/password-synchronization2.md)
