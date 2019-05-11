---
title: 有关更新应用程序的重要注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- updating, applications
- applications, planning
- applications, updating
- planning, applications
- planning, updating
- updating, planning
ms.assetid: e7690bdf-943d-4bb6-b8cd-a6841b722d40
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39b3bdd5d939edd1fa1d930d5711f8bac8a8f71c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382587"
---
# <a name="important-considerations-for-updating-applications"></a><span data-ttu-id="8dff2-102">有关更新应用程序的重要注意事项</span><span class="sxs-lookup"><span data-stu-id="8dff2-102">Important Considerations for Updating Applications</span></span>
<span data-ttu-id="8dff2-103">以下是更新应用程序，尤其是在生产环境中运行的是之前要考虑的重要问题。</span><span class="sxs-lookup"><span data-stu-id="8dff2-103">The following are important issues to consider before updating an application, especially one that is running in a production environment.</span></span>  
  
## <a name="general-considerations"></a><span data-ttu-id="8dff2-104">一般注意事项</span><span class="sxs-lookup"><span data-stu-id="8dff2-104">General considerations</span></span>  
  
-   <span data-ttu-id="8dff2-105">参与方和规则是在组作用域中可见，因此添加其他参与方和规则可能会中断其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="8dff2-105">Parties and rules are visible at a group scope, so adding additional parties and rules could disrupt other applications.</span></span>  
  
-   <span data-ttu-id="8dff2-106">如果取消部署的其他项目所依赖的项目依赖的程序集必须首先取消部署。</span><span class="sxs-lookup"><span data-stu-id="8dff2-106">If you are undeploying an artifact on which another artifact depends, the dependent artifact must be undeployed first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8dff2-107">在 BizTalk Server 管理控制台将显示一条警告，并阻止您从错误的顺序取消部署项目。</span><span class="sxs-lookup"><span data-stu-id="8dff2-107">The BizTalk Server Administration console will display a warning and prevent you from undeploying artifacts in the incorrect order.</span></span>  
  
-   <span data-ttu-id="8dff2-108">如果更新现有应用程序中的 BizTalk 程序集时，可能需要重新启动主机实例以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="8dff2-108">If a BizTalk assembly in an existing application is updated, you may need to restart host instances for the changes to take effect.</span></span> <span data-ttu-id="8dff2-109">重新启动主机实例停止所有主机实例运行其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="8dff2-109">Restarting a host instance stops all other applications that are running on the host instance.</span></span>  
  
-   <span data-ttu-id="8dff2-110">如果你使用 Visual Studio 部署到生产环境中 （我们强烈建议不要这样做） 的应用程序和项目属性中重新启动主机实例选项设置为 True，所有主机实例时部署应用程序，将重新都启动包括那些不与此应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="8dff2-110">If you use Visual Studio to deploy an application into a production environment (which we strongly recommend against doing) and the Restart Host Instances option is set to True in project properties, all host instances will restart when you deploy the application, including those that are not associated with this application.</span></span> <span data-ttu-id="8dff2-111">这将停止所有本地计算机上的任何主机实例运行其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="8dff2-111">This will stop all other applications that are running on any host instance on the local computer.</span></span>  
  
-   <span data-ttu-id="8dff2-112">如果你想要更新 BizTalk Server 程序集 （包含业务流程、 架构或映射） 为 BizTalk 应用程序部署，可以执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="8dff2-112">If you want to update a BizTalk Server assembly (containing an orchestration, schema, or map) which is deployed as a BizTalk application, you can do any of the following:</span></span>  
  
    -   <span data-ttu-id="8dff2-113">执行的并行部署。</span><span class="sxs-lookup"><span data-stu-id="8dff2-113">Perform a side-by-side deployment.</span></span> <span data-ttu-id="8dff2-114">适当地可以通过递增版本号通常修改的较新的程序集。</span><span class="sxs-lookup"><span data-stu-id="8dff2-114">You can appropriately modify the newer assembly typically by incrementing the version.</span></span> <span data-ttu-id="8dff2-115">这样，两个具有不同的完全限定程序集名称的程序集。</span><span class="sxs-lookup"><span data-stu-id="8dff2-115">This makes both the assemblies have a distinct fully qualified assembly name.</span></span> <span data-ttu-id="8dff2-116">有关详细信息，请参阅[如何部署到运行的并排方案与现有版本的应用程序的新版本](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md)。</span><span class="sxs-lookup"><span data-stu-id="8dff2-116">For more information, see [How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md).</span></span>  
  
    -   <span data-ttu-id="8dff2-117">现有的 BizTalk Server 程序集替换为新的程序集。</span><span class="sxs-lookup"><span data-stu-id="8dff2-117">Replace the existing BizTalk Server assembly with a new assembly.</span></span> <span data-ttu-id="8dff2-118">必须停止所有主机实例可能加载过期程序集、 替换过期程序集位于 GAC 中的并然后重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="8dff2-118">You must stop all host instances that can possibly load the out-dated assembly, replace the out-dated assembly in the GAC, and then restart the host instances.</span></span>  
  
