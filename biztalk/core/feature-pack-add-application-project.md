---
title: 步骤 1-添加应用程序项目并更新 json |Microsoft Docs
description: 将 BizTalk Server 应用程序项目添加在 Visual Studio 中，并更新 BizTalkServerInventory.json 文件与 Dll、 绑定文件和应用程序的 Visual Studio Team Services 的部署序列
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0230d0b280be412e3138ffbafd83d3810cf1163
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826357"
---
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a><span data-ttu-id="60f88-103">步骤 1： 在 Visual Studio 中添加 BizTalk Server 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="60f88-103">Step 1: Add the BizTalk Server Application project in Visual Studio</span></span>

<span data-ttu-id="60f88-104">生成使用 Visual Studio Team Services 在应用程序时，新的 BizTalk 项目文件创建 –.btaproj。</span><span class="sxs-lookup"><span data-stu-id="60f88-104">When you build your applications using Visual Studio Team Services, a new BizTalk project file is created – .btaproj.</span></span> <span data-ttu-id="60f88-105">此新项目将包含所有 BizTalk 应用程序生成和部署使用 VSTS 生成和发布功能。</span><span class="sxs-lookup"><span data-stu-id="60f88-105">This new project holds all the BizTalk applications that you build and deploy using the VSTS build and release features.</span></span> 

<span data-ttu-id="60f88-106">BizTalk 应用程序项目包含`BizTalkServerInventory.json`文件。</span><span class="sxs-lookup"><span data-stu-id="60f88-106">The BizTalk Application Project includes the `BizTalkServerInventory.json` file.</span></span> <span data-ttu-id="60f88-107">此文件中添加 BizTalk 程序集、 添加 BizTalk 应用程序，绑定文件，然后设置部署序列。</span><span class="sxs-lookup"><span data-stu-id="60f88-107">In this file, add your BizTalk assemblies, add the binding files for your BizTalk application, and then set a deployment sequence.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="60f88-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="60f88-108">Before you begin</span></span>

