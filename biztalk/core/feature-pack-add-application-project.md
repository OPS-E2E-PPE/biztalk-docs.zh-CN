---
title: "步骤 1-添加应用程序项目和更新 json |Microsoft 文档"
description: "将 BizTalk Server 应用程序项目添加在 Visual Studio 中，并使用的 Dll，绑定文件和应用程序的 Visual Studio Team Services 的部署序列更新 BizTalkServerInventory.json 文件"
ms.custom: 
ms.date: 11/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46cb8a2072280e62cd8c3438521531f8cf3b55aa
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a><span data-ttu-id="3df80-103">步骤 1： 在 Visual Studio 中添加 BizTalk Server 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="3df80-103">Step 1: Add the BizTalk Server Application project in Visual Studio</span></span>

<span data-ttu-id="3df80-104">生成你的应用程序使用 Visual Studio Team Services 时，BizTalk 项目创建新的文件是 –.btaproj。</span><span class="sxs-lookup"><span data-stu-id="3df80-104">When you build your applications using Visual Studio Team Services, a new BizTalk project file is created – .btaproj.</span></span> <span data-ttu-id="3df80-105">此新项目包含所有 BizTalk 应用程序生成和部署使用 VSTS 生成和发布功能。</span><span class="sxs-lookup"><span data-stu-id="3df80-105">This new project holds all the BizTalk applications that you build and deploy using the VSTS build and release features.</span></span> 

<span data-ttu-id="3df80-106">BizTalk 应用程序项目包含`BizTalkServerInventory.json`文件。</span><span class="sxs-lookup"><span data-stu-id="3df80-106">The BizTalk Application Project includes the `BizTalkServerInventory.json` file.</span></span> <span data-ttu-id="3df80-107">在此文件中，添加你的 BizTalk 程序集、 添加 BizTalk 应用程序时，绑定文件，然后设置的部署序列。</span><span class="sxs-lookup"><span data-stu-id="3df80-107">In this file, add your BizTalk assemblies, add the binding files for your BizTalk application, and then set a deployment sequence.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="3df80-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="3df80-108">Before you begin</span></span>

