---
title: 单一登录： 事件 10707 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59629786-4f98-4861-aba3-153670bafc12
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81f4d484aa7a69f23cb66a921f1c630db9fcf790
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
ms.locfileid: "22271773"
---
# <a name="single-sign-on-event-10707"></a>单一登录： 事件 10707
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|產品名稱|企業單一登入|  
|產品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10707|  
|事件源|ENTSSO|  
|元件|N\A|  
|符号名称|SSO_WARN_PS_NO_APP_SYNC|  
|消息正文|此适配器的密码同步标志必须允许密码同步并且必须匹配全局标志。 请检查适配器标志和全局标志。%r<br /><br /> 适配器: %1|  
  
## <a name="explanation"></a>解释  
 此警告事件表明此适配器的密码同步标志必须允许密码同步并且必须匹配全局标志。  
  
 密码同步适配器的密码同步由两个标志控制，一个允许将密码发送到外部系统 (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL)，另一个允许从外部系统接收密码 (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB)。 为成功进行密码同步，这些标志必须都设置为“全局标志”，也可以设置为特定适配器标志。 当外部密码同步适配器请求密码同步，并且这些标志未设置为“全局标志”和适配器标志时，将发出此警告事件。  
  
## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  
  
-   使用 SSO 管理 MMC 管理单元 (系统 & #124;属性 & #124;选项） 或命令行工具  `ssomanage –enable winsync/extsync` 若要启用的全局标志。  
  
## <a name="more-info"></a>详细信息
  
-   **企业单一登录标志** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
  
-   [如何管理密码同步](../core/how-to-administer-password-synchronization.md)