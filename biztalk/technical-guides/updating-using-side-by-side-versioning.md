---
title: "更新使用的并行版本控制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9721a091-98ec-4f0b-ad1f-6ca184956e7c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe8264b76867c2f4fa3200f906e1d99975c9e0eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="updating-using-side-by-side-versioning"></a><span data-ttu-id="454d7-102">更新使用的并行版本控制</span><span class="sxs-lookup"><span data-stu-id="454d7-102">Updating Using Side-by-Side Versioning</span></span>
<span data-ttu-id="454d7-103">如果你不能为计划停机时间，或具有不能以终止的非常长时间运行业务流程实例，可能需要的并行版本控制。</span><span class="sxs-lookup"><span data-stu-id="454d7-103">If you are not able to schedule downtime, or have very long-running orchestration instances that cannot be terminated, side-by-side versioning may be required.</span></span> <span data-ttu-id="454d7-104">在此类型的升级，同一个应用程序或应用程序项目的两个版本运行并排显示。</span><span class="sxs-lookup"><span data-stu-id="454d7-104">In this type of upgrade, two versions of the same application or application artifacts run side-by-side.</span></span> <span data-ttu-id="454d7-105">名称相同的但以不同方式版本控制要部署的程序集和正在运行，本质上是允许的.NET 运行时，BizTalk Server 还允许它。</span><span class="sxs-lookup"><span data-stu-id="454d7-105">The .NET runtime inherently allows for same-named but differently versioned assemblies to be deployed and running, and BizTalk Server also allows it.</span></span>  
  
 <span data-ttu-id="454d7-106">你想要推出主要应用程序升级以增量方式，例如使其可供业务合作伙伴的子集最初，而不是到所有伙伴在一次时有用的应用程序的并行版本控制。</span><span class="sxs-lookup"><span data-stu-id="454d7-106">Side-by-side versioning of applications is useful when you want to roll out a major application upgrade incrementally, for example making it available to a subset of business partners initially, rather than to all partners at once.</span></span> <span data-ttu-id="454d7-107">通过使用此方法，您可以继续运行现有应用程序，以便为尚未使用新版本的用户提供服务，直到您已准备就绪，可以完全转换到新版本。</span><span class="sxs-lookup"><span data-stu-id="454d7-107">Using this approach allows you to continue running the existing application to service the users who are not yet using the new version until you are ready to completely cut over to the new version.</span></span>  
  
 <span data-ttu-id="454d7-108">您创建应用程序版本的方式与创建程序集版本（通过递增版本号）的方式不同。</span><span class="sxs-lookup"><span data-stu-id="454d7-108">You do not create application versions in the same manner that you create assembly versions, by incrementing the version number.</span></span> <span data-ttu-id="454d7-109">相反，你创建的新应用程序具有不同的名称从原始应用程序，并填充它的应用程序项目的新版本。</span><span class="sxs-lookup"><span data-stu-id="454d7-109">Instead, you create a new application that has a different name from the original application, and populate it with the new versions of the application artifacts.</span></span>  
  
 <span data-ttu-id="454d7-110">因为许多类型的项目（例如程序集）只能存在于 BizTalk 组的一个应用程序中，所以，您必须首先递增已在该组中存在的所有程序集的版本号，然后才能将它们部署到新的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="454d7-110">Because many types of artifacts, such as assemblies, can exist in only one application in a BizTalk group, you must increment the version number of any assemblies that already exist in the group before you can deploy them into the new application.</span></span>  
  
 <span data-ttu-id="454d7-111">有关更新的应用程序或使用的并行版本控制的业务流程所需的任务的分步列表，请参阅[清单： 更新应用程序使用的并行版本控制](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)和[清单： 更新使用的并行版本控制的业务流程](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)。</span><span class="sxs-lookup"><span data-stu-id="454d7-111">For a step-by-step list of tasks required to update an application or orchestration using side-by-side versioning, see [Checklist: Updating an Application Using Side-by-Side Versioning](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md) and [Checklist: Updating an Orchestration Using Side-by-Side Versioning](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md).</span></span> <span data-ttu-id="454d7-112">有关如何让应用程序的并行部署的详细说明，请参阅"[如何部署到运行并行应用程序与现有版本的新版本](http://go.microsoft.com/fwlink/?LinkId=155143)(http://go.microsoft.com/fwlink/?LinkId = 155143) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="454d7-112">For detailed instructions on how to have side-by-side deployment of applications, see "[How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version](http://go.microsoft.com/fwlink/?LinkId=155143) (http://go.microsoft.com/fwlink/?LinkId=155143) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="454d7-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="454d7-113">In This Section</span></span>  
  
-   [<span data-ttu-id="454d7-114">如何更新使用的并行版本控制的映射</span><span class="sxs-lookup"><span data-stu-id="454d7-114">How to Update a Map Using Side-by-Side Versioning</span></span>](../technical-guides/how-to-update-a-map-using-side-by-side-versioning.md)  
  
-   [<span data-ttu-id="454d7-115">如何更新管道使用的并行版本控制</span><span class="sxs-lookup"><span data-stu-id="454d7-115">How to Update a Pipeline Using Side-by-Side Versioning</span></span>](../technical-guides/how-to-update-a-pipeline-using-side-by-side-versioning.md)  
  
-   [<span data-ttu-id="454d7-116">更新使用的并行版本控制的架构</span><span class="sxs-lookup"><span data-stu-id="454d7-116">Updating a Schema Using Side-by-Side Versioning</span></span>](../technical-guides/updating-a-schema-using-side-by-side-versioning.md)