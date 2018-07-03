---
title: 更新使用的并行版本控制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9721a091-98ec-4f0b-ad1f-6ca184956e7c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36be63c9cef6a016ea4ad34d98a2750be86491d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974254"
---
# <a name="updating-using-side-by-side-versioning"></a><span data-ttu-id="10bc3-102">更新使用的并行版本控制</span><span class="sxs-lookup"><span data-stu-id="10bc3-102">Updating Using Side-by-Side Versioning</span></span>
<span data-ttu-id="10bc3-103">如果您不能计划停机时间，或者具有不能终止的长时间运行的业务流程实例，可能需要的并行版本控制。</span><span class="sxs-lookup"><span data-stu-id="10bc3-103">If you are not able to schedule downtime, or have very long-running orchestration instances that cannot be terminated, side-by-side versioning may be required.</span></span> <span data-ttu-id="10bc3-104">在此类型的升级，两个版本的同一应用程序或应用程序项目运行的并行。</span><span class="sxs-lookup"><span data-stu-id="10bc3-104">In this type of upgrade, two versions of the same application or application artifacts run side-by-side.</span></span> <span data-ttu-id="10bc3-105">.NET 运行时本质上是允许的名称相同的但以不同的方式已进行版本管理程序集部署并运行，并且 BizTalk Server 还允许它。</span><span class="sxs-lookup"><span data-stu-id="10bc3-105">The .NET runtime inherently allows for same-named but differently versioned assemblies to be deployed and running, and BizTalk Server also allows it.</span></span>  
  
 <span data-ttu-id="10bc3-106">通过并行版本控制的应用程序时，要推出升级主要应用程序以增量方式，例如使其可供业务合作伙伴的子集最初，而不是所有合作伙伴在一次。</span><span class="sxs-lookup"><span data-stu-id="10bc3-106">Side-by-side versioning of applications is useful when you want to roll out a major application upgrade incrementally, for example making it available to a subset of business partners initially, rather than to all partners at once.</span></span> <span data-ttu-id="10bc3-107">通过使用此方法，您可以继续运行现有应用程序，以便为尚未使用新版本的用户提供服务，直到您已准备就绪，可以完全转换到新版本。</span><span class="sxs-lookup"><span data-stu-id="10bc3-107">Using this approach allows you to continue running the existing application to service the users who are not yet using the new version until you are ready to completely cut over to the new version.</span></span>  
  
 <span data-ttu-id="10bc3-108">您创建应用程序版本的方式与创建程序集版本（通过递增版本号）的方式不同。</span><span class="sxs-lookup"><span data-stu-id="10bc3-108">You do not create application versions in the same manner that you create assembly versions, by incrementing the version number.</span></span> <span data-ttu-id="10bc3-109">相反，您创建新的应用程序具有与原始应用程序，不同的名称，并填充的新版本的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="10bc3-109">Instead, you create a new application that has a different name from the original application, and populate it with the new versions of the application artifacts.</span></span>  
  
 <span data-ttu-id="10bc3-110">因为许多类型的项目（例如程序集）只能存在于 BizTalk 组的一个应用程序中，所以，您必须首先递增已在该组中存在的所有程序集的版本号，然后才能将它们部署到新的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="10bc3-110">Because many types of artifacts, such as assemblies, can exist in only one application in a BizTalk group, you must increment the version number of any assemblies that already exist in the group before you can deploy them into the new application.</span></span>  
  
 <span data-ttu-id="10bc3-111">分步更新的应用程序或业务流程使用的并行版本控制所需的任务的列表，请参阅[清单： 更新应用程序使用的并行版本控制](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)和[核对清单： 更新业务流程使用的并行版本控制](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)。</span><span class="sxs-lookup"><span data-stu-id="10bc3-111">For a step-by-step list of tasks required to update an application or orchestration using side-by-side versioning, see [Checklist: Updating an Application Using Side-by-Side Versioning](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md) and [Checklist: Updating an Orchestration Using Side-by-Side Versioning](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md).</span></span> <span data-ttu-id="10bc3-112">有关如何通过并行部署的应用程序的详细说明，请参阅"[如何部署到运行并行应用程序与现有版本的新版本](http://go.microsoft.com/fwlink/?LinkId=155143)(<http://go.microsoft.com/fwlink/?LinkId=155143>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="10bc3-112">For detailed instructions on how to have side-by-side deployment of applications, see "[How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version](http://go.microsoft.com/fwlink/?LinkId=155143) (<http://go.microsoft.com/fwlink/?LinkId=155143>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10bc3-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="10bc3-113">In This Section</span></span>  
  
-   [<span data-ttu-id="10bc3-114">如何使用并排版本控制更新映射</span><span class="sxs-lookup"><span data-stu-id="10bc3-114">How to Update a Map Using Side-by-Side Versioning</span></span>](../technical-guides/how-to-update-a-map-using-side-by-side-versioning.md)  
  
-   [<span data-ttu-id="10bc3-115">如何使用并排版本控制更新管道</span><span class="sxs-lookup"><span data-stu-id="10bc3-115">How to Update a Pipeline Using Side-by-Side Versioning</span></span>](../technical-guides/how-to-update-a-pipeline-using-side-by-side-versioning.md)  
  
-   [<span data-ttu-id="10bc3-116">使用并排版本控制更新架构</span><span class="sxs-lookup"><span data-stu-id="10bc3-116">Updating a Schema Using Side-by-Side Versioning</span></span>](../technical-guides/updating-a-schema-using-side-by-side-versioning.md)