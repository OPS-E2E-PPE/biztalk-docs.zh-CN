---
title: "如何导出绑定到绑定文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3734ae6d-b790-40f2-8403-d7c7fdbe381b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d1d39bfa1bfd4cc837a77586d6c462c6b7d7f06
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-export-bindings-to-a-binding-file"></a><span data-ttu-id="9c70e-102">如何导出绑定到绑定文件</span><span class="sxs-lookup"><span data-stu-id="9c70e-102">How to Export Bindings to a Binding File</span></span>
<span data-ttu-id="9c70e-103">你可以导出到使用绑定文件的另一个现有 BizTalk 应用程序的 BizTalk 应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="9c70e-103">You can export the bindings of a BizTalk application into another existing BizTalk application using a binding file.</span></span> <span data-ttu-id="9c70e-104">你还可以导出组中的所有绑定或程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="9c70e-104">You can also export all the bindings in a group or the binding for an assembly.</span></span> <span data-ttu-id="9c70e-105">随后，你可以导入的应用程序或组的这些绑定。</span><span class="sxs-lookup"><span data-stu-id="9c70e-105">Subsequently, you can import those bindings into either an application or group.</span></span>  
  
 <span data-ttu-id="9c70e-106">绑定文件是一个 XML 文件，描述 BizTalk 管理数据库和它们之间的关系中的项目。</span><span class="sxs-lookup"><span data-stu-id="9c70e-106">A binding file is an XML file that describes the artifacts in the BizTalk Management database and their relationships.</span></span> <span data-ttu-id="9c70e-107">它包含每个 BizTalk Server 业务流程、 管道、 映射或 BizTalk 程序集、 应用程序或组的作用域中的架构的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="9c70e-107">It contains binding information for each BizTalk Server orchestration, pipeline, map, or schema in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="9c70e-108">它包含每个发送端口的配置设置、 发送端口组、 接收端口、 接收位置，和方。</span><span class="sxs-lookup"><span data-stu-id="9c70e-108">It contains the configuration settings for each send port, send port group, receive port, receive location, and party.</span></span> <span data-ttu-id="9c70e-109">它还介绍每个业务流程绑定到的主机以及其信任级别。</span><span class="sxs-lookup"><span data-stu-id="9c70e-109">It also describes which host each orchestration is bound to and its trust level.</span></span>  
  
## <a name="why-to-export-to-a-binding-file"></a><span data-ttu-id="9c70e-110">为什么要将导出到绑定文件</span><span class="sxs-lookup"><span data-stu-id="9c70e-110">Why to Export to a Binding File</span></span>  
 <span data-ttu-id="9c70e-111">绑定文件可以部署在下列情况中通过加速无需手动配置绑定：</span><span class="sxs-lookup"><span data-stu-id="9c70e-111">Binding files can speed deployment in the following scenarios by avoiding the need to manually configure bindings:</span></span>  
  
-   <span data-ttu-id="9c70e-112">**将应用程序从一种部署环境移到另一个**</span><span class="sxs-lookup"><span data-stu-id="9c70e-112">**Moving an application from one deployment environment to another**</span></span>  
  
     <span data-ttu-id="9c70e-113">使用绑定文件可以通过避免需要手动配置绑定对于不同的部署环境，如从开发环境到测试环境的速度部署。</span><span class="sxs-lookup"><span data-stu-id="9c70e-113">Using a binding file can speed deployment by avoiding the need to manually configure bindings for different deployment environments, such as from a development environment to a test environment.</span></span>  
  
-   <span data-ttu-id="9c70e-114">**更新程序集**</span><span class="sxs-lookup"><span data-stu-id="9c70e-114">**Updating an assembly**</span></span>  
  
     <span data-ttu-id="9c70e-115">绑定文件可用于自动将应用或重新应用到的程序集更新后的程序集绑定。</span><span class="sxs-lookup"><span data-stu-id="9c70e-115">You can use a binding file to automatically apply or reapply the bindings to an assembly after an update of the assembly.</span></span>  
  
-   <span data-ttu-id="9c70e-116">**将程序集部署到多个 BizTalk 组**</span><span class="sxs-lookup"><span data-stu-id="9c70e-116">**Deploying an assembly to multiple BizTalk groups**</span></span>  
  
     <span data-ttu-id="9c70e-117">你可以避免需要单独配置为使用绑定文件部署到多个 BizTalk 组程序集绑定。</span><span class="sxs-lookup"><span data-stu-id="9c70e-117">You can avoid the need to separately configure the bindings for an assembly deployed into multiple BizTalk groups by using a binding file.</span></span>  
  
 <span data-ttu-id="9c70e-118">使用绑定文件使您可以灵活地将绑定应用于应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c70e-118">Using a binding file gives you flexibility in applying bindings to an application.</span></span> <span data-ttu-id="9c70e-119">如果导出为.msi 文件的应用程序，你仅可指定将.msi 文件导出的所有应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="9c70e-119">When you export an application to an .msi file, you can only specify that all of the bindings for the application will be exported to the .msi file.</span></span> <span data-ttu-id="9c70e-120">使用绑定文件可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9c70e-120">With binding files you can do the following:</span></span>  
  