-   <span data-ttu-id="8dff2-119">如果部署全新的应用程序以替换现有应用程序，你必须更正其他应用程序以及要替换的应用程序之间的所有引用。</span><span class="sxs-lookup"><span data-stu-id="8dff2-119">If you deploy an entirely new application to replace an existing application, you must correct any references between other applications and the application that you are replacing.</span></span>  
  
## <a name="considerations-for-updating-schemas"></a><span data-ttu-id="8dff2-120">更新架构的注意事项</span><span class="sxs-lookup"><span data-stu-id="8dff2-120">Considerations for updating schemas</span></span>  
  
-   <span data-ttu-id="8dff2-121">如果向 BizTalk 组中包括的新架构具有与现有架构相同的消息类型的应用程序添加程序集，管道中发生架构解析时将使用具有最高版本号的架构。</span><span class="sxs-lookup"><span data-stu-id="8dff2-121">If you add an assembly to an application that includes a new schema with the same message type as an existing schema in the BizTalk group, the schema with the highest version number will be used when schema resolution occurs in pipelines.</span></span> <span data-ttu-id="8dff2-122">此外，如果一种消息类型所引用的多个.NET 类型，此二义性可能会导致管道执行失败。</span><span class="sxs-lookup"><span data-stu-id="8dff2-122">In addition, if one message type refers to more than one .NET type, this ambiguity may cause pipeline execution failure.</span></span> <span data-ttu-id="8dff2-123">这是实例的因为架构查找使用的消息类型、 目标命名空间和根的名称。</span><span class="sxs-lookup"><span data-stu-id="8dff2-123">This is because schema lookup uses message type, the target namespace, and root name of the instance.</span></span> <span data-ttu-id="8dff2-124">这可能与新的架构相同的消息类型与使用的架构的任何应用程序中的管道。</span><span class="sxs-lookup"><span data-stu-id="8dff2-124">This can occur for pipelines in any application that uses a schema with the same message type as the new schema.</span></span> <span data-ttu-id="8dff2-125">有关架构解析的详细信息，请参阅[管道组件中的架构解析](../core/schema-resolution-in-pipeline-components.md)。</span><span class="sxs-lookup"><span data-stu-id="8dff2-125">For more information about schema resolution, see [Schema Resolution in Pipeline Components](../core/schema-resolution-in-pipeline-components.md).</span></span>  
  
-   <span data-ttu-id="8dff2-126">更新架构时，还必须依赖于架构的任何业务流程以及更新引用架构 （或创建新映射） 的映射。</span><span class="sxs-lookup"><span data-stu-id="8dff2-126">When you update a schema, you must also update the maps that reference the schema (or create new maps) as well as any orchestrations that rely on the schema.</span></span>  
  
-   <span data-ttu-id="8dff2-127">如果递增的架构版本，则应更新架构以了解任何管道实例和管道组件使用它的引用。</span><span class="sxs-lookup"><span data-stu-id="8dff2-127">If you increment a schema version, you should update the reference to the schema for any pipeline instances and pipeline components that use it.</span></span>  
  
-   <span data-ttu-id="8dff2-128">取消部署架构会导致该架构的以前版本，如果可用，变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="8dff2-128">Undeploying a schema causes the previous version of the schema, if available, to become active.</span></span>  
  
## <a name="considerations-for-updating-policies"></a><span data-ttu-id="8dff2-129">更新策略的注意事项</span><span class="sxs-lookup"><span data-stu-id="8dff2-129">Considerations for updating policies</span></span>  
  
-   <span data-ttu-id="8dff2-130">BizTalk Server 运行时使用的策略处于已部署状态的最高版本。</span><span class="sxs-lookup"><span data-stu-id="8dff2-130">The highest version of a policy that is in a deployed state is used by the BizTalk Server runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dff2-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="8dff2-131">See Also</span></span>  
 [<span data-ttu-id="8dff2-132">更新 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="8dff2-132">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)