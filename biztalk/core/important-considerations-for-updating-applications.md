---
title: 更新应用程序的重要注意事项 |Microsoft 文档
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
ms.openlocfilehash: c24528dcce390376b7ac2e47199aa5ae06d412a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257741"
---
# <a name="important-considerations-for-updating-applications"></a><span data-ttu-id="bdc61-102">更新应用程序的重要注意事项</span><span class="sxs-lookup"><span data-stu-id="bdc61-102">Important Considerations for Updating Applications</span></span>
<span data-ttu-id="bdc61-103">以下为更新应用程序时，特别是更新在生产环境中运行的应用程序时，需要注意的重要事项。</span><span class="sxs-lookup"><span data-stu-id="bdc61-103">The following are important issues to consider before updating an application, especially one that is running in a production environment.</span></span>  
  
## <a name="general-considerations"></a><span data-ttu-id="bdc61-104">常规注意事项</span><span class="sxs-lookup"><span data-stu-id="bdc61-104">General considerations</span></span>  
  
-   <span data-ttu-id="bdc61-105">因为参与方和规则在组作用域可见，所以添加另外的参与方和规则可能会中断其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="bdc61-105">Parties and rules are visible at a group scope, so adding additional parties and rules could disrupt other applications.</span></span>  
  
-   <span data-ttu-id="bdc61-106">如果要取消部署被其他项目所依赖的项目，必须首先取消部署依赖它的项目。</span><span class="sxs-lookup"><span data-stu-id="bdc61-106">If you are undeploying an artifact on which another artifact depends, the dependent artifact must be undeployed first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bdc61-107">BizTalk Server 管理控制台将显示警告并防止以不正确的顺序取消部署项目。</span><span class="sxs-lookup"><span data-stu-id="bdc61-107">The BizTalk Server Administration console will display a warning and prevent you from undeploying artifacts in the incorrect order.</span></span>  
  
-   <span data-ttu-id="bdc61-108">如果现有应用程序中的 BizTalk 程序集进行了更新，你可能需要重新启动主机实例以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="bdc61-108">If a BizTalk assembly in an existing application is updated, you may need to restart host instances for the changes to take effect.</span></span> <span data-ttu-id="bdc61-109">重新启动主机实例将停止所有主机实例运行其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="bdc61-109">Restarting a host instance stops all other applications that are running on the host instance.</span></span>  
  
-   <span data-ttu-id="bdc61-110">如果您使用 Visual Studio 将某一应用程序部署到生产环境中（极力建议您不要这么做），并将项目属性中的“重新启动主机实例”选项设为“True”，那么在您部署此应用程序时，所有主机实例都将重新启动，包括那些不与此应用程序关联的主机实例。</span><span class="sxs-lookup"><span data-stu-id="bdc61-110">If you use Visual Studio to deploy an application into a production environment (which we strongly recommend against doing) and the Restart Host Instances option is set to True in project properties, all host instances will restart when you deploy the application, including those that are not associated with this application.</span></span> <span data-ttu-id="bdc61-111">这样会停止在本地计算机的任何主机实例上运行的所有其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="bdc61-111">This will stop all other applications that are running on any host instance on the local computer.</span></span>  
  
-   <span data-ttu-id="bdc61-112">如果你想要更新 BizTalk Server 程序集 （包含业务流程、 架构或映射） 作为 BizTalk 应用程序部署，可以执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="bdc61-112">If you want to update a BizTalk Server assembly (containing an orchestration, schema, or map) which is deployed as a BizTalk application, you can do any of the following:</span></span>  
  
    -   <span data-ttu-id="bdc61-113">执行并排显示部署。</span><span class="sxs-lookup"><span data-stu-id="bdc61-113">Perform a side-by-side deployment.</span></span> <span data-ttu-id="bdc61-114">通常可以通过递增版本号来适当地修改较新的程序集。</span><span class="sxs-lookup"><span data-stu-id="bdc61-114">You can appropriately modify the newer assembly typically by incrementing the version.</span></span> <span data-ttu-id="bdc61-115">这可以使两个程序集都具有独特的完全限定的程序集名称。</span><span class="sxs-lookup"><span data-stu-id="bdc61-115">This makes both the assemblies have a distinct fully qualified assembly name.</span></span> <span data-ttu-id="bdc61-116">有关详细信息，请参阅[如何部署到运行的并行与现有版本的应用程序的新版本](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md)。</span><span class="sxs-lookup"><span data-stu-id="bdc61-116">For more information, see [How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md).</span></span>  
  
    -   <span data-ttu-id="bdc61-117">将现有的 BizTalk Server 程序集替换为新的程序集。</span><span class="sxs-lookup"><span data-stu-id="bdc61-117">Replace the existing BizTalk Server assembly with a new assembly.</span></span> <span data-ttu-id="bdc61-118">您必须停止所有可能加载过期程序集的主机实例，替换 GAC 中的过期程序集，然后重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="bdc61-118">You must stop all host instances that can possibly load the out-dated assembly, replace the out-dated assembly in the GAC, and then restart the host instances.</span></span>  
  
