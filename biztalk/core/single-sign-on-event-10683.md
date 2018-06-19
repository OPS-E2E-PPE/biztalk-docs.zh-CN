---
title: 单一登录： 事件 10683 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83cd1b96-cd79-4ddc-952b-94a7de216666
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c383a02400523686f00011c5eb6f71c9542ec5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271541"
---
# <a name="single-sign-on-event-10683"></a>单一登录： 事件 10683
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10683|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD|  
|消息正文|重播文件已删除，因为它太 old.%r<br />重播文件： %1|  
  
## <a name="explanation"></a>解释  
 此警告事件表明重播文件因太旧而被删除。 ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。 在这种情况下，密码更改存储在临时的加密文件中，在重新变为可用时重播回 SSO 数据库。 当要将文件重播回 SSO 数据库时，如果检测到文件太旧，则会放弃该文件。 所有旧的密码更改将被丢弃 SSO 密码同步系统;`password sync age`参数确定密码的最大时间段更改请求和可以使用命令行工具控制， **ssoconfig-syncAge**或 SSO 管理 MMC。  
  
## <a name="user-action"></a>用户操作  
  
-   不需要用户进行任何操作。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  
  
-   [密码同步](../core/password-synchronization2.md)