---
title: BAM 事件总线服务存储过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- stored procedures, Even Bus Service [BAM]
- Event Bus Service [BAM], stored procedures
ms.assetid: 18a7bd40-50ce-44f2-88ae-45a2e3c8d3f4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44dce10113b8a3a85b7c1dd177f637933b582ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230333"
---
# <a name="bam-event-bus-service-stored-procedures"></a><span data-ttu-id="a16c9-102">BAM 事件总线服务存储过程</span><span class="sxs-lookup"><span data-stu-id="a16c9-102">BAM Event Bus Service Stored Procedures</span></span>
<span data-ttu-id="a16c9-103">使用以下存储的过程来管理与 BAM 事件总线服务：</span><span class="sxs-lookup"><span data-stu-id="a16c9-103">You use the following stored procedures to manage the BAM Event Bus service:</span></span>  
  
-   <span data-ttu-id="a16c9-104">若要暂停 BAM 事件总线服务，在事务中的 TDDS_BlockTDDS 存储过程 （不带提交事务） 对 BAM 数据库执行。</span><span class="sxs-lookup"><span data-stu-id="a16c9-104">To pause the BAM Event Bus service, execute the TDDS_BlockTDDS stored procedure within a transaction (without committing the transaction) on the BAM database.</span></span> <span data-ttu-id="a16c9-105">若要恢复 BAM 事件总线服务，提交 TDDS_BlockTDDS 事务。</span><span class="sxs-lookup"><span data-stu-id="a16c9-105">To resume the BAM Event Bus service, commit the TDDS_BlockTDDS transaction.</span></span>  
  
-   <span data-ttu-id="a16c9-106">若要启用多台计算机上的 BAM 事件总线服务，确定哪些主机用于对其进行跟踪，然后将这些计算机加入到跟踪主机。</span><span class="sxs-lookup"><span data-stu-id="a16c9-106">To enable the BAM Event Bus service on multiple computers, identify which host(s) to use for tracking, and then join those computers to the tracking host.</span></span>  
  
-   <span data-ttu-id="a16c9-107">若要设置会话超时和检测信号间隔，请使用 TDDS_UpdateSettings 存储过程。</span><span class="sxs-lookup"><span data-stu-id="a16c9-107">To set up a session time-out and heartbeat interval, use the TDDS_UpdateSettings stored procedure.</span></span> <span data-ttu-id="a16c9-108">只有 BTS_ADMIN_USERS 组的成员有权执行此存储的过程。</span><span class="sxs-lookup"><span data-stu-id="a16c9-108">Only members of the BTS_ADMIN_USERS group have permission to execute this stored procedure.</span></span>  
  
     <span data-ttu-id="a16c9-109">TDDS_UpdateSettings 存储过程具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="a16c9-109">The TDDS_UpdateSettings stored procedure has the following parameters:</span></span>  
  
    -   <span data-ttu-id="a16c9-110">@RefreshIntervalint。设置为大于 60 秒。</span><span class="sxs-lookup"><span data-stu-id="a16c9-110">@RefreshInterval int. Set to greater than 60 seconds.</span></span>  
  
    -   <span data-ttu-id="a16c9-111">@SqlCommandTimeoutint。设置为小于号 RefreshInterval。</span><span class="sxs-lookup"><span data-stu-id="a16c9-111">@SqlCommandTimeout int. Set to less than RefreshInterval.</span></span>  
  
    -   <span data-ttu-id="a16c9-112">@SessionTimeoutint。设置为大于 RefreshInterval 两次。</span><span class="sxs-lookup"><span data-stu-id="a16c9-112">@SessionTimeout int. Set to greater than two times the RefreshInterval.</span></span>  
  
    -   <span data-ttu-id="a16c9-113">@EventLoggingIntervalnvarchar(16)。</span><span class="sxs-lookup"><span data-stu-id="a16c9-113">@EventLoggingInterval nvarchar(16).</span></span> <span data-ttu-id="a16c9-114">设置为大于 60 秒。</span><span class="sxs-lookup"><span data-stu-id="a16c9-114">Set to greater than 60 seconds.</span></span>  
  
    -   <span data-ttu-id="a16c9-115">@RetryCountint。将设置为大于 60 秒</span><span class="sxs-lookup"><span data-stu-id="a16c9-115">@RetryCount int. Set to greater than 60 seconds</span></span>  
  
    -   <span data-ttu-id="a16c9-116">@ThreadPerSessionint。此参数已废弃不用。</span><span class="sxs-lookup"><span data-stu-id="a16c9-116">@ThreadPerSession int. This parameter is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a16c9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a16c9-117">See Also</span></span>  
 [<span data-ttu-id="a16c9-118">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="a16c9-118">Managing BAM</span></span>](../core/managing-bam.md)