---
title: 单一登录： 事件 10611 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4549ac01-b828-478f-aea0-862e14fac149
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca43eff86b20df7000c973f7c6ade472a8780de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023563"
---
# <a name="single-sign-on-event-10611"></a>单一登录： 事件 10611
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                         企业单一登录                                                                                                         |
| 产品版本 |                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    事件 ID     |                                                                                                                   10611                                                                                                                   |
|  事件源   |                                                                                                                  ENTSSO                                                                                                                   |
|    组件    |                                                                                                                    N/A                                                                                                                    |
|  符号名称  |                                                                                                     SSO_INFO_SERVICE_STARTING_NO_SSL                                                                                                      |
|  消息正文   | SSO 服务正在启动。%r<br /><br /> 计算机名称: %1 %r<br /><br /> SQL Server 名称: %2 %r<br /><br /> SSO 数据库名称: %3 %r<br /><br /> 不使用 SSL。 有关如何保护 SQL Server 连接安全的详细信息，请参阅文档。 |
  
## <a name="explanation"></a>解释  
 ENTSSO 服务正在启动，但未使用安全套接字层 (SSL)。 建议您保护从 SSO 服务到 SQL 的连接安全。  
  
## <a name="user-action"></a>用户操作  
 请参阅文档，[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)  
  
 实例时都提供 SQL Server 登录名。