* <span data-ttu-id="60f88-109">这些步骤假定你有现有的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="60f88-109">These steps assume you have an existing BizTalk project.</span></span> <span data-ttu-id="60f88-110">如果没有设置，可以使用 HelloWorld SDK 示例 (\Program 文件 (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld)。</span><span class="sxs-lookup"><span data-stu-id="60f88-110">If not, you can use the HelloWorld SDK sample (\Program Files (x86)\Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld).</span></span> 
* <span data-ttu-id="60f88-111">具有到向 BizTalk 项目准备就绪的 XML 绑定文件的路径。</span><span class="sxs-lookup"><span data-stu-id="60f88-111">Have the path to the XML binding file to your BizTalk project ready.</span></span> 
* <span data-ttu-id="60f88-112">知道你的 VSTS 帐户、 你的集合，以及你团队项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="60f88-112">Know your VSTS account, your collection, and your team project details.</span></span>
* <span data-ttu-id="60f88-113">已经熟悉 git 概念，包括克隆和使用存储库。</span><span class="sxs-lookup"><span data-stu-id="60f88-113">Be familiar with git concepts, including cloning and working with repositories.</span></span> 
* <span data-ttu-id="60f88-114">请务必[功能包 2](https://aka.ms/bts2016fp2)安装。</span><span class="sxs-lookup"><span data-stu-id="60f88-114">Be sure [Feature Pack 2](https://aka.ms/bts2016fp2) is installed.</span></span>

## <a name="add-the-application-project"></a><span data-ttu-id="60f88-115">添加应用程序项目</span><span class="sxs-lookup"><span data-stu-id="60f88-115">Add the application project</span></span>

1. <span data-ttu-id="60f88-116">在 BizTalk 服务器上，在 Visual Studio 中打开解决方案 (ProjectName.sln)。</span><span class="sxs-lookup"><span data-stu-id="60f88-116">On the BizTalk Server, open your solution (ProjectName.sln) in Visual Studio.</span></span> <span data-ttu-id="60f88-117">不要选择 Visual Studio Blend。</span><span class="sxs-lookup"><span data-stu-id="60f88-117">Do not select Visual Studio Blend.</span></span>

2. <span data-ttu-id="60f88-118">在解决方案资源管理器，右键单击你的项目，然后选择**生成**。</span><span class="sxs-lookup"><span data-stu-id="60f88-118">In solution explorer, right-click your project, and select **Build**.</span></span> <span data-ttu-id="60f88-119">请确保你的生成成功。</span><span class="sxs-lookup"><span data-stu-id="60f88-119">Be sure your build succeeds.</span></span> <span data-ttu-id="60f88-120">右键单击你的项目，然后选择**部署**。</span><span class="sxs-lookup"><span data-stu-id="60f88-120">Right-click your project, and select **Deploy**.</span></span> <span data-ttu-id="60f88-121">请确保在部署成功。</span><span class="sxs-lookup"><span data-stu-id="60f88-121">Be sure your deploy succeeds.</span></span>

3. <span data-ttu-id="60f88-122">右键单击你的解决方案，选择**外**，然后选择**添加新项目**。</span><span class="sxs-lookup"><span data-stu-id="60f88-122">Right-click your solution, select **Add**, and select **Add New Project**.</span></span>

4. <span data-ttu-id="60f88-123">选择**BizTalk 项目**选项卡上，选择 **.NET Framework 4.6.1**从该下拉列表中，然后选择**BizTalk Server 应用程序项目**。</span><span class="sxs-lookup"><span data-stu-id="60f88-123">Select the **BizTalk Projects** tab, select **.NET Framework 4.6.1** from the drop-down list, and select **BizTalk Server Application Project**.</span></span> <span data-ttu-id="60f88-124">输入名称 (例如 appProjectHelloWorld)，并选择**确定**:</span><span class="sxs-lookup"><span data-stu-id="60f88-124">Enter a name (e.g. appProjectHelloWorld), and select **OK**:</span></span>  

    ![添加应用程序项目](../core/media/add-application-project.png)

5. <span data-ttu-id="60f88-126">在解决方案资源管理器中右键单击新添加的应用程序项目 (.btaproj) 中，选择**外**，选择**引用**。</span><span class="sxs-lookup"><span data-stu-id="60f88-126">In Solution Explorer, right-click your newly-added application project (.btaproj), select **Add**, select **Reference**.</span></span> <span data-ttu-id="60f88-127">展开**项目**选项卡，然后检查您的 BizTalk 项目 （在使用 VSTS 部署是项目）。</span><span class="sxs-lookup"><span data-stu-id="60f88-127">Expand the **Projects** tab, and check your BizTalk project (the project you are deploying using VSTS).</span></span> <span data-ttu-id="60f88-128">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="60f88-128">Select **OK**.</span></span>  
    <span data-ttu-id="60f88-129">添加后，展开**引用**应用程序项目 (例如 appProjectHelloWorld) 若要查看 BizTalk 项目下你刚添加。</span><span class="sxs-lookup"><span data-stu-id="60f88-129">Once added, expand **References** under your application project (e.g. appProjectHelloWorld) to see the BizTalk project you just added.</span></span> 

6. <span data-ttu-id="60f88-130">在解决方案资源管理器中右键单击你的应用程序项目 (.btaproj) 中，选择**外**，选择**现有项**，并**添加**绑定 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="60f88-130">In Solution Explorer, right-click your application project (.btaproj), select **Add**, select **Existing Item**, and **Add** your binding XML file.</span></span>

7. <span data-ttu-id="60f88-131">打开 binding.xml 的属性，并设置**复制到输出目录**到**始终复制**。</span><span class="sxs-lookup"><span data-stu-id="60f88-131">Open the properties of binding.xml, and set **Copy to Output Directory** to **Copy always**.</span></span> <span data-ttu-id="60f88-132">**保存**所做的更改：</span><span class="sxs-lookup"><span data-stu-id="60f88-132">**Save** your changes:</span></span>  

    ![绑定文件属性](../core/media/xml-binding-file-properties.png)

8. <span data-ttu-id="60f88-134">可选。</span><span class="sxs-lookup"><span data-stu-id="60f88-134">Optional.</span></span> <span data-ttu-id="60f88-135">右键单击新添加的应用程序项目，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="60f88-135">Right-click your newly-added application project, and select **Properties**.</span></span> <span data-ttu-id="60f88-136">自定义**应用程序名称**想要显示在 BizTalk 管理：</span><span class="sxs-lookup"><span data-stu-id="60f88-136">Customize the **Application Name** you want displayed in BizTalk Administration:</span></span>  

    ![应用程序名称](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a><span data-ttu-id="60f88-138">配置 JSON 模板</span><span class="sxs-lookup"><span data-stu-id="60f88-138">Configure the JSON template</span></span>

1. <span data-ttu-id="60f88-139">在 Visual Studio 中，在应用程序项目 (.btaproj) 打开`BizTalkServerInventory.json`文件。</span><span class="sxs-lookup"><span data-stu-id="60f88-139">In Visual Studio, in your application project (.btaproj), open the `BizTalkServerInventory.json` file.</span></span> 

2. <span data-ttu-id="60f88-140">该模板包括以下各节：</span><span class="sxs-lookup"><span data-stu-id="60f88-140">The template includes the following sections:</span></span> 

    | | |
    |---|---|
    |<span data-ttu-id="60f88-141">BizTalkAssemblies</span><span class="sxs-lookup"><span data-stu-id="60f88-141">BizTalkAssemblies</span></span> | <span data-ttu-id="60f88-142">在应用程序中使用的程序集</span><span class="sxs-lookup"><span data-stu-id="60f88-142">The assemblies used in your applications</span></span> |
    |<span data-ttu-id="60f88-143">BindingFiles</span><span class="sxs-lookup"><span data-stu-id="60f88-143">BindingFiles</span></span> | <span data-ttu-id="60f88-144">所引用的绑定文件</span><span class="sxs-lookup"><span data-stu-id="60f88-144">The binding files you are referencing</span></span>|
    |<span data-ttu-id="60f88-145">DeploymentSequence</span><span class="sxs-lookup"><span data-stu-id="60f88-145">DeploymentSequence</span></span> | <span data-ttu-id="60f88-146">若要安装的元素序列</span><span class="sxs-lookup"><span data-stu-id="60f88-146">The sequence for the elements to be installed</span></span>|
    
    <span data-ttu-id="60f88-147">示例模板：</span><span class="sxs-lookup"><span data-stu-id="60f88-147">Sample template:</span></span> 
    
    ![FP1 Json 模板图像 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > <span data-ttu-id="60f88-149">具体取决于解决方案的复杂性，你想在生成中的元素必须引用此 JSON 模板文件中。</span><span class="sxs-lookup"><span data-stu-id="60f88-149">Depending on the complexity of your solution, the elements you want in the build must be referenced in this JSON template file.</span></span>

3. <span data-ttu-id="60f88-150">在`BizTalkAssemblies`，添加您的 BizTalk 项目使用的程序集：</span><span class="sxs-lookup"><span data-stu-id="60f88-150">In `BizTalkAssemblies`, add the assemblies used by your BizTalk project:</span></span> 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName",
            "Path": "PathToAssembly
        }
    ]
    ```

4. <span data-ttu-id="60f88-151">在`BindingsFiles`，添加您的 BizTalk 项目的绑定文件：</span><span class="sxs-lookup"><span data-stu-id="60f88-151">In `BindingsFiles`, add the binding files for your BizTalk project:</span></span> 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name",
            "Path": "PathToBindingFile
        }
    ]
    ```

5. <span data-ttu-id="60f88-152">在中`DeploymentSequence`，用所需部署，并在安装它们的顺序添加应用程序名称[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="60f88-152">In `DeploymentSequence`, add the application names in the order you want them deployed, and installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span></span> 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```


6. <span data-ttu-id="60f88-153">**保存**所做的更改。</span><span class="sxs-lookup"><span data-stu-id="60f88-153">**Save** your changes.</span></span> <span data-ttu-id="60f88-154">完成后，你的.json 文件看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="60f88-154">When finished, your .json file looks like the following:</span></span> 

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

7. <span data-ttu-id="60f88-155">**可选**。</span><span class="sxs-lookup"><span data-stu-id="60f88-155">**Optional**.</span></span> <span data-ttu-id="60f88-156">右键单击你的应用程序项目 (例如 appProjectHelloWorld)，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="60f88-156">Right-click your application project (e.g. appProjectHelloWorld), and select **Properties**.</span></span> <span data-ttu-id="60f88-157">为新值，可以设置调试或发布版本。</span><span class="sxs-lookup"><span data-stu-id="60f88-157">You can set the Debug or Release version to a new value.</span></span> <span data-ttu-id="60f88-158">我们不在这些步骤，但请注意你可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="60f88-158">We don’t in these steps, but be aware you can do this.</span></span>  

    ![设置调试或发布版本](../core/media/application-project-version.png)

8. <span data-ttu-id="60f88-160">右键单击你的应用程序项目 (例如 appProjectHelloWorld)，然后选择**生成**。</span><span class="sxs-lookup"><span data-stu-id="60f88-160">Right-click your application project (e.g. appProjectHelloWorld), and select **Build**.</span></span> <span data-ttu-id="60f88-161">如果成功，在中创建的 zip 文件 **_yourApplicationProject_\bin\debug**文件夹：</span><span class="sxs-lookup"><span data-stu-id="60f88-161">If it succeeds, a zip file is created in **_yourApplicationProject_\bin\debug** folder:</span></span>  

    ![生成的 zip 文件](../core/media/application-project-zip-file.png)

9. <span data-ttu-id="60f88-163">选择你的解决方案，然后选择**团队资源管理器**选项卡。在 VSTS 中，选择**Connect**。</span><span class="sxs-lookup"><span data-stu-id="60f88-163">Select your solution, and select the **Team Explorer** tab. Under VSTS, select **Connect**.</span></span>  

    ![连接到 Team Services](../core/media/connect-team-services.png)

10. <span data-ttu-id="60f88-165">选择你的 VSTS 帐户、 你的集合和你的团队项目。</span><span class="sxs-lookup"><span data-stu-id="60f88-165">Select your VSTS account, your collection, and your team project.</span></span> <span data-ttu-id="60f88-166">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="60f88-166">Select **OK**.</span></span> <span data-ttu-id="60f88-167">如果未尚未创建 VSTS 帐户，然后创建一个 ([步骤 2： 创建 VSTS 令牌](feature-pack-create-vsts-token.md)提供一些指导)。</span><span class="sxs-lookup"><span data-stu-id="60f88-167">If you didn’t create a VSTS account yet, then create one ([Step 2: Create the VSTS token](feature-pack-create-vsts-token.md) provides some guidance).</span></span> <span data-ttu-id="60f88-168">在创建后回到此步骤中，并连接。</span><span class="sxs-lookup"><span data-stu-id="60f88-168">Once it's created, come back to this step, and connect.</span></span>  

    ![选择集合和项目](../core/media/team-collections-projects.png)

11. <span data-ttu-id="60f88-170">连接时，可能会收到提示克隆此存储库。</span><span class="sxs-lookup"><span data-stu-id="60f88-170">When you connect, you may get a prompt to clone this repository.</span></span> <span data-ttu-id="60f88-171">选择**克隆此存储库**链接。</span><span class="sxs-lookup"><span data-stu-id="60f88-171">Select the **Clone this repository** link.</span></span>  

    ![克隆存储库](../core/media/vsts-clone-repository.png)

12. <span data-ttu-id="60f88-173">记下的 URL 和路径，然后选择**克隆**:</span><span class="sxs-lookup"><span data-stu-id="60f88-173">Note the URL and paths, and select **Clone**:</span></span>  

    ![存储库路径](../core/media/clone-repo-paths.png)

<span data-ttu-id="60f88-175">完成后，Visual Studio Team Service 部署任务将具有所需的文件和安装序列。</span><span class="sxs-lookup"><span data-stu-id="60f88-175">Once completed, the Visual Studio Team Service deployment task honors the required files and the install sequence.</span></span> 

> [!TIP]
> <span data-ttu-id="60f88-176">如果之后在 git 中克隆到你的项目进行更改，则可以**阶段**所做的更改，然后**推送**，Visual Studio 内。</span><span class="sxs-lookup"><span data-stu-id="60f88-176">If you make changes to your project after you clone in git, you can **Stage** your changes, and then **Push**, all within Visual Studio.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="60f88-177">用户进行的操作</span><span class="sxs-lookup"><span data-stu-id="60f88-177">What you did</span></span>

<span data-ttu-id="60f88-178">在 BizTalk 项目中，您添加了一个 BizTalk 应用程序项目 (.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="60f88-178">In your BizTalk project, you added a BizTalk Application project (.btaproj).</span></span> <span data-ttu-id="60f88-179">此项目用于自动执行部署的 BizTalk Server 项目使用 VSTS。</span><span class="sxs-lookup"><span data-stu-id="60f88-179">This project is used to automate deployments of your BizTalk Server projects using VSTS.</span></span> <span data-ttu-id="60f88-180">创建应用程序项目后，即添加到 BizTalk 项目的引用。</span><span class="sxs-lookup"><span data-stu-id="60f88-180">After you created the application project, you added a reference to your BizTalk project.</span></span> <span data-ttu-id="60f88-181">然后，您更新的 JSON 文件，告知自动的部署要部署，若要使用，哪些绑定文件的 Dll 和部署应用程序的顺序。</span><span class="sxs-lookup"><span data-stu-id="60f88-181">Then, you updated a JSON file that tells the automated deployment what DLLs to deploy, which binding file to use, and the order to deploy the applications.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="60f88-182">后续步骤</span><span class="sxs-lookup"><span data-stu-id="60f88-182">Next steps</span></span>
[<span data-ttu-id="60f88-183">步骤 2： 创建 VSTS 令牌</span><span class="sxs-lookup"><span data-stu-id="60f88-183">Step 2: Create the VSTS token</span></span>](feature-pack-create-vsts-token.md)  
[<span data-ttu-id="60f88-184">步骤 3： 创建生成和发布定义</span><span class="sxs-lookup"><span data-stu-id="60f88-184">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="60f88-185">配置环境令牌和变量</span><span class="sxs-lookup"><span data-stu-id="60f88-185">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)
