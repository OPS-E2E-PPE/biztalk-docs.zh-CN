---
title: "部署 A4SWIFT 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, A4SWIFT
- deploying, A4SWIFT schemas
- A4SWIFT, deploying schemas
- schemas, deploying
ms.assetid: a6aed2cd-3578-442e-ab1e-8284cc5f7b72
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc89b26d0eee970268d5e9084cd0827d3100fd7b
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="deploying-a4swift-schemas"></a><span data-ttu-id="dffc5-102">部署 A4SWIFT 架构</span><span class="sxs-lookup"><span data-stu-id="dffc5-102">Deploying A4SWIFT Schemas</span></span>
<span data-ttu-id="dffc5-103">你必须部署你想要交换的 SWIFT 消息的架构。</span><span class="sxs-lookup"><span data-stu-id="dffc5-103">You must deploy schemas for the SWIFT messages that you want to exchange.</span></span>  
  
 <span data-ttu-id="dffc5-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="dffc5-104">**Summary**</span></span>  
  
 <span data-ttu-id="dffc5-105">部署以下架构：</span><span class="sxs-lookup"><span data-stu-id="dffc5-105">Deploy the following schemas:</span></span>  
  
-   <span data-ttu-id="dffc5-106">SWIFT 基 Types.xsd</span><span class="sxs-lookup"><span data-stu-id="dffc5-106">SWIFT Base Types.xsd</span></span>  
  
-   <span data-ttu-id="dffc5-107">SWIFT 常见数据 Types.xsd</span><span class="sxs-lookup"><span data-stu-id="dffc5-107">SWIFT Common Data Types.xsd</span></span>  
  
-   <span data-ttu-id="dffc5-108">对于消息类型，例如，MT103.xsd 特定的架构</span><span class="sxs-lookup"><span data-stu-id="dffc5-108">Specific schema for a message type, for example, MT103.xsd</span></span>  
  
### <a name="to-create-a-strong-named-swift-project"></a><span data-ttu-id="dffc5-109">若要创建具有强名称的 SWIFT 项目</span><span class="sxs-lookup"><span data-stu-id="dffc5-109">To create a strong-named SWIFT project</span></span>  
  
1.  <span data-ttu-id="dffc5-110">在 Visual Studio 中，单击**文件**，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-110">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="dffc5-111">在新建项目对话框中，在**项目类型**窗格中，选择**BizTalk 项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="dffc5-111">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  
  
3.  <span data-ttu-id="dffc5-112">在**模板**窗格中，选择**空 BizTalk 服务器项目**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-112">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  
  
4.  <span data-ttu-id="dffc5-113">在**名称**框中，键入所需项目名称的名称。</span><span class="sxs-lookup"><span data-stu-id="dffc5-113">In the **Name** box, type the name you want for the project name.</span></span>  
  
5.  <span data-ttu-id="dffc5-114">在**解决方案**框中，选择**创建新的解决方案**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-114">In the **Solution** box, select **Create new Solution**.</span></span> <span data-ttu-id="dffc5-115">在**位置**框中，输入要添加架构项目到项目的位置。</span><span class="sxs-lookup"><span data-stu-id="dffc5-115">In the **Location** box, enter the location of the project that you are adding the schema project to.</span></span>  
  
6.  <span data-ttu-id="dffc5-116">单击**确定**打开新项目。</span><span class="sxs-lookup"><span data-stu-id="dffc5-116">Click **OK** to open the new project.</span></span>  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="dffc5-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]将新项目添加到解决方案资源管理器，并在指定的文件夹中创建的项目文件夹和文件。</span><span class="sxs-lookup"><span data-stu-id="dffc5-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] adds a new project to Solution Explorer, and creates the project folder and files in the folder specified.</span></span>  
  
7.  <span data-ttu-id="dffc5-118">启动 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="dffc5-118">Start Visual Studio command prompt.</span></span>  
  
