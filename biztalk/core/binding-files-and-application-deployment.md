---
title: "绑定文件和应用程序部署 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings
- deploying [applications], binding files
- assemblies, binding files
- bindings, applying
- groups, assemblies
- applications, binding files
- binding files, applications
- bindings, hosts
- deploying, assemblies
- updating, assemblies
- assemblies, updating
- hosts, bindings
- binding files, assemblies
- applications, moving
- assemblies, deploying
- binding files, about binding files
- bindings, about bindings
- groups, deploying
- binding files, deploying
- bindings, binding files
ms.assetid: 396ad021-8001-4ed8-8b28-85b72f981fae
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc6908f962cd3bb8f9fdec3fcaab6bc131c889da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="binding-files-and-application-deployment"></a><span data-ttu-id="0a738-102">绑定文件和应用程序部署</span><span class="sxs-lookup"><span data-stu-id="0a738-102">Binding Files and Application Deployment</span></span>
<span data-ttu-id="0a738-103">本主题提供概述信息，说明如何使用绑定文件简化 BizTalk 程序集和应用程序的部署。</span><span class="sxs-lookup"><span data-stu-id="0a738-103">This topic provides overview information about using binding files to make BizTalk assembly and application deployment easier.</span></span> <span data-ttu-id="0a738-104">在下列情况下，您会发现，由于使用绑定文件避免了手动配置绑定，因此可以加速部署过程：</span><span class="sxs-lookup"><span data-stu-id="0a738-104">You may find that binding files speed deployment in the following scenarios by avoiding the need to manually configure bindings:</span></span>  
  
-   <span data-ttu-id="0a738-105">将应用程序从一种部署环境移到另一个。</span><span class="sxs-lookup"><span data-stu-id="0a738-105">Moving an application from one deployment environment to another.</span></span>  
  
-   <span data-ttu-id="0a738-106">更新程序集。</span><span class="sxs-lookup"><span data-stu-id="0a738-106">Updating an assembly.</span></span>  
  
-   <span data-ttu-id="0a738-107">将程序集部署到多个 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="0a738-107">Deploying an assembly to multiple BizTalk groups.</span></span>  
  
## <a name="what-is-a-binding"></a><span data-ttu-id="0a738-108">什么是绑定？</span><span class="sxs-lookup"><span data-stu-id="0a738-108">What is a binding?</span></span>  
 <span data-ttu-id="0a738-109">绑定可以在逻辑终结点（如业务流程端口或角色链接）与物理终结点（如发送/接收端口或参与方）之间创建映射。</span><span class="sxs-lookup"><span data-stu-id="0a738-109">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="0a738-110">这样即可在 BizTalk 业务解决方案的不同组件之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="0a738-110">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="0a738-111">使用 BizTalk Server 管理控制台可以创建绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-111">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="0a738-112">什么是绑定文件？</span><span class="sxs-lookup"><span data-stu-id="0a738-112">What is a binding file?</span></span>  
 <span data-ttu-id="0a738-113">绑定文件是一个 .xml 文件，其中包含 BizTalk 程序集、应用程序或组范围内的每一 BizTalk 业务流程、管道、映射或架构的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="0a738-113">A binding file is an .xml file that contains binding information for each BizTalk orchestration, pipeline, map, or schema in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="0a738-114">绑定文件描述各个业务流程绑定到的主机、主机信任级别，以及已经配置的每个发送端口、发送端口组、接收端口、接收位置和参与方的设置。</span><span class="sxs-lookup"><span data-stu-id="0a738-114">The binding file describes what host each orchestration is bound to and its trust level as well as the settings for each send port, send port group, receive port, receive location, and party that has been configured.</span></span> <span data-ttu-id="0a738-115">您可以生成绑定文件，然后将其中包含的绑定应用到某个程序集、应用程序或组，以避免在不同的部署环境中手动配置绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-115">You can generate binding files and then apply the bindings they contain to an assembly, application, or group to avoid needing to manually configure bindings in different deployment environments.</span></span>  
  
## <a name="why-use-binding-files"></a><span data-ttu-id="0a738-116">为什么使用绑定文件？</span><span class="sxs-lookup"><span data-stu-id="0a738-116">Why use binding files?</span></span>  
 <span data-ttu-id="0a738-117">在以下情况下可能需要使用绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0a738-117">You may want to use binding files in the following scenarios.</span></span>  
  
