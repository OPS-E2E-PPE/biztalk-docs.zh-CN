---
title: 开发活动的先决条件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c91405-f9a4-4676-b5c5-fe90b3b51b45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbc79fd31e78581d98ecad34579958ff90f3b1e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006254"
---
# <a name="prerequisites-for-the-development-activities"></a><span data-ttu-id="77bb4-102">开发活动的先决条件</span><span class="sxs-lookup"><span data-stu-id="77bb4-102">Prerequisites for the Development Activities</span></span>
<span data-ttu-id="77bb4-103">本部分介绍如何准备环境，以完成的一部分包括的开发活动中的步骤[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="77bb4-103">This section describes how to prepare your environment to complete the steps in the development activities that are included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="77bb4-104">你在尝试任何开发活动中的过程之前，请完成以下设置：</span><span class="sxs-lookup"><span data-stu-id="77bb4-104">Complete the following setup before you attempt any of the procedures in the development activities:</span></span>  
  
## <a name="set-up-your-computer-to-perform-the-procedures-in-the-biztalk-esb-toolkit-development-activities"></a><span data-ttu-id="77bb4-105">设置你的计算机以执行 BizTalk ESB 工具包开发活动中的过程</span><span class="sxs-lookup"><span data-stu-id="77bb4-105">Set up your computer to perform the procedures in the BizTalk ESB Toolkit development activities</span></span>  
  
1.  <span data-ttu-id="77bb4-106">安装和部署路线示例应用程序、 动态解析示例应用程序和多个 Web 服务示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="77bb4-106">Install and deploy the Itinerary sample application, the Dynamic Resolution sample application, and the Multiple Web Services sample application.</span></span> <span data-ttu-id="77bb4-107">有关安装和部署这些应用程序的详细信息，请参阅[BizTalk ESB 工具包示例应用程序](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="77bb4-107">For more information about installing and deploying these applications, see [BizTalk ESB Toolkit Sample Applications](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md).</span></span>  
  
2.  <span data-ttu-id="77bb4-108">运行 UDDI 发布服务器实用程序。</span><span class="sxs-lookup"><span data-stu-id="77bb4-108">Run the UDDI Publisher Utility.</span></span>  
  
3.  <span data-ttu-id="77bb4-109">您开发计算机上，在 Windows 资源管理器，创建以下路径：</span><span class="sxs-lookup"><span data-stu-id="77bb4-109">On your development computer, in Windows Explorer, create the following paths:</span></span>  
  
    -   <span data-ttu-id="77bb4-110">C:\HowTos</span><span class="sxs-lookup"><span data-stu-id="77bb4-110">C:\HowTos</span></span>  
  
    -   <span data-ttu-id="77bb4-111">C:\HowTos\Itineraries</span><span class="sxs-lookup"><span data-stu-id="77bb4-111">C:\HowTos\Itineraries</span></span>  
  
    -   <span data-ttu-id="77bb4-112">C:\HowTos\DropFolder</span><span class="sxs-lookup"><span data-stu-id="77bb4-112">C:\HowTos\DropFolder</span></span>  
  
    -   <span data-ttu-id="77bb4-113">C:\HowTos\Out</span><span class="sxs-lookup"><span data-stu-id="77bb4-113">C:\HowTos\Out</span></span>  
  
4.  <span data-ttu-id="77bb4-114">确保您的 BizTalk Server 服务帐户具有**完全控制**到 C:\HowTos 目录结构的权限。</span><span class="sxs-lookup"><span data-stu-id="77bb4-114">Ensure that your BizTalk Server service account has **Full Control** permissions to the C:\HowTos directory structure.</span></span>  
  
5.  <span data-ttu-id="77bb4-115">确保你的 Microsoft BizTalk Server 服务帐户具有**编写**C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out 权限。</span><span class="sxs-lookup"><span data-stu-id="77bb4-115">Ensure that your Microsoft BizTalk Server service account has **Write** permissions to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out.</span></span>  
  
6.  <span data-ttu-id="77bb4-116">将以下的测试消息复制到 C:\HowTos 文件夹：</span><span class="sxs-lookup"><span data-stu-id="77bb4-116">Copy the following test message to the C:\HowTos folder:</span></span>  
  
    -   <span data-ttu-id="77bb4-117">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.xml</span><span class="sxs-lookup"><span data-stu-id="77bb4-117">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.xml</span></span>  
  
7.  <span data-ttu-id="77bb4-118">在 C:\HowTos 文件夹中，创建路线测试客户端应用程序，在以下位置找到的快捷方式：</span><span class="sxs-lookup"><span data-stu-id="77bb4-118">In the C:\HowTos folder, create a shortcut to the Itinerary Test Client application, found at the following location:</span></span>  
  
    -   <span data-ttu-id="77bb4-119">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB。Itinerary.Test\bin\Debug\ESB。Itinerary.Test.exe</span><span class="sxs-lookup"><span data-stu-id="77bb4-119">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug\ESB.Itinerary.Test.exe</span></span>  
  
## <a name="create-the-visual-studio-solution"></a><span data-ttu-id="77bb4-120">创建 Visual Studio 解决方案</span><span class="sxs-lookup"><span data-stu-id="77bb4-120">Create the Visual Studio solution</span></span>  
  
1.  <span data-ttu-id="77bb4-121">在 Visual Studio 中，在文件菜单中，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="77bb4-121">In Visual Studio, on the File menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="77bb4-122">在**新项目**对话框中，在项目类型窗格中，单击**Visual C#**，然后单击**类库**在模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="77bb4-122">In the **New Project** dialog box, in the Project types pane, click **Visual C#**, and then click **Class Library** in the Templates pane.</span></span>  
  
3.  <span data-ttu-id="77bb4-123">在**名称**框中，键入**ItineraryLibrary**。</span><span class="sxs-lookup"><span data-stu-id="77bb4-123">In the **Name** box, type **ItineraryLibrary**.</span></span>  
  
4.  <span data-ttu-id="77bb4-124">在**位置**框中，键入**C:\HowTos**。</span><span class="sxs-lookup"><span data-stu-id="77bb4-124">In the **Location** box, type **C:\HowTos**.</span></span>  
  
5.  <span data-ttu-id="77bb4-125">选择**创建解决方案的目录**复选框。</span><span class="sxs-lookup"><span data-stu-id="77bb4-125">Select the **Create directory for solution** check box.</span></span>  
  
6.  <span data-ttu-id="77bb4-126">在**解决方案名称**框中，键入**模式**，然后单击**确定**以创建解决方案。</span><span class="sxs-lookup"><span data-stu-id="77bb4-126">In the **Solution Name** box, type **Patterns**, and then click **OK** to create the solution.</span></span>  
  
7.  <span data-ttu-id="77bb4-127">删除**Class1.cs**文件从**ItineraryLibrary**项目。</span><span class="sxs-lookup"><span data-stu-id="77bb4-127">Delete the **Class1.cs** file from the **ItineraryLibrary** project.</span></span>