-   <span data-ttu-id="9c70e-121">从当前应用程序的所有绑定、 从当前的组中，所有绑定或仅单个程序集的绑定将其导出到绑定文件。</span><span class="sxs-lookup"><span data-stu-id="9c70e-121">Export to a binding file all bindings from the current application, all bindings from the current group, or only the bindings for a single assembly.</span></span> <span data-ttu-id="9c70e-122">（你执行操作，通过管理控制台中的应用程序中用于导出绑定命令。）</span><span class="sxs-lookup"><span data-stu-id="9c70e-122">(You do so by using the Export Bindings command for an application in the Administration console.)</span></span>  
  
-   <span data-ttu-id="9c70e-123">以便立即应用自己的绑定或绑定会应用到另一组导入应用程序时，你可以将绑定文件添加到 （使用添加资源命令） 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c70e-123">You can add a binding file to an application (using the Add Resources command) so that its bindings are applied immediately or so the bindings are applied when the application is imported into another group.</span></span>  
  
-   <span data-ttu-id="9c70e-124">你可以将多个绑定文件添加到应用程序 （使用添加资源命令），并指定每个目标部署环境。</span><span class="sxs-lookup"><span data-stu-id="9c70e-124">You can add multiple binding files to an application (using the Add Resources command) and specify a target deployment environment for each one.</span></span> <span data-ttu-id="9c70e-125">这使您要用于多个部署环境的一个部署包。</span><span class="sxs-lookup"><span data-stu-id="9c70e-125">This enables you to use a single deployment package for multiple deployment environments.</span></span> <span data-ttu-id="9c70e-126">当你导入应用程序时，你可以选择要应用的绑定。</span><span class="sxs-lookup"><span data-stu-id="9c70e-126">When you import the application, you can select which bindings to apply.</span></span>  
  
-   <span data-ttu-id="9c70e-127">可以将单独绑定文件导出为应用程序中的多个程序集。</span><span class="sxs-lookup"><span data-stu-id="9c70e-127">You can export separate binding files for multiple assemblies in an application.</span></span>  
  
-   <span data-ttu-id="9c70e-128">您可以在生成绑定文件后对其进行编辑，以更改其中的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="9c70e-128">You can edit binding files after you generate them to change their binding information.</span></span>  
  
## <a name="how-to-export-to-a-binding-file"></a><span data-ttu-id="9c70e-129">如何将导出到绑定文件</span><span class="sxs-lookup"><span data-stu-id="9c70e-129">How to Export to a Binding File</span></span>  
 <span data-ttu-id="9c70e-130">通过在 BizTalk Server 管理控制台中，执行应用程序的导出绑定命令或命令行上使用 BTSTask ExportBindings 命令导出到绑定文件的应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="9c70e-130">You export the bindings of an application to a binding file by executing the Export Bindings command for the application in the BizTalk Server Administration console, or by using the BTSTask ExportBindings command on the command line.</span></span>  
  
 <span data-ttu-id="9c70e-131">出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。</span><span class="sxs-lookup"><span data-stu-id="9c70e-131">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="9c70e-132">在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="9c70e-132">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="9c70e-133">您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。</span><span class="sxs-lookup"><span data-stu-id="9c70e-133">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span>  
  
 <span data-ttu-id="9c70e-134">绑定文件中的信息将取代现有的配置信息。</span><span class="sxs-lookup"><span data-stu-id="9c70e-134">Information in a binding file supersedes existing configuration information.</span></span> <span data-ttu-id="9c70e-135">如果绑定文件中项目的名称与现有配置中项目的名称相匹配，则当您导入绑定文件时绑定文件中的项目将更新现有配置中的项目。</span><span class="sxs-lookup"><span data-stu-id="9c70e-135">If the name of an artifact in a binding file matches the name of an artifact in your existing configuration, the artifact in the binding file will update the artifact in your existing configuration when you import the binding file.</span></span>  
  
 <span data-ttu-id="9c70e-136">有关主机和信任级别绑定文件中的存储方式的信息，绑定文件中的主机和信任级别匹配主机和信任级别在应用程序和在其中应用绑定的顺序，请参阅[绑定文件和应用程序部署](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)。</span><span class="sxs-lookup"><span data-stu-id="9c70e-136">For information about how hosts and trust levels are stored in binding files, how host and trust levels in a binding file are matched to hosts and trust levels in the application, and the order in which bindings are applied, see [Binding Files and Application Deployment](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).</span></span> <span data-ttu-id="9c70e-137">有关如何导出 BizTalk 应用程序的绑定的说明，请参阅[如何导出 BizTalk 应用程序的绑定](http://go.microsoft.com/fwlink/?LinkId=155009)(http://go.microsoft.com/fwlink/?LinkId=155009)。</span><span class="sxs-lookup"><span data-stu-id="9c70e-137">For instructions on how to export bindings for a BizTalk application, see [How to Export Bindings for a BizTalk Application](http://go.microsoft.com/fwlink/?LinkId=155009) (http://go.microsoft.com/fwlink/?LinkId=155009).</span></span>