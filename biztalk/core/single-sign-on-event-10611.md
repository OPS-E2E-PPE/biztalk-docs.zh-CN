---
title: 单一登录： 事件 10611 |Microsoft 文档
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
ms.openlocfilehash: 3582ee070b960b7eb17facc8d48e0b3e11dc5b9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270413"
---
# <a name="single-sign-on-event-10611"></a>单一登录： 事件 10611
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10611|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_INFO_SERVICE_STARTING_NO_SSL|  
|消息正文|SSO 服务正在启动。%r<br /><br /> 计算机名: %1 %r<br /><br /> SQL Server 名称: %2 %r<br /><br /> SSO 数据库名称: %3 %r<br /><br /> 不使用 SSL。 有关如何保护 SQL Server 连接安全的详细信息，请参阅文档。|  
  
## <a name="explanation"></a>解释  
 ENTSSO 服务正在启动，但未使用安全套接字层 (SSL)。 建议您保护从 SSO 服务到 SQL 的连接安全。  
  
## <a name="user-action"></a>用户操作  
 请参阅文档：[如何为 SSO 启用 SSL](../core/how-to-enable-ssl-for-sso.md)  
  
 实例时都提供 SQL Server 登录名。