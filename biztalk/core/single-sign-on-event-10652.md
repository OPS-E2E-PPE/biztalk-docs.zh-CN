---
title: 单一登录： 事件 10652 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7fe452-bcec-4722-8ec6-78d4fe462a0a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62066b2fbbc47d07fa57f047313ed5ed8cda47d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270909"
---
# <a name="single-sign-on-event-10652"></a>单一登录： 事件 10652
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10652|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_PASSWORD_SYNC_START_FAILED|  
|消息正文|密码同步服务初始化失败。%r<br /><br /> 错误代码： %1|  
  
## <a name="explanation"></a>解释  
 此错误事件表示，由于发生异常，密码同步服务无法启动。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
-   检查应用程序和系统事件日志，以了解 ENTSSO 或其他服务的相关错误。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [密码同步](../core/password-synchronization2.md)