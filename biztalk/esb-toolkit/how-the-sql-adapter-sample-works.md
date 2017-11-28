---
title: "SQL 适配器示例的工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77811152-cc8e-4090-89eb-e3a402a46e5e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ff56f2f2f88d35290ffd897d107910e206ac98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-sql-adapter-sample-works"></a><span data-ttu-id="a12d9-102">SQL 适配器示例的工作原理</span><span class="sxs-lookup"><span data-stu-id="a12d9-102">How the SQL Adapter Sample Works</span></span>
<span data-ttu-id="a12d9-103">SQL 适配器示例提供了使用路由服务和转换消息服务配置示例双向路线。</span><span class="sxs-lookup"><span data-stu-id="a12d9-103">The SQL Adapter sample provides a sample two-way itinerary configured with the routing service and a transform messaging service.</span></span>  
  
 <span data-ttu-id="a12d9-104">路由服务配置了静态冲突解决程序，指定应将消息路由执行名为 InsertProduct 使用 WCF 自定义适配器提供程序的 GlobalBankESB 数据库内的一个 SQL 存储过程。</span><span class="sxs-lookup"><span data-stu-id="a12d9-104">The routing service is configured with a STATIC resolver, which specifies that the message should be routed to execute a SQL stored procedure within the GlobalBankESB database named InsertProduct using the WCF-Custom adapter provider.</span></span>  
  
 <span data-ttu-id="a12d9-105">转换服务指定的地图，将传入消息转换为 InsertProduct 存储过程接受的格式。</span><span class="sxs-lookup"><span data-stu-id="a12d9-105">The transform service specifies a map that converts the incoming message to the format accepted by the InsertProduct stored procedure.</span></span>