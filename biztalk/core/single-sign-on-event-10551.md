---
title: 单一登录： 事件 10551 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33434989-08d8-4d13-a3cc-4c5543add69c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a014d9fa9adec99a05eba3f4a0f17047e2e1175
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973486"
---
# <a name="single-sign-on-event-10551"></a>单一登录： 事件 10551
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                   企业单一登录                                                                                                   |
| 产品版本 |                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                   |
|    事件 ID     |                                                                                                             10551                                                                                                             |
|  事件源   |                                                                                                            ENTSSO                                                                                                             |
|    组件    |                                                                                                              N/A                                                                                                              |
|  符号名称  |                                                                                                     SSO_WARN_INVALID_USER                                                                                                     |
|  消息正文   | 无法创建映射，因为指定的用户不是有效 application.%r<br /><br /> 域名: %1 %r<br /><br /> 用户名: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 应用程序用户： %4 |
  
## <a name="explanation"></a>解释  
 指定的用户无效。 这可能是拼写错误。  
  
## <a name="user-action"></a>用户操作  
 检查警告信息中列出的用户名，确认它是否正确性，然后再次创建该映射。