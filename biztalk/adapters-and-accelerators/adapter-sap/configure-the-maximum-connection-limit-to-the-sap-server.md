---
title: 配置到 SAP 服务器的最大连接限制 |Microsoft 文档
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
ms.openlocfilehash: 853a3b78b82e242750e30099f847045ff590f125
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215845"
---
# <a name="configure-the-maximum-connection-limit-to-the-sap-server"></a><span data-ttu-id="e3115-102">配置到 SAP 服务器的最大连接限制</span><span class="sxs-lookup"><span data-stu-id="e3115-102">Configure the Maximum Connection Limit to the SAP Server</span></span>
<span data-ttu-id="e3115-103">SAP 数据提供程序允许适配器客户端控制的最大可以在内部打开提供程序的连接数。</span><span class="sxs-lookup"><span data-stu-id="e3115-103">The Data Provider for SAP enables adapter clients to control the maximum number of connections that can be opened by the provider internally.</span></span> <span data-ttu-id="e3115-104">可以通过设置环境变量，CPIC_MAX_CONV 对此进行控制。</span><span class="sxs-lookup"><span data-stu-id="e3115-104">You can control this by setting the environment variable, CPIC_MAX_CONV.</span></span>  
  
 <span data-ttu-id="e3115-105">例如，如果 CPIC_MAX_CONV 设置为任何数值，随时打开的 RFC 连接数将小于或等于该数字值。</span><span class="sxs-lookup"><span data-stu-id="e3115-105">For example, if CPIC_MAX_CONV is set to any numerical value, the number of RFC connections opened at any time will be less than or equal to that numerical value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3115-106">将适用于单独下将此值设置的过程/appdomain 的每个服务器的数字值。</span><span class="sxs-lookup"><span data-stu-id="e3115-106">The numerical value will be applicable for every server individually under the process/appdomain which sets this value.</span></span>  
  
 <span data-ttu-id="e3115-107">例如，如果为 SAP 使用数据提供程序的应用程序，已在过程级别设置为"x"设置其环境变量，并且连接到两个不同的服务器 A 和 B，然后的最大连接数为 A 和 B 将"x"分别。</span><span class="sxs-lookup"><span data-stu-id="e3115-107">For example, if an application using Data provider for SAP, has set its environment variable at process level to “x” and connects to two different servers A and B, then the maximum number of connections for both A and B will be “x” respectively.</span></span>