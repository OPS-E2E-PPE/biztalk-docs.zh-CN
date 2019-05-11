---
title: 单一登录：Event 11060 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4851fba-0d3a-4a29-b720-a1d175d20555
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ded0ef8904e0a9def8d02ffe477ef7a3d846c14d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258686"
---
# <a name="single-sign-on-event-11060"></a>单一登录：事件 11060
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                               企业单一登录                                                                                               |
| 产品版本 |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    事件 ID     |                                                                                                         11060                                                                                                         |
|  事件源   |                                                                                                        ENTSSO                                                                                                         |
|    组件    |                                                                                                          不可用                                                                                                          |
|  符号名称  |                                                                                            SSO_WARN_PS_MIIS_ACCESS_DENIED                                                                                             |
|  消息正文   | 从 MIIS 进行 Windows 密码更改将仅接受来自 account.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户: %2 %r<br /><br /> SSO 服务帐户: %3 %r<br /><br /> 错误代码： %4 |
  
## <a name="explanation"></a>解释  
 ENTSSO 服务器从 Microsoft Identity Integration Server (MIIS) 收到密码更改。 但是，ENTSSO 服务器将只接受从 MIIS 进行密码更改，如果客户端用户 （调用方） 是与 SSO 服务帐户相同的帐户。  
  
## <a name="user-action"></a>用户操作  
 检查 MIIS 中密码同步调用方的配置。 有关详细信息，请参阅[如何实现 MIIS 密码同步配置 ENTSSO](../core/how-to-configure-entsso-for-miis-password-sync.md)。