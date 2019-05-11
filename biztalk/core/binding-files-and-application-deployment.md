---
title: 绑定文件和应用程序部署 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53037b44001d22f3f1f2b1463cd2f6d057d41355
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358366"
---
# <a name="binding-files-and-application-deployment"></a><span data-ttu-id="954a6-102">绑定文件和应用程序部署</span><span class="sxs-lookup"><span data-stu-id="954a6-102">Binding Files and Application Deployment</span></span>
<span data-ttu-id="954a6-103">本主题提供有关使用绑定文件简化 BizTalk 程序集和应用程序部署的概述信息。</span><span class="sxs-lookup"><span data-stu-id="954a6-103">This topic provides overview information about using binding files to make BizTalk assembly and application deployment easier.</span></span> <span data-ttu-id="954a6-104">您可能会发现绑定文件避免了手动配置绑定在以下方案中加快部署速度：</span><span class="sxs-lookup"><span data-stu-id="954a6-104">You may find that binding files speed deployment in the following scenarios by avoiding the need to manually configure bindings:</span></span>  
  
-   <span data-ttu-id="954a6-105">在一个部署环境之间移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="954a6-105">Moving an application from one deployment environment to another.</span></span>  
  
-   <span data-ttu-id="954a6-106">更新的程序集。</span><span class="sxs-lookup"><span data-stu-id="954a6-106">Updating an assembly.</span></span>  
  
-   <span data-ttu-id="954a6-107">将程序集部署到多个 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="954a6-107">Deploying an assembly to multiple BizTalk groups.</span></span>  
  
## <a name="what-is-a-binding"></a><span data-ttu-id="954a6-108">什么是绑定？</span><span class="sxs-lookup"><span data-stu-id="954a6-108">What is a binding?</span></span>  
 <span data-ttu-id="954a6-109">一个绑定和之间创建映射逻辑终结点，如业务流程端口或角色链接，物理终结点，如发送和接收端口或参与方。</span><span class="sxs-lookup"><span data-stu-id="954a6-109">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="954a6-110">这样，BizTalk 业务解决方案的不同组件之间的通信。</span><span class="sxs-lookup"><span data-stu-id="954a6-110">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="954a6-111">可以使用 BizTalk Server 管理控制台来创建绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-111">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="954a6-112">什么是绑定文件？</span><span class="sxs-lookup"><span data-stu-id="954a6-112">What is a binding file?</span></span>  
 <span data-ttu-id="954a6-113">绑定文件是一个.xml 文件，其中每个 BizTalk 业务流程、 管道、 映射或架构的 BizTalk 程序集、 应用程序或组作用域中的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="954a6-113">A binding file is an .xml file that contains binding information for each BizTalk orchestration, pipeline, map, or schema in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="954a6-114">绑定文件描述每个业务流程绑定到哪些主机和信任级别，以及每个发送端口设置、 发送端口组、 接收端口、 接收位置，且已配置的参与方。</span><span class="sxs-lookup"><span data-stu-id="954a6-114">The binding file describes what host each orchestration is bound to and its trust level as well as the settings for each send port, send port group, receive port, receive location, and party that has been configured.</span></span> <span data-ttu-id="954a6-115">您可以生成绑定文件，并将它们包含的绑定应用到的程序集、 程序或组，以避免在不同的部署环境中手动配置绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-115">You can generate binding files and then apply the bindings they contain to an assembly, application, or group to avoid needing to manually configure bindings in different deployment environments.</span></span>  
  
## <a name="why-use-binding-files"></a><span data-ttu-id="954a6-116">为什么使用绑定文件？</span><span class="sxs-lookup"><span data-stu-id="954a6-116">Why use binding files?</span></span>  
 <span data-ttu-id="954a6-117">您可能想要使用以下方案中的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="954a6-117">You may want to use binding files in the following scenarios.</span></span>  
  
