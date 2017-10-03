---
title: "单一登录： 事件 10721 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90295307-2dfa-4f21-9697-aaafd0a0b85e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcf17d9e32d56bba9985fe476a6830257889052a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10721"></a>单一登录： 事件 10721
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10721|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_INFO_REPLAY_FILE_CLOSED_FULL|  
|消息正文|重播文件已关闭，因为它已满。%r<br /><br /> 文件名： %1|  
  
## <a name="explanation"></a>解释  
 此信息事件表明，重播文件已关闭，因为它已满。 如有必要，将创建一个新的重播文件。  
  
## <a name="user-action"></a>用户操作  
  
-   不必进行用户操作。  
  
 有关详细信息，请参阅下列资源：  
  
-   [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  
  
-   [密码同步](../core/password-synchronization2.md)