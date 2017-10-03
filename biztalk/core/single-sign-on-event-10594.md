---
title: "单一登录： 事件 10594 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f4c6041-39a8-49bc-b39e-66cb6eb2efae
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804b2616080ceee0b6a31f7623e19e05c11481f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10594"></a>单一登录： 事件 10594
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10594|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_WARN_TICKET_VALIDATE_FAILED|  
|消息正文|票证验证失败。 发送方姓名必须与匹配的票证 issuer.%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 票证颁发者: %2 %r<br /><br /> 发送方姓名： %3|  
  
## <a name="explanation"></a>解释  
 为了使票证有效，“票证颁发者”字段与“发件人姓名”字段（在警告消息中）必须匹配。 但是，如果消息是通过不受信任的 BizTalk 主机发送的，则“发件人姓名”字段将更改为该不受信任的 BizTalk 主机的名称，并且票证将无效。  
  
## <a name="user-action"></a>用户操作  
 如果您要使用企业单一登录，请确保您的消息只流经受信任的 BizTalk 主机。 这将降低在消息中篡改数据的风险。  
  
 如果您完全理解您的方案中的安全情况，可以关闭对此应用程序的验证。 请注意，验证是一个管理选项，可以关闭系统验证，也可以只关闭对此特定应用程序进行验证。