### <a name="moving-from-one-environment-to-another"></a><span data-ttu-id="954a6-118">将其从一个环境移到另一个</span><span class="sxs-lookup"><span data-stu-id="954a6-118">Moving from one environment to another</span></span>  
 <span data-ttu-id="954a6-119">绑定文件可用于轻松地将应用程序在不同部署环境到另一个，如从开发环境到测试环境。</span><span class="sxs-lookup"><span data-stu-id="954a6-119">You can use binding files to make it easier to move an application from one deployment environment to another, such as from a development environment to a test environment.</span></span> <span data-ttu-id="954a6-120">这是因为绑定通常必须重新配置为不同的部署环境，但通过使用绑定文件，可以避免重复执行此手动配置步骤。</span><span class="sxs-lookup"><span data-stu-id="954a6-120">This is because bindings often must be reconfigured for different deployment environments, but by using binding files, you can avoid repeatedly performing this manual configuration step.</span></span>  
  
 <span data-ttu-id="954a6-121">可以执行此操作的一种方法是创建要部署到新环境的应用程序时，选择从中绑定的库。</span><span class="sxs-lookup"><span data-stu-id="954a6-121">One way you can do this is to create a library of bindings from which to select when deploying the application into a new environment.</span></span> <span data-ttu-id="954a6-122">例如，您可以为你的测试环境，另一个用于生产环境中创建绑定文件，然后将这两个添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="954a6-122">For example, you can create a binding file for your test environment and another one for your production environment and then add them both to the application.</span></span> <span data-ttu-id="954a6-123">当应用程序导入测试环境时，可以选择一个选项来应用测试绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-123">When you import the application into the test environment, you can select an option to apply the test bindings.</span></span> <span data-ttu-id="954a6-124">同样，当应用程序导入生产环境时，可以选择一个选项来应用生产绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-124">Likewise, when you import the application into the production environment, you can select an option to apply the production bindings.</span></span> <span data-ttu-id="954a6-125">这就无需重新配置为不同环境手动绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-125">This avoids the need to reconfigure bindings manually for different environments.</span></span> <span data-ttu-id="954a6-126">另一种方法是将应用程序导入其中后，导入当前环境的已创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-126">Another way is to import bindings that you have created for the current environment after importing the application into it.</span></span> <span data-ttu-id="954a6-127">这会自动应用绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-127">This automatically applies the bindings.</span></span>  
  
### <a name="updating-an-assembly"></a><span data-ttu-id="954a6-128">更新的程序集</span><span class="sxs-lookup"><span data-stu-id="954a6-128">Updating an assembly</span></span>  
 <span data-ttu-id="954a6-129">更新应用程序中的程序集时，其绑定通常被覆盖，否则该程序集可能未绑定，强制您手动重新配置绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-129">When you update an assembly in an application, its bindings are often overwritten or else the assembly may not be bound at all, forcing you to manually reconfigure bindings.</span></span> <span data-ttu-id="954a6-130">若要避免此问题，可以按如下所示使用绑定文件：</span><span class="sxs-lookup"><span data-stu-id="954a6-130">To avoid this, you can use a binding file as follows:</span></span>  
  
-   <span data-ttu-id="954a6-131">**正在更新同一版本的程序集。**</span><span class="sxs-lookup"><span data-stu-id="954a6-131">**Updating the same version of an assembly.**</span></span> <span data-ttu-id="954a6-132">如果程序集具有早期绑定端口或动态端口，并更改 BizTalk Server 管理控制台中的端口配置，设置将会丢失时使用的程序集具有相同的版本号更新程序集。</span><span class="sxs-lookup"><span data-stu-id="954a6-132">If the assembly has early bound ports or dynamic ports, and you changed the port configuration in the BizTalk Server Administration console, the settings will be lost when you update the assembly with an assembly having the same version number.</span></span> <span data-ttu-id="954a6-133">可以为要更新的程序集导出绑定文件。</span><span class="sxs-lookup"><span data-stu-id="954a6-133">You can export a binding file for the assembly you are going to update.</span></span> <span data-ttu-id="954a6-134">在更新程序集之后可以导入应用程序的程序集，然后导入其绑定文件以重新应用以前的绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-134">After updating the assembly you can import the assembly into the application and then import its binding file to reapply the previous bindings.</span></span>  
  
-   <span data-ttu-id="954a6-135">**使用更新的版本更新的程序集。**</span><span class="sxs-lookup"><span data-stu-id="954a6-135">**Updating an assembly with a newer version.**</span></span> <span data-ttu-id="954a6-136">可以为要更新，然后编辑它以反映新的程序集版本的程序集导出绑定文件。</span><span class="sxs-lookup"><span data-stu-id="954a6-136">You can export a binding file for the assembly that you are going to update and then edit it to reflect the new assembly version.</span></span> <span data-ttu-id="954a6-137">新的程序集版本导入应用程序后，您可以将绑定文件导入要应用这些绑定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="954a6-137">After you import the new assembly version into the application, you can import the binding file into the application to apply the bindings.</span></span> <span data-ttu-id="954a6-138">有关编辑绑定文件的说明，请参阅[自定义绑定文件](../core/customizing-binding-files.md)。</span><span class="sxs-lookup"><span data-stu-id="954a6-138">For instructions on editing a binding file, see [Customizing Binding Files](../core/customizing-binding-files.md).</span></span>  
  
