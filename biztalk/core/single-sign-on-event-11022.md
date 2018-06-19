---
title: 单一登录： 事件 11022 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c65ca12b-dda8-408b-9512-39df6f8e035b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccae36e9beef672e6c5fb7917c88341ce4bb3c08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276989"
---
# <a name="single-sign-on-event-11022"></a>单一登录： 事件 11022
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11022|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED|  
|消息正文|外部密码更改将导致不同外部帐户的更改。%r<br /><br /> 此操作已被阻止，因为此外部系统的适配器配置为不允许映射冲突。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户: %3 %r<br /><br /> 外部帐户 1: %4 %r<br /><br /> 外部帐户 2: %5|  
  
## <a name="explanation"></a>解释  
 此信息消息表示，外部密码更改（可能导致不同的外部帐户更改）失败。  
  
## <a name="user-action"></a>用户操作  
 尽管没有做出任何更改（因为此系统配置为不允许映射冲突），您仍然应该立即确认这是利用您的信息和授权做出的更改。 如果是这样，无需进行任何操作。 如果不是，请查明进行更改的位置，并确认此更改位于系统中的安全位置。