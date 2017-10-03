---
title: "附录 c: BizTalk Server 和 SQL Server Hyper V 支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05bc03d4-8fe7-490d-84e2-05dae7a7441e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20cd40f642c61b124b16bdca8431eb94a4b1cf91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-c-biztalk-server-and-sql-server-hyper-v-supportability"></a><span data-ttu-id="e7dc0-102">附录 c: BizTalk Server 和 SQL Server Hyper V 支持性</span><span class="sxs-lookup"><span data-stu-id="e7dc0-102">Appendix C: BizTalk Server and SQL Server Hyper-V Supportability</span></span>
<span data-ttu-id="e7dc0-103">测试方案中所述[测试 BizTalk 服务器虚拟化性能](../technical-guides/testing-biztalk-server-virtualization-performance.md)与执行[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]和[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e7dc0-103">The test scenarios described in [Testing BizTalk Server Virtualization Performance](../technical-guides/testing-biztalk-server-virtualization-performance.md) were performed with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] and [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)].</span></span> [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="e7dc0-104">在 Microsoft Virtual Server 2005 上运行或在支持操作系统上安装，则支持[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]HYPER-V。</span><span class="sxs-lookup"><span data-stu-id="e7dc0-104"> is supported when installed on a supported operating system that is running on Microsoft Virtual Server 2005 or on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Hyper-V.</span></span> <span data-ttu-id="e7dc0-105">有关详细信息，请参阅 Microsoft 知识库文章"Microsoft BizTalk Server 可支持性的虚拟机上"在可用[http://go.microsoft.com/fwlink/?LinkId=148941](http://go.microsoft.com/fwlink/?LinkId=148941)。</span><span class="sxs-lookup"><span data-stu-id="e7dc0-105">For more information, see the Microsoft Knowledge Base article “Microsoft BizTalk Server supportability on a virtual machine” available at [http://go.microsoft.com/fwlink/?LinkId=148941](http://go.microsoft.com/fwlink/?LinkId=148941).</span></span>  
  
 <span data-ttu-id="e7dc0-106">支持策略[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]上受支持的操作系统上运行安装时[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]HYPER-V 记录在 Microsoft 知识库文章"的硬件中运行的 Microsoft SQL Server 产品的支持策略虚拟化环境"在可用[http://go.microsoft.com/fwlink/?LinkId=148942](http://go.microsoft.com/fwlink/?LinkId=148942)。</span><span class="sxs-lookup"><span data-stu-id="e7dc0-106">Support policy for [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] when installed on a supported operating system that is running on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Hyper-V is documented in the Microsoft Knowledge Base article “Support policy for Microsoft SQL Server products that are running in a hardware virtualization environment” available at [http://go.microsoft.com/fwlink/?LinkId=148942](http://go.microsoft.com/fwlink/?LinkId=148942).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e7dc0-107">截止到撰写本指南中，在 HYPER-V 环境上的 SQL Server 实例的群集不受支持的方案。</span><span class="sxs-lookup"><span data-stu-id="e7dc0-107">As of the writing of this guide, clustering of a SQL Server instance on a Hyper-V environment is not a supported scenario.</span></span>