### <a name="deploying-an-assembly-to-multiple-biztalk-groups"></a><span data-ttu-id="954a6-139">将程序集部署到多个 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="954a6-139">Deploying an assembly to multiple BizTalk groups</span></span>  
 <span data-ttu-id="954a6-140">在部署到多个 BizTalk 组程序集时，可以传输以及该程序集的程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-140">When you deploy an assembly into multiple BizTalk groups, you can transport the bindings for the assembly along with the assembly.</span></span> <span data-ttu-id="954a6-141">这就无需单独配置每个组中的程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-141">This avoids the need to separately configure the bindings for the assembly in each group.</span></span> <span data-ttu-id="954a6-142">您可以按如下所示执行此操作：</span><span class="sxs-lookup"><span data-stu-id="954a6-142">You can do this as follows:</span></span>  
  
1.  <span data-ttu-id="954a6-143">为你想要部署导出的程序集的绑定的程序集创建绑定文件。</span><span class="sxs-lookup"><span data-stu-id="954a6-143">Create a binding file for the assembly that you want to deploy by exporting the assembly's bindings.</span></span>  
  
2.  <span data-ttu-id="954a6-144">将程序集和其绑定文件添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="954a6-144">Add the assembly and its binding file to an application.</span></span> <span data-ttu-id="954a6-145">如果要部署独立于其他项目的程序集，该应用程序可以包含仅将程序集和绑定文件。</span><span class="sxs-lookup"><span data-stu-id="954a6-145">If you are deploying the assembly separately from other artifacts, the application can contain only the assembly and the binding file.</span></span>  
  
3.  <span data-ttu-id="954a6-146">导出应用程序，务必选择一同导出绑定文件的.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="954a6-146">Export an .msi file for the application, being sure to select the binding file to export as well.</span></span>  
  
4.  <span data-ttu-id="954a6-147">应用程序.msi 文件导入 BizTalk 组和你想要将其部署的应用程序。</span><span class="sxs-lookup"><span data-stu-id="954a6-147">Import the application .msi file into the BizTalk groups and applications where you want to deploy it.</span></span> <span data-ttu-id="954a6-148">文件中的绑定会自动应用上导入程序集。</span><span class="sxs-lookup"><span data-stu-id="954a6-148">The bindings in the file are automatically applied to the assembly on import.</span></span>  
  
