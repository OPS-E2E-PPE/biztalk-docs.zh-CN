---
title: "单一登录： 事件 10653 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0d85aca-20d9-4d65-8834-b31eacf143c8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91ec21a7883c3c1d3e97519f9239050ea18035fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10653"></a>单一登录： 事件 10653
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10653|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED|  
|消息正文|拒绝访问（适用于适配器的）密码同步服务器。%r|  
  
## <a name="explanation"></a>解释  
 此错误事件表示，客户端尝试与服务器联系，但是调用被拒绝。 这可能是由许多不同原因引起的，例如协议不正确或没有足够的安全权限。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
-   请注意此消息中的信息和事件日志中的任何相关信息并与 Microsoft 产品支持服务联系。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [密码同步](../core/password-synchronization2.md)