---
title: 单一登录： 事件 11046 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb82191b-2235-4efc-b254-59c2ff3f3080
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f00d7cbb50b29867771bfb236bbca417324186a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969478"
---
# <a name="single-sign-on-event-11046"></a>单一登录： 事件 11046
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                        企业单一登录                                                                                        |
| 产品版本 |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    事件 ID     |                                                                                                  11046                                                                                                  |
|  事件源   |                                                                                                 ENTSSO                                                                                                  |
|    组件    |                                                                                                   N/A                                                                                                   |
|  符号名称  |                                                                                   SSO_WARN_EXISTING_MAPPING_EXTERNAL                                                                                    |
|  消息正文   | 无法创建映射，因为指定的外部帐户已经存在映射。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 应用程序名称: %2 %r<br /><br /> 外部帐户： %3 |
  
## <a name="explanation"></a>解释  
 映射已存在指定外部帐户，并且不允许重复。  
  
## <a name="user-action"></a>用户操作  
 不需要用户进行任何操作。