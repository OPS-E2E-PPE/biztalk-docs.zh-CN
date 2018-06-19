---
title: 单一登录： 事件 10517 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b63e4b0-0ef6-45c2-b8b1-55ac20e79e26
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2716eb7d331ec5c15070555a028c00310188856c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271237"
---
# <a name="single-sign-on-event-10517"></a>单一登录： 事件 10517
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10517|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_BAD_SSO_ADMIN|  
|消息正文|SSO 管理员帐户无效。 如果是本地帐户，请检查服务器上是否存在此帐户。 如果是域帐户，请与域管理员联系。 当帐户有效时，启用 SSO。%r<br /><br /> SSO Administrators: %1 %r<br /><br /> 无效帐户: %2 %r<br /><br /> 错误代码： %3|  
  
## <a name="explanation"></a>解释  
 此错误事件表示为企业单一登录指定的 SSO 管理员帐户不是有效的 Windows 帐户。 运行企业单一登录服务的服务帐户必须是此帐户的成员。 SSO 管理员帐户可以是 Windows 组帐户，也可以是单个帐户。 SSO 管理员帐户可以是域组帐户，也可以是本地组帐户。 时使用个人帐户，不能为其他个人帐户更改此帐户。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
-   验证 SSO 管理员帐户是否存在。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [SSO 用户组](../core/sso-user-groups.md)