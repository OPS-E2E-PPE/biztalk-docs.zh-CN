---
title: "创建环境的令牌和变量 |Microsoft 文档\""
description: "更新绑定文件以使用环境标记，并在 VSTS 中自动执行部署的 BizTalk Server 应用程序中创建变量"
ms.custom: 
ms.date: 11/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d84fa393410e3084c87e762140530a45b0b78b5
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a><span data-ttu-id="b6d09-103">配置环境的令牌和自动部署的变量</span><span class="sxs-lookup"><span data-stu-id="b6d09-103">Configure environmental tokens and variables for automatic deployment</span></span>
<span data-ttu-id="b6d09-104">使用 Visual Studio Team Services (VSTS) 变量中的你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]绑定文件。</span><span class="sxs-lookup"><span data-stu-id="b6d09-104">Use Visual Studio Team Services (VSTS) variables in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] binding files.</span></span>

## <a name="overview"></a><span data-ttu-id="b6d09-105">概述</span><span class="sxs-lookup"><span data-stu-id="b6d09-105">Overview</span></span>
<span data-ttu-id="b6d09-106">在 VSTS 环境中，你可以添加变量，并将它们设置为一个值。</span><span class="sxs-lookup"><span data-stu-id="b6d09-106">In a VSTS environment, you can add variables, and set them to a value.</span></span> <span data-ttu-id="b6d09-107">例如，你可以创建*sendPortPath*变量，并将其值设置为物理文件夹，在你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b6d09-107">For example, you can create a *sendPortPath* variable, and set its value to a physical folder on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="b6d09-108">在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]应用程序绑定文件，可配置的变量可以是任何内容中的 XML 标记，如接收位置名称、 主机、 发送端口 URI，等等。</span><span class="sxs-lookup"><span data-stu-id="b6d09-108">Within the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] application binding file, the configurable variables can be anything within an XML tag, such as the receive location name, host, send port URI, and so on.</span></span> 

<span data-ttu-id="b6d09-109">这些变量特定于你的 VSTS 环境，并且可以用于部署到多个相同的应用程序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="b6d09-109">These variables are specific to your VSTS environment, and can be used to deploy the same application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span> 

<span data-ttu-id="b6d09-110">我们向您展示如何将 VSTS 变量添加在绑定文件中，以及如何创建 VSTS 中的变量。</span><span class="sxs-lookup"><span data-stu-id="b6d09-110">We show you how to add the VSTS variable in your binding file, and how to create the variable within VSTS.</span></span> 

## <a name="add-variables-to-the-binding-file"></a><span data-ttu-id="b6d09-111">将变量添加到绑定文件</span><span class="sxs-lookup"><span data-stu-id="b6d09-111">Add variables to the binding file</span></span>

1. <span data-ttu-id="b6d09-112">打开应用程序绑定文件：</span><span class="sxs-lookup"><span data-stu-id="b6d09-112">Open the application binding file:</span></span>

    ![打开绑定文件](../core/media/biztalk-feature-pack-1-binding-1.png)

2. <span data-ttu-id="b6d09-114">查找你想要更改的元素：</span><span class="sxs-lookup"><span data-stu-id="b6d09-114">Find the element you want to change:</span></span>

    ![选择的元素](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. <span data-ttu-id="b6d09-116">删除的填充的值，并将其与你变量： `$(YourValue)`。</span><span class="sxs-lookup"><span data-stu-id="b6d09-116">Remove the populated value, and replace it with you variables: `$(YourValue)`.</span></span> <span data-ttu-id="b6d09-117">例如，输入`$(SendPort1)`:</span><span class="sxs-lookup"><span data-stu-id="b6d09-117">For example, enter `$(SendPort1)`:</span></span> 

    ![绑定文件](../core/media/biztalk-feature-pack-1-binding-3.png)

4. <span data-ttu-id="b6d09-119">完成后，保存该绑定文件，并将其添加到 JSON 生成模板 (中的步骤[步骤 1： 添加应用程序项目 （&） 更新.json 模板](feature-pack-add-application-project.md))。</span><span class="sxs-lookup"><span data-stu-id="b6d09-119">When done, save the binding file, and add it to your JSON build template (steps in [Step 1: Add Application project & update .json template](feature-pack-add-application-project.md)).</span></span>

## <a name="create-the-variables-in-vsts"></a><span data-ttu-id="b6d09-120">在 VSTS 中创建变量</span><span class="sxs-lookup"><span data-stu-id="b6d09-120">Create the variables in VSTS</span></span>

1. <span data-ttu-id="b6d09-121">在你的 VSTS 帐户，选择**生成和发布**，然后选择**版本**。</span><span class="sxs-lookup"><span data-stu-id="b6d09-121">In your VSTS account, select **Build and release**, and select **Releases**.</span></span>

2. <span data-ttu-id="b6d09-122">选择你**释放定义**，然后选择**变量**:</span><span class="sxs-lookup"><span data-stu-id="b6d09-122">Select your **Release definition**, and select **Variables**:</span></span>  

    ![绑定文件](../core/media/vsts-release-variables.png)

3. <span data-ttu-id="b6d09-124">选择**添加**，并创建的变量的名称和值：</span><span class="sxs-lookup"><span data-stu-id="b6d09-124">Select **Add**, and create the variable names and values:</span></span>   

    ![配置变量](../core/media/environment-specific-variables.png)

4. <span data-ttu-id="b6d09-126">**保存**所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b6d09-126">**Save** your changes.</span></span> <span data-ttu-id="b6d09-127">当启动部署时，会将值添加从绑定文件。</span><span class="sxs-lookup"><span data-stu-id="b6d09-127">When the deploy is initiated, the values are added from the binding file.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6d09-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6d09-128">See also</span></span>
[<span data-ttu-id="b6d09-129">使用 Visual Studio Team Services 中配置自动部署</span><span class="sxs-lookup"><span data-stu-id="b6d09-129">Configure automatic deployment with Visual Studio Team Services</span></span>](configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  
[<span data-ttu-id="b6d09-130">配置功能包</span><span class="sxs-lookup"><span data-stu-id="b6d09-130">Configure the feature pack</span></span>](configure-the-feature-pack.md)