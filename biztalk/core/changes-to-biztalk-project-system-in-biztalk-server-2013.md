---
title: 将更改为 BizTalk Server 2013 中 BizTalk 项目系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82f0dd18-073c-4cba-aa0d-48076c58f874
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db58dd7bde1162e9d266201a92422be887bb03d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357540"
---
# <a name="changes-to-biztalk-project-system-in-biztalk-server-2013"></a><span data-ttu-id="2bfb3-102">在 BizTalk Server 2013 中 BizTalk 项目系统的更改</span><span class="sxs-lookup"><span data-stu-id="2bfb3-102">Changes to BizTalk Project System in BizTalk Server 2013</span></span>
<span data-ttu-id="2bfb3-103">本主题提供您的更改的高级概述到 BizTalk Server 中的 BizTalk 项目系统。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-103">This topic gives you a high-level overview of changes to the BizTalk Project System in BizTalk Server.</span></span>  
  
## <a name="project-properties-are-displayed-in-project-designer-window"></a><span data-ttu-id="2bfb3-104">项目设计器窗口中显示项目属性</span><span class="sxs-lookup"><span data-stu-id="2bfb3-104">Project properties are displayed in project designer window</span></span>  
 <span data-ttu-id="2bfb3-105">BizTalk Server 项目的属性现在显示在项目设计器的 Visual Studio 而不是在属性对话框。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-105">Properties for a BizTalk Server project are now displayed in the Project Designer of Visual Studio instead of in a Properties dialog.</span></span> <span data-ttu-id="2bfb3-106">项目设计器提供集中管理项目属性、 设置和资源。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-106">The Project Designer provides a centralized location for managing project properties, settings, and resources.</span></span> <span data-ttu-id="2bfb3-107">项目设计器为单个窗口在 Visual Studio IDE 中，类似于其他设计器，例如窗体或类设计器，其中包含通过在左侧选项卡访问的页面数。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-107">The Project Designer appears as a single window in the Visual Studio IDE, much the same as other designers such as the Form or Class designers and contains a number of pages that are accessed through tabs on the left-hand side.</span></span> <span data-ttu-id="2bfb3-108">有关详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=190417 ](http://go.microsoft.com/fwlink/?LinkId=190417)。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-108">For more information, see [http://go.microsoft.com/fwlink/?LinkId=190417](http://go.microsoft.com/fwlink/?LinkId=190417).</span></span>  
  
## <a name="properties-for-schema-and-map-files-are-displayed-in-properties-window"></a><span data-ttu-id="2bfb3-109">在属性窗口中将显示属性架构和映射文件</span><span class="sxs-lookup"><span data-stu-id="2bfb3-109">Properties for schema and map files are displayed in Properties window</span></span>  
 <span data-ttu-id="2bfb3-110">属性架构和映射文件，如**输入实例文件名**并**测试映射输入实例**将显示在属性窗口使用而不是在单独**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-110">Properties for schema and map files such as **Input Instance Filename** and **Test Map Input Instance** are displayed in the Properties window with instead of in a separate **Properties** dialog box.</span></span>  
  
## <a name="add-web-reference-option-on-projects"></a><span data-ttu-id="2bfb3-111">添加 Web 引用的项目选项</span><span class="sxs-lookup"><span data-stu-id="2bfb3-111">Add Web Reference option on projects</span></span>  
 <span data-ttu-id="2bfb3-112">**添加 Web 引用**右键单击项目名称时，选项不可用或**引用**在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-112">The **Add Web Reference** option is not available when you right-click the project name or **References** in the Solution Explorer.</span></span> <span data-ttu-id="2bfb3-113">可以使用以下步骤来添加对 Web 服务 (.asmx) 的 Web 引用：</span><span class="sxs-lookup"><span data-stu-id="2bfb3-113">You can add a Web reference to a Web service (.asmx) by using the following steps:</span></span>  
  
1. <span data-ttu-id="2bfb3-114">右键单击**引用**在项目中，然后单击**添加服务引用**。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-114">Right-click **References** in the project, and then click **Add Service Reference**.</span></span>  
  
2. <span data-ttu-id="2bfb3-115">在中**添加服务引用**对话框中，单击**高级**。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-115">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
3. <span data-ttu-id="2bfb3-116">在中**服务引用设置**对话框中，单击**添加 Web 引用**。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-116">In the **Service Reference Settings** dialog box, click **Add Web Reference**.</span></span>  
  
4. <span data-ttu-id="2bfb3-117">键入的 URL，然后依次**转**。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-117">Type the URL, and then click **Go**.</span></span>  
  
5. <span data-ttu-id="2bfb3-118">单击**添加引用**添加 Web 引用。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-118">Click **Add Reference** to add the Web reference.</span></span>  
  
   > [!TIP]
   >  <span data-ttu-id="2bfb3-119">添加对 BizTalk 项目的 Web 引用后**添加 Web 引用**菜单选项才可用引用、 Web 引用和项目节点上。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-119">After you add a Web reference to a BizTalk project, the **Add Web Reference** menu option is available on the References, Web References and project nodes.</span></span>  
  
   <span data-ttu-id="2bfb3-120">有关添加服务和 Web 引用的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=131577 ](http://go.microsoft.com/fwlink/?LinkId=131577)。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-120">For more information about adding service and Web references, see [http://go.microsoft.com/fwlink/?LinkId=131577](http://go.microsoft.com/fwlink/?LinkId=131577).</span></span>  
  
## <a name="msbuild-integration"></a><span data-ttu-id="2bfb3-121">MSBUILD 集成</span><span class="sxs-lookup"><span data-stu-id="2bfb3-121">MSBUILD Integration</span></span>  
 <span data-ttu-id="2bfb3-122">Visual Studio 使用 MSBUILD 项目文件格式来存储有关托管项目包括 BizTalk 项目的生成信息。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-122">Visual Studio uses the MSBUILD project file format to store build information about managed projects including BizTalk projects.</span></span> <span data-ttu-id="2bfb3-123">有关详细信息，请参阅[与 Visual Studio 的 MSBUILD 集成](../core/msbuild-integration-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-123">For more information, see [MSBUILD Integration with Visual Studio](../core/msbuild-integration-with-visual-studio.md).</span></span>  
  
## <a name="team-foundation-server-integration"></a><span data-ttu-id="2bfb3-124">Team Foundation Server 集成</span><span class="sxs-lookup"><span data-stu-id="2bfb3-124">Team Foundation Server integration</span></span>  
 <span data-ttu-id="2bfb3-125">对于 BizTalk 项目，可以作为源控制系统中使用 Team Foundation Server。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-125">You can use Team Foundation Server as a source control system for BizTalk projects.</span></span> <span data-ttu-id="2bfb3-126">你可以从解决方案资源管理器窗口本身执行操作，如签入和签出。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-126">You can perform operations such as check-in and check-out from Solution Explorer window itself.</span></span>  
  
## <a name="support-for-unit-testing"></a><span data-ttu-id="2bfb3-127">对单元测试的支持</span><span class="sxs-lookup"><span data-stu-id="2bfb3-127">Support for unit testing</span></span>  
 <span data-ttu-id="2bfb3-128">此功能可以对单元测试架构、 映射和管道。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-128">This feature allows you to unit test schemas, maps, and pipelines.</span></span> <span data-ttu-id="2bfb3-129">有关详细信息，请参阅[Unit Testing 与 BizTalk Server 项目](../core/unit-testing-with-biztalk-server-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-129">For more information, see [Unit Testing with BizTalk Server Projects](../core/unit-testing-with-biztalk-server-projects.md).</span></span>  
  
## <a name="debug-map-feature"></a><span data-ttu-id="2bfb3-130">调试映射功能</span><span class="sxs-lookup"><span data-stu-id="2bfb3-130">Debug Map feature</span></span>  
 <span data-ttu-id="2bfb3-131">**调试映射功能**。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-131">**Debug Map feature**.</span></span> <span data-ttu-id="2bfb3-132">您可以通过使用在中的使用内联 XSLT 调试程序调试映射 (XSLT) [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-132">You can debug a map (XSLT) by using the inline XSLT debugger with in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="2bfb3-133">有关详细信息，请参阅[如何调试映射](../core/how-to-debug-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-133">For more information, see [How to Debug Maps](../core/how-to-debug-maps.md).</span></span>  
  
## <a name="migrating-biztalk-server-projects"></a><span data-ttu-id="2bfb3-134">迁移 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="2bfb3-134">Migrating BizTalk Server projects</span></span>  
 <span data-ttu-id="2bfb3-135">早期版本开发的 visual Studio 项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将迁移到 BizTalk Server 环境中，通过使用 Visual Studio 转换向导。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-135">Visual Studio projects developed for earlier version of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be migrated to the BizTalk Server environment by using the Visual Studio conversion wizard.</span></span> <span data-ttu-id="2bfb3-136">有关详细信息，请参阅[迁移 BizTalk Server 项目](../core/migrating-a-biztalk-server-project.md)。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-136">For more information, see [Migrating a BizTalk Server Project](../core/migrating-a-biztalk-server-project.md).</span></span>  
  
## <a name="release-and-debug-build-types"></a><span data-ttu-id="2bfb3-137">发布和调试版本类型</span><span class="sxs-lookup"><span data-stu-id="2bfb3-137">Release and Debug build types</span></span>  
 <span data-ttu-id="2bfb3-138">现在，BizTalk 项目有两种生成类型：**发行**并**调试**，它取代了**开发**并**部署**的早期版本。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-138">BizTalk projects now have two build types: **Release** and **Debug**, which replaces **Development** and **Deployment** of earlier versions.</span></span> <span data-ttu-id="2bfb3-139">但是，您仍然可以看到**开发**并**部署**从迁移的项目配置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-139">However, you will continue to see the **Development** and **Deployment** configurations for the projects that are migrated from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)].</span></span>  
  
