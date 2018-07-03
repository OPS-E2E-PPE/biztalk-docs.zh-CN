---
title: 单一登录： 事件 10856 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10c06a86-e402-4adc-abbe-5ded923d626a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 707160ddfededefd5f0ef47e77df08844b38abcf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989342"
---
# <a name="single-sign-on-event-10856"></a>单一登录： 事件 10856
## <a name="details"></a>详细信息  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  产品名称   |                   企业单一登录                    |
| 产品版本 |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    事件 ID     |                             10856                              |
|  事件源   |                             ENTSSO                             |
|    组件    |                              N/A                               |
|  符号名称  |               ENTSSO_E_MAPPING_CREATE_RESTRICTED               |
|  消息正文   | 应用程序用户不能为此应用程序创建映射。 |
  
## <a name="explanation"></a>解释  
 此应用程序已配置为不允许应用程序用户组的成员创建映射。  
  
## <a name="user-action"></a>用户操作  
 您应请求具有足够权限的用户来创建这些映射。