-   <span data-ttu-id="bdc61-119">如果要部署一个全新的应用程序以替换现有的应用程序，必须更正其他应用程序与要替换的应用程序之间的所有引用。</span><span class="sxs-lookup"><span data-stu-id="bdc61-119">If you deploy an entirely new application to replace an existing application, you must correct any references between other applications and the application that you are replacing.</span></span>  
  
## <a name="considerations-for-updating-schemas"></a><span data-ttu-id="bdc61-120">更新架构时的注意事项</span><span class="sxs-lookup"><span data-stu-id="bdc61-120">Considerations for updating schemas</span></span>  
  
-   <span data-ttu-id="bdc61-121">如果将程序集添加到 BizTalk 组中包括具有与现有架构相同的消息类型的新架构的应用程序中时，在管道中发生的架构解析时，将使用版本号最高的架构。</span><span class="sxs-lookup"><span data-stu-id="bdc61-121">If you add an assembly to an application that includes a new schema with the same message type as an existing schema in the BizTalk group, the schema with the highest version number will be used when schema resolution occurs in pipelines.</span></span> <span data-ttu-id="bdc61-122">此外，如果一种消息类型引用多个.NET 类型，这种混乱情况可能会导致管道执行失败。</span><span class="sxs-lookup"><span data-stu-id="bdc61-122">In addition, if one message type refers to more than one .NET type, this ambiguity may cause pipeline execution failure.</span></span> <span data-ttu-id="bdc61-123">原因在于架构查找使用的是消息类型、目标命名空间和实例的根名称。</span><span class="sxs-lookup"><span data-stu-id="bdc61-123">This is because schema lookup uses message type, the target namespace, and root name of the instance.</span></span> <span data-ttu-id="bdc61-124">对于所使用的架构与新架构具有相同消息类型的任何应用程序，其中的管道都可能发生这种问题。</span><span class="sxs-lookup"><span data-stu-id="bdc61-124">This can occur for pipelines in any application that uses a schema with the same message type as the new schema.</span></span> <span data-ttu-id="bdc61-125">有关架构解析的详细信息，请参阅[管道组件中的架构解析](../core/schema-resolution-in-pipeline-components.md)。</span><span class="sxs-lookup"><span data-stu-id="bdc61-125">For more information about schema resolution, see [Schema Resolution in Pipeline Components](../core/schema-resolution-in-pipeline-components.md).</span></span>  
  
-   <span data-ttu-id="bdc61-126">更新某一架构时，必须同时更新引用此架构的映射（或创建新映射），以及任何依赖于此架构的业务流程。</span><span class="sxs-lookup"><span data-stu-id="bdc61-126">When you update a schema, you must also update the maps that reference the schema (or create new maps) as well as any orchestrations that rely on the schema.</span></span>  
  
-   <span data-ttu-id="bdc61-127">如果递增了某一架构的版本，应为使用此架构的任何管道实例和管道组件更新对此架构的引用。</span><span class="sxs-lookup"><span data-stu-id="bdc61-127">If you increment a schema version, you should update the reference to the schema for any pipeline instances and pipeline components that use it.</span></span>  
  
-   <span data-ttu-id="bdc61-128">取消部署某一架构会导致此架构的以前版本（如可用）变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="bdc61-128">Undeploying a schema causes the previous version of the schema, if available, to become active.</span></span>  
  
## <a name="considerations-for-updating-policies"></a><span data-ttu-id="bdc61-129">更新策略时的注意事项</span><span class="sxs-lookup"><span data-stu-id="bdc61-129">Considerations for updating policies</span></span>  
  
-   <span data-ttu-id="bdc61-130">BizTalk Server 运行时会使用处于部署状态的策略的最高版本。</span><span class="sxs-lookup"><span data-stu-id="bdc61-130">The highest version of a policy that is in a deployed state is used by the BizTalk Server runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc61-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdc61-131">See Also</span></span>  
 [<span data-ttu-id="bdc61-132">更新 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="bdc61-132">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)