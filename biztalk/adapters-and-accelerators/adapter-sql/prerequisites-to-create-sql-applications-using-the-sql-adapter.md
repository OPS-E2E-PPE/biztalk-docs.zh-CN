---
title: 创建 SQL 应用程序使用 SQL 适配器的先决条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb3a8963-88a8-4db0-a740-eb54b041931c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9ef38dfaa603550c810dd7a3c5e114ecc3c028e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972214"
---
# <a name="prerequisites-to-create-sql-applications-using-the-sql-adapter"></a><span data-ttu-id="c9a68-102">创建 SQL 应用程序使用 SQL 适配器的先决条件</span><span class="sxs-lookup"><span data-stu-id="c9a68-102">Prerequisites to create SQL applications using the SQL adapter</span></span>
<span data-ttu-id="c9a68-103">在开发 BizTalk 应用程序使用之前必须做什么[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c9a68-103">What you must do before developing BizTalk applications using the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)].</span></span> <span data-ttu-id="c9a68-104">本主题还列出了一些 BizTalk Server 工具，用于开发 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c9a68-104">The topic also lists some BizTalk Server tools that are used to develop BizTalk applications.</span></span>  

## <a name="create-a-strong-named-key-file"></a><span data-ttu-id="c9a68-105">创建强名称密钥文件</span><span class="sxs-lookup"><span data-stu-id="c9a68-105">Create a strong-named key file</span></span>
<span data-ttu-id="c9a68-106">必须创建一个强名称密钥文件，若要在 Microsoft 中生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c9a68-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="c9a68-107">强名称包含项目的标识，其简单文本名称、 版本号和区域性信息 （如果提供），加上公钥和数字签名。</span><span class="sxs-lookup"><span data-stu-id="c9a68-107">A strong name consists of the project's identity—its simple text name, version number, and culture information (if provided)—plus a public key and a digital signature.</span></span> <span data-ttu-id="c9a68-108">强名称密钥文件包含公钥和私钥。</span><span class="sxs-lookup"><span data-stu-id="c9a68-108">The strong-name key file contains the public key and the private key.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="c9a68-109">创建强名称密钥文件是一次性任务。</span><span class="sxs-lookup"><span data-stu-id="c9a68-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="c9a68-110">为您开发的所有 BizTalk 应用程序，可以使用相同的密钥。</span><span class="sxs-lookup"><span data-stu-id="c9a68-110">You can use the same key for all the BizTalk applications you develop.</span></span>  

### <a name="prerequisites"></a><span data-ttu-id="c9a68-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="c9a68-111">Prerequisites</span></span>  
 <span data-ttu-id="c9a68-112">必须具有 Microsoft[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]想要创建一个强名称密钥的计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="c9a68-112">You must have Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed on the computer where you want to create a strong-name key.</span></span>  

### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="c9a68-113">创建强名称密钥文件</span><span class="sxs-lookup"><span data-stu-id="c9a68-113">Create a strong-name key file</span></span>  

1.  <span data-ttu-id="c9a68-114">打开 Visual Studio 开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="c9a68-114">Open the developer command prompt for Visual Studio.</span></span>  

2.  <span data-ttu-id="c9a68-115">在命令提示符处，导航到你想要创建的密钥文件的位置。</span><span class="sxs-lookup"><span data-stu-id="c9a68-115">At the command prompt, navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="c9a68-116">例如，键入`cd C:\Sample`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c9a68-116">For example, type `cd C:\Sample`, and then press ENTER.</span></span>  

3.  <span data-ttu-id="c9a68-117">在命令提示符下，键入 `sn -k <key file name>.snk`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="c9a68-117">At the command prompt, type `sn -k <key file name>.snk`, and then press ENTER.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="c9a68-118">应会收到一条消息表明密钥对已写入到强名称密钥文件的命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="c9a68-118">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  

4.  <span data-ttu-id="c9a68-119">在命令提示符下，键入 `exit`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="c9a68-119">At the command prompt, type `exit`, and then press ENTER.</span></span>  

## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="c9a68-120">了解 BizTalk Server 工具</span><span class="sxs-lookup"><span data-stu-id="c9a68-120">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="c9a68-121">有关如何使用主题[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]中[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)编写时会假定您具有大量的工作知识的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。</span><span class="sxs-lookup"><span data-stu-id="c9a68-121">The topics on how to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in [Building blocks to develop BizTalk applications with the SQL adapter](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md) are written with the assumption that you have working knowledge of a number of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span> <span data-ttu-id="c9a68-122">使用以下工具来开发 BizTalk 应用程序使用[!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c9a68-122">You use the following tools to develop BizTalk applications using the [!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:</span></span>  

- <span data-ttu-id="c9a68-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9a68-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 

- <span data-ttu-id="c9a68-124">BizTalk 浏览器</span><span class="sxs-lookup"><span data-stu-id="c9a68-124">BizTalk Explorer</span></span>  

- <span data-ttu-id="c9a68-125">业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="c9a68-125">Orchestration designer</span></span>  

- <span data-ttu-id="c9a68-126">管道设计器</span><span class="sxs-lookup"><span data-stu-id="c9a68-126">Pipeline designer</span></span>  

- <span data-ttu-id="c9a68-127">BizTalk 映射器</span><span class="sxs-lookup"><span data-stu-id="c9a68-127">BizTalk mapper</span></span>  

- <span data-ttu-id="c9a68-128">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="c9a68-128">BizTalk Server Administration console</span></span>  

### <a name="prerequisites"></a><span data-ttu-id="c9a68-129">必要條件</span><span class="sxs-lookup"><span data-stu-id="c9a68-129">Prerequisites</span></span>  
 <span data-ttu-id="c9a68-130">必须安装 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以访问之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。</span><span class="sxs-lookup"><span data-stu-id="c9a68-130">You must install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  

### <a name="biztalk-server-tools"></a><span data-ttu-id="c9a68-131">BizTalk Server 工具</span><span class="sxs-lookup"><span data-stu-id="c9a68-131">BizTalk Server Tools</span></span>  
 <span data-ttu-id="c9a68-132">下表包含本节中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]说明了如何使用每个列出的工具的文档。</span><span class="sxs-lookup"><span data-stu-id="c9a68-132">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  


