---
title: 单一登录：Event 10679 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645f2b74-2cbe-4c6a-b0f5-7e31f93f88c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f3b551d0c5eecab6ad84b54303bd2c25bbf46eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397440"
---
# <a name="single-sign-on-event-10679"></a>单一登录：事件 10679
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                           企业单一登录                                                                                                            |
| 产品版本 |                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                           |
|    事件 ID     |                                                                                                                     10679                                                                                                                      |
|  事件源   |                                                                                                                     ENTSSO                                                                                                                     |
|    组件    |                                                                                                                      N\A                                                                                                                       |
|  符号名称  |                                                                                                          SSO_WARN_PS_MAPPING_DISABLED                                                                                                          |
|  消息正文   | 外部密码更改。 密码未更改外部帐户因为映射被 disabled.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户： %4 |

## <a name="explanation"></a>解释  
 此警告事件表示，密码未更改外部帐户因为已禁用映射。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

-   使用 SSO 管理工具来启用此适配器的映射。  

## <a name="more-info"></a>详细信息

- [密码同步](../core/password-synchronization2.md)  

- **密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
