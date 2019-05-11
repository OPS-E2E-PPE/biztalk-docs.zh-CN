---
title: 单一登录：Event 10820 | Microsoft Docs
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
ms.openlocfilehash: 59b0795514529e4e4236ebab96ceb5730171884f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395468"
---
# <a name="single-sign-on-event-10820"></a>单一登录：事件 10820
## <a name="details"></a>详细信息  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  产品名称   |                                  企业单一登录                                   |
| 产品版本 |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    事件 ID     |                                            10820                                             |
|  事件源   |                                            ENTSSO                                            |
|    组件    |                                             不可用                                              |
|  符号名称  |                                ENTSSO_E_REQUIRE_OLD_PASSWORD                                 |
|  消息正文   | 更改外部帐户的密码时，适配器必须提供旧密码。 |
  
## <a name="explanation"></a>解释  
 此应用程序配置密码同步适配器所需提供旧密码的方式。  
  
## <a name="user-action"></a>用户操作  
 检查您的密码同步适配器的配置。