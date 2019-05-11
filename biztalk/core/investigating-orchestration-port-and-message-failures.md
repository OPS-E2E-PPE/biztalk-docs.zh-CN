---
title: 调查业务流程、 端口和消息失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Administration Console [BizTalk Server], Group Hub page
- orchestrations, errors
- errors, ports
- errors, orchestrations
- Group Hub page [Administration Console]
- ports, errors
- MessageBox database, accessing data
- errors, messages
- messages, errors
- data, MessageBox database
ms.assetid: 50b0d272-2d48-4e0f-82ce-6ecc7a65b064
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5841327da65842b7d9c442604e9d1740a23f1eb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329958"
---
# <a name="investigating-orchestration-port-and-message-failures"></a><span data-ttu-id="854cf-102">调查业务流程、 端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="854cf-102">Investigating Orchestration, Port, and Message Failures</span></span>
<span data-ttu-id="854cf-103">可以使用 BizTalk Server 管理控制台中组中心页来调查业务流程、 端口和消息失败。</span><span class="sxs-lookup"><span data-stu-id="854cf-103">You can use the Group Hub page in the BizTalk Server Administration Console to investigate orchestration, port, and message failures.</span></span> <span data-ttu-id="854cf-104">组中心页可以访问系统，访问 MessageBox 数据库中的数据的当前实时状态。</span><span class="sxs-lookup"><span data-stu-id="854cf-104">The Group Hub page provides access to the current real-time state of the system, accessing data in the MessageBox database.</span></span> <span data-ttu-id="854cf-105">您可以查看业务流程、 端口和消息传送，及其关联的消息以及等的所有服务实例。</span><span class="sxs-lookup"><span data-stu-id="854cf-105">You can view all service instances such as orchestrations, ports, and messaging, along with their associated messages.</span></span> <span data-ttu-id="854cf-106">使用组中心页可以：</span><span class="sxs-lookup"><span data-stu-id="854cf-106">Using the Group Hub page you can:</span></span>  
  
-   <span data-ttu-id="854cf-107">请参阅当前正在运行的服务实例，如业务流程和消息传送和及其关联的消息。</span><span class="sxs-lookup"><span data-stu-id="854cf-107">See currently running service instances such as orchestrations and messaging, and their associated messages.</span></span>  
  
-   <span data-ttu-id="854cf-108">查找到 MessageBox 数据库中的视图的当前数据和系统的实时状态。</span><span class="sxs-lookup"><span data-stu-id="854cf-108">Look into the MessageBox database for a view of the current data and the real-time state of the system.</span></span>  
  
-   <span data-ttu-id="854cf-109">挂起、 终止和恢复服务实例。</span><span class="sxs-lookup"><span data-stu-id="854cf-109">Suspend, terminate, and resume service instances.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="854cf-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="854cf-110">In This Section</span></span>  
  
-   [<span data-ttu-id="854cf-111">业务流程故障</span><span class="sxs-lookup"><span data-stu-id="854cf-111">Orchestration Failures</span></span>](../core/orchestration-failures.md)  
  
-   [<span data-ttu-id="854cf-112">消息失败的类型</span><span class="sxs-lookup"><span data-stu-id="854cf-112">Types of Message Failures</span></span>](../core/types-of-message-failures.md)  
  
-   [<span data-ttu-id="854cf-113">如何挂起业务流程实例或端口</span><span class="sxs-lookup"><span data-stu-id="854cf-113">How to Suspend Orchestration Instances or Ports</span></span>](../core/how-to-suspend-orchestration-instances-or-ports.md)  
  
-   [<span data-ttu-id="854cf-114">如何终止挂起的业务流程实例</span><span class="sxs-lookup"><span data-stu-id="854cf-114">How to Terminate Suspended Orchestration Instances</span></span>](../core/how-to-terminate-suspended-orchestration-instances.md)  
  
-   [<span data-ttu-id="854cf-115">如何恢复挂起的业务流程实例</span><span class="sxs-lookup"><span data-stu-id="854cf-115">How to Resume Suspended Orchestration Instances</span></span>](../core/how-to-resume-suspended-orchestration-instances.md)