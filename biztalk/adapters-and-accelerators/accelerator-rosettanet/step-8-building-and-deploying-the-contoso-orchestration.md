---
title: 步骤 8：生成和部署 Contoso 业务流程 |Microsoft Docs
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
ms.openlocfilehash: 68708976c91d96b3729b1a39776981d9345eb519
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280647"
---
# <a name="step-8-building-and-deploying-the-contoso-orchestration"></a><span data-ttu-id="87c0e-102">步骤 8：生成和部署 Contoso 业务流程</span><span class="sxs-lookup"><span data-stu-id="87c0e-102">Step 8: Building and Deploying the Contoso Orchestration</span></span>
<span data-ttu-id="87c0e-103">在此步骤中，将生成业务流程项目和使用 BizTalk 部署向导部署该网站。</span><span class="sxs-lookup"><span data-stu-id="87c0e-103">In this step, you build the Orchestration project and deploy it using the BizTalk Deployment Wizard.</span></span> <span data-ttu-id="87c0e-104">这将程序集添加到配置数据库，并安装在全局程序集缓存 (GAC) 中的程序集。</span><span class="sxs-lookup"><span data-stu-id="87c0e-104">This adds the assembly to the Configuration database and installs the assembly in the Global Assembly Cache (GAC).</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="87c0e-105">若要为您的程序集分配强名称</span><span class="sxs-lookup"><span data-stu-id="87c0e-105">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="87c0e-106">在解决方案资源管理器中右键单击**PrivateResponder**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="87c0e-106">In Solution Explorer, right-click the **PrivateResponder** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="87c0e-107">在 PrivateResponder 属性页对话框中，选择**程序集**在左窗格中。</span><span class="sxs-lookup"><span data-stu-id="87c0e-107">In the PrivateResponder Property Pages dialog box, select **Assembly** from the left pane.</span></span>  
  
3.  <span data-ttu-id="87c0e-108">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号按钮 (**...**).</span><span class="sxs-lookup"><span data-stu-id="87c0e-108">In the right pane, scroll down to the **Strong name** section, click the field to the right of the **Assembly Key File**, and then click the ellipsis button (**…**).</span></span>  
  
4.  <span data-ttu-id="87c0e-109">找到你的项目文件夹，选择**FabConPriceAvail.snk**文件，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="87c0e-109">Locate your project folder, select the **FabConPriceAvail.snk** file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="87c0e-110">在右窗格中，选择**False**从**程序集延迟签名**下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="87c0e-110">In the right pane, select **False** from the **Assembly Delay Sign** drop down list.</span></span>  
  
6.  <span data-ttu-id="87c0e-111">单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="87c0e-111">Click **OK** to save the changes.</span></span>  
  
### <a name="to-build-and-deploy-the-orchestration-project"></a><span data-ttu-id="87c0e-112">若要生成和部署业务流程项目</span><span class="sxs-lookup"><span data-stu-id="87c0e-112">To build and deploy the orchestration project</span></span>  
  
1.  <span data-ttu-id="87c0e-113">在解决方案资源管理器中右键单击**PrivateResponder**项目，并单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="87c0e-113">In Solution Explorer, right-click the **PrivateResponder** project, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87c0e-114">您可以放心地忽略生成过程中出现任何警告。</span><span class="sxs-lookup"><span data-stu-id="87c0e-114">You can safely ignore any warnings that occur during the build process.</span></span>  
  
2.  <span data-ttu-id="87c0e-115">已成功生成后，再次右键单击项目，然后依次**部署**。</span><span class="sxs-lookup"><span data-stu-id="87c0e-115">After the build has succeeded, right-click the project again, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c0e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="87c0e-116">See Also</span></span>  
 [<span data-ttu-id="87c0e-117">步骤 9：启动 Contoso 业务流程</span><span class="sxs-lookup"><span data-stu-id="87c0e-117">Step 9: Starting the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)