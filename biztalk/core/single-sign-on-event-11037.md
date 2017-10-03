---
title: "单一登录： 事件 11037 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b523ff56-112e-4798-97d2-b1b19e130ec7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 245b4af07a88c4015048db0ea20fe04b714d0ed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11037"></a>单一登录： 事件 11037
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11037|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_INFO_PS_MAPPING_INVALID|  
|消息正文|外部密码更改。 未更改外部帐户的密码，因为映射不再有效。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户： %4|  
  
## <a name="explanation"></a>解释  
 映射不再是“应用程序用户”组的一部分。  
  
## <a name="user-action"></a>用户操作  
 此消息列出了外部帐户和应用程序的名称。 您可以使用这一信息来查明映射不再有效的原因。