---
title: 创建 SAP 应用程序的先决条件 |Microsoft Docs
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
ms.openlocfilehash: 72225a059d5b655555f46f06758df11de3eaa8e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978566"
---
# <a name="prerequisites-to-create-sap-applications"></a><span data-ttu-id="7348e-102">创建 SAP 应用程序的先决条件</span><span class="sxs-lookup"><span data-stu-id="7348e-102">Prerequisites to create SAP applications</span></span>
<span data-ttu-id="7348e-103">本部分提供有关在开发 BizTalk 应用程序使用之前必须执行的任务的信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7348e-103">This section provides information about tasks that you must perform before developing BizTalk applications using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="7348e-104">部分还列出了一些 BizTalk Server 工具，用于开发 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7348e-104">The section also lists some BizTalk Server tools that are used to develop BizTalk applications.</span></span>  

## <a name="create-a-strong-name-key-file"></a><span data-ttu-id="7348e-105">创建强名称密钥文件</span><span class="sxs-lookup"><span data-stu-id="7348e-105">Create a strong-name key file</span></span>

<span data-ttu-id="7348e-106">必须创建一个强名称密钥文件，若要在 Microsoft 中生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7348e-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="7348e-107">强名称包含项目的标识，其简单文本名称、 版本号和区域性信息 （如果提供），加上公钥和数字签名。</span><span class="sxs-lookup"><span data-stu-id="7348e-107">A strong name consists of the project's identity—its simple text name, version number, and culture information (if provided)—plus a public key and a digital signature.</span></span> <span data-ttu-id="7348e-108">强名称密钥文件包含公钥和私钥。</span><span class="sxs-lookup"><span data-stu-id="7348e-108">The strong-name key file contains the public key and the private key.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="7348e-109">创建强名称密钥文件是一次性任务。</span><span class="sxs-lookup"><span data-stu-id="7348e-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="7348e-110">为您开发的所有 BizTalk 应用程序，可以使用相同的密钥。</span><span class="sxs-lookup"><span data-stu-id="7348e-110">You can use the same key for all the BizTalk applications you develop.</span></span>  

1.  <span data-ttu-id="7348e-111">打开 Visual Studio 开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="7348e-111">Open the developer command prompt for Visual Studio.</span></span>  

2.  <span data-ttu-id="7348e-112">在命令提示符处导航到你想要创建的密钥文件的位置。</span><span class="sxs-lookup"><span data-stu-id="7348e-112">At the command prompt navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="7348e-113">例如，键入**cd C:\Sample**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="7348e-113">For example, type **cd C:\Sample**,and then press ENTER.</span></span>  

3.  <span data-ttu-id="7348e-114">在命令提示符下，键入 `sn -k <key file name\>.snk`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="7348e-114">At the command prompt, type `sn -k <key file name\>.snk`, and then press ENTER.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="7348e-115">应会收到一条消息表明密钥对已写入到强名称密钥文件的命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="7348e-115">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  

4.  <span data-ttu-id="7348e-116">在命令提示符处，键入**退出**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="7348e-116">At the command prompt, type **exit**, and then press ENTER.</span></span>  

## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="7348e-117">了解 BizTalk Server 工具</span><span class="sxs-lookup"><span data-stu-id="7348e-117">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="7348e-118">有关如何使用主题[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]中[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)假定你有多个 BizTalk Server 工具的实践知识。</span><span class="sxs-lookup"><span data-stu-id="7348e-118">The topics on how to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in [Develop BizTalk applications](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md) assume that you have working knowledge of a number of BizTalk Server tools.</span></span> <span data-ttu-id="7348e-119">将使用以下工具来开发 BizTalk 应用程序使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7348e-119">You will use the following tools to develop BizTalk applications using [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:</span></span>  

- <span data-ttu-id="7348e-120">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7348e-120">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 

- <span data-ttu-id="7348e-121">业务流程 eesigner</span><span class="sxs-lookup"><span data-stu-id="7348e-121">Orchestration eesigner</span></span>  

- <span data-ttu-id="7348e-122">管道设计器</span><span class="sxs-lookup"><span data-stu-id="7348e-122">Pipeline designer</span></span>  

- <span data-ttu-id="7348e-123">BizTalk 映射器</span><span class="sxs-lookup"><span data-stu-id="7348e-123">BizTalk mapper</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7348e-124"> 管理控制台</span><span class="sxs-lookup"><span data-stu-id="7348e-124"> Administration console</span></span>  


### <a name="prerequisites"></a><span data-ttu-id="7348e-125">必要條件</span><span class="sxs-lookup"><span data-stu-id="7348e-125">Prerequisites</span></span>  
 <span data-ttu-id="7348e-126">必须安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以访问之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具。</span><span class="sxs-lookup"><span data-stu-id="7348e-126">You must install [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  

### <a name="biztalk-server-tools"></a><span data-ttu-id="7348e-127">BizTalk Server 工具</span><span class="sxs-lookup"><span data-stu-id="7348e-127">BizTalk Server Tools</span></span>  
 <span data-ttu-id="7348e-128">下表包含本节中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]说明了如何使用每个列出的工具的文档。</span><span class="sxs-lookup"><span data-stu-id="7348e-128">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  


|                                   <span data-ttu-id="7348e-129">工具</span><span class="sxs-lookup"><span data-stu-id="7348e-129">Tool</span></span>                                    |                                                                                                                                                                                              <span data-ttu-id="7348e-130">本节中的主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]核心文档</span><span class="sxs-lookup"><span data-stu-id="7348e-130">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>                                                                                                                                                                                               |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] | <span data-ttu-id="7348e-131">-   [使用 Visual Studio](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="7348e-131">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="7348e-132">-   [使用 BizTalk 项目](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="7348e-132">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="7348e-133">-   [部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="7348e-133">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="7348e-134">了解更多有关 Visual Studio 解决方案、 项目和项在[解决方案和项目在 Visual Studio 中的](https://msdn.microsoft.com/library/b142f8e7.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7348e-134">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span> |
|                          <span data-ttu-id="7348e-135">业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="7348e-135">Orchestration Designer</span></span>                           |                                                                                                                                                                                          [<span data-ttu-id="7348e-136">创建业务流程使用业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="7348e-136">Creating orchestrations using orchestration designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)                                                                                                                                                                                           |
|                             <span data-ttu-id="7348e-137">管道设计器</span><span class="sxs-lookup"><span data-stu-id="7348e-137">Pipeline Designer</span></span>                             |                                                                                                                                                                                                    [<span data-ttu-id="7348e-138">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="7348e-138">Creating pipelines using pipeline designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)                                                                                                                                                                                                     |
|                              <span data-ttu-id="7348e-139">BizTalk 映射器</span><span class="sxs-lookup"><span data-stu-id="7348e-139">BizTalk Mapper</span></span>                               |                                                                                                                                                                                                            [<span data-ttu-id="7348e-140">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="7348e-140">Creating maps using BizTalk mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)                                                                                                                                                                                                             |
|                   <span data-ttu-id="7348e-141">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="7348e-141">BizTalk Server Administration console</span></span>                   |                                                                                                                                                                                               [<span data-ttu-id="7348e-142">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="7348e-142">Using the BizTalk Server Administration console</span></span>](../../core/using-the-biztalk-server-administration-console.md)                                                                                                                                                                                                |

## <a name="next"></a><span data-ttu-id="7348e-143">Next</span><span class="sxs-lookup"><span data-stu-id="7348e-143">Next</span></span>
[<span data-ttu-id="7348e-144">生成块以创建 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="7348e-144">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)