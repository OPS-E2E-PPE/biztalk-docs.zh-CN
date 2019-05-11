---
title: 配置使用 WCF LOB 适配器 SDK 原子、 一致、 隔离和持久的事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20d2613-c77d-4b0d-b2e2-3ed28a8fb36c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ddf068c29fca7ffae186ad7417f35d8f44786dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363831"
---
# <a name="configure-atomic-consistent-isolated-and-durable-transactions-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="d7c7d-102">配置使用 WCF LOB 适配器 SDK 原子、 一致、 隔离和持久的事务</span><span class="sxs-lookup"><span data-stu-id="d7c7d-102">Configure atomic, consistent, isolated, and durable transactions using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="d7c7d-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]支持通过公开的功能所依赖的事务[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d7c7d-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports transactions by relying on functionality exposed by the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span> <span data-ttu-id="d7c7d-104">通过使用公开的 API [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，您的适配器可以支持事务和程序的操作：</span><span class="sxs-lookup"><span data-stu-id="d7c7d-104">By using the API exposed by [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], your adapter can support transactions and operations that are:</span></span>  
  
- <span data-ttu-id="d7c7d-105">**原子**，确保的所有挂起的更新都已提交或 none 提交和回滚到其以前的状态。</span><span class="sxs-lookup"><span data-stu-id="d7c7d-105">**Atomic**, ensuring that either all pending updates are committed or none are committed and are rolled back to their previous state.</span></span>  
  
- <span data-ttu-id="d7c7d-106">**一致**，确保所做的更改从一个一致的状态到另一个。</span><span class="sxs-lookup"><span data-stu-id="d7c7d-106">**Consistent**, ensuring that changes made are from one consistent state to another.</span></span>  
  
- <span data-ttu-id="d7c7d-107">**独立**，阻止访问未提交的更改，在其他挂起的事务的事务。</span><span class="sxs-lookup"><span data-stu-id="d7c7d-107">**Isolated**, preventing a transaction to access uncommitted changes in other pending transactions.</span></span>  
  
- <span data-ttu-id="d7c7d-108">**持久**，这意味着提交后，更新将为持久遇到故障时。</span><span class="sxs-lookup"><span data-stu-id="d7c7d-108">**Durable**, meaning that once committed, updates will be persistent in the face of failures.</span></span>  
  
  <span data-ttu-id="d7c7d-109">适配器开发人员针对关系数据库系统或其他业务线系统的支持 （或预期） 的事务将需要确定如何在目标系统支持，并公开的事务支持，然后确定相应[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]要使用的事务模型。</span><span class="sxs-lookup"><span data-stu-id="d7c7d-109">Adapter developers targeting relational database systems or other line-of-business systems that support (or expect) transactions will need to identify how the target system supports and exposes transaction support and then identify an appropriate [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transaction model to use.</span></span>  
  
  <span data-ttu-id="d7c7d-110">有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]事务，请参阅[Windows Communication Foundation 事务概述](https://msdn.microsoft.com/library/ms733904.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d7c7d-110">For more information about [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transactions, see [Windows Communication Foundation Transactions Overview](https://msdn.microsoft.com/library/ms733904.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d7c7d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7c7d-111">See Also</span></span>  
 [<span data-ttu-id="d7c7d-112">规划和设计您的适配器使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="d7c7d-112">Plan and Design your Adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)