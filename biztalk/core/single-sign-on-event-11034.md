---
title: 单一登录： 事件 11034 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 828bc5fb-12ab-4eea-94f2-2434ad0ee033
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c66245fe478dddeb539344503d8658719a604ed5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278213"
---
# <a name="single-sign-on-event-11034"></a>单一登录： 事件 11034
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11034|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_INFO_PS_WIN_CHANGE_APP_INCORRECT_TYPE|  
|消息正文|Windows 密码更改。 检测到此 Windows 帐户的一个映射，但由于应用程序的类型不正确，此映射被忽略。 只有“个人”或“组”类型的应用程序才支持 Windows 密码同步。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 应用程序: %3 %r<br /><br /> 外部帐户: %4 %r<br /><br /> 客户端用户： %5|  
  
## <a name="explanation"></a>解释  
 只有“个人”或“组”类型的应用程序才支持 Windows 密码同步。  
  
## <a name="user-action"></a>用户操作  
 有关详细信息，请参阅[密码同步](../core/password-synchronization2.md)。