---
title: "单一登录： 事件 10733 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 01520ae4-f692-4697-82ce-53a8a63b5bd9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1387d7c853bba91bea429470d9a615e065a6e8dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10733"></a>单一登录： 事件 10733
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10733|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_PS_SET_WINDOWS_PASSWORD|  
|消息正文|更新 SSO 数据库中的 Windows 密码失败。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户： %2\\%3 %r<br /><br /> 错误代码： %4|  
  
## <a name="explanation"></a>解释  
 此警告事件表示密码同步更新在 SSO 数据库中指定的 Windows 帐户密码失败。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  
  
-   检查相关错误的系统和应用程序事件日志。  
  
-   验证指定帐户的密码是否为有效的 Windows 密码。  
  
 有关详细信息，请参阅下列资源：  
  
-   [密码同步](../core/password-synchronization2.md)