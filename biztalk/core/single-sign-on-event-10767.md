---
title: 单一登录：事件 10767 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef5efc04-a0b5-4fc7-9d0e-f7aa9a9c413d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f225e6e80467aa269e579846c6c8ece05963cdb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394296"
---
# <a name="single-sign-on-event-10767"></a>单一登录：事件 10767
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                企业单一登录                                                |
| 产品版本 |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                |
|    事件 ID     |                                                          10767                                                          |
|  事件源   |                                                         ENTSSO                                                          |
|    组件    |                                                           不可用                                                           |
|  符号名称  |                                                 ENTSSO_E_NO_SSO_SERVER                                                  |
|  消息正文   | 无法联系 SSO 服务器"%1"。 检查配置了 SSO 以及 SSO 服务正在该服务器上。 |
  
## <a name="explanation"></a>解释  
 ENTSSO 客户端将无法联系 ENTSSO 服务器。  
  
## <a name="user-action"></a>用户操作  
 检查网络连接，并确保正确拼写了服务器名称。