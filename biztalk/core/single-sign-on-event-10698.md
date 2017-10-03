---
title: "单一登录： 事件 10698 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f467934d-fef5-4962-a341-18f272d84108
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca4d65927e7e9d01f7c73eb64a19bc613496f5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10698"></a>单一登录： 事件 10698
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10698|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_INFO_REPLAY_FILE_DELETED|  
|消息正文|重播文件或进度文件已 deleted.%r<br /><br /> 文件名： %1|  
  
## <a name="explanation"></a>解释  
 此信息事件指示 SSO 已删除了某个重播和/或进度文件。  
  
 ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。 进度文件指示距离通过 SSO 时能够读取文件的情况下与 SSO 数据库的联系重播再次将丢失。  
  
## <a name="user-action"></a>用户操作  
  
-   不需要用户进行任何操作。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  
  
-   [密码同步](../core/password-synchronization2.md)