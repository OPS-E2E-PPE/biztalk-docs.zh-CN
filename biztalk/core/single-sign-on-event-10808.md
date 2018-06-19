---
title: 单一登录： 事件 10808 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4efc1d-f163-4440-a78e-53065c6af36c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b891a8cb076c332eca8918ece713385c1bbccc3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277085"
---
# <a name="single-sign-on-event-10808"></a>单一登录： 事件 10808
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10808|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED|  
|消息正文|没有为主机启动的单一登录启用 SSO 系统。|  
  
## <a name="explanation"></a>解释  
 没有为主机启动的单一登录启用 SSO 系统。  
  
## <a name="user-action"></a>用户操作  
 使用管理工具配置主机启动的单一登录。 这便会设置  
  
 SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS 标记。