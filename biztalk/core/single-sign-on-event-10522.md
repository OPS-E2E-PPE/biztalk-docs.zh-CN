---
title: 单一登录： 事件 10522 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd634a57-01dc-44bd-bcf9-668689db7b77
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b56999d7898af01d0009a7722d78aed0dbf5dbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271877"
---
# <a name="single-sign-on-event-10522"></a>单一登录： 事件 10522
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10522|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_REENCRYPT|  
|消息正文|SSO 数据库重新加密失败。 将在 %1%minutes.%r 试<br /><br /> 错误代码： %2|  
  
## <a name="explanation"></a>解释  
 此错误事件指示 SSO 数据库重新加密失败。 SSO 服务启动时在主密钥服务器，它执行的第一个操作是检查是否有任何内容仍使用以前的主密钥加密的 SSO 数据库中。 如果找到任何内容，则系统会解密此信息（使用上一个密钥）并使用当前主密钥对其重新加密。 如果由于某种原因这一过程失败，则系统会发出此事件消息。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
-   检查错误代码，以确定错误的根本原因可能是什么。 这可能是网络或数据库的问题。 如果它是间歇性的然后不不需要任何操作因为将一小段延迟后再次尝试重新加密。 如果此问题不是间歇性，停止 SSO 服务，然后尝试解决此问题。 问题解决后重新启动 SSO 服务。重新启动 SSO 服务将自动执行重新加密。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何显示的 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)  
  
-   [主密钥服务器](../core/master-secret-server.md)