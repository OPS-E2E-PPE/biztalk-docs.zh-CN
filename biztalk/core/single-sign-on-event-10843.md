---
title: "单一登录： 事件 10843 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 847e464e-5733-4703-905f-d44a4c4f5cc3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd86a39d515858e1cda09317ba6139bc67c95ed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10843"></a>单一登录： 事件 10843
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10843|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_NO_SECRET2|  
|消息正文|无法执行加密或解密，因为密钥不在主密钥服务器中。 有关相关错误，请参阅事件日志（在计算机 %1 上）。|  
  
## <a name="explanation"></a>解释  
 拒绝访问。  
  
## <a name="user-action"></a>用户操作  
 主密钥服务器脱机，或主密钥服务器缺少所需的主密钥。 参阅指定计算机上的事件日志，了解相关错误。