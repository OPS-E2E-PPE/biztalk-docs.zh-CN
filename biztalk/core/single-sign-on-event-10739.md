---
title: 单一登录： 事件 10739 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1039c832-80ff-4cc2-97b4-2671672b6b12
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8a3dc964d830155a63a5ada8817e8b44aaa4c18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271349"
---
# <a name="single-sign-on-event-10739"></a>单一登录： 事件 10739
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10739|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER|  
|消息正文|更新 SSO 数据库中的 Windows 密码失败。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户： %3\\%4 %r<br /><br /> 错误代码： %5|  
  
## <a name="explanation"></a>解释  
 此警告事件表示 SSO 更新 SSO 数据库中的 Windows 密码失败。 导致该警告消息中描述的失败的原因有很多，在某些情况下，此警告可能表示配置问题，或者是在进行密码更改时删除了映射。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   重试更改密码。  
  
-   如果更多的尝试继续失败，则使用 UI 或命令行工具来手动更改密码。  
  
 有关详细信息，请参阅下列资源：  
  
-   [密码同步](../core/password-synchronization2.md)