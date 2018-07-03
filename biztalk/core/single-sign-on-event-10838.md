---
title: 单一登录： 事件 10838 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e4de1c1-6529-4f97-8510-d10bf6f30ddc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f286f5a2560180b70e9595e1a028975c284baa5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006262"
---
# <a name="single-sign-on-event-10838"></a>单一登录： 事件 10838
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                              企业单一登录                                              |
| 产品版本 |                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                              |
|    事件 ID     |                                                        10838                                                        |
|  事件源   |                                                       ENTSSO                                                        |
|    组件    |                                                         N/A                                                         |
|  符号名称  |                                          ENTSSO_E_MAX_SSO_DATABASE_CREATE                                           |
|  消息正文   | SSO 可以创建的最大 SQL 数据库名称长度为 123 个字符，以便允许默认日志文件名称。 |
  
## <a name="explanation"></a>解释  
 SSO 可以创建的最大 SQL 数据库名称长度为 123 个字符，以便允许默认日志文件名称。  
  
## <a name="user-action"></a>用户操作  
 使用符合这些规则的名称。