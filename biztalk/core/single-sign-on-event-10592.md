---
title: 单一登录： 事件 10592 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e044f9bd-c384-4f08-81f0-699e0c774c45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9fdf7259de2217c2e6cd616f58b3b1118bf991c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017253"
---
# <a name="single-sign-on-event-10592"></a>单一登录： 事件 10592
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                             企业单一登录                                                              |
| 产品版本 |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    事件 ID     |                                                                       10592                                                                        |
|  事件源   |                                                                       ENTSSO                                                                       |
|    组件    |                                                                        N/A                                                                         |
|  符号名称  |                                                           SSO_WARN_TICKET_DECRYPT_FAILED                                                           |
|  消息正文   | 无法对票证进行解密。 票证无效或者可能已过期。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 错误代码： %2 |
  
## <a name="explanation"></a>解释  
 票证无效或者可能已过期。  
  
## <a name="user-action"></a>用户操作  
 确认要使用的票证是有效的并且尚未过期。