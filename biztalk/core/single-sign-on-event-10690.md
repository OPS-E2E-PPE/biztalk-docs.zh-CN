---
title: "单一登录： 事件 10690 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0998f8dc-47de-4dc3-8905-3844177a7c54
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c320db046a61e77577bb6fe2778904ab445f253
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10690"></a>单一登录： 事件 10690
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10690|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_REPLAY_INCORRECT_RECORD_NUMBER|  
|消息正文|重播 file.%r 中检测到损坏<br /><br /> 重播文件： %1|  
  
## <a name="explanation"></a>解释  
 SSO 已重新建立与 SSO 数据库的联系，但无法读取重播文件，因为损坏，该值指示此错误事件。 如果 SSO 无法打开重播文件，将会继续执行下一步的重播文件 （如果有）。  
  
 ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。 进度文件指示距离通过 SSO 时能够读取文件的情况下与 SSO 数据库的联系重播再次将丢失。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
-   检查有相关事件的系统和应用程序事件日志。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  
  
-   [密码同步](../core/password-synchronization2.md)