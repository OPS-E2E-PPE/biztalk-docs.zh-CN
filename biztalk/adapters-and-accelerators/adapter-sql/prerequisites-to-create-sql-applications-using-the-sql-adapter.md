---
title: "要创建 SQL 应用程序使用的 SQL 适配器系统必备组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb3a8963-88a8-4db0-a740-eb54b041931c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b16480a98a3e4974cb8f71641e7e8628ed549e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="prerequisites-to-create-sql-applications-using-the-sql-adapter"></a><span data-ttu-id="4d2ff-102">创建 SQL 应用程序使用的 SQL 适配器的先决条件</span><span class="sxs-lookup"><span data-stu-id="4d2ff-102">Prerequisites to create SQL applications using the SQL adapter</span></span>
<span data-ttu-id="4d2ff-103">在开发使用的 BizTalk 应用程序之前必须执行什么[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-103">What you must do before developing BizTalk applications using the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)].</span></span> <span data-ttu-id="4d2ff-104">此主题还列出一些用于开发 BizTalk 应用程序的 BizTalk Server 工具。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-104">The topic also lists some BizTalk Server tools that are used to develop BizTalk applications.</span></span>  

## <a name="create-a-strong-named-key-file"></a><span data-ttu-id="4d2ff-105">创建具有强名称密钥文件</span><span class="sxs-lookup"><span data-stu-id="4d2ff-105">Create a strong-named key file</span></span>
<span data-ttu-id="4d2ff-106">你必须创建一个强名称密钥文件，以生成在 Microsoft 中的项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="4d2ff-107">强名称的项目的标识组成 — 其简单文本名称、 版本号和区域性信息 （如果有的话）-加上一个公钥和数字签名。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-107">A strong name consists of the project's identity—its simple text name, version number, and culture information (if provided)—plus a public key and a digital signature.</span></span> <span data-ttu-id="4d2ff-108">强名称密钥文件包含公钥和私钥。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-108">The strong-name key file contains the public key and the private key.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4d2ff-109">创建强名称密钥文件是一次性的任务。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="4d2ff-110">相同的密钥可用于开发的所有 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-110">You can use the same key for all the BizTalk applications you develop.</span></span>  
  
### <a name="prerequisites"></a><span data-ttu-id="4d2ff-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="4d2ff-111">Prerequisites</span></span>  
 <span data-ttu-id="4d2ff-112">你必须具有 Microsoft[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]你想要创建强名称密钥在计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-112">You must have Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed on the computer where you want to create a strong-name key.</span></span>  
  
### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="4d2ff-113">创建强名称密钥文件</span><span class="sxs-lookup"><span data-stu-id="4d2ff-113">Create a strong-name key file</span></span>  
  
1.  <span data-ttu-id="4d2ff-114">打开 Visual Studio 开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-114">Open the developer command prompt for Visual Studio.</span></span>  
  
2.  <span data-ttu-id="4d2ff-115">在命令提示符处，导航到你想要创建的密钥文件的位置。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-115">At the command prompt, navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="4d2ff-116">例如，键入`cd C:\Sample`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-116">For example, type `cd C:\Sample`, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="4d2ff-117">在命令提示符下，键入 `sn -k <key file name>.snk`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-117">At the command prompt, type `sn -k <key file name>.snk`, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d2ff-118">你应该会收到一条消息，指出的密钥对已写入到强名称密钥文件的命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-118">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  
  
4.  <span data-ttu-id="4d2ff-119">在命令提示符下，键入 `exit`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-119">At the command prompt, type `exit`, and then press ENTER.</span></span>  
  
## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="4d2ff-120">了解 BizTalk Server 工具</span><span class="sxs-lookup"><span data-stu-id="4d2ff-120">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="4d2ff-121">有关如何使用主题[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]中[开发与 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)通过假设你有大量的工作知识编写[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-121">The topics on how to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in [Building blocks to develop BizTalk applications with the SQL adapter](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md) are written with the assumption that you have working knowledge of a number of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span> <span data-ttu-id="4d2ff-122">使用以下工具来开发 BizTalk 应用程序使用[!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4d2ff-122">You use the following tools to develop BizTalk applications using the [!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:</span></span>  
  
-   <span data-ttu-id="4d2ff-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d2ff-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="4d2ff-124">BizTalk 浏览器</span><span class="sxs-lookup"><span data-stu-id="4d2ff-124">BizTalk Explorer</span></span>  
  
-   <span data-ttu-id="4d2ff-125">业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="4d2ff-125">Orchestration designer</span></span>  
  
-   <span data-ttu-id="4d2ff-126">管道设计器</span><span class="sxs-lookup"><span data-stu-id="4d2ff-126">Pipeline designer</span></span>  
  
-   <span data-ttu-id="4d2ff-127">BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="4d2ff-127">BizTalk mapper</span></span>  
  
-   <span data-ttu-id="4d2ff-128">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="4d2ff-128">BizTalk Server Administration console</span></span>  
  
### <a name="prerequisites"></a><span data-ttu-id="4d2ff-129">先决条件</span><span class="sxs-lookup"><span data-stu-id="4d2ff-129">Prerequisites</span></span>  
 <span data-ttu-id="4d2ff-130">你必须安装 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以访问之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-130">You must install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  
  
### <a name="biztalk-server-tools"></a><span data-ttu-id="4d2ff-131">BizTalk Server 工具</span><span class="sxs-lookup"><span data-stu-id="4d2ff-131">BizTalk Server Tools</span></span>  
 <span data-ttu-id="4d2ff-132">下表包含中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]说明如何使用每个列出的工具的文档。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-132">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  
  
