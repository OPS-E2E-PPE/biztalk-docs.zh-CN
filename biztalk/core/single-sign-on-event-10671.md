---
title: 单一登录： 事件 10671 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c5564f-6412-4e83-9bec-03264e992ebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db44ecfd9980db445d3a611e4992f4b3961b3548
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270613"
---
# <a name="single-sign-on-event-10671"></a>单一登录： 事件 10671
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10671|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED|  
|消息正文|Windows 密码更改将导致更改同一外部系统上的多个帐户。%r<br /><br /> 这是允许的，因为此外部系统的适配器配置为允许映射冲突。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户: %3 %r<br /><br /> 外部帐户 1: %4 %r<br /><br /> 外部帐户 2: %5|  
  
## <a name="explanation"></a>解释  
 此信息事件表示 Windows 密码更改将更改同一外部系统上的多个帐户。  
  
## <a name="user-action"></a>用户操作  
  
-   不需要用户进行任何操作。  
  
## <a name="more-info"></a>详细信息
  
-   **密码同步适配器属性： 选项**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [密码同步](../core/password-synchronization2.md)