8.  <span data-ttu-id="dffc5-119">在 Visual Studio 命令提示符处，浏览到 **\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-119">At the Visual Studio command prompt, browse to **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT**.</span></span>  
  
9. <span data-ttu-id="dffc5-120">在命令提示符处，键入**sn-k key.snk**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="dffc5-120">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="dffc5-121">确保在命令提示符窗口中，该值指示密钥对已写入 key.snk 显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="dffc5-121">Ensure that a message is displayed in the command-prompt window indicating that a key pair was written to key.snk.</span></span>  
  
10. <span data-ttu-id="dffc5-122">在解决方案资源管理器，右键单击你的项目名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-122">In Solution Explorer, right-click your project name, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="dffc5-123">在左窗格中**属性页**对话框中，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-123">In the left pane of the **Property Pages** dialog box, click **Assembly**.</span></span>  
  
12. <span data-ttu-id="dffc5-124">在右窗格中**属性页**对话框中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （） 按钮。</span><span class="sxs-lookup"><span data-stu-id="dffc5-124">In the right pane of the **Property Pages** dialog box, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis () button.</span></span>  
  
13. <span data-ttu-id="dffc5-125">在**程序集密钥文件**对话框中，浏览到 **\<*驱动器*\>: files\microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)]，单击**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-125">In the **Assembly Key File** dialog box, browse to **\<*drive*\>:\Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)], click **key.snk**, and then click **Open**.</span></span>  
  
14. <span data-ttu-id="dffc5-126">在**属性页**对话框中，单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="dffc5-126">In the **Property Pages** dialog box, click **OK** to save your changes.</span></span>  
  
### <a name="to-add-a-swift-schema"></a><span data-ttu-id="dffc5-127">若要添加 SWIFT 架构</span><span class="sxs-lookup"><span data-stu-id="dffc5-127">To add a SWIFT schema</span></span>  
  
1.  <span data-ttu-id="dffc5-128">在解决方案资源管理器的 Visual Studio 中，打开你的项目。</span><span class="sxs-lookup"><span data-stu-id="dffc5-128">In Solution Explorer of Visual Studio, open your project.</span></span>  
  
2.  <span data-ttu-id="dffc5-129">右键单击你的项目，指向 **添加**, ，然后单击 **现有项**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-129">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span>  
  
3.  <span data-ttu-id="dffc5-130">在**添加现有项**对话框中，在:\\**程序 Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT-SRG\<版本\>\Base 架构**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-130">In the **Add Existing Item** dialog box, in the :\\**Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Schemas**.</span></span> <span data-ttu-id="dffc5-131">选择**SWIFT 基 Types.xsd**和**SWIFT 常见数据 Types.xsd**架构，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-131">Select the **SWIFT Base Types.xsd** and **SWIFT Common Data Types.xsd** schemas, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="dffc5-132">右键单击你的项目，指向**添加**，然后单击**添加现有项**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-132">Right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
5.  <span data-ttu-id="dffc5-133">在**添加现有项**对话框中，在**查找**下拉列表框中，移动到**\<驱动器\>: files\microsoft BizTalk Accelerator for SWIFT \<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category n\MTxxx**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-133">In the **Add Existing Item** dialog box, in the **Look in** drop-down box, move to **\<drive\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category n\MTxxx**.</span></span> <span data-ttu-id="dffc5-134">实例选择消息类型，架构**MT103.xsd**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-134">Select a schema for a message type, for instance **MT103.xsd**, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dffc5-135">A4SWIFT 将添加你的项目的架构，如解决方案资源管理器中所示。</span><span class="sxs-lookup"><span data-stu-id="dffc5-135">A4SWIFT adds the schema for your project, as shown in Solution Explorer.</span></span>  
  
6.  <span data-ttu-id="dffc5-136">在解决方案资源管理器，右键单击项目名称，然后单击 **生成**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-136">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
7.  <span data-ttu-id="dffc5-137">在解决方案资源管理器，右键单击项目名称，然后单击 **部署**。</span><span class="sxs-lookup"><span data-stu-id="dffc5-137">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>