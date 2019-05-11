---
title: 如何创建 BizTalk 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, projects
- projects, creating
- solutions
- solutions, adding projects
ms.assetid: a6900234-f989-4601-96c5-41d435c2f8b4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c21d98c829f98c321902a4431bc19ab03a79293
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385507"
---
# <a name="how-to-create-biztalk-projects"></a><span data-ttu-id="95a8e-102">如何创建 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="95a8e-102">How to Create BizTalk Projects</span></span>
<span data-ttu-id="95a8e-103">若要创建 BizTalk Server 运行的应用程序，首先将一个或多个 BizTalk 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="95a8e-103">To create an application that runs on BizTalk Server, you start by adding one or more BizTalk projects to a solution.</span></span> <span data-ttu-id="95a8e-104">本部分介绍了一些在使用 BizTalk 项目时，可能执行的任务。</span><span class="sxs-lookup"><span data-stu-id="95a8e-104">This section describes some of the tasks that you might perform when you work with BizTalk projects.</span></span>  
  
 <span data-ttu-id="95a8e-105">有关创建解决方案和项目的详细信息，请参阅"解决方案、 项目和项的简介"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]网址[ http://go.microsoft.com/fwlink/?LinkId=124069 ](http://go.microsoft.com/fwlink/?LinkId=124069)。</span><span class="sxs-lookup"><span data-stu-id="95a8e-105">For more information about creating solutions and projects, see "Introduction to Solutions, Projects, and Items" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://go.microsoft.com/fwlink/?LinkId=124069](http://go.microsoft.com/fwlink/?LinkId=124069).</span></span>  
  
### <a name="to-create-a-biztalk-project"></a><span data-ttu-id="95a8e-106">若要创建 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="95a8e-106">To create a BizTalk project</span></span>  
  
1. <span data-ttu-id="95a8e-107">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="95a8e-107">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="95a8e-108">在中**新的项目**对话框中**项目类型**区域中，选择**BizTalk 项目**。</span><span class="sxs-lookup"><span data-stu-id="95a8e-108">In the **New Project** dialog box, in the **Project Types** area, select **BizTalk Projects**.</span></span>  
  
3. <span data-ttu-id="95a8e-109">在中**模板**区域中，选择其中一个 BizTalk Server 项目模板。</span><span class="sxs-lookup"><span data-stu-id="95a8e-109">In the **Templates** area, select one of the BizTalk Server Project templates.</span></span>  
  
4. <span data-ttu-id="95a8e-110">指定项目的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="95a8e-110">Specify project name and its location.</span></span>  
  
5. <span data-ttu-id="95a8e-111">选择**创建新的解决方案**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="95a8e-111">Select **Create New Solution** and click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95a8e-112">用户可配置属性中的一些**新的项目**仅当你使用与 BizTalk 项目系统时，才出现的对话框。</span><span class="sxs-lookup"><span data-stu-id="95a8e-112">Some of the user configurable properties in the **New Projects** dialog box appear only when you are working with the BizTalk project system.</span></span> <span data-ttu-id="95a8e-113">有关不同的 BizTalk Server 项目模板及其用法的详细信息，请参阅[BizTalk Server 项目模板](../core/biztalk-server-project-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="95a8e-113">For more information about the different BizTalk Server project templates and their use, see [BizTalk Server Project Templates](../core/biztalk-server-project-templates.md).</span></span>  
  
### <a name="to-add-a-new-biztalk-project-to-a-solution"></a><span data-ttu-id="95a8e-114">若要向解决方案添加新的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="95a8e-114">To add a new BizTalk project to a solution</span></span>  
  
1. <span data-ttu-id="95a8e-115">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中打开该解决方案。</span><span class="sxs-lookup"><span data-stu-id="95a8e-115">Open the solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="95a8e-116">右键单击解决方案名称，指向**外**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="95a8e-116">Right-click the solution name, point to **Add**, and click **New Project**.</span></span>  
  
3. <span data-ttu-id="95a8e-117">在中**项目类型**区域中，选择**BizTalk 项目**，然后在**模板**区域中，选择其中一个 BizTalk Server 项目模板。</span><span class="sxs-lookup"><span data-stu-id="95a8e-117">In the **Project Types** area, select **BizTalk Projects**, and in the **Templates** area, select one of the BizTalk Server Project templates.</span></span>  
  
4. <span data-ttu-id="95a8e-118">选择**将添加到解决方案**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="95a8e-118">Select **Add to Solution** and click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95a8e-119">不支持以下菜单命令**开放**的子菜单**文件**菜单：**从 Web 项目**并**文件从 Web**。</span><span class="sxs-lookup"><span data-stu-id="95a8e-119">The following menu commands are not supported on the **Open** submenu of the **File** menu: **Project From Web** and **File From Web**.</span></span> <span data-ttu-id="95a8e-120">有关详细信息，请参阅[使用 Visual Studio](../core/using-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="95a8e-120">For more information, see [Using Visual Studio](../core/using-visual-studio.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95a8e-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="95a8e-121">In This Section</span></span>  
  
-   [<span data-ttu-id="95a8e-122">创建 BizTalk 项目时的注意事项</span><span class="sxs-lookup"><span data-stu-id="95a8e-122">Considerations When Creating BizTalk Projects</span></span>](../core/considerations-when-creating-biztalk-projects.md)  
  
-   [<span data-ttu-id="95a8e-123">添加项目项</span><span class="sxs-lookup"><span data-stu-id="95a8e-123">Adding Project Items</span></span>](../core/adding-project-items.md)  
  
-   [<span data-ttu-id="95a8e-124">解决方案生成配置</span><span class="sxs-lookup"><span data-stu-id="95a8e-124">Solution Build Configurations</span></span>](../core/solution-build-configurations.md)