---
title: 单一登录： 事件 10535 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b570b0b-5c45-4be3-80c9-a2c50601b677
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3f96032c8176a251090453e493487a97d9cf0fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270077"
---
# <a name="single-sign-on-event-10535"></a>单一登录： 事件 10535
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10535|  
|事件源|ENTSSO|  
|组件|CO|  
|符号名称|SSO_INFO_API_AUDIT|  
|消息正文|SSO 审核%r<br /><br /> 函数: %1 %r<br /><br /> 跟踪 ID: %2 %r<br /><br /> 客户端计算机: %3 %r<br /><br /> 客户端用户: %4 %r<br /><br /> 应用程序名称： %5|  
  
## <a name="explanation"></a>解释  
 此信息审核事件表明，发生了一个达到用户定义的审核级别的事件。 此事件消息包括：  
  
 **函数：** 正在执行的函数  
  
 **跟踪 ID:** 唯一 GUID 生成第一个 SSO API 时调用。  
  
 **客户端计算机：** 函数生成的位置的客户端计算机。  
  
 **客户端用户：** 调用该函数的用户帐户的名称。  
  
 **应用程序名：** 名称的 SSO affiliate 应用程序与此函数。  
  
 此类型事件用于诊断应用程序开发、疑难解答或运行过程中的问题。 提供的信息可用于确定正在调用的 SSO API。  
  
 审核级别可以设置为 0/1/2/3 – 0 意味着“无”、1 意味着“低”（只显示错误）、2 意味着“中”（显示错误和警告），以及 3 意味着“高”（显示所有的审核消息）。  
  
## <a name="user-action"></a>用户操作  
  
-   检查相关事件消息的事件日志。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何审核 SSO](../core/how-to-audit-sso.md)  
  
-   [使用 SSO](../core/using-sso.md)