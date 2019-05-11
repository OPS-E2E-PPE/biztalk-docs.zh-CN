---
title: 创建跟踪配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, creating
- creating, tracking profiles
ms.assetid: 62598529-9763-4c73-acbe-06ce5650134a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92845adb81be88d195f456a3d82ad86676d5b962
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389850"
---
# <a name="creating-tracking-profiles"></a><span data-ttu-id="fdef2-102">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="fdef2-102">Creating Tracking Profiles</span></span>
<span data-ttu-id="fdef2-103">创建新的跟踪配置文件或修改现有更好地管理和监视你的组织的特定业务流程。</span><span class="sxs-lookup"><span data-stu-id="fdef2-103">You create a new tracking profile or modify an existing one to better manage and monitor a specific business process for your organization.</span></span> <span data-ttu-id="fdef2-104">跟踪配置文件编辑器 (TPE)，可定义要收集来满足业务分析人员的要求的数据。</span><span class="sxs-lookup"><span data-stu-id="fdef2-104">The Tracking Profile Editor (TPE) allows you to define the data to collect to meet the business analyst's requirement.</span></span> <span data-ttu-id="fdef2-105">创建或修改的配置文件可以是简单或根据您的业务要求的那样复杂。</span><span class="sxs-lookup"><span data-stu-id="fdef2-105">The profile you create or modify can be as simple or as complex as you like depending on your business requirements.</span></span>  
  
 <span data-ttu-id="fdef2-106">作为开发人员，您可以创建基于 BAM 活动定义的新配置文件。</span><span class="sxs-lookup"><span data-stu-id="fdef2-106">As a developer, you create a new profile based on a BAM activity definition.</span></span> <span data-ttu-id="fdef2-107">已部署的活动定义可能已为其定义的配置文件。</span><span class="sxs-lookup"><span data-stu-id="fdef2-107">A deployed activity definition may already have a profile defined for it.</span></span> <span data-ttu-id="fdef2-108">如果没有，通过执行这些任务来创建跟踪配置文件：</span><span class="sxs-lookup"><span data-stu-id="fdef2-108">If not, you create a tracking profile by performing these tasks:</span></span>  
  
-   <span data-ttu-id="fdef2-109">选择部署服务器和数据库</span><span class="sxs-lookup"><span data-stu-id="fdef2-109">Selecting a deployment server and database</span></span>  
  
-   <span data-ttu-id="fdef2-110">从 BizTalk 管理数据库中选择已部署的 BAM 活动定义</span><span class="sxs-lookup"><span data-stu-id="fdef2-110">Selecting a deployed BAM activity definition from the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="fdef2-111">定义从业务流程提取的数据</span><span class="sxs-lookup"><span data-stu-id="fdef2-111">Defining the data to be extracted from the orchestration</span></span>  
  
-   <span data-ttu-id="fdef2-112">连接活动，如果您的业务流程的实际实现跨多个业务流程</span><span class="sxs-lookup"><span data-stu-id="fdef2-112">Connecting activities, if the actual implementation of your business process spans more than one orchestration</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdef2-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="fdef2-113">In This Section</span></span>  
  
-   [<span data-ttu-id="fdef2-114">如何创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="fdef2-114">How to Create a Tracking Profile</span></span>](../core/how-to-create-a-tracking-profile.md)  
  
-   [<span data-ttu-id="fdef2-115">如何将映射事件源</span><span class="sxs-lookup"><span data-stu-id="fdef2-115">How to Map Event Sources</span></span>](../core/how-to-map-event-sources.md)  
  
-   [<span data-ttu-id="fdef2-116">如何映射项数据</span><span class="sxs-lookup"><span data-stu-id="fdef2-116">How to Map Item Data</span></span>](../core/how-to-map-item-data.md)  
  
-   [<span data-ttu-id="fdef2-117">如何创建一个继续符</span><span class="sxs-lookup"><span data-stu-id="fdef2-117">How to Create a Continuation</span></span>](../core/how-to-create-a-continuation.md)  
  
-   [<span data-ttu-id="fdef2-118">如何映射多个程序集</span><span class="sxs-lookup"><span data-stu-id="fdef2-118">How to Map Multiple Assemblies</span></span>](../core/how-to-map-multiple-assemblies.md)  
  
-   [<span data-ttu-id="fdef2-119">如何将应用和删除跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="fdef2-119">How to Apply and Remove a Tracking Profile</span></span>](../core/how-to-apply-and-remove-a-tracking-profile.md)