---
title: 单一登录： 事件 10820 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2da93a2c-d00d-4ca0-a0cf-453cee4bf3c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78b566c4dfe4437017b743228c9bae2631c79a00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011654"
---
# <a name="single-sign-on-event-10820"></a>单一登录： 事件 10820
## <a name="details"></a>详细信息  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  产品名称   |                                  企业单一登录                                   |
| 产品版本 |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    事件 ID     |                                            10820                                             |
|  事件源   |                                            ENTSSO                                            |
|    组件    |                                             N/A                                              |
|  符号名称  |                                ENTSSO_E_REQUIRE_OLD_PASSWORD                                 |
|  消息正文   | 为外部帐户更改密码时，适配器必须提供旧密码。 |
  
## <a name="explanation"></a>解释  
 此应用程序配置为需要密码同步适配器提供旧密码。  
  
## <a name="user-action"></a>用户操作  
 检查密码同步适配器的配置。