### <a name="moving-from-one-environment-to-another"></a><span data-ttu-id="0a738-118">转移到不同环境</span><span class="sxs-lookup"><span data-stu-id="0a738-118">Moving from one environment to another</span></span>  
 <span data-ttu-id="0a738-119">您可以使用绑定文件简化应用程序在不同部署环境之间的转移，比如从开发环境移至测试环境。</span><span class="sxs-lookup"><span data-stu-id="0a738-119">You can use binding files to make it easier to move an application from one deployment environment to another, such as from a development environment to a test environment.</span></span> <span data-ttu-id="0a738-120">这是因为不同的部署环境往往要求重新配置绑定，但通过使用绑定文件，您可以避免重复执行这一手动配置步骤。</span><span class="sxs-lookup"><span data-stu-id="0a738-120">This is because bindings often must be reconfigured for different deployment environments, but by using binding files, you can avoid repeatedly performing this manual configuration step.</span></span>  
  
 <span data-ttu-id="0a738-121">进行此操作的方法之一是创建一个绑定库，在将应用程序部署到新环境时从绑定库中进行选择。</span><span class="sxs-lookup"><span data-stu-id="0a738-121">One way you can do this is to create a library of bindings from which to select when deploying the application into a new environment.</span></span> <span data-ttu-id="0a738-122">例如，可以为您的测试环境创建一个绑定文件，为生产环境创建另一个绑定文件，然后将它们一同添加到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="0a738-122">For example, you can create a binding file for your test environment and another one for your production environment and then add them both to the application.</span></span> <span data-ttu-id="0a738-123">将该应用程序导入测试环境时，可以选择一个选项来应用测试绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-123">When you import the application into the test environment, you can select an option to apply the test bindings.</span></span> <span data-ttu-id="0a738-124">同样，将该应用程序导入生产环境时，也可以选择一个选项来应用生产绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-124">Likewise, when you import the application into the production environment, you can select an option to apply the production bindings.</span></span> <span data-ttu-id="0a738-125">这样可以避免为不同环境手动重新配置绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-125">This avoids the need to reconfigure bindings manually for different environments.</span></span> <span data-ttu-id="0a738-126">另一种方法是在将应用程序导入当前环境后，再导入为该环境创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-126">Another way is to import bindings that you have created for the current environment after importing the application into it.</span></span> <span data-ttu-id="0a738-127">这样可以自动应用绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-127">This automatically applies the bindings.</span></span>  
  
### <a name="updating-an-assembly"></a><span data-ttu-id="0a738-128">更新程序集</span><span class="sxs-lookup"><span data-stu-id="0a738-128">Updating an assembly</span></span>  
 <span data-ttu-id="0a738-129">在更新应用程序中的一个程序集时，通常会覆盖该程序集的绑定，也有可能该程序集根本未绑定，所以您不得不手动重新配置绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-129">When you update an assembly in an application, its bindings are often overwritten or else the assembly may not be bound at all, forcing you to manually reconfigure bindings.</span></span> <span data-ttu-id="0a738-130">为避免此情况，您可按如下所示使用绑定文件：</span><span class="sxs-lookup"><span data-stu-id="0a738-130">To avoid this, you can use a binding file as follows:</span></span>  
  
-   <span data-ttu-id="0a738-131">**正在更新相同版本的程序集。**</span><span class="sxs-lookup"><span data-stu-id="0a738-131">**Updating the same version of an assembly.**</span></span> <span data-ttu-id="0a738-132">如果程序集具有早期绑定端口或动态端口，而您在 BizTalk Server 管理控制台中更改了端口配置，在您使用相同版本号的程序集来更新当前程序集时这些设置将丢失。</span><span class="sxs-lookup"><span data-stu-id="0a738-132">If the assembly has early bound ports or dynamic ports, and you changed the port configuration in the BizTalk Server Administration console, the settings will be lost when you update the assembly with an assembly having the same version number.</span></span> <span data-ttu-id="0a738-133">您可以导出准备更新的程序集的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0a738-133">You can export a binding file for the assembly you are going to update.</span></span> <span data-ttu-id="0a738-134">更新程序集后，您可以将该程序集导入应用程序，然后导入其绑定文件以重新应用先前的绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-134">After updating the assembly you can import the assembly into the application and then import its binding file to reapply the previous bindings.</span></span>  
  
