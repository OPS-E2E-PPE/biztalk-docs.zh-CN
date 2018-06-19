---
title: 将使用 WCF LOB 适配器 SDK 原子、 一致、 隔离和持久的事务进行配置 |Microsoft 文档
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
ms.openlocfilehash: 58cf80a70b04e20aeb25b27210d88dfd861d7539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224237"
---
# <a name="configure-atomic-consistent-isolated-and-durable-transactions-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="2b2fa-102">将使用 WCF LOB 适配器 SDK 的原子、 一致、 隔离和持久事务配置</span><span class="sxs-lookup"><span data-stu-id="2b2fa-102">Configure atomic, consistent, isolated, and durable transactions using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="2b2fa-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过依赖公开的功能支持事务[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports transactions by relying on functionality exposed by the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span> <span data-ttu-id="2b2fa-104">通过使用 API 公开的[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，你的适配器可以支持事务和的操作：</span><span class="sxs-lookup"><span data-stu-id="2b2fa-104">By using the API exposed by [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], your adapter can support transactions and operations that are:</span></span>  
  
-   <span data-ttu-id="2b2fa-105">**原子**，确保所有挂起的更新都已提交，或任何已提交并已将回滚到其先前状态。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-105">**Atomic**, ensuring that either all pending updates are committed or none are committed and are rolled back to their previous state.</span></span>  
  
-   <span data-ttu-id="2b2fa-106">**一致**，确保所做的更改都从一个一致状态，到另一个。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-106">**Consistent**, ensuring that changes made are from one consistent state to another.</span></span>  
  
-   <span data-ttu-id="2b2fa-107">**独立**，阻止访问以其他挂起的事务未提交的更改中的事务。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-107">**Isolated**, preventing a transaction to access uncommitted changes in other pending transactions.</span></span>  
  
-   <span data-ttu-id="2b2fa-108">**持久**，这意味着，一旦提交，则更新将会在遇到故障时保持持久。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-108">**Durable**, meaning that once committed, updates will be persistent in the face of failures.</span></span>  
  
 <span data-ttu-id="2b2fa-109">适配器开发人员针对关系数据库系统或其他业务线系统支持 （或希望） 事务将需要确定如何在目标系统支持和公开的事务支持，然后确定相应[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]要使用的事务模型。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-109">Adapter developers targeting relational database systems or other line-of-business systems that support (or expect) transactions will need to identify how the target system supports and exposes transaction support and then identify an appropriate [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transaction model to use.</span></span>  
  
 <span data-ttu-id="2b2fa-110">有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]事务，请参阅[Windows Communication Foundation 事务概述](https://msdn.microsoft.com/library/ms733904.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2b2fa-110">For more information about [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transactions, see [Windows Communication Foundation Transactions Overview](https://msdn.microsoft.com/library/ms733904.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2b2fa-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b2fa-111">See Also</span></span>  
 [<span data-ttu-id="2b2fa-112">规划和设计你使用 WCF LOB 适配器 SDK 的适配器</span><span class="sxs-lookup"><span data-stu-id="2b2fa-112">Plan and Design your Adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)