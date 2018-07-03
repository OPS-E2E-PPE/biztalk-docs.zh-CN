---
title: 单一登录： 事件 10665 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d0de9d0-9b46-4f3a-b796-1ce3de01cf4c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e820b5d682a3ea5947d4811038d4a9bc5eaa38c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013918"
---
# <a name="single-sign-on-event-10665"></a>单一登录： 事件 10665
## <a name="details"></a>详细信息  

|                 |                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                               企业单一登录                                                |
| 产品版本 |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    事件 ID     |                                                         10665                                                          |
|  事件源   |                                                         ENTSSO                                                         |
|    组件    |                                                          N\A                                                           |
|  符号名称  |                                                 SSO_WARN_NO_PROPERTIES                                                 |
|  消息正文   | 读取密码同步适配器属性时出错。 将使用默认值。%r<br /><br /> 适配器: %1 %r<br /><br /> 错误代码： %2 |

## <a name="explanation"></a>解释  
 此警告事件表明，读取默认密码同步适配器属性时出错。 每个密码同步适配器都具有与其关联的配置属性。 这些属性存储在 SSO 配置存储中，是在创建密码同步适配器时由 SSO 命令行工具或 SSO 管理 MMC 创建的。  如果密码同步适配器是通过任何其他方法创建的，则可能会缺少某些属性，从而导致出现此错误。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  

-   验证密码同步适配器属性是否正确无误。  

-   重新创建密码同步适配器  

## <a name="more-info"></a>详细信息

- **密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [密码同步](../core/password-synchronization2.md)