## <a name="embedding-tracking-and-debugging-information"></a><span data-ttu-id="2bfb3-140">嵌入跟踪和调试信息</span><span class="sxs-lookup"><span data-stu-id="2bfb3-140">Embedding tracking and debugging information</span></span>  
 <span data-ttu-id="2bfb3-141">**嵌入跟踪信息**并**生成调试信息**输出配置属性替换为**定义 TRACE 常量**和**定义 DEBUG 常量**生成选项**生成**项目设计器选项卡。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-141">The **Embed Tracking Information** and **Generate Debugging Information** output configuration properties are replaced by the **Define TRACE constant** and **Define DEBUG constant** build options on the **Build** tab of Project Designer.</span></span> <span data-ttu-id="2bfb3-142">**BPEL 兼容代码生成**配置属性替换为**BPEL 兼容代码生成**项目属性窗口中的属性。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-142">The **BPEL Compliance code generation** configuration property is replaced by **BPEL compliance code generation** property in the project properties window.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2bfb3-143">Visual Studio 转换向导已经自动将前面提到的设置迁移到新环境。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-143">The Visual Studio Conversion Wizard takes care of automatically migrates the preceding mentioned settings to new environment.</span></span>  
  
## <a name="user-access-control"></a><span data-ttu-id="2bfb3-144">用户访问控制</span><span class="sxs-lookup"><span data-stu-id="2bfb3-144">User Access Control</span></span>  
 <span data-ttu-id="2bfb3-145">Visual Studio 不允许您使用的用户访问控制 (UAC) 功能，除非使用管理权限运行 Visual Studio 部署 BizTalk 项目的计算机上。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-145">Visual Studio does not let you deploy a BizTalk project on a computer with the User Access Control (UAC) feature turned on unless you run Visual Studio with administrative privileges.</span></span> <span data-ttu-id="2bfb3-146">若要使用管理权限运行 Visual Studio，请单击**启动**，依次指向**所有程序**，指向**Microsoft Visual Studio**，右键单击**Microsoft Visual Studio\<版本\>**，然后单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-146">To run Visual Studio with administrative privileges, click **Start**, point to **All Programs**, point to **Microsoft Visual Studio**, right-click **Microsoft Visual Studio \<version\>**, and then click **Run as administrator**.</span></span>  
  
