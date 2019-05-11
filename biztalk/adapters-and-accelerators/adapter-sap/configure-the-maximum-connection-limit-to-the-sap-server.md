---
title: 配置到 SAP 服务器的最大连接限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 858ed90e-b219-43cc-ad63-ae8e1eb2159a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4286fbbaeaca1aefaf6a7ea995a068eba25c0690
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373770"
---
# <a name="configure-the-maximum-connection-limit-to-the-sap-server"></a><span data-ttu-id="ce0d5-102">配置到 SAP 服务器的最大连接限制</span><span class="sxs-lookup"><span data-stu-id="ce0d5-102">Configure the Maximum Connection Limit to the SAP Server</span></span>
<span data-ttu-id="ce0d5-103">SAP 数据提供程序使适配器客户端来控制可以在内部的提供程序打开的连接的最大数目。</span><span class="sxs-lookup"><span data-stu-id="ce0d5-103">The Data Provider for SAP enables adapter clients to control the maximum number of connections that can be opened by the provider internally.</span></span> <span data-ttu-id="ce0d5-104">可以通过设置环境变量，CPIC_MAX_CONV 对此进行控制。</span><span class="sxs-lookup"><span data-stu-id="ce0d5-104">You can control this by setting the environment variable, CPIC_MAX_CONV.</span></span>  
  
 <span data-ttu-id="ce0d5-105">例如，如果 CPIC_MAX_CONV 设置为任何数值，随时打开的 RFC 连接数会小于或等于该数字值。</span><span class="sxs-lookup"><span data-stu-id="ce0d5-105">For example, if CPIC_MAX_CONV is set to any numerical value, the number of RFC connections opened at any time will be less than or equal to that numerical value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce0d5-106">数字值将适用于单独下设置此值的进程/appdomain 的每个服务器。</span><span class="sxs-lookup"><span data-stu-id="ce0d5-106">The numerical value will be applicable for every server individually under the process/appdomain which sets this value.</span></span>  
  
 <span data-ttu-id="ce0d5-107">例如，如果使用 Data provider for SAP 应用程序，已在进程级别设置为"x"设置其环境变量，并且连接到两个不同的服务器 A 和 B，然后的最大连接数为 A 和 B 将为"x"分别。</span><span class="sxs-lookup"><span data-stu-id="ce0d5-107">For example, if an application using Data provider for SAP, has set its environment variable at process level to “x” and connects to two different servers A and B, then the maximum number of connections for both A and B will be “x” respectively.</span></span>