---
title: 单一登录： 事件 10686 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e71f2a-e51d-4736-b06a-117142d30dae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600226ef7440b8be9d7927481170291b6c63faae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271021"
---
# <a name="single-sign-on-event-10686"></a>单一登录： 事件 10686
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10686|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_INFO_REPLAY_STARTED|  
|消息正文|正在重播存储的外部密码更改。%r<br /><br /> 重播文件： %1|  
  
## <a name="explanation"></a>解释  
 此消息事件表示，SSO 正在重播已存储的外部密码更改文件。 ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。  
  
## <a name="user-action"></a>用户操作  
  
-   不需要用户进行任何操作。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  
  
-   [密码同步](../core/password-synchronization2.md)