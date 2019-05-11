---
title: 如何将绑定导出到绑定文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3734ae6d-b790-40f2-8403-d7c7fdbe381b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1a9868fab993578d5b62c0606a68ffce4b2d3fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253489"
---
# <a name="how-to-export-bindings-to-a-binding-file"></a><span data-ttu-id="70706-102">如何将绑定导出到绑定文件</span><span class="sxs-lookup"><span data-stu-id="70706-102">How to Export Bindings to a Binding File</span></span>
<span data-ttu-id="70706-103">您可以导出到使用的绑定文件的另一个现有 BizTalk 应用程序的 BizTalk 应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="70706-103">You can export the bindings of a BizTalk application into another existing BizTalk application using a binding file.</span></span> <span data-ttu-id="70706-104">此外可以导出一个组中的所有绑定或程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="70706-104">You can also export all the bindings in a group or the binding for an assembly.</span></span> <span data-ttu-id="70706-105">随后，您可以导入的应用程序或组的这些绑定。</span><span class="sxs-lookup"><span data-stu-id="70706-105">Subsequently, you can import those bindings into either an application or group.</span></span>  
  
 <span data-ttu-id="70706-106">绑定文件是一个 XML 文件，描述 BizTalk 管理数据库和它们之间的关系中的项目。</span><span class="sxs-lookup"><span data-stu-id="70706-106">A binding file is an XML file that describes the artifacts in the BizTalk Management database and their relationships.</span></span> <span data-ttu-id="70706-107">它包含每个 BizTalk Server 业务流程、 管道、 映射或架构的 BizTalk 程序集、 应用程序或组作用域中的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="70706-107">It contains binding information for each BizTalk Server orchestration, pipeline, map, or schema in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="70706-108">它包含每个发送端口的配置设置、 发送端口组、 接收端口、 接收位置，并参与方。</span><span class="sxs-lookup"><span data-stu-id="70706-108">It contains the configuration settings for each send port, send port group, receive port, receive location, and party.</span></span> <span data-ttu-id="70706-109">它还介绍了每个业务流程绑定到的主机和信任级别。</span><span class="sxs-lookup"><span data-stu-id="70706-109">It also describes which host each orchestration is bound to and its trust level.</span></span>  
  
## <a name="why-to-export-to-a-binding-file"></a><span data-ttu-id="70706-110">为何要将导出到绑定文件</span><span class="sxs-lookup"><span data-stu-id="70706-110">Why to Export to a Binding File</span></span>  
 <span data-ttu-id="70706-111">绑定文件可以加速部署在以下情况下通过无需手动配置绑定：</span><span class="sxs-lookup"><span data-stu-id="70706-111">Binding files can speed deployment in the following scenarios by avoiding the need to manually configure bindings:</span></span>  
  
- <span data-ttu-id="70706-112">**在一个部署环境之间移动应用程序**</span><span class="sxs-lookup"><span data-stu-id="70706-112">**Moving an application from one deployment environment to another**</span></span>  
  
   <span data-ttu-id="70706-113">使用绑定文件可以通过无需手动配置绑定对于不同的部署环境，如从开发环境到测试环境的速度部署。</span><span class="sxs-lookup"><span data-stu-id="70706-113">Using a binding file can speed deployment by avoiding the need to manually configure bindings for different deployment environments, such as from a development environment to a test environment.</span></span>  
  
- <span data-ttu-id="70706-114">**更新的程序集**</span><span class="sxs-lookup"><span data-stu-id="70706-114">**Updating an assembly**</span></span>  
  
   <span data-ttu-id="70706-115">绑定文件可用于自动应用或重新应用到的程序集的更新后的程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="70706-115">You can use a binding file to automatically apply or reapply the bindings to an assembly after an update of the assembly.</span></span>  
  
- <span data-ttu-id="70706-116">**将程序集部署到多个 BizTalk 组**</span><span class="sxs-lookup"><span data-stu-id="70706-116">**Deploying an assembly to multiple BizTalk groups**</span></span>  
  
   <span data-ttu-id="70706-117">你可以无需单独配置使用绑定文件部署到多个 BizTalk 组的程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="70706-117">You can avoid the need to separately configure the bindings for an assembly deployed into multiple BizTalk groups by using a binding file.</span></span>  
  
  <span data-ttu-id="70706-118">使用绑定文件使您可以灵活地将绑定应用到应用程序。</span><span class="sxs-lookup"><span data-stu-id="70706-118">Using a binding file gives you flexibility in applying bindings to an application.</span></span> <span data-ttu-id="70706-119">导出到.msi 文件的应用程序时，您可以只指定，所有应用程序的绑定将导出到.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="70706-119">When you export an application to an .msi file, you can only specify that all of the bindings for the application will be exported to the .msi file.</span></span> <span data-ttu-id="70706-120">使用绑定文件可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="70706-120">With binding files you can do the following:</span></span>  
  
