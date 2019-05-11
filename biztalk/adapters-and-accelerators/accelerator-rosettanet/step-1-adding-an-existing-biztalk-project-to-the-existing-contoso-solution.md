---
title: 第 1 步：向现有 Contoso 解决方案添加现有 BizTalk 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, adding to solutions
- private process tutorial, adding projects to solutions
ms.assetid: 9e84d282-01aa-4611-8462-c1acef234042
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a735dbd582d309f5927f66fd55d70227c7e3ca89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281737"
---
# <a name="step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution"></a><span data-ttu-id="69058-102">第 1 步：向现有 Contoso 解决方案添加现有 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="69058-102">Step 1: Adding an Existing BizTalk Project to the Existing Contoso Solution</span></span>
<span data-ttu-id="69058-103">The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 包含专用业务流程的自定义你自己的专用流程时可作为很好的起点。</span><span class="sxs-lookup"><span data-stu-id="69058-103">The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK contains a private process orchestration that serves as a good starting point when customizing your own private process.</span></span> <span data-ttu-id="69058-104">在此步骤中，可以将该业务流程添加到你的解决方案和更改程序集名称以避免冲突，与在过程中安装的 PrivateResponder 业务流程[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="69058-104">In this step, you add that orchestration to your solution and change the assembly name to avoid conflict with the PrivateResponder orchestration installed during the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] installation.</span></span> <span data-ttu-id="69058-105">在开始之前，打开你在中创建的 Contoso 解决方案[步骤 1:为 Contoso 价格与可用性请求创建新的 BizTalk 解决方案](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)。</span><span class="sxs-lookup"><span data-stu-id="69058-105">Before you start, open the Contoso solution you created in [Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md).</span></span>  
  
### <a name="to-add-the-privateresponder-project-to-the-contoso-solution"></a><span data-ttu-id="69058-106">若要向 Contoso 解决方案添加 PrivateResponder 项目</span><span class="sxs-lookup"><span data-stu-id="69058-106">To add the PrivateResponder project to the Contoso solution</span></span>  
  
1.  <span data-ttu-id="69058-107">将 PrivateResponder SDK 示例复制到 Contoso 解决方案文件夹。</span><span class="sxs-lookup"><span data-stu-id="69058-107">Copy the PrivateResponder SDK sample to your Contoso solution folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69058-108">默认情况下，PrivateResponder SDK 示例位于 C:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\PrivateResponder 文件夹。</span><span class="sxs-lookup"><span data-stu-id="69058-108">By default, the PrivateResponder SDK sample is located in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder folder.</span></span>  
  
2.  <span data-ttu-id="69058-109">在 Visual Studio 中，单击**文件**，依次指向**添加**，然后单击**现有项目**。</span><span class="sxs-lookup"><span data-stu-id="69058-109">In Visual Studio, click **File**, point to **Add**, and then click **Existing Project**.</span></span>  
  
3.  <span data-ttu-id="69058-110">在添加现有项目对话框中，找到你的解决方案，选择的文件夹**PrivateResponder.btproj**项目文件，然后依次**打开**。</span><span class="sxs-lookup"><span data-stu-id="69058-110">In the Add Existing Project dialog box, locate the folder for your solution, select the **PrivateResponder.btproj** project file, and then click **Open**.</span></span>  
  
### <a name="to-change-the-privateresponder-assembly-name-and-default-namespace"></a><span data-ttu-id="69058-111">若要更改 PrivateResponder 程序集名称和默认命名空间</span><span class="sxs-lookup"><span data-stu-id="69058-111">To change the PrivateResponder assembly name and default namespace</span></span>  
  
1.  <span data-ttu-id="69058-112">在解决方案资源管理器，右键单击**PrivateResponder**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="69058-112">In Solution Explorer, right click the **PrivateResponder** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="69058-113">在 PrivateResponder 属性页对话框中，在控制台树中，单击**常规**。</span><span class="sxs-lookup"><span data-stu-id="69058-113">In the PrivateResponder Property Pages dialog box, in the console tree, click **General**.</span></span> <span data-ttu-id="69058-114">在详细信息窗格中，在**程序集名称**框中，键入**ContosoPriceAndAvailability.PrivateResponder**。</span><span class="sxs-lookup"><span data-stu-id="69058-114">In the details pane, in the **Assembly Name** box, type **ContosoPriceAndAvailability.PrivateResponder**.</span></span>  
  
3.  <span data-ttu-id="69058-115">在中**默认 Namespace**框中，键入**ContosoPriceAndAvailability**。</span><span class="sxs-lookup"><span data-stu-id="69058-115">In the **Default Namespace** box, type **ContosoPriceAndAvailability**.</span></span>  
  
4.  <span data-ttu-id="69058-116">单击**确定**以关闭 PrivateResponder 属性页对话框。</span><span class="sxs-lookup"><span data-stu-id="69058-116">Click **OK** to close the PrivateResponder Property Pages dialog box.</span></span>  
  
5.  <span data-ttu-id="69058-117">在解决方案资源管理器中双击**PrivateResponder.odx**。</span><span class="sxs-lookup"><span data-stu-id="69058-117">In Solution Explorer, double-click **PrivateResponder.odx**.</span></span>  
  
6.  <span data-ttu-id="69058-118">在中**业务流程视图**窗口中，确保**业务流程属性**(在**PrivateResponderProcess**) 处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="69058-118">In the **Orchestration View** window, ensure that **Orchestration Properties** (under **PrivateResponderProcess**) is selected.</span></span>  
  
7.  <span data-ttu-id="69058-119">在中**属性**窗口，请在**Namespace**字段中，键入**ContosoPriceAndAvailability**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="69058-119">In the **Properties** window, in the **Namespace** field, type **ContosoPriceAndAvailability**, and then press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69058-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="69058-120">See Also</span></span>  
 [<span data-ttu-id="69058-121">步骤 2：定义和发布 Contoso 的词汇</span><span class="sxs-lookup"><span data-stu-id="69058-121">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)