---
title: 单一登录：事件 11031 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ecd24c2-e251-4eb9-b3ca-ec0f095bb23a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b0a8f424cc0b26e26b1006d6b1aca8be0339f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379855"
---
# <a name="single-sign-on-event-11031"></a>单一登录：事件 11031
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                企业单一登录                                                                                                                                |
| 产品版本 |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    事件 ID     |                                                                                                                                          11031                                                                                                                                          |
|  事件源   |                                                                                                                                         ENTSSO                                                                                                                                          |
|    组件    |                                                                                                                                           不可用                                                                                                                                           |
|  符号名称  |                                                                                                                         SSO_INFO_PS_WIN_CHANGE_INVALID_MAPPING                                                                                                                          |
|  消息正文   | Windows 密码更改。 已检测到但被忽略，因为它不再 valid.%r 此 Windows 帐户的映射<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 应用程序: %3 %r<br /><br /> 外部帐户: %4 %r<br /><br /> 客户端用户： %5 |
  
## <a name="explanation"></a>解释  
 它可能是 Windows 帐户存在并有效，但不在应用程序用户帐户。  
  
## <a name="user-action"></a>用户操作  
 删除映射，然后尝试重新创建它。