## <a name="c-files-in-a-biztalk-project"></a><span data-ttu-id="2bfb3-147">C#BizTalk 项目中的文件</span><span class="sxs-lookup"><span data-stu-id="2bfb3-147">C# files in a BizTalk project</span></span>  
 <span data-ttu-id="2bfb3-148">BizTalk Server，可将帮助程序类与 BizTalk 项目仅满足灵活包装需求相结合。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-148">BizTalk Server allows you to combine helper classes with BizTalk artifacts for flexible packaging needs only.</span></span>  <span data-ttu-id="2bfb3-149">但是，不能直接通过添加新的 C# 文件**添加新项**或**添加新的类**菜单选项。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-149">However, you cannot add a new C# file directly by using the **Add New Item** or **Add New Class** menu options.</span></span>  
  
## <a name="generatecsfiles-registry-key-is-obsolete"></a><span data-ttu-id="2bfb3-150">GenerateCSFiles 注册表项已过时</span><span class="sxs-lookup"><span data-stu-id="2bfb3-150">GenerateCSFiles registry key is obsolete</span></span>  
 <span data-ttu-id="2bfb3-151">**GenerateCSFiles**注册表项现已过时。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-151">The **GenerateCSFiles** registry key is obsolete now.</span></span> <span data-ttu-id="2bfb3-152">所有生成的.cs 文件将显示在解决方案资源管理器窗口。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-152">All generated .cs files are displayed in the Solution Explorer window.</span></span> <span data-ttu-id="2bfb3-153">可能需要单击**显示所有文件**在解决方案资源管理器窗口以查看与某些 BizTalk 项相关联的.cs 文件中的工具栏项。</span><span class="sxs-lookup"><span data-stu-id="2bfb3-153">You may need to click **Show All Files** toolbar item in the Solution Explorer window to see .cs files associated with some of the BizTalk items.</span></span>