* <span data-ttu-id="3df80-109">这些步骤假定你的一个现有的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="3df80-109">These steps assume you have an existing BizTalk project.</span></span> <span data-ttu-id="3df80-110">如果没有，则可以使用 HelloWorld SDK 示例 (\Program Files (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld)。</span><span class="sxs-lookup"><span data-stu-id="3df80-110">If not, you can use the HelloWorld SDK sample (\Program Files (x86)\Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld).</span></span> 
* <span data-ttu-id="3df80-111">到 XML 绑定文件到你的 BizTalk 项目准备具有路径。</span><span class="sxs-lookup"><span data-stu-id="3df80-111">Have the path to the XML binding file to your BizTalk project ready.</span></span> 
* <span data-ttu-id="3df80-112">知道你的 VSTS 帐户、 你的集合和你团队项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3df80-112">Know your VSTS account, your collection, and your team project details.</span></span>
* <span data-ttu-id="3df80-113">熟悉 git 概念，包括克隆和使用存储库。</span><span class="sxs-lookup"><span data-stu-id="3df80-113">Be familiar with git concepts, including cloning and working with repositories.</span></span> 
* <span data-ttu-id="3df80-114">请确保[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)安装</span><span class="sxs-lookup"><span data-stu-id="3df80-114">Be sure [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) is installed</span></span>

## <a name="add-the-application-project"></a><span data-ttu-id="3df80-115">添加应用程序项目</span><span class="sxs-lookup"><span data-stu-id="3df80-115">Add the application project</span></span>

1. <span data-ttu-id="3df80-116">在 BizTalk Server 中，在 Visual Studio 中打开你的解决方案 (ProjectName.sln)。</span><span class="sxs-lookup"><span data-stu-id="3df80-116">On the BizTalk Server, open your solution (ProjectName.sln) in Visual Studio.</span></span> <span data-ttu-id="3df80-117">不要选择 Visual Studio Blend。</span><span class="sxs-lookup"><span data-stu-id="3df80-117">Do not select Visual Studio Blend.</span></span>

2. <span data-ttu-id="3df80-118">在解决方案资源管理器，右键单击你的项目，然后选择**生成**。</span><span class="sxs-lookup"><span data-stu-id="3df80-118">In solution explorer, right-click your project, and select **Build**.</span></span> <span data-ttu-id="3df80-119">请确保你的生成成功。</span><span class="sxs-lookup"><span data-stu-id="3df80-119">Be sure your build succeeds.</span></span> <span data-ttu-id="3df80-120">右键单击你的项目，然后选择**部署**。</span><span class="sxs-lookup"><span data-stu-id="3df80-120">Right-click your project, and select **Deploy**.</span></span> <span data-ttu-id="3df80-121">请确保你部署成功。</span><span class="sxs-lookup"><span data-stu-id="3df80-121">Be sure your deploy succeeds.</span></span>

3. <span data-ttu-id="3df80-122">右键单击你的解决方案，选择**添加**，然后选择**添加新项目**。</span><span class="sxs-lookup"><span data-stu-id="3df80-122">Right-click your solution, select **Add**, and select **Add New Project**.</span></span>

4. <span data-ttu-id="3df80-123">选择**BizTalk 项目**选项卡上，选择**.NET Framework 4.6.1**从该下拉列表中，并选择**BizTalk 服务器应用程序项目**。</span><span class="sxs-lookup"><span data-stu-id="3df80-123">Select the **BizTalk Projects** tab, select **.NET Framework 4.6.1** from the drop-down list, and select **BizTalk Server Application Project**.</span></span> <span data-ttu-id="3df80-124">输入名称 (例如 appProjectHelloWorld)，并选择**确定**:</span><span class="sxs-lookup"><span data-stu-id="3df80-124">Enter a name (e.g. appProjectHelloWorld), and select **OK**:</span></span>  

    ![添加应用程序项目](../core/media/add-application-project.png)

5. <span data-ttu-id="3df80-126">在解决方案资源管理器，右键单击新添加的应用程序项目 (.btaproj) 中，选择**添加**，选择**引用**。</span><span class="sxs-lookup"><span data-stu-id="3df80-126">In Solution Explorer, right-click your newly-added application project (.btaproj), select **Add**, select **Reference**.</span></span> <span data-ttu-id="3df80-127">展开**项目**选项卡，然后选中你的 BizTalk 项目 （你部署使用 VSTS 是项目）。</span><span class="sxs-lookup"><span data-stu-id="3df80-127">Expand the **Projects** tab, and check your BizTalk project (the project you are deploying using VSTS).</span></span> <span data-ttu-id="3df80-128">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="3df80-128">Select **OK**.</span></span>  
    <span data-ttu-id="3df80-129">添加后，展开**引用**你应用程序的项目 (例如 appProjectHelloWorld) 若要查看 BizTalk 项目下你刚添加。</span><span class="sxs-lookup"><span data-stu-id="3df80-129">Once added, expand **References** under your application project (e.g. appProjectHelloWorld) to see the BizTalk project you just added.</span></span> 

6. <span data-ttu-id="3df80-130">在解决方案资源管理器，右键单击你的应用程序项目 (.btaproj) 中，选择**添加**，选择**现有项**，和**添加**你绑定的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="3df80-130">In Solution Explorer, right-click your application project (.btaproj), select **Add**, select **Existing Item**, and **Add** your binding XML file.</span></span>

7. <span data-ttu-id="3df80-131">打开 binding.xml 的属性并设置**复制到输出目录**到**始终复制**。</span><span class="sxs-lookup"><span data-stu-id="3df80-131">Open the properties of binding.xml, and set **Copy to Output Directory** to **Copy always**.</span></span> <span data-ttu-id="3df80-132">**保存**所做的更改：</span><span class="sxs-lookup"><span data-stu-id="3df80-132">**Save** your changes:</span></span>  

    ![绑定文件属性](../core/media/xml-binding-file-properties.png)


## <a name="configure-the-json-template"></a><span data-ttu-id="3df80-134">配置的 JSON 模板</span><span class="sxs-lookup"><span data-stu-id="3df80-134">Configure the JSON template</span></span>

1. <span data-ttu-id="3df80-135">在 Visual Studio 中，在应用程序项目 (.btaproj) 打开`BizTalkServerInventory.json`文件。</span><span class="sxs-lookup"><span data-stu-id="3df80-135">In Visual Studio, in your application project (.btaproj), open the `BizTalkServerInventory.json` file.</span></span> 

2. <span data-ttu-id="3df80-136">该模板包括以下各节：</span><span class="sxs-lookup"><span data-stu-id="3df80-136">The template includes the following sections:</span></span> 

    | | |
    |---|---|
    |<span data-ttu-id="3df80-137">BizTalkAssemblies</span><span class="sxs-lookup"><span data-stu-id="3df80-137">BizTalkAssemblies</span></span> | <span data-ttu-id="3df80-138">在应用程序中使用的程序集</span><span class="sxs-lookup"><span data-stu-id="3df80-138">The assemblies used in your applications</span></span> |
    |<span data-ttu-id="3df80-139">BindingFiles</span><span class="sxs-lookup"><span data-stu-id="3df80-139">BindingFiles</span></span> | <span data-ttu-id="3df80-140">你正在引用绑定文件</span><span class="sxs-lookup"><span data-stu-id="3df80-140">The binding files you are referencing</span></span>|
    |<span data-ttu-id="3df80-141">DeploymentSequence</span><span class="sxs-lookup"><span data-stu-id="3df80-141">DeploymentSequence</span></span> | <span data-ttu-id="3df80-142">若要安装的元素序列</span><span class="sxs-lookup"><span data-stu-id="3df80-142">The sequence for the elements to be installed</span></span>|
    
    <span data-ttu-id="3df80-143">示例模板：</span><span class="sxs-lookup"><span data-stu-id="3df80-143">Sample template:</span></span> 
    
    ![FP1 Json 模板图像 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > <span data-ttu-id="3df80-145">根据你的解决方案的复杂性，必须在此 JSON 模板文件中引用您要在生成中的元素。</span><span class="sxs-lookup"><span data-stu-id="3df80-145">Depending on the complexity of your solution, the elements you want in the build must be referenced in this JSON template file.</span></span>

3. <span data-ttu-id="3df80-146">在`BizTalkAssemblies`，添加你的 BizTalk 项目使用的程序集：</span><span class="sxs-lookup"><span data-stu-id="3df80-146">In `BizTalkAssemblies`, add the assemblies used by your BizTalk project:</span></span> 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName"
            "Path": "PathToAssembly
        }
    ]
    ```

4. <span data-ttu-id="3df80-147">在`BindingsFiles`，添加你的 BizTalk 项目的绑定文件：</span><span class="sxs-lookup"><span data-stu-id="3df80-147">In `BindingsFiles`, add the binding files for your BizTalk project:</span></span> 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name"
            "Path": "PathToBindingFile
        }
    ]
    ```

