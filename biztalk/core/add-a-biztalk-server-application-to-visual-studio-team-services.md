---
title: "添加到 Visual Studio Team Services BizTalk Server 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2c7a1ff-0f26-45f3-9a9b-4c99a67b51a9
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: d3fc8c0253c8e2517f78c2d60fdc7c74a983bdbd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="add-a-biztalk-server-application-to-visual-studio-team-services"></a><span data-ttu-id="a136a-102">添加到 Visual Studio Team Services BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="a136a-102">Add a BizTalk Server application to Visual Studio Team Services</span></span>
<span data-ttu-id="a136a-103">添加[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]VSTS 来自动部署使用持续集成到项目。</span><span class="sxs-lookup"><span data-stu-id="a136a-103">Add a [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] project to VSTS to automatically deploy using continuous integration.</span></span>  

<span data-ttu-id="a136a-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，你可以自动部署您的应用程序你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]使用 Visual Studio Team Services (VSTS) 的环境。</span><span class="sxs-lookup"><span data-stu-id="a136a-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can automatically deploy your applications to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments using Visual Studio Team Services (VSTS).</span></span> 

<span data-ttu-id="a136a-105">此主题提供概述，并列出来部署你从 Visual Studio 的解决方案的关键步骤你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a136a-105">This topics provides an overview, and lists the key steps to deploy your solution from Visual Studio to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a136a-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="a136a-106">Prerequisites</span></span>
* <span data-ttu-id="a136a-107">安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a136a-107">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* [<span data-ttu-id="a136a-108">为自动部署配置 VSTS</span><span class="sxs-lookup"><span data-stu-id="a136a-108">Configure VSTS for automatic deployment</span></span>](../core/configure-visual-studio-team-services-to-deploy-biztalk-solutions-or-projects.md)
* <span data-ttu-id="a136a-109">知识和体验使用 Git 和 Visual Studio 中的存储库。</span><span class="sxs-lookup"><span data-stu-id="a136a-109">Knowledge and experience working with Git and repositories in Visual Studio.</span></span> <span data-ttu-id="a136a-110">如果你是新手存储库和版本控制，这些可能是很好的资源：</span><span class="sxs-lookup"><span data-stu-id="a136a-110">If you're brand new to repositories and version control, these may be good resources:</span></span> 

    [<span data-ttu-id="a136a-111">了解 Git</span><span class="sxs-lookup"><span data-stu-id="a136a-111">Learn Git</span></span>](https://www.visualstudio.com/learn-git/)  
    [<span data-ttu-id="a136a-112">Git 和 Team Services</span><span class="sxs-lookup"><span data-stu-id="a136a-112">Git and Team Services</span></span>](https://www.visualstudio.com/docs/git/overview)
* <span data-ttu-id="a136a-113">知识和经验 BizTalk 在中使用项目[!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a136a-113">Knowledge and experience working with BizTalk projects in [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]</span></span>

## <a name="add-biztalk-project-to-vsts"></a><span data-ttu-id="a136a-114">将 BizTalk 项目添加到 VSTS</span><span class="sxs-lookup"><span data-stu-id="a136a-114">Add BizTalk project to VSTS</span></span>
1. <span data-ttu-id="a136a-115">在**Visual Studio**，连接到你**源代码存储库**，和**克隆**到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="a136a-115">In **Visual Studio**, connect to your **Source repository**, and **Clone** it to your machine.</span></span>
2. <span data-ttu-id="a136a-116">打开或创建**BizTalk 项目**(.btproj)。</span><span class="sxs-lookup"><span data-stu-id="a136a-116">Open or Create a **BizTalk Project** (.btproj).</span></span>

   > [!NOTE]
   > <span data-ttu-id="a136a-117">也可以将多个项目添加到同一个解决方案。</span><span class="sxs-lookup"><span data-stu-id="a136a-117">You can add multiple project into the same solution.</span></span>
   
3. <span data-ttu-id="a136a-118">添加新**BizTalk 服务器应用程序项目**(.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="a136a-118">Add a new **BizTalk Server Application Project** (.btaproj).</span></span>
4. <span data-ttu-id="a136a-119">右键单击中的项目**解决方案资源管理器**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="a136a-119">Right-click the project in the **Solution Explorer**, and select **Properties**.</span></span>
5. <span data-ttu-id="a136a-120">配置**版本**和连接属性添加到你**Visual Studio Team Services**帐户。</span><span class="sxs-lookup"><span data-stu-id="a136a-120">Configure the **Version** and the connection properties to your **Visual Studio Team Services** account.</span></span>

    ![Visual Studio 配置 FP1 BizTalk](../core/media/visual-studio-configuration-fp1-biztalk.png)

6. <span data-ttu-id="a136a-122">添加所有程序集和应用程序所需的项目。</span><span class="sxs-lookup"><span data-stu-id="a136a-122">Add all the assemblies and artifacts needed by your application.</span></span>
7. <span data-ttu-id="a136a-123">更新**binding.xml**具有正确的绑定信息文件。</span><span class="sxs-lookup"><span data-stu-id="a136a-123">Update the **binding.xml** file with the correct binding information.</span></span>
8. <span data-ttu-id="a136a-124">更新**BizTalkServerInventory.json**与所有项目和项目上安装的正确顺序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a136a-124">Update the **BizTalkServerInventory.json** with all the artifacts, and the correct order for the artifacts to be installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>
9. <span data-ttu-id="a136a-125">右键单击和**生成**解决方案以检查是否有任何错误。</span><span class="sxs-lookup"><span data-stu-id="a136a-125">Right-click and **build** your solution to check for any errors.</span></span> 
10. <span data-ttu-id="a136a-126">生成成功完成后，右键单击你的解决方案，然后选择**部署**。</span><span class="sxs-lookup"><span data-stu-id="a136a-126">When the build completes successfully, right-click your solution, and select **Deploy**.</span></span>
11. <span data-ttu-id="a136a-127">应自动将你的应用程序部署到你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a136a-127">Your application should automatically deploy to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="a136a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a136a-128">See also</span></span>
[<span data-ttu-id="a136a-129">配置功能包</span><span class="sxs-lookup"><span data-stu-id="a136a-129">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)