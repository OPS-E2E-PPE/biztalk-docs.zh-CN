---
title: 单一登录： 事件 11071 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c0f61b9-cd86-482b-a8fe-0093a928c89b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e744e4f477ee45e6f634e8e4b2ca976754cbecf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276293"
---
# <a name="single-sign-on-event-11071"></a>单一登录： 事件 11071
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11071|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH|  
|消息正文|已放弃 Windows 密码更改，因为 Windows 密码长度为零个字符。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 客户端用户： %3|  
  
## <a name="explanation"></a>解释  
 已放弃 Windows 密码更改，因为 Windows 密码长度为零个字符。 已提供 Windows 帐户和客户端用户名。  
  
## <a name="user-action"></a>用户操作  
 使用 SSO 系统要求的字符的个数和类型重新更改密码。