---
title: 步骤 8： 构建和部署 Contoso 业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, building solutions
- private process tutorial, deploying solutions
ms.assetid: d350b87a-0e4e-4837-ad39-fb5b1fdc1532
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 706c5ab2b52d30aeedfba7b3e002dc637fcece93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209301"
---
# <a name="step-8-building-and-deploying-the-contoso-orchestration"></a><span data-ttu-id="bd446-102">步骤 8： 构建和部署 Contoso 业务流程</span><span class="sxs-lookup"><span data-stu-id="bd446-102">Step 8: Building and Deploying the Contoso Orchestration</span></span>
<span data-ttu-id="bd446-103">在此步骤中，您将生成 Orchestration 项目并使用“BizTalk 部署向导”部署该项目。</span><span class="sxs-lookup"><span data-stu-id="bd446-103">In this step, you build the Orchestration project and deploy it using the BizTalk Deployment Wizard.</span></span> <span data-ttu-id="bd446-104">这会将程序集添加到 Configuration 数据库，并在全局程序集缓存 (GAC) 中安装该程序集。</span><span class="sxs-lookup"><span data-stu-id="bd446-104">This adds the assembly to the Configuration database and installs the assembly in the Global Assembly Cache (GAC).</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="bd446-105">指定程序集的强名称</span><span class="sxs-lookup"><span data-stu-id="bd446-105">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="bd446-106">在解决方案资源管理器，右键单击**PrivateResponder**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="bd446-106">In Solution Explorer, right-click the **PrivateResponder** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="bd446-107">在 PrivateResponder 属性页对话框中，选择**程序集**从左窗格。</span><span class="sxs-lookup"><span data-stu-id="bd446-107">In the PrivateResponder Property Pages dialog box, select **Assembly** from the left pane.</span></span>  
  
3.  <span data-ttu-id="bd446-108">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号按钮 (**...**).</span><span class="sxs-lookup"><span data-stu-id="bd446-108">In the right pane, scroll down to the **Strong name** section, click the field to the right of the **Assembly Key File**, and then click the ellipsis button (**…**).</span></span>  
  
4.  <span data-ttu-id="bd446-109">找到你的项目文件夹中，选择**FabConPriceAvail.snk**文件，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="bd446-109">Locate your project folder, select the **FabConPriceAvail.snk** file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="bd446-110">在右窗格中，选择**False**从**程序集延迟签名**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="bd446-110">In the right pane, select **False** from the **Assembly Delay Sign** drop down list.</span></span>  
  
6.  <span data-ttu-id="bd446-111">单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="bd446-111">Click **OK** to save the changes.</span></span>  
  
### <a name="to-build-and-deploy-the-orchestration-project"></a><span data-ttu-id="bd446-112">生成和部署业务流程项目</span><span class="sxs-lookup"><span data-stu-id="bd446-112">To build and deploy the orchestration project</span></span>  
  
1.  <span data-ttu-id="bd446-113">在解决方案资源管理器，右键单击**PrivateResponder**项目，，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="bd446-113">In Solution Explorer, right-click the **PrivateResponder** project, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd446-114">可以放心地忽略在生成过程中出现的任何警告。</span><span class="sxs-lookup"><span data-stu-id="bd446-114">You can safely ignore any warnings that occur during the build process.</span></span>  
  
2.  <span data-ttu-id="bd446-115">已成功生成后，再次右键单击项目，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="bd446-115">After the build has succeeded, right-click the project again, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd446-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd446-116">See Also</span></span>  
 [<span data-ttu-id="bd446-117">步骤 9： 启动 Contoso 业务流程</span><span class="sxs-lookup"><span data-stu-id="bd446-117">Step 9: Starting the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)