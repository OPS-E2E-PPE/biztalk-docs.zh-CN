---
title: "单一登录： 事件 10809 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e010c6ee391e72ec270ddbdc767bed861836cb8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10809"></a>单一登录： 事件 10809
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10809|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_HISSO_APP_NOT_ENABLED|  
|消息正文|主机启动的单一登录未启用该应用程序。|  
  
## <a name="explanation"></a>解释  
 主机启动的单一登录未启用该应用程序。  
  
## <a name="user-action"></a>用户操作  
 使用管理工具配置主机启动的单一登录。 这便会设置  
  
 SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS 标志。