## <a name="how-can-i-generate-and-use-binding-files"></a><span data-ttu-id="954a6-149">如何生成和使用绑定文件？</span><span class="sxs-lookup"><span data-stu-id="954a6-149">How can I generate and use binding files?</span></span>  
 <span data-ttu-id="954a6-150">BizTalk 程序集、 应用程序或组，不会自动生成绑定文件，但可以生成绑定文件导出的绑定，如中所述[导出绑定](../core/exporting-bindings6.md)。</span><span class="sxs-lookup"><span data-stu-id="954a6-150">A binding file is not automatically generated for a BizTalk assembly, application, or group, but you can generate a binding file by exporting bindings, as described in [Exporting Bindings](../core/exporting-bindings6.md).</span></span> <span data-ttu-id="954a6-151">你可以然后导入绑定文件的应用程序或组，如中所述[如何将绑定导入到 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)并[如何将绑定导入到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)，它自动应用其中的绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-151">You can then import the binding file into an application or group, as described in [How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md) and [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md), which automatically applies its bindings.</span></span>  
  
 <span data-ttu-id="954a6-152">或者，向应用程序添加绑定文件，以便应用程序导入另一个组，而不是立即应用，如中所述应用其绑定[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md).</span><span class="sxs-lookup"><span data-stu-id="954a6-152">Alternatively, you can add the binding file to an application so that its bindings are applied when the application is imported into another group, rather than being applied immediately, as described in [How to Add a Binding File to an Application](../core/how-to-add-a-binding-file-to-an-application2.md).</span></span> <span data-ttu-id="954a6-153">使用最后一个方法，可以将多个绑定文件添加到应用程序，并选择性地指定为每个目标部署环境。</span><span class="sxs-lookup"><span data-stu-id="954a6-153">Using the last method, you can add multiple binding files to an application and optionally specify a target deployment environment for each one.</span></span> <span data-ttu-id="954a6-154">当您导入应用程序时，然后，可以选择要应用的绑定基于目标部署环境，如中所述[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="954a6-154">When you import the application, you can then select which bindings to apply, based on the target deployment environment, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span> <span data-ttu-id="954a6-155">使用最后一个方法，您可还导入单独的绑定文件不同的程序集在应用程序中。</span><span class="sxs-lookup"><span data-stu-id="954a6-155">Using the last method, you can also import separate binding files for the different assemblies in your application.</span></span>  
  
 <span data-ttu-id="954a6-156">生成对其进行更改其绑定信息后，可以编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="954a6-156">You can edit binding files after you generate them to change their binding information.</span></span> <span data-ttu-id="954a6-157">有关详细信息，请参阅[自定义绑定文件](../core/customizing-binding-files.md)。</span><span class="sxs-lookup"><span data-stu-id="954a6-157">For more information, see [Customizing Binding Files](../core/customizing-binding-files.md).</span></span>  
  
## <a name="how-are-bindings-applied"></a><span data-ttu-id="954a6-158">如何应用绑定？</span><span class="sxs-lookup"><span data-stu-id="954a6-158">How are bindings applied?</span></span>  
 <span data-ttu-id="954a6-159">当绑定文件导入应用程序，或者当应用程序导入到新的 BizTalk 组，则应用绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-159">Bindings are applied when a binding file is imported into an application, or when an application is imported into a new BizTalk group.</span></span> <span data-ttu-id="954a6-160">使用绑定文件时，务必了解项目将如何绑定到主机和应用绑定的顺序。</span><span class="sxs-lookup"><span data-stu-id="954a6-160">When using binding files, it is important to understand how artifacts are bound to hosts and in the order in which bindings are applied.</span></span>  
  
### <a name="binding-to-hosts"></a><span data-ttu-id="954a6-161">将绑定到主机</span><span class="sxs-lookup"><span data-stu-id="954a6-161">Binding to hosts</span></span>  
 <span data-ttu-id="954a6-162">导出绑定时单独或作为应用程序的一部分，主机和信任级别存储在绑定文件中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="954a6-162">When bindings are exported either separately or as part of an application, hosts and trust levels are stored in the binding file as follows:</span></span>  
  
- <span data-ttu-id="954a6-163">**发送端口。**</span><span class="sxs-lookup"><span data-stu-id="954a6-163">**Send Port.**</span></span> <span data-ttu-id="954a6-164">与发送处理程序关联的主机的信任级别。</span><span class="sxs-lookup"><span data-stu-id="954a6-164">Trust level of the host associated with the send handler.</span></span>  
  
- <span data-ttu-id="954a6-165">**接收位置。**</span><span class="sxs-lookup"><span data-stu-id="954a6-165">**Receive Location.**</span></span> <span data-ttu-id="954a6-166">与接收处理程序相关联的主机的信任级别。</span><span class="sxs-lookup"><span data-stu-id="954a6-166">Trust level of the host associated with the receive handler.</span></span>  
  
- <span data-ttu-id="954a6-167">**业务流程。**</span><span class="sxs-lookup"><span data-stu-id="954a6-167">**Orchestration.**</span></span> <span data-ttu-id="954a6-168">主机的信任级别。</span><span class="sxs-lookup"><span data-stu-id="954a6-168">Trust Level of the host.</span></span>  
  
  <span data-ttu-id="954a6-169">当要将绑定导入应用程序或应用程序从.msi 文件导入新的 BizTalk 组时，主机和绑定文件中的信任级别与匹配主机和在应用程序中的信任级别，如下所示：</span><span class="sxs-lookup"><span data-stu-id="954a6-169">When the bindings are imported into an application, or an application is imported from the .msi file into a new BizTalk group, hosts and trust levels in the binding files are matched to hosts and trust levels in the application, as follows:</span></span>  
  
- <span data-ttu-id="954a6-170">**发送端口。**</span><span class="sxs-lookup"><span data-stu-id="954a6-170">**Send Port.**</span></span> <span data-ttu-id="954a6-171">发送端口绑定到具有相同名称的发送处理程序并且绑定到具有相同信任级别为存储在绑定文件中的主机。</span><span class="sxs-lookup"><span data-stu-id="954a6-171">The send port is bound to a send handler of the same name and bound to a host with the same trust level as that stored in the binding file.</span></span>  
  
- <span data-ttu-id="954a6-172">**接收位置。**</span><span class="sxs-lookup"><span data-stu-id="954a6-172">**Receive Location.**</span></span> <span data-ttu-id="954a6-173">接收位置绑定到具有相同名称的接收处理程序并且绑定到具有相同信任级别为存储在绑定文件中的主机。</span><span class="sxs-lookup"><span data-stu-id="954a6-173">The receive location is bound to a receive handler of the same name and bound to a host with the same trust level as that stored in the binding file.</span></span>  
  
- <span data-ttu-id="954a6-174">**业务流程。**</span><span class="sxs-lookup"><span data-stu-id="954a6-174">**Orchestrations.**</span></span> <span data-ttu-id="954a6-175">业务流程绑定到绑定文件中的主机具有相同名称和信任级别和的中。</span><span class="sxs-lookup"><span data-stu-id="954a6-175">The orchestration is bound to a host with the same name and trust level and as that in the binding file.</span></span>  
  
### <a name="order-in-which-bindings-are-applied"></a><span data-ttu-id="954a6-176">绑定的应用顺序</span><span class="sxs-lookup"><span data-stu-id="954a6-176">Order in which bindings are applied</span></span>  
 <span data-ttu-id="954a6-177">导入应用程序时，绑定按以下顺序应用：</span><span class="sxs-lookup"><span data-stu-id="954a6-177">When you import an application, bindings are applied in the following order:</span></span>  
  
1. <span data-ttu-id="954a6-178">应用程序绑定由 BizTalk Server 生成的未显式添加到应用程序通过绑定文件，但已经显式选择导出到应用程序.msi 文件的用户。</span><span class="sxs-lookup"><span data-stu-id="954a6-178">Application bindings generated by BizTalk Server that were not explicitly added to the application via a binding file, but that were explicitly selected by the user for export into the application .msi file.</span></span>  
  
2. <span data-ttu-id="954a6-179">绑定的文件的已添加到应用程序，以及哪些没有指定目标部署环境中的绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-179">Bindings in binding files that have been added to the application, and which do not have a target deployment environment specified.</span></span> <span data-ttu-id="954a6-180">这些绑定可以按任何特定顺序应用。</span><span class="sxs-lookup"><span data-stu-id="954a6-180">These bindings are applied in no specific order.</span></span>  
  
3. <span data-ttu-id="954a6-181">导入绑定的文件的已添加到应用程序，并且具有所选应用程序的部署环境相匹配的相关联的目标部署环境中的绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-181">Bindings in binding files that have been added to the application, and which have an associated target deployment environment that matches the deployment environment selected for application import.</span></span> <span data-ttu-id="954a6-182">这些绑定可以按任何特定顺序应用。</span><span class="sxs-lookup"><span data-stu-id="954a6-182">These bindings are applied in no specific order.</span></span>  
  
   <span data-ttu-id="954a6-183">当导入过程中应用绑定时，已应用的绑定将覆盖具有相同名称的新绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-183">As bindings are applied during the import process, bindings that have already been applied are overwritten by new bindings that have the same name.</span></span> <span data-ttu-id="954a6-184">换而言之，具有特定名称的最后一个绑定，应用将生效。</span><span class="sxs-lookup"><span data-stu-id="954a6-184">In other words, the last binding of a particular name to be applied takes effect.</span></span>  
  
   <span data-ttu-id="954a6-185">例如，如果某个现有的应用程序包括一个名为 SendPort1 的发送端口和绑定文件将应用描述具有相同名称的发送端口，绑定文件中的设置将覆盖 SendPort1 的现有设置。</span><span class="sxs-lookup"><span data-stu-id="954a6-185">For example, if an existing application includes a send port named SendPort1, and a binding file is applied that describes a send port with the same name, the settings in the binding file will overwrite the existing settings for SendPort1.</span></span> <span data-ttu-id="954a6-186">如果现有应用程序包含名为 ErrorHandling.ErrorHandler.ResubmitLogic，例如，业务流程，绑定文件描述具有相同名称的业务流程，所有现有绑定业务流程将使用进行编写绑定文件中的绑定。</span><span class="sxs-lookup"><span data-stu-id="954a6-186">If an existing application includes an orchestration named ErrorHandling.ErrorHandler.ResubmitLogic, for example, and a binding file describes an orchestration having the same name, all of the existing bindings for the orchestration will be written with the bindings in the binding file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="954a6-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="954a6-187">See Also</span></span>  
 [<span data-ttu-id="954a6-188">了解 BizTalk 应用程序的部署和管理</span><span class="sxs-lookup"><span data-stu-id="954a6-188">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)