- <span data-ttu-id="70706-121">当前应用程序中的所有绑定、 当前组中的所有绑定或仅单个程序集的绑定将其导出到绑定文件。</span><span class="sxs-lookup"><span data-stu-id="70706-121">Export to a binding file all bindings from the current application, all bindings from the current group, or only the bindings for a single assembly.</span></span> <span data-ttu-id="70706-122">（仍使用此管理控制台中为应用程序中使用导出绑定命令。）</span><span class="sxs-lookup"><span data-stu-id="70706-122">(You do so by using the Export Bindings command for an application in the Administration console.)</span></span>  
  
- <span data-ttu-id="70706-123">可以向应用程序 （使用添加资源命令） 添加绑定文件，以便立即应用其绑定或使应用程序导入到另一个组时应用绑定。</span><span class="sxs-lookup"><span data-stu-id="70706-123">You can add a binding file to an application (using the Add Resources command) so that its bindings are applied immediately or so the bindings are applied when the application is imported into another group.</span></span>  
  
- <span data-ttu-id="70706-124">可以将多个绑定文件添加到应用程序 （使用添加资源命令），并指定每个目标部署环境。</span><span class="sxs-lookup"><span data-stu-id="70706-124">You can add multiple binding files to an application (using the Add Resources command) and specify a target deployment environment for each one.</span></span> <span data-ttu-id="70706-125">这使您要用于多个部署环境的单个部署包。</span><span class="sxs-lookup"><span data-stu-id="70706-125">This enables you to use a single deployment package for multiple deployment environments.</span></span> <span data-ttu-id="70706-126">导入应用程序时，可以选择要应用的绑定。</span><span class="sxs-lookup"><span data-stu-id="70706-126">When you import the application, you can select which bindings to apply.</span></span>  
  
- <span data-ttu-id="70706-127">您可以单独的绑定文件导出的应用程序中的多个程序集。</span><span class="sxs-lookup"><span data-stu-id="70706-127">You can export separate binding files for multiple assemblies in an application.</span></span>  
  
- <span data-ttu-id="70706-128">生成对其进行更改其绑定信息后，可以编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="70706-128">You can edit binding files after you generate them to change their binding information.</span></span>  
  
## <a name="how-to-export-to-a-binding-file"></a><span data-ttu-id="70706-129">如何将导出到绑定文件</span><span class="sxs-lookup"><span data-stu-id="70706-129">How to Export to a Binding File</span></span>  
 <span data-ttu-id="70706-130">通过在 BizTalk Server 管理控制台中，执行应用程序的导出绑定命令或通过在命令行上使用 BTSTask ExportBindings 命令导出到绑定文件的应用程序的绑定。</span><span class="sxs-lookup"><span data-stu-id="70706-130">You export the bindings of an application to a binding file by executing the Export Bindings command for the application in the BizTalk Server Administration console, or by using the BTSTask ExportBindings command on the command line.</span></span>  
  
 <span data-ttu-id="70706-131">出于安全原因，在导出绑定文件时 BizTalk Server 将从文件删除绑定密码。</span><span class="sxs-lookup"><span data-stu-id="70706-131">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="70706-132">导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。</span><span class="sxs-lookup"><span data-stu-id="70706-132">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="70706-133">发送端口在 BizTalk Server 管理控制台的传输属性对话框中配置密码，或接收位置。</span><span class="sxs-lookup"><span data-stu-id="70706-133">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span>  
  
 <span data-ttu-id="70706-134">绑定文件中的信息将取代现有的配置信息。</span><span class="sxs-lookup"><span data-stu-id="70706-134">Information in a binding file supersedes existing configuration information.</span></span> <span data-ttu-id="70706-135">如果绑定文件中项目的名称与现有配置中的项目的名称相匹配，绑定文件中的项目的项目将更新现有配置中导入绑定文件时。</span><span class="sxs-lookup"><span data-stu-id="70706-135">If the name of an artifact in a binding file matches the name of an artifact in your existing configuration, the artifact in the binding file will update the artifact in your existing configuration when you import the binding file.</span></span>  
  
 <span data-ttu-id="70706-136">有关如何将主机和信任级别存储在绑定文件的内容，如何将绑定文件中的主机和信任级别匹配的主机和信任级别中应用程序，以及应用绑定的顺序，请参阅[绑定文件和应用程序部署](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)。</span><span class="sxs-lookup"><span data-stu-id="70706-136">For information about how hosts and trust levels are stored in binding files, how host and trust levels in a binding file are matched to hosts and trust levels in the application, and the order in which bindings are applied, see [Binding Files and Application Deployment](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).</span></span> <span data-ttu-id="70706-137">有关如何导出 BizTalk 应用程序的绑定的说明，请参阅[如何导出 BizTalk 应用程序的绑定](http://go.microsoft.com/fwlink/?LinkId=155009)(http://go.microsoft.com/fwlink/?LinkId=155009)。</span><span class="sxs-lookup"><span data-stu-id="70706-137">For instructions on how to export bindings for a BizTalk application, see [How to Export Bindings for a BizTalk Application](http://go.microsoft.com/fwlink/?LinkId=155009) (http://go.microsoft.com/fwlink/?LinkId=155009).</span></span>