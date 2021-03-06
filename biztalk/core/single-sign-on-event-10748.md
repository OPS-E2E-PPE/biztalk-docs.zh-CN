---
title: 单一登录：Event 10748 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4b18ea-6565-4c0b-89f8-30a8c67601ba
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 518f12cbf89b345775c6e486d522ca1e667d9142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395486"
---
# <a name="single-sign-on-event-10748"></a>单一登录：事件 10748
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                              企业单一登录                                                                                              |
| 产品版本 |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    事件 ID     |                                                                                                        10748                                                                                                        |
|  事件源   |                                                                                                       ENTSSO                                                                                                        |
|    组件    |                                                                                                         N\A                                                                                                         |
|  符号名称  |                                                                                           SSO_WARN_PS_ADAPTER_NOT_RUNNING                                                                                           |
|  消息正文   | 无法联系目标适配器。<br /><br /> 它不能运行或 initialized.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> SSO 服务器名称: %3 %r<br /><br /> 错误代码： %4 |

## <a name="explanation"></a>解释  
 此警告事件表示密码同步无法联系指定的密码同步适配器。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

- 检查外部适配器。  

- 使用 Mmc 管理单元或命令行工具启用适配器。  

- 检查系统和应用程序事件日志中的关联错误。  

  有关详细信息，请参阅下列资源：  

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)
