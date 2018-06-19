---
title: 单一登录： 事件 10706 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73db77e-5bb6-431c-a8ca-5682d7ab3d6a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5703c81d87376349561f644da558b8594cd51b79
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
ms.locfileid: "22271557"
---
# <a name="single-sign-on-event-10706"></a>单一登录： 事件 10706
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|產品名稱|企業單一登入|  
|產品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10706|  
|事件源|ENTSSO|  
|元件|N\A|  
|符号名称|SSO_WARN_PS_NO_GLOBAL_SYNC|  
|消息正文|组适配器要求全局标志允许密码同步。 请检查全局标志。%r<br /><br /> 适配器: %1|  
  
## <a name="explanation"></a>解释  
 此警告事件表示，外部密码同步适配器请求密码同步，并且未设置全局标记。 有两个标志，允许发送到外部系统的密码︰ SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL，另一个允许接收来自外部系统 SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB 的密码。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   使用 SSO 管理 MMC 管理单元中，(系统 & #124;属性 & #124;选项） 或命令行工具  `ssomanage –enable winsync/extsync` 若要启用的全局标志。  
  
## <a name="more-info"></a>详细信息
  
-   **企业单一登录标志** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [如何管理密码同步](../core/how-to-administer-password-synchronization.md)