---
title: "单一登录： 事件 10509 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f906823f-db3f-45fc-bf61-cbe6a9566bd7
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4d61cbb7af195aa88c36b64149366334c835b80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10509"></a>单一登录： 事件 10509
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10509|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_INFO_SERVICE_REMOVE_FAILED|  
|消息正文|无法删除 SSO 服务。%r<br /><br /> 错误代码： %1|  
  
## <a name="explanation"></a>解释  
 此事件表示无法卸载 ENTSSO 服务。 只有在手动卸载企业单一登录时，才会发生此事件。  
  
## <a name="user-action"></a>用户操作  
 若要解决此事件，请执行以下操作：  
  
-   检查应用程序和系统事件日志，以了解 ENTSSO 或其他服务的相关错误。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [安装 SSO](../core/installing-sso.md)  
  
-   [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)