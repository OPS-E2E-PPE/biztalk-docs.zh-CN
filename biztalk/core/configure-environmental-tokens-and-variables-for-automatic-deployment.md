---
title: "配置环境的令牌和自动部署变量 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 7d148f79fceb68b24feb45882ab89767369ed7e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a><span data-ttu-id="46f1d-102">配置环境的令牌和自动部署的变量</span><span class="sxs-lookup"><span data-stu-id="46f1d-102">Configure environmental tokens and variables for automatic deployment</span></span>
<span data-ttu-id="46f1d-103">使用 Visual Studio Team Services (VSTS) 变量中的你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]绑定文件。</span><span class="sxs-lookup"><span data-stu-id="46f1d-103">Use Visual Studio Team Services (VSTS) variables in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] binding files.</span></span>

## <a name="overview"></a><span data-ttu-id="46f1d-104">概述</span><span class="sxs-lookup"><span data-stu-id="46f1d-104">Overview</span></span>
<span data-ttu-id="46f1d-105">在 VSTS 环境中，你可以添加变量，并将它们设置为一个值。</span><span class="sxs-lookup"><span data-stu-id="46f1d-105">In a VSTS environment, you can add variables, and set them to a value.</span></span> <span data-ttu-id="46f1d-106">例如，你可以创建*sendPortPath*变量，并将其值设置为物理文件夹，在你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="46f1d-106">For example, you can create a *sendPortPath* variable, and set its value to a physical folder on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="46f1d-107">在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]应用程序绑定文件，可配置的变量可以是任何内容中的 XML 标记，如接收位置名称、 主机、 发送端口 URI，等等。</span><span class="sxs-lookup"><span data-stu-id="46f1d-107">Within the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] application binding file, the configurable variables can be anything within an XML tag, such as the receive location name, host, send port URI, and so on.</span></span> 

<span data-ttu-id="46f1d-108">这些变量特定于你的 VSTS 环境，并且可以用于部署到多个相同的应用程序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="46f1d-108">These variables are specific to your VSTS environment, and can be used to deploy the same application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span> 

<span data-ttu-id="46f1d-109">在本主题中，我们演示如何添加 VSTS 变量在绑定文件中，以及如何创建 VSTS 中的变量。</span><span class="sxs-lookup"><span data-stu-id="46f1d-109">In this topic, we show you how add the VSTS variable in your binding file, and how to create the variable within VSTS.</span></span> 

## <a name="configure-the-variables-in-your-biztalk-binding-file"></a><span data-ttu-id="46f1d-110">在 BizTalk 绑定文件中配置的变量</span><span class="sxs-lookup"><span data-stu-id="46f1d-110">Configure the variables in your BizTalk Binding file</span></span>

<span data-ttu-id="46f1d-111">下面的示例摘自[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]绑定文件，并演示如何应用令牌。</span><span class="sxs-lookup"><span data-stu-id="46f1d-111">The following example is a part of a [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] binding file, and shows how to apply the tokens.</span></span>

1. <span data-ttu-id="46f1d-112">打开应用程序绑定文件：</span><span class="sxs-lookup"><span data-stu-id="46f1d-112">Open the application binding file:</span></span>

    ![BizTalk 功能包 1 绑定 1](../core/media/biztalk-feature-pack-1-binding-1.png)

2. <span data-ttu-id="46f1d-114">查找你想要更改的元素：</span><span class="sxs-lookup"><span data-stu-id="46f1d-114">Find the element you want to change:</span></span>

    ![BizTalk 功能包 1 绑定 2](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. <span data-ttu-id="46f1d-116">删除的填充的值，并将其与你变量： `$(YourValue)`。</span><span class="sxs-lookup"><span data-stu-id="46f1d-116">Remove the populated value, and replace it with you variables: `$(YourValue)`.</span></span> <span data-ttu-id="46f1d-117">例如，输入`$(SendPort1)`:</span><span class="sxs-lookup"><span data-stu-id="46f1d-117">For example, enter `$(SendPort1)`:</span></span> 

    ![BizTalk 功能包 1 绑定 3](../core/media/biztalk-feature-pack-1-binding-3.png)


4. <span data-ttu-id="46f1d-119">完成后，保存该绑定文件，并将其应用到 JSON 生成模板。</span><span class="sxs-lookup"><span data-stu-id="46f1d-119">When done, save the binding file, and apply it to your JSON build template.</span></span>
5. <span data-ttu-id="46f1d-120">登录到 Visual Studio 团队服务解决方案，然后选择**生成和发布**。</span><span class="sxs-lookup"><span data-stu-id="46f1d-120">Sign in to your Visual Studio Team Service solution, and select **Build and release**.</span></span>
6. <span data-ttu-id="46f1d-121">转到**版本**。</span><span class="sxs-lookup"><span data-stu-id="46f1d-121">Go to **Release**.</span></span> <span data-ttu-id="46f1d-122">选择你**释放定义**，或创建一个新。</span><span class="sxs-lookup"><span data-stu-id="46f1d-122">Select your **Release definition**, or create a new one.</span></span>
7. <span data-ttu-id="46f1d-123">下**环境**，选择**添加新环境**，或将更改为现有环境：</span><span class="sxs-lookup"><span data-stu-id="46f1d-123">Under **Environments**, select **Add a new environment**, or change to an existing environment:</span></span> 

    ![添加新的环境](../core/media/add-a-new-environment.png)

8. <span data-ttu-id="46f1d-125">单击省略号，然后选择**配置变量**:</span><span class="sxs-lookup"><span data-stu-id="46f1d-125">Click the ellipses, and select **configure variables**:</span></span>

    ![配置变量](../core/media/configure-variables.png)

9. <span data-ttu-id="46f1d-127">通过添加每个环境中使用绑定文件中创建的标记名称的变量中，你可以部署您的应用程序使用不同的值的多个环境：</span><span class="sxs-lookup"><span data-stu-id="46f1d-127">By adding the variables for each environment, using the token names created in the binding file, you can deploy your applications to multiple environments with different values:</span></span>

    ![环境特定变量](../core/media/environment-specific-variables.png)
    
10. <span data-ttu-id="46f1d-129">选择**确定**以保存新变量。</span><span class="sxs-lookup"><span data-stu-id="46f1d-129">Select **OK** to save the new variables.</span></span>
11. <span data-ttu-id="46f1d-130">生成开始后，会将值添加从绑定文件。</span><span class="sxs-lookup"><span data-stu-id="46f1d-130">Once the build is initiated, the values are added from binding file.</span></span>

## <a name="next-step"></a><span data-ttu-id="46f1d-131">下一步</span><span class="sxs-lookup"><span data-stu-id="46f1d-131">Next step</span></span>
[<span data-ttu-id="46f1d-132">添加到 VSTS BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="46f1d-132">Add a BizTalk application to VSTS</span></span>](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)