|<span data-ttu-id="4d2ff-133">工具</span><span class="sxs-lookup"><span data-stu-id="4d2ff-133">Tool</span></span>|<span data-ttu-id="4d2ff-134">中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]核心文档</span><span class="sxs-lookup"><span data-stu-id="4d2ff-134">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]|<span data-ttu-id="4d2ff-135">-   [使用 Visual Studio](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="4d2ff-135">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="4d2ff-136">-   [使用 BizTalk 项目](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="4d2ff-136">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="4d2ff-137">-   [部署到 BizTalk 应用程序从 Visual Studio BizTalk 程序集](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="4d2ff-137">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="4d2ff-138">了解更多有关 Visual Studio 解决方案、 项目和项在[解决方案和 Visual Studio 中的项目](https://msdn.microsoft.com/library/b142f8e7.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4d2ff-138">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span>|  
|<span data-ttu-id="4d2ff-139">业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="4d2ff-139">Orchestration Designer</span></span>|[<span data-ttu-id="4d2ff-140">创建使用业务流程设计器的业务流程</span><span class="sxs-lookup"><span data-stu-id="4d2ff-140">Creating orchestrations using orchestration designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)|  
|<span data-ttu-id="4d2ff-141">管道设计器</span><span class="sxs-lookup"><span data-stu-id="4d2ff-141">Pipeline Designer</span></span>| [<span data-ttu-id="4d2ff-142">创建管道使用管道设计器</span><span class="sxs-lookup"><span data-stu-id="4d2ff-142">Creating pipelines using pipeline designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)|  
|<span data-ttu-id="4d2ff-143">BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="4d2ff-143">BizTalk Mapper</span></span>| [<span data-ttu-id="4d2ff-144">创建映射使用 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="4d2ff-144">Creating maps using BizTalk mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)|  
|<span data-ttu-id="4d2ff-145">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="4d2ff-145">BizTalk Server Administration console</span></span>|[<span data-ttu-id="4d2ff-146">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="4d2ff-146">Using the BizTalk Server Administration console</span></span>](../../core/using-the-biztalk-server-administration-console.md)|  

## <a name="next"></a><span data-ttu-id="4d2ff-147">Next</span><span class="sxs-lookup"><span data-stu-id="4d2ff-147">Next</span></span>
[<span data-ttu-id="4d2ff-148">开发具有 SQL 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="4d2ff-148">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)