5. <span data-ttu-id="3df80-148">在`DeploymentSequence`，将应用程序名称添加你希望他们部署，并在上安装的顺序[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3df80-148">In `DeploymentSequence`, add the application names in the order you want them deployed, and installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span></span> 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```


6. <span data-ttu-id="3df80-149">**保存**所做的更改。</span><span class="sxs-lookup"><span data-stu-id="3df80-149">**Save** your changes.</span></span> <span data-ttu-id="3df80-150">完成后，如下所示.json 文件：</span><span class="sxs-lookup"><span data-stu-id="3df80-150">When finished, your .json file looks like the following:</span></span> 

    ```
    {
      "$schema": "C:\\Program Files (x86)\\Microsoft BizTalk Server 2016\\Developer Tools\\BizTalkServerAppplicationSchema.json",
      "BizTalkAssemblies": [
        {
          "Name": "HelloWorld",
          "Path": "HelloWorld\\bin\\Release\\HelloWorld.dll"
        }
      ],
      "BindingsFiles": [
        {
          "Name": "HelloWorldBinding",
          "Path": "HelloWorld\\HelloWorldBinding.xml"
        }
      ],
      "DeploymentSequence": [
        "HelloWorld", "HelloWorldBinding"
      ]
    }
    ```

7. <span data-ttu-id="3df80-151">**可选**。</span><span class="sxs-lookup"><span data-stu-id="3df80-151">**Optional**.</span></span> <span data-ttu-id="3df80-152">右键单击你的应用程序项目 (例如 appProjectHelloWorld)，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="3df80-152">Right-click your application project (e.g. appProjectHelloWorld), and select **Properties**.</span></span> <span data-ttu-id="3df80-153">你可以将调试或发布版本设置为新值。</span><span class="sxs-lookup"><span data-stu-id="3df80-153">You can set the Debug or Release version to a new value.</span></span> <span data-ttu-id="3df80-154">我们不在这些步骤中，但请注意你可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3df80-154">We don’t in these steps, but be aware you can do this.</span></span>  

    ![设置调试或发布版本](../core/media/application-project-version.png)

8. <span data-ttu-id="3df80-156">右键单击你的应用程序项目 (例如 appProjectHelloWorld)，然后选择**生成**。</span><span class="sxs-lookup"><span data-stu-id="3df80-156">Right-click your application project (e.g. appProjectHelloWorld), and select **Build**.</span></span> <span data-ttu-id="3df80-157">如果成功，在中创建的 zip 文件 ***yourApplicationProject*\bin\debug**文件夹：</span><span class="sxs-lookup"><span data-stu-id="3df80-157">If it succeeds, a zip file is created in ***yourApplicationProject*\bin\debug** folder:</span></span>  

    ![生成的 zip 文件](../core/media/application-project-zip-file.png)

9. <span data-ttu-id="3df80-159">选择你的解决方案，然后选择**团队资源管理器**选项卡。在 VSTS 下, 选择**连接**。</span><span class="sxs-lookup"><span data-stu-id="3df80-159">Select your solution, and select the **Team Explorer** tab. Under VSTS, select **Connect**.</span></span>  

    ![连接到 Team Services](../core/media/connect-team-services.png)

10. <span data-ttu-id="3df80-161">选择你的 VSTS 帐户、 你的集合和你的团队项目。</span><span class="sxs-lookup"><span data-stu-id="3df80-161">Select your VSTS account, your collection, and your team project.</span></span> <span data-ttu-id="3df80-162">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="3df80-162">Select **OK**.</span></span> <span data-ttu-id="3df80-163">如果你未尚未创建 VSTS 帐户，然后创建一个 ([步骤 2： 创建 VSTS 令牌](feature-pack-create-vsts-token.md)提供了一些指导)。</span><span class="sxs-lookup"><span data-stu-id="3df80-163">If you didn’t create a VSTS account yet, then create one ([Step 2: Create the VSTS token](feature-pack-create-vsts-token.md) provides some guidance).</span></span> <span data-ttu-id="3df80-164">一旦创建，回到此步骤中，并连接。</span><span class="sxs-lookup"><span data-stu-id="3df80-164">Once it's created, come back to this step, and connect.</span></span>  

    ![选择你的集合和项目](../core/media/team-collections-projects.png)

11. <span data-ttu-id="3df80-166">连接时，可能会收到克隆此存储库的提示。</span><span class="sxs-lookup"><span data-stu-id="3df80-166">When you connect, you may get a prompt to clone this repository.</span></span> <span data-ttu-id="3df80-167">选择**克隆此存储库**链接。</span><span class="sxs-lookup"><span data-stu-id="3df80-167">Select the **Clone this repository** link.</span></span>  

    ![克隆存储库](../core/media/vsts-clone-repository.png)

12. <span data-ttu-id="3df80-169">记下的 URL 和路径，然后选择**克隆**:</span><span class="sxs-lookup"><span data-stu-id="3df80-169">Note the URL and paths, and select **Clone**:</span></span>  

    ![存储库路径](../core/media/clone-repo-paths.png)

<span data-ttu-id="3df80-171">完成后，Visual Studio 团队服务部署任务服从所需的文件和安装序列。</span><span class="sxs-lookup"><span data-stu-id="3df80-171">Once completed, the Visual Studio Team Service deployment task honors the required files and the install sequence.</span></span> 

> [!TIP]
> <span data-ttu-id="3df80-172">如果之后在 git 中克隆到你的项目中进行了更改，则可以**阶段**所做的更改，然后**推送**，Visual Studio 中的所有。</span><span class="sxs-lookup"><span data-stu-id="3df80-172">If you make changes to your project after you clone in git, you can **Stage** your changes, and then **Push**, all within Visual Studio.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="3df80-173">您进行的操作</span><span class="sxs-lookup"><span data-stu-id="3df80-173">What you did</span></span>

<span data-ttu-id="3df80-174">在 BizTalk 项目中，添加了 BizTalk 应用程序项目 (.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="3df80-174">In your BizTalk project, you added a BizTalk Application project (.btaproj).</span></span> <span data-ttu-id="3df80-175">此项目使用自动完成部署使用 VSTS 你 BizTalk Server 项目。</span><span class="sxs-lookup"><span data-stu-id="3df80-175">This project is used to automate deployments of your BizTalk Server projects using VSTS.</span></span> <span data-ttu-id="3df80-176">创建应用程序项目后，你将添加到你的 BizTalk 应用程序项目的引用。</span><span class="sxs-lookup"><span data-stu-id="3df80-176">After you created the application project, you added a reference to your BizTalk application project.</span></span> <span data-ttu-id="3df80-177">然后，您将更新一个 JSON 文件，告知在自动的部署，若要部署，若要使用，哪些绑定文件哪些 Dll 和部署应用程序的顺序。</span><span class="sxs-lookup"><span data-stu-id="3df80-177">Then, you updated a JSON file that tells the automated deployment what DLLs to deploy, which binding file to use, and the order to deploy the applications.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="3df80-178">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3df80-178">Next steps</span></span>
[<span data-ttu-id="3df80-179">步骤 2： 创建 VSTS 令牌</span><span class="sxs-lookup"><span data-stu-id="3df80-179">Step 2: Create the VSTS token</span></span>](feature-pack-create-vsts-token.md)  
[<span data-ttu-id="3df80-180">步骤 3： 创建构建并发布定义</span><span class="sxs-lookup"><span data-stu-id="3df80-180">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="3df80-181">配置环境的令牌和变量</span><span class="sxs-lookup"><span data-stu-id="3df80-181">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)