|                                   <span data-ttu-id="c9a68-133">工具</span><span class="sxs-lookup"><span data-stu-id="c9a68-133">Tool</span></span>                                    |                                                                                                                                                                                              <span data-ttu-id="c9a68-134">本节中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]核心文档</span><span class="sxs-lookup"><span data-stu-id="c9a68-134">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>                                                                                                                                                                                               |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] | <span data-ttu-id="c9a68-135">-   [使用 Visual Studio](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="c9a68-135">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="c9a68-136">-   [使用 BizTalk 项目](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="c9a68-136">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="c9a68-137">-   [部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="c9a68-137">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="c9a68-138">了解更多有关 Visual Studio 解决方案、 项目和项在[解决方案和项目在 Visual Studio 中的](https://msdn.microsoft.com/library/b142f8e7.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c9a68-138">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span> |
|                          <span data-ttu-id="c9a68-139">业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="c9a68-139">Orchestration Designer</span></span>                           |                                                                                                                                                                                          [<span data-ttu-id="c9a68-140">创建业务流程使用业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="c9a68-140">Creating orchestrations using orchestration designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)                                                                                                                                                                                           |
|                             <span data-ttu-id="c9a68-141">管道设计器</span><span class="sxs-lookup"><span data-stu-id="c9a68-141">Pipeline Designer</span></span>                             |                                                                                                                                                                                                    [<span data-ttu-id="c9a68-142">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="c9a68-142">Creating pipelines using pipeline designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)                                                                                                                                                                                                     |
|                              <span data-ttu-id="c9a68-143">BizTalk 映射器</span><span class="sxs-lookup"><span data-stu-id="c9a68-143">BizTalk Mapper</span></span>                               |                                                                                                                                                                                                            [<span data-ttu-id="c9a68-144">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="c9a68-144">Creating maps using BizTalk mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)                                                                                                                                                                                                             |
|                   <span data-ttu-id="c9a68-145">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="c9a68-145">BizTalk Server Administration console</span></span>                   |                                                                                                                                                                                               [<span data-ttu-id="c9a68-146">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="c9a68-146">Using the BizTalk Server Administration console</span></span>](../../core/using-the-biztalk-server-administration-console.md)                                                                                                                                                                                                |

## <a name="next"></a><span data-ttu-id="c9a68-147">Next</span><span class="sxs-lookup"><span data-stu-id="c9a68-147">Next</span></span>
[<span data-ttu-id="c9a68-148">若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="c9a68-148">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)