-   <span data-ttu-id="0a738-135">**更新的较新版本的程序集。**</span><span class="sxs-lookup"><span data-stu-id="0a738-135">**Updating an assembly with a newer version.**</span></span> <span data-ttu-id="0a738-136">您可以导出准备更新的程序集的绑定文件，然后编辑该文件以反映新的程序集版本。</span><span class="sxs-lookup"><span data-stu-id="0a738-136">You can export a binding file for the assembly that you are going to update and then edit it to reflect the new assembly version.</span></span> <span data-ttu-id="0a738-137">将新的程序集版本导入应用程序后，您可以将绑定文件导入应用程序以应用绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-137">After you import the new assembly version into the application, you can import the binding file into the application to apply the bindings.</span></span> <span data-ttu-id="0a738-138">有关编辑绑定文件的说明，请参阅[自定义绑定文件](../core/customizing-binding-files.md)。</span><span class="sxs-lookup"><span data-stu-id="0a738-138">For instructions on editing a binding file, see [Customizing Binding Files](../core/customizing-binding-files.md).</span></span>  
  
### <a name="deploying-an-assembly-to-multiple-biztalk-groups"></a><span data-ttu-id="0a738-139">将程序集部署到多个 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="0a738-139">Deploying an assembly to multiple BizTalk groups</span></span>  
 <span data-ttu-id="0a738-140">将程序集部署到多个 BizTalk 组时，可以将程序集的绑定与该程序集一同传输。</span><span class="sxs-lookup"><span data-stu-id="0a738-140">When you deploy an assembly into multiple BizTalk groups, you can transport the bindings for the assembly along with the assembly.</span></span> <span data-ttu-id="0a738-141">这样可以避免在每个组中为程序集分别配置绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-141">This avoids the need to separately configure the bindings for the assembly in each group.</span></span> <span data-ttu-id="0a738-142">可按如下方式操作：</span><span class="sxs-lookup"><span data-stu-id="0a738-142">You can do this as follows:</span></span>  
  
1.  <span data-ttu-id="0a738-143">通过导出程序集绑定为要部署的程序集创建绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0a738-143">Create a binding file for the assembly that you want to deploy by exporting the assembly's bindings.</span></span>  
  
2.  <span data-ttu-id="0a738-144">向应用程序添加程序集及其绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0a738-144">Add the assembly and its binding file to an application.</span></span> <span data-ttu-id="0a738-145">如果您要将程序集与其他项目分开部署，则应用程序只能包含程序集及绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0a738-145">If you are deploying the assembly separately from other artifacts, the application can contain only the assembly and the binding file.</span></span>  
  
3.  <span data-ttu-id="0a738-146">导出应用程序的 .msi 文件，务必选择一同导出绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0a738-146">Export an .msi file for the application, being sure to select the binding file to export as well.</span></span>  
  
4.  <span data-ttu-id="0a738-147">将应用程序的 .msi 文件导入要在其中部署该文件的 BizTalk 组和应用程序。</span><span class="sxs-lookup"><span data-stu-id="0a738-147">Import the application .msi file into the BizTalk groups and applications where you want to deploy it.</span></span> <span data-ttu-id="0a738-148">文件中的绑定将在导入时自动应用到程序集内。</span><span class="sxs-lookup"><span data-stu-id="0a738-148">The bindings in the file are automatically applied to the assembly on import.</span></span>  
  
