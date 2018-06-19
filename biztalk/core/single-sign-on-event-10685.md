---
title: 单一登录： 事件 10685 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 810b37b5-51c4-4201-8d88-0bf7d9e16dae
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47844a979e93789f4baa94fbcbd58fd23762db84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271637"
---
# <a name="single-sign-on-event-10685"></a>单一登录： 事件 10685
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10685|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_REPLAY_CANNOT_OPEN|  
|消息正文|无法打开重播文件或进度文件。%r<br /><br /> 文件名: %1 %r<br /><br /> 错误代码： %2|  
  
## <a name="explanation"></a>解释  
 此警告事件表明 SSO 已经与 SSO 数据库重新建立了联系，但无法打开重播文件或进度文件。 如果 SSO 无法打开重播文件，它将继续尝试打开下一个重播文件。  
  
 ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。 进度文件指示，当在播放重播文件的过程中再次与 SSO 数据库失去联系时，SSO 能够读取多少重播文件。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告事件，请执行以下操作：  
  
-   您应检查系统和应用程序事件日志中的相关事件，确定 SSO 无法与 SSO 数据库取得联系的原因。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  
  
-   [密码同步](../core/password-synchronization2.md)