---
title: "单一登录： 事件 10682 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46f0f425-3946-4bac-a412-488c4afe460d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79aeff556fbbbbbbbcf41f63a37ab3b47311d697
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10682"></a>单一登录： 事件 10682
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10682|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_REPLAY_INVALID_DIR_FOUND|  
|消息正文|找到一个目录中重播文件目录-它将 ignored.%r<br />目录： %1|  
  
## <a name="explanation"></a>解释  
 此警告事件表明在重播文件目录中找到一个目录。 ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。 在这种情况下，密码更改存储在临时加密文件中，并在该文件再次可用时重播回 SSO 数据库。 重播文件目录应只包含重播文件（如果找到一个目录，则会发出此错误消息）。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下一项或多项操作：  
  
-   使用命令行工具 ssoconfig-replayFiles 更改您的重播目录。  
  
-   删除损坏的目录（如果未使用）。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  
  
-   [密码同步](../core/password-synchronization2.md)