---
title: "步骤 1： 将现有 BizTalk 项目添加到现有的 Contoso 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects, adding to solutions
- private process tutorial, adding projects to solutions
ms.assetid: 9e84d282-01aa-4611-8462-c1acef234042
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c6a6bd5807702cb01c4c7cbc13780b95cc3da2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution"></a><span data-ttu-id="12d00-102">步骤 1： 将现有 BizTalk 项目添加到现有的 Contoso 解决方案</span><span class="sxs-lookup"><span data-stu-id="12d00-102">Step 1: Adding an Existing BizTalk Project to the Existing Contoso Solution</span></span>
<span data-ttu-id="12d00-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 包含专用业务流程，在自定义你自己的专用流程时它是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="12d00-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK contains a private process orchestration that serves as a good starting point when customizing your own private process.</span></span> <span data-ttu-id="12d00-104">在此步骤中，将该业务流程添加到解决方案，然后更改程序集的名称，以避免此名称与 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装过程中安装的 PrivateResponder 业务流程相冲突。</span><span class="sxs-lookup"><span data-stu-id="12d00-104">In this step, you add that orchestration to your solution and change the assembly name to avoid conflict with the PrivateResponder orchestration installed during the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] installation.</span></span> <span data-ttu-id="12d00-105">在开始之前，打开你在中创建 Contoso 解决方案[步骤 1： 为 Contoso 价格和可用性请求创建一个新的 BizTalk 解决方案](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)。</span><span class="sxs-lookup"><span data-stu-id="12d00-105">Before you start, open the Contoso solution you created in [Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md).</span></span>  
  
### <a name="to-add-the-privateresponder-project-to-the-contoso-solution"></a><span data-ttu-id="12d00-106">向 Contoso 解决方案添加 PrivateResponder 项目</span><span class="sxs-lookup"><span data-stu-id="12d00-106">To add the PrivateResponder project to the Contoso solution</span></span>  
  
1.  <span data-ttu-id="12d00-107">将 PrivateResponder SDK 示例复制到 Contoso 解决方案文件夹中。</span><span class="sxs-lookup"><span data-stu-id="12d00-107">Copy the PrivateResponder SDK sample to your Contoso solution folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12d00-108">默认情况下，PrivateResponder SDK 示例位于 C:\Program Files\Microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK\PrivateResponder 文件夹。</span><span class="sxs-lookup"><span data-stu-id="12d00-108">By default, the PrivateResponder SDK sample is located in the C:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\PrivateResponder folder.</span></span>  
  
2.  <span data-ttu-id="12d00-109">在 Visual Studio 中，单击**文件**，指向**添加**，然后单击**现有项目**。</span><span class="sxs-lookup"><span data-stu-id="12d00-109">In Visual Studio, click **File**, point to **Add**, and then click **Existing Project**.</span></span>  
  
3.  <span data-ttu-id="12d00-110">在添加现有项目对话框中，找到你的解决方案中，选择的文件夹**PrivateResponder.btproj**项目文件，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="12d00-110">In the Add Existing Project dialog box, locate the folder for your solution, select the **PrivateResponder.btproj** project file, and then click **Open**.</span></span>  
  
### <a name="to-change-the-privateresponder-assembly-name-and-default-namespace"></a><span data-ttu-id="12d00-111">更改 PrivateResponder 程序集名称和默认命名空间</span><span class="sxs-lookup"><span data-stu-id="12d00-111">To change the PrivateResponder assembly name and default namespace</span></span>  
  
1.  <span data-ttu-id="12d00-112">在解决方案资源管理器，右键单击**PrivateResponder**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="12d00-112">In Solution Explorer, right click the **PrivateResponder** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="12d00-113">在控制台树中，PrivateResponder 属性页对话框中单击**常规**。</span><span class="sxs-lookup"><span data-stu-id="12d00-113">In the PrivateResponder Property Pages dialog box, in the console tree, click **General**.</span></span> <span data-ttu-id="12d00-114">在详细信息窗格中，在**程序集名称**框中，键入**ContosoPriceAndAvailability.PrivateResponder**。</span><span class="sxs-lookup"><span data-stu-id="12d00-114">In the details pane, in the **Assembly Name** box, type **ContosoPriceAndAvailability.PrivateResponder**.</span></span>  
  
3.  <span data-ttu-id="12d00-115">在**默认 Namespace**框中，键入**ContosoPriceAndAvailability**。</span><span class="sxs-lookup"><span data-stu-id="12d00-115">In the **Default Namespace** box, type **ContosoPriceAndAvailability**.</span></span>  
  
4.  <span data-ttu-id="12d00-116">单击**确定**以关闭 PrivateResponder 属性页对话框。</span><span class="sxs-lookup"><span data-stu-id="12d00-116">Click **OK** to close the PrivateResponder Property Pages dialog box.</span></span>  
  
5.  <span data-ttu-id="12d00-117">在解决方案资源管理器中，双击**PrivateResponder.odx**。</span><span class="sxs-lookup"><span data-stu-id="12d00-117">In Solution Explorer, double-click **PrivateResponder.odx**.</span></span>  
  
6.  <span data-ttu-id="12d00-118">在**业务流程视图**窗口中，确保**业务流程属性**(下**PrivateResponderProcess**) 选择。</span><span class="sxs-lookup"><span data-stu-id="12d00-118">In the **Orchestration View** window, ensure that **Orchestration Properties** (under **PrivateResponderProcess**) is selected.</span></span>  
  
7.  <span data-ttu-id="12d00-119">在**属性**窗口，请在**Namespace**字段中，键入**ContosoPriceAndAvailability**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="12d00-119">In the **Properties** window, in the **Namespace** field, type **ContosoPriceAndAvailability**, and then press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d00-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12d00-120">See Also</span></span>  
 [<span data-ttu-id="12d00-121">步骤 2： 定义和 contoso 发布词汇</span><span class="sxs-lookup"><span data-stu-id="12d00-121">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)