## <a name="how-can-i-generate-and-use-binding-files"></a><span data-ttu-id="0a738-149">如何生成和使用绑定文件？</span><span class="sxs-lookup"><span data-stu-id="0a738-149">How can I generate and use binding files?</span></span>  
 <span data-ttu-id="0a738-150">BizTalk 程序集，应用程序，或组，不自动生成一个绑定文件但中所述，你可以通过导出的绑定，生成绑定文件[导出绑定](../core/exporting-bindings6.md)。</span><span class="sxs-lookup"><span data-stu-id="0a738-150">A binding file is not automatically generated for a BizTalk assembly, application, or group, but you can generate a binding file by exporting bindings, as described in [Exporting Bindings](../core/exporting-bindings6.md).</span></span> <span data-ttu-id="0a738-151">你可以然后绑定文件导入的应用程序或组中中, 所述[如何导入到 BizTalk 应用程序的绑定](../core/how-to-import-bindings-into-a-biztalk-application.md)和[如何导入绑定到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)，后者自动将应用自己的绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-151">You can then import the binding file into an application or group, as described in [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md) and [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md), which automatically applies its bindings.</span></span>  
  
 <span data-ttu-id="0a738-152">或者，向应用程序添加的绑定文件，以便在将应用程序导入另一个组，而不立即应用中所述应用自己的绑定[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md).</span><span class="sxs-lookup"><span data-stu-id="0a738-152">Alternatively, you can add the binding file to an application so that its bindings are applied when the application is imported into another group, rather than being applied immediately, as described in [How to Add a Binding File to an Application](../core/how-to-add-a-binding-file-to-an-application2.md).</span></span> <span data-ttu-id="0a738-153">使用最后一种方法可以向应用程序添加多个绑定文件，而且可以选择分别为每个绑定文件指定目标环境。</span><span class="sxs-lookup"><span data-stu-id="0a738-153">Using the last method, you can add multiple binding files to an application and optionally specify a target deployment environment for each one.</span></span> <span data-ttu-id="0a738-154">当你导入应用程序时，然后，可以选择要将应用，哪些绑定中所述，在目标部署环境中，基于[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="0a738-154">When you import the application, you can then select which bindings to apply, based on the target deployment environment, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span> <span data-ttu-id="0a738-155">使用最后一种方法，还可以在应用程序中分别导入不同程序集的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0a738-155">Using the last method, you can also import separate binding files for the different assemblies in your application.</span></span>  
  
 <span data-ttu-id="0a738-156">您可以在生成绑定文件后对其进行编辑，以更改其中的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="0a738-156">You can edit binding files after you generate them to change their binding information.</span></span> <span data-ttu-id="0a738-157">有关详细信息，请参阅[自定义绑定文件](../core/customizing-binding-files.md)。</span><span class="sxs-lookup"><span data-stu-id="0a738-157">For more information, see [Customizing Binding Files](../core/customizing-binding-files.md).</span></span>  
  
## <a name="how-are-bindings-applied"></a><span data-ttu-id="0a738-158">如何应用绑定？</span><span class="sxs-lookup"><span data-stu-id="0a738-158">How are bindings applied?</span></span>  
 <span data-ttu-id="0a738-159">将绑定文件导入应用程序或是将应用程序导入新的 BizTalk 组时，将应用绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-159">Bindings are applied when a binding file is imported into an application, or when an application is imported into a new BizTalk group.</span></span> <span data-ttu-id="0a738-160">使用绑定文件时，务须理解项目绑定到主机的方式以及应用绑定的顺序。</span><span class="sxs-lookup"><span data-stu-id="0a738-160">When using binding files, it is important to understand how artifacts are bound to hosts and in the order in which bindings are applied.</span></span>  
  
### <a name="binding-to-hosts"></a><span data-ttu-id="0a738-161">绑定到主机</span><span class="sxs-lookup"><span data-stu-id="0a738-161">Binding to hosts</span></span>  
 <span data-ttu-id="0a738-162">导出绑定时（单独导出或作为应用程序的一部分导出），主机和信任级别按如下方式存储在绑定文件中：</span><span class="sxs-lookup"><span data-stu-id="0a738-162">When bindings are exported either separately or as part of an application, hosts and trust levels are stored in the binding file as follows:</span></span>  
  
-   <span data-ttu-id="0a738-163">**发送端口。**</span><span class="sxs-lookup"><span data-stu-id="0a738-163">**Send Port.**</span></span> <span data-ttu-id="0a738-164">与发送处理程序关联的主机的信任级别。</span><span class="sxs-lookup"><span data-stu-id="0a738-164">Trust level of the host associated with the send handler.</span></span>  
  
-   <span data-ttu-id="0a738-165">**接收位置。**</span><span class="sxs-lookup"><span data-stu-id="0a738-165">**Receive Location.**</span></span> <span data-ttu-id="0a738-166">与接收处理程序关联的主机的信任级别。</span><span class="sxs-lookup"><span data-stu-id="0a738-166">Trust level of the host associated with the receive handler.</span></span>  
  
-   <span data-ttu-id="0a738-167">**业务流程。**</span><span class="sxs-lookup"><span data-stu-id="0a738-167">**Orchestration.**</span></span> <span data-ttu-id="0a738-168">主机的信任级别。</span><span class="sxs-lookup"><span data-stu-id="0a738-168">Trust Level of the host.</span></span>  
  
 <span data-ttu-id="0a738-169">将绑定导入应用程序或是将应用程序从 .msi 文件导入新的 BizTalk 组时，绑定文件中的主机和信任级别将与应用程序中的主机和信任级别进行匹配，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0a738-169">When the bindings are imported into an application, or an application is imported from the .msi file into a new BizTalk group, hosts and trust levels in the binding files are matched to hosts and trust levels in the application, as follows:</span></span>  
  
-   <span data-ttu-id="0a738-170">**发送端口。**</span><span class="sxs-lookup"><span data-stu-id="0a738-170">**Send Port.**</span></span> <span data-ttu-id="0a738-171">发送端口会绑定到同名的发送处理程序，并绑定到具有与绑定文件中所存储信任级别相同的信任级别的主机。</span><span class="sxs-lookup"><span data-stu-id="0a738-171">The send port is bound to a send handler of the same name and bound to a host with the same trust level as that stored in the binding file.</span></span>  
  
-   <span data-ttu-id="0a738-172">**接收位置。**</span><span class="sxs-lookup"><span data-stu-id="0a738-172">**Receive Location.**</span></span> <span data-ttu-id="0a738-173">接收位置绑定到同名的接收处理程序，并且绑定到的主机的信任级别与存储在绑定文件中的信任级别相同。</span><span class="sxs-lookup"><span data-stu-id="0a738-173">The receive location is bound to a receive handler of the same name and bound to a host with the same trust level as that stored in the binding file.</span></span>  
  
-   <span data-ttu-id="0a738-174">**业务流程。**</span><span class="sxs-lookup"><span data-stu-id="0a738-174">**Orchestrations.**</span></span> <span data-ttu-id="0a738-175">业务流程绑定到与绑定文件中的主机名称和信任级别相同的主机。</span><span class="sxs-lookup"><span data-stu-id="0a738-175">The orchestration is bound to a host with the same name and trust level and as that in the binding file.</span></span>  
  
### <a name="order-in-which-bindings-are-applied"></a><span data-ttu-id="0a738-176">绑定的应用顺序</span><span class="sxs-lookup"><span data-stu-id="0a738-176">Order in which bindings are applied</span></span>  
 <span data-ttu-id="0a738-177">导入应用程序时，绑定按如下顺序应用：</span><span class="sxs-lookup"><span data-stu-id="0a738-177">When you import an application, bindings are applied in the following order:</span></span>  
  
1.  <span data-ttu-id="0a738-178">由 BizTalk Server 生成的、未通过绑定文件显式添加到应用程序但用户已经显式选择导出到应用程序 .msi 文件的应用程序绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-178">Application bindings generated by BizTalk Server that were not explicitly added to the application via a binding file, but that were explicitly selected by the user for export into the application .msi file.</span></span>  
  
2.  <span data-ttu-id="0a738-179">已经添加到应用程序但并未指定目标部署环境的绑定文件中的绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-179">Bindings in binding files that have been added to the application, and which do not have a target deployment environment specified.</span></span> <span data-ttu-id="0a738-180">这些绑定可以按任意顺序应用。</span><span class="sxs-lookup"><span data-stu-id="0a738-180">These bindings are applied in no specific order.</span></span>  
  
3.  <span data-ttu-id="0a738-181">已经添加到应用程序、并且具有关联目标部署环境（与为导入应用程序选定的部署环境相匹配）的绑定文件中的绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-181">Bindings in binding files that have been added to the application, and which have an associated target deployment environment that matches the deployment environment selected for application import.</span></span> <span data-ttu-id="0a738-182">这些绑定可以按任意顺序应用。</span><span class="sxs-lookup"><span data-stu-id="0a738-182">These bindings are applied in no specific order.</span></span>  
  
 <span data-ttu-id="0a738-183">由于绑定在导入过程中应用，所以已应用的绑定将被同名的新绑定所覆盖。</span><span class="sxs-lookup"><span data-stu-id="0a738-183">As bindings are applied during the import process, bindings that have already been applied are overwritten by new bindings that have the same name.</span></span> <span data-ttu-id="0a738-184">换言之，将应用的具有特定名称的最后一个绑定生效。</span><span class="sxs-lookup"><span data-stu-id="0a738-184">In other words, the last binding of a particular name to be applied takes effect.</span></span>  
  
 <span data-ttu-id="0a738-185">例如，如果某个现有应用程序包括一个名为 SendPort1 的发送端口，并且应用的绑定文件描述的是同名的发送端口，那么该绑定文件中的设置将覆盖 SendPort1 的现有设置。</span><span class="sxs-lookup"><span data-stu-id="0a738-185">For example, if an existing application includes a send port named SendPort1, and a binding file is applied that describes a send port with the same name, the settings in the binding file will overwrite the existing settings for SendPort1.</span></span> <span data-ttu-id="0a738-186">又如，如果某个现有应用程序包括一个名为 ErrorHandling.ErrorHandler.ResubmitLogic 的业务流程，并且绑定文件描述了同名的业务流程，那么该绑定文件中的绑定将覆盖该业务流程中的所有现有绑定。</span><span class="sxs-lookup"><span data-stu-id="0a738-186">If an existing application includes an orchestration named ErrorHandling.ErrorHandler.ResubmitLogic, for example, and a binding file describes an orchestration having the same name, all of the existing bindings for the orchestration will be written with the bindings in the binding file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a738-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a738-187">See Also</span></span>  
 [<span data-ttu-id="0a738-188">了解 BizTalk 应用程序部署和管理</span><span class="sxs-lookup"><span data-stu-id="0a738-188">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)