---
title: 单一登录： 事件 11035 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d551083c-a897-4a76-a40c-2254d3a3e52e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e104d28517eab153880e3c922f3fd1f174a6170a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276709"
---
# <a name="single-sign-on-event-11035"></a>单一登录： 事件 11035
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11035|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER|  
|消息正文|Windows 密码更改。 已检测到此 Windows 帐户的映射，但忽略该映射，因为尚未为此应用程序配置密码同步。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 应用程序: %3 %r<br /><br /> 外部帐户: %4 %r<br /><br /> 客户端用户： %5|  
  
## <a name="explanation"></a>解释  
 已检测到此 Windows 帐户的映射，但忽略该映射，因为尚未为此应用程序配置密码同步。  
  
## <a name="user-action"></a>用户操作  
 有关配置密码同步的信息，请参阅[密码同步](../core/password-synchronization2.md)。