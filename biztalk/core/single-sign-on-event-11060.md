---
title: "单一登录： 事件 11060 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4851fba-0d3a-4a29-b720-a1d175d20555
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1423b7385e6c0b8f78fb815ec48b749556cd291f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11060"></a>单一登录： 事件 11060
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|11060|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_PS_MIIS_ACCESS_DENIED|  
|消息正文|只有 SSO 服务帐户接受 MIIS 中的 Windows 密码更改。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户: %2 %r<br /><br /> SSO 服务帐户: %3 %r<br /><br /> 错误代码： %4|  
  
## <a name="explanation"></a>解释  
 ENTSSO 服务器已接受来自 Microsoft Identity Integration Server (MIIS) 的密码更改。 但是，如果客户端用户（调用方）的帐户与 SSO 服务帐户相同，则 ENTSSO 服务器将只接受 MIIS 中的密码更改。  
  
## <a name="user-action"></a>用户操作  
 检查 MIIS 中密码同步调用方的配置。 有关详细信息，请参阅[如何用于 miis 进行密码同步配置 ENTSSO](../core/how-to-configure-entsso-for-miis-password-sync.md)。