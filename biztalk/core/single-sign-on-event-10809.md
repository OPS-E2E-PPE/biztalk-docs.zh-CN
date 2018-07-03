---
title: 单一登录： 事件 10809 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d4bf5ba006af8c479abc621accdc28296c0eae3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016060"
---
# <a name="single-sign-on-event-10809"></a>单一登录： 事件 10809
## <a name="details"></a>详细信息  
  
|                 |                                                                   |
|-----------------|-------------------------------------------------------------------|
|  产品名称   |                     企业单一登录                     |
| 产品版本 |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]     |
|    事件 ID     |                               10809                               |
|  事件源   |                              ENTSSO                               |
|    组件    |                                N/A                                |
|  符号名称  |                  ENTSSO_E_HISSO_APP_NOT_ENABLED                   |
|  消息正文   | 主机启动的单一登录未启用该应用程序。 |
  
## <a name="explanation"></a>解释  
 主机启动的单一登录未启用该应用程序。  
  
## <a name="user-action"></a>用户操作  
 使用管理工具配置主机启动的单一登录。 这会设置  
  
 SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS 标志。