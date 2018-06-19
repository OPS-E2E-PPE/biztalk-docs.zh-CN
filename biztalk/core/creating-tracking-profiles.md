---
title: 创建跟踪配置文件 |Microsoft 文档
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
ms.openlocfilehash: 6ce1edcab724201dc03792a37b0b796625201351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238269"
---
# <a name="creating-tracking-profiles"></a><span data-ttu-id="6fc4c-102">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6fc4c-102">Creating Tracking Profiles</span></span>
<span data-ttu-id="6fc4c-103">创建新的跟踪配置文件或修改现有更好地管理和监视你的组织的特定业务流程。</span><span class="sxs-lookup"><span data-stu-id="6fc4c-103">You create a new tracking profile or modify an existing one to better manage and monitor a specific business process for your organization.</span></span> <span data-ttu-id="6fc4c-104">跟踪配置文件编辑器 （键入） 允许你定义要收集以满足业务分析师的要求的数据。</span><span class="sxs-lookup"><span data-stu-id="6fc4c-104">The Tracking Profile Editor (TPE) allows you to define the data to collect to meet the business analyst's requirement.</span></span> <span data-ttu-id="6fc4c-105">创建或修改的配置文件可以是简单或很复杂，根据需要具体取决于你的业务要求。</span><span class="sxs-lookup"><span data-stu-id="6fc4c-105">The profile you create or modify can be as simple or as complex as you like depending on your business requirements.</span></span>  
  
 <span data-ttu-id="6fc4c-106">作为开发人员，你可以创建新的配置文件基于 BAM 活动定义。</span><span class="sxs-lookup"><span data-stu-id="6fc4c-106">As a developer, you create a new profile based on a BAM activity definition.</span></span> <span data-ttu-id="6fc4c-107">已部署的活动定义可能已为其定义的配置文件。</span><span class="sxs-lookup"><span data-stu-id="6fc4c-107">A deployed activity definition may already have a profile defined for it.</span></span> <span data-ttu-id="6fc4c-108">如果没有，请通过执行这些任务中创建跟踪配置文件：</span><span class="sxs-lookup"><span data-stu-id="6fc4c-108">If not, you create a tracking profile by performing these tasks:</span></span>  
  
-   <span data-ttu-id="6fc4c-109">选择部署服务器和数据库</span><span class="sxs-lookup"><span data-stu-id="6fc4c-109">Selecting a deployment server and database</span></span>  
  
-   <span data-ttu-id="6fc4c-110">从 BizTalk 管理数据库中选择已部署的 BAM 活动定义</span><span class="sxs-lookup"><span data-stu-id="6fc4c-110">Selecting a deployed BAM activity definition from the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="6fc4c-111">定义要从业务流程中提取的数据</span><span class="sxs-lookup"><span data-stu-id="6fc4c-111">Defining the data to be extracted from the orchestration</span></span>  
  
-   <span data-ttu-id="6fc4c-112">连接活动，如果您的业务流程的实际实现跨多个业务流程</span><span class="sxs-lookup"><span data-stu-id="6fc4c-112">Connecting activities, if the actual implementation of your business process spans more than one orchestration</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6fc4c-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="6fc4c-113">In This Section</span></span>  
  
-   [<span data-ttu-id="6fc4c-114">如何创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6fc4c-114">How to Create a Tracking Profile</span></span>](../core/how-to-create-a-tracking-profile.md)  
  
-   [<span data-ttu-id="6fc4c-115">如何将映射事件源</span><span class="sxs-lookup"><span data-stu-id="6fc4c-115">How to Map Event Sources</span></span>](../core/how-to-map-event-sources.md)  
  
-   [<span data-ttu-id="6fc4c-116">如何将映射项数据</span><span class="sxs-lookup"><span data-stu-id="6fc4c-116">How to Map Item Data</span></span>](../core/how-to-map-item-data.md)  
  
-   [<span data-ttu-id="6fc4c-117">如何创建一个延续任务</span><span class="sxs-lookup"><span data-stu-id="6fc4c-117">How to Create a Continuation</span></span>](../core/how-to-create-a-continuation.md)  
  
-   [<span data-ttu-id="6fc4c-118">如何将映射多个程序集</span><span class="sxs-lookup"><span data-stu-id="6fc4c-118">How to Map Multiple Assemblies</span></span>](../core/how-to-map-multiple-assemblies.md)  
  
-   [<span data-ttu-id="6fc4c-119">如何将应用并删除跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6fc4c-119">How to Apply and Remove a Tracking Profile</span></span>](../core/how-to-apply-and-remove-a-tracking-profile.md)