---
title: 要创建的 SAP 应用程序系统必备组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51ae9569-4081-4142-9ee2-8ae0069e9d90
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7cddc252868bf47ace0d73e81ddb1c7721bf8a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216397"
---
# <a name="prerequisites-to-create-sap-applications"></a><span data-ttu-id="9e757-102">若要创建的 SAP 应用程序的先决条件</span><span class="sxs-lookup"><span data-stu-id="9e757-102">Prerequisites to create SAP applications</span></span>
<span data-ttu-id="9e757-103">本部分提供有关开发 BizTalk 应用程序使用之前必须执行的任务的信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9e757-103">This section provides information about tasks that you must perform before developing BizTalk applications using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="9e757-104">部分还列出了一些用于开发 BizTalk 应用程序的 BizTalk Server 工具。</span><span class="sxs-lookup"><span data-stu-id="9e757-104">The section also lists some BizTalk Server tools that are used to develop BizTalk applications.</span></span>  
  
## <a name="create-a-strong-name-key-file"></a><span data-ttu-id="9e757-105">创建强名称密钥文件</span><span class="sxs-lookup"><span data-stu-id="9e757-105">Create a strong-name key file</span></span>

<span data-ttu-id="9e757-106">你必须创建一个强名称密钥文件，以生成在 Microsoft 中的项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9e757-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="9e757-107">强名称的项目的标识组成 — 其简单文本名称、 版本号和区域性信息 （如果有的话）-加上一个公钥和数字签名。</span><span class="sxs-lookup"><span data-stu-id="9e757-107">A strong name consists of the project's identity—its simple text name, version number, and culture information (if provided)—plus a public key and a digital signature.</span></span> <span data-ttu-id="9e757-108">强名称密钥文件包含公钥和私钥。</span><span class="sxs-lookup"><span data-stu-id="9e757-108">The strong-name key file contains the public key and the private key.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9e757-109">创建强名称密钥文件是一次性的任务。</span><span class="sxs-lookup"><span data-stu-id="9e757-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="9e757-110">相同的密钥可用于开发的所有 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e757-110">You can use the same key for all the BizTalk applications you develop.</span></span>  
  
1.  <span data-ttu-id="9e757-111">打开 Visual Studio 开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="9e757-111">Open the developer command prompt for Visual Studio.</span></span>  
  
2.  <span data-ttu-id="9e757-112">在命令提示符导航到你想要创建的密钥文件的位置。</span><span class="sxs-lookup"><span data-stu-id="9e757-112">At the command prompt navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="9e757-113">例如，键入**cd C:\Sample**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="9e757-113">For example, type **cd C:\Sample**,and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="9e757-114">在命令提示符下，键入 `sn -k <key file name\>.snk`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="9e757-114">At the command prompt, type `sn -k <key file name\>.snk`, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e757-115">你应该会收到一条消息，指出的密钥对已写入到强名称密钥文件的命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="9e757-115">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  
  
4.  <span data-ttu-id="9e757-116">在命令提示符处，键入**退出**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="9e757-116">At the command prompt, type **exit**, and then press ENTER.</span></span>  

## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="9e757-117">了解 BizTalk Server 工具</span><span class="sxs-lookup"><span data-stu-id="9e757-117">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="9e757-118">有关如何使用主题[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]中[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)假定您有大量的 BizTalk Server 工具的应用知识。</span><span class="sxs-lookup"><span data-stu-id="9e757-118">The topics on how to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in [Develop BizTalk applications](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md) assume that you have working knowledge of a number of BizTalk Server tools.</span></span> <span data-ttu-id="9e757-119">将使用以下工具来开发 BizTalk 应用程序使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9e757-119">You will use the following tools to develop BizTalk applications using [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:</span></span>  
  
-   <span data-ttu-id="9e757-120">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e757-120">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="9e757-121">业务流程 eesigner</span><span class="sxs-lookup"><span data-stu-id="9e757-121">Orchestration eesigner</span></span>  
  
-   <span data-ttu-id="9e757-122">管道设计器</span><span class="sxs-lookup"><span data-stu-id="9e757-122">Pipeline designer</span></span>  
  
-   <span data-ttu-id="9e757-123">BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="9e757-123">BizTalk mapper</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9e757-124"> 管理控制台</span><span class="sxs-lookup"><span data-stu-id="9e757-124"> Administration console</span></span>  

  
### <a name="prerequisites"></a><span data-ttu-id="9e757-125">先决条件</span><span class="sxs-lookup"><span data-stu-id="9e757-125">Prerequisites</span></span>  
 <span data-ttu-id="9e757-126">必须安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以访问之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。</span><span class="sxs-lookup"><span data-stu-id="9e757-126">You must install [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  
  
### <a name="biztalk-server-tools"></a><span data-ttu-id="9e757-127">BizTalk Server 工具</span><span class="sxs-lookup"><span data-stu-id="9e757-127">BizTalk Server Tools</span></span>  
 <span data-ttu-id="9e757-128">下表包含中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]说明如何使用每个列出的工具的文档。</span><span class="sxs-lookup"><span data-stu-id="9e757-128">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  

|<span data-ttu-id="9e757-129">工具</span><span class="sxs-lookup"><span data-stu-id="9e757-129">Tool</span></span>|<span data-ttu-id="9e757-130">中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]核心文档</span><span class="sxs-lookup"><span data-stu-id="9e757-130">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]|<span data-ttu-id="9e757-131">-   [使用 Visual Studio](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="9e757-131">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="9e757-132">-   [使用 BizTalk 项目](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="9e757-132">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="9e757-133">-   [部署到 BizTalk 应用程序从 Visual Studio BizTalk 程序集](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="9e757-133">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="9e757-134">了解更多有关 Visual Studio 解决方案、 项目和项在[解决方案和 Visual Studio 中的项目](https://msdn.microsoft.com/library/b142f8e7.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9e757-134">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span>|  
|<span data-ttu-id="9e757-135">业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="9e757-135">Orchestration Designer</span></span>|[<span data-ttu-id="9e757-136">创建使用业务流程设计器的业务流程</span><span class="sxs-lookup"><span data-stu-id="9e757-136">Creating orchestrations using orchestration designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)|  
|<span data-ttu-id="9e757-137">管道设计器</span><span class="sxs-lookup"><span data-stu-id="9e757-137">Pipeline Designer</span></span>| [<span data-ttu-id="9e757-138">创建管道使用管道设计器</span><span class="sxs-lookup"><span data-stu-id="9e757-138">Creating pipelines using pipeline designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)|  
|<span data-ttu-id="9e757-139">BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="9e757-139">BizTalk Mapper</span></span>| [<span data-ttu-id="9e757-140">创建映射使用 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="9e757-140">Creating maps using BizTalk mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)|  
|<span data-ttu-id="9e757-141">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="9e757-141">BizTalk Server Administration console</span></span>|[<span data-ttu-id="9e757-142">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="9e757-142">Using the BizTalk Server Administration console</span></span>](../../core/using-the-biztalk-server-administration-console.md)|  

## <a name="next"></a><span data-ttu-id="9e757-143">Next</span><span class="sxs-lookup"><span data-stu-id="9e757-143">Next</span></span>
[<span data-ttu-id="9e757-144">若要创建的 SAP 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="9e757-144">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)