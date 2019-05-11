---
title: 单一登录：Event 10676 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec0e86fb-921d-4505-b458-51b565123ea7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1779d8f30d4e82d9c63dacc503cbd9dfab555a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397478"
---
# <a name="single-sign-on-event-10676"></a>单一登录：事件 10676
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                             企业单一登录                                                                                             |
| 产品版本 |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    事件 ID     |                                                                                                       10676                                                                                                       |
|  事件源   |                                                                                                      ENTSSO                                                                                                       |
|    组件    |                                                                                                        N\A                                                                                                        |
|  符号名称  |                                                                                          SSO_ERROR_REQUIRE_OLD_PASSWORD                                                                                           |
|  消息正文   | 外部密码更改。 更改外部帐户的密码时，适配器必须提供旧 password.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户： %3 |

## <a name="explanation"></a>解释  
 此错误事件表示密码同步适配器已配置为要求从外部系统，旧密码，但未提供旧密码。 未配置外部系统 （外部密码同步适配器），或者按预期运行或密码同步适配器配置不正确。 此错误也可能返回错误代码符号名称 ENTSSO_E_REQUIRE_OLD_PASSWORD。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

-   使用 SSO 管理工具来设置用户可配置属性**验证旧密码**密码同步适配器选项属性选项卡上。创建适配器通过命令行工具 (ssops.exe) 使用的标志名称时，还可以设置此属性`verifyOldPassword`和也时创建一个新的密码同步适配器使用密码同步适配器向导。  

## <a name="more-info"></a>详细信息

- [密码同步](../core/password-synchronization2.md)  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
