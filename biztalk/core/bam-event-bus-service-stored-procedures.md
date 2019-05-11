---
title: BAM 事件总线服务存储过程 |Microsoft Docs
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
ms.openlocfilehash: 138ca26becc8b35207219dd050e13c8557066301
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358526"
---
# <a name="bam-event-bus-service-stored-procedures"></a><span data-ttu-id="1129e-102">BAM 事件总线服务存储过程</span><span class="sxs-lookup"><span data-stu-id="1129e-102">BAM Event Bus Service Stored Procedures</span></span>
<span data-ttu-id="1129e-103">使用以下存储的过程来管理 BAM 事件总线服务：</span><span class="sxs-lookup"><span data-stu-id="1129e-103">You use the following stored procedures to manage the BAM Event Bus service:</span></span>  
  
-   <span data-ttu-id="1129e-104">若要暂停 BAM 事件总线服务，执行 （不带提交事务） 的 BAM 数据库的事务中 TDDS_BlockTDDS 存储过程。</span><span class="sxs-lookup"><span data-stu-id="1129e-104">To pause the BAM Event Bus service, execute the TDDS_BlockTDDS stored procedure within a transaction (without committing the transaction) on the BAM database.</span></span> <span data-ttu-id="1129e-105">若要恢复 BAM 事件总线服务，请提交 TDDS_BlockTDDS 事务。</span><span class="sxs-lookup"><span data-stu-id="1129e-105">To resume the BAM Event Bus service, commit the TDDS_BlockTDDS transaction.</span></span>  
  
-   <span data-ttu-id="1129e-106">若要启用多台计算机上的 BAM 事件总线服务，标识要用于跟踪的主机，然后将这些计算机加入到跟踪主机。</span><span class="sxs-lookup"><span data-stu-id="1129e-106">To enable the BAM Event Bus service on multiple computers, identify which host(s) to use for tracking, and then join those computers to the tracking host.</span></span>  
  
-   <span data-ttu-id="1129e-107">若要设置会话超时和检测信号间隔，请使用 TDDS_UpdateSettings 存储过程。</span><span class="sxs-lookup"><span data-stu-id="1129e-107">To set up a session time-out and heartbeat interval, use the TDDS_UpdateSettings stored procedure.</span></span> <span data-ttu-id="1129e-108">只有 BTS_ADMIN_USERS 组的成员有权执行此存储的过程。</span><span class="sxs-lookup"><span data-stu-id="1129e-108">Only members of the BTS_ADMIN_USERS group have permission to execute this stored procedure.</span></span>  
  
     <span data-ttu-id="1129e-109">TDDS_UpdateSettings 存储过程具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="1129e-109">The TDDS_UpdateSettings stored procedure has the following parameters:</span></span>  
  
    -   <span data-ttu-id="1129e-110">@RefreshInterval int。设置为大于 60 秒。</span><span class="sxs-lookup"><span data-stu-id="1129e-110">@RefreshInterval int. Set to greater than 60 seconds.</span></span>  
  
    -   <span data-ttu-id="1129e-111">@SqlCommandTimeout int。设置为小于 RefreshInterval。</span><span class="sxs-lookup"><span data-stu-id="1129e-111">@SqlCommandTimeout int. Set to less than RefreshInterval.</span></span>  
  
    -   <span data-ttu-id="1129e-112">@SessionTimeout int。设置为大于 RefreshInterval 两次。</span><span class="sxs-lookup"><span data-stu-id="1129e-112">@SessionTimeout int. Set to greater than two times the RefreshInterval.</span></span>  
  
    -   <span data-ttu-id="1129e-113">@EventLoggingInterval nvarchar(16)。</span><span class="sxs-lookup"><span data-stu-id="1129e-113">@EventLoggingInterval nvarchar(16).</span></span> <span data-ttu-id="1129e-114">设置为大于 60 秒。</span><span class="sxs-lookup"><span data-stu-id="1129e-114">Set to greater than 60 seconds.</span></span>  
  
    -   <span data-ttu-id="1129e-115">@RetryCount int。设置为大于 60 秒</span><span class="sxs-lookup"><span data-stu-id="1129e-115">@RetryCount int. Set to greater than 60 seconds</span></span>  
  
    -   <span data-ttu-id="1129e-116">@ThreadPerSession int。此参数是已过时。</span><span class="sxs-lookup"><span data-stu-id="1129e-116">@ThreadPerSession int. This parameter is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1129e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1129e-117">See Also</span></span>  
 [<span data-ttu-id="1129e-118">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="1129e-118">Managing BAM</span></span>](../core/managing-bam.md)