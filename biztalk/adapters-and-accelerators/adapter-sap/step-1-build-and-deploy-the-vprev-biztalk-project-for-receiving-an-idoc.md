---
title: "步骤 1： 生成并部署用于接收 IDOC vPrev BizTalk 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, building and deploying previous version of BizTalk project for receiving an IDOC
- migrating, building and deploying previous version of BizTalk project for receiving an IDOC
- migration
ms.assetid: ab6bdf9a-dca5-4acd-97b2-a9afe9792978
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad9654f295f0f43b720b7ac77aec4ac6315f78ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc"></a><span data-ttu-id="937b8-102">步骤 1： 生成并部署用于接收 IDOC vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="937b8-102">Step 1: Build and Deploy the vPrev BizTalk Project for Receiving an IDOC</span></span>
<span data-ttu-id="937b8-103">![步骤 1，共 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="937b8-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="937b8-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="937b8-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="937b8-105">**目标：**在此步骤中，生成和部署你现有的 vPrev BizTalk 项目，从某个 SAP 系统接收 IDOC。</span><span class="sxs-lookup"><span data-stu-id="937b8-105">**Objective:** In this step, you build and deploy your existing vPrev BizTalk project to receive an IDOC from an SAP system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="937b8-106">不需要对 vPrev BizTalk 项目进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="937b8-106">You do not need to make any change to the vPrev BizTalk project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="937b8-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="937b8-107">Prerequisites</span></span>  
 <span data-ttu-id="937b8-108">你必须有一个 vPrev BizTalk 项目，从某个 SAP 系统接收 ORDERS03 IDOC。</span><span class="sxs-lookup"><span data-stu-id="937b8-108">You must have a vPrev BizTalk project to receive an ORDERS03 IDOC from an SAP system.</span></span>  
  
### <a name="to-build-and-deploy-the-vprev-biztalk-project"></a><span data-ttu-id="937b8-109">若要生成并部署 vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="937b8-109">To build and deploy the vPrev BizTalk project</span></span>  
  
1.  <span data-ttu-id="937b8-110">创建生成和部署解决方案所需的强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="937b8-110">Create a strong-name key file required to build and deploy the solution.</span></span> <span data-ttu-id="937b8-111">若要创建强名称密钥文件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="937b8-111">To create a strong-name key file, do the following:</span></span>  
  
    1.  <span data-ttu-id="937b8-112">启动 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="937b8-112">Start Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="937b8-113">在命令提示符导航到你想要创建的密钥文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="937b8-113">At the command prompt navigate to the folder where you want to create the key file.</span></span> <span data-ttu-id="937b8-114">例如，键入**cd C:\Sample**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="937b8-114">For example, type **cd C:\Sample**, and then press ENTER.</span></span>  
  
    3.  <span data-ttu-id="937b8-115">在命令提示符处，键入**sn-k\<密钥文件名称 >.snk**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="937b8-115">At the command prompt, type **sn -k \<key file name>.snk**, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="937b8-116">右键单击解决方案资源管理器中的 BizTalk 解决方案名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="937b8-116">Right-click the BizTalk solution name in Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="937b8-117">在**属性页**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="937b8-117">In the **Property Pages** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="937b8-118">单击**配置属性**的复选框从左窗格中，并确保**生成**和**部署**选择列。</span><span class="sxs-lookup"><span data-stu-id="937b8-118">Click **Configuration Properties** from the left pane, and make sure the check boxes in the **Build** and **Deploy** columns are selected.</span></span>  
  
    2.  <span data-ttu-id="937b8-119">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="937b8-119">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="937b8-120">右键单击解决方案资源管理器中的 BizTalk 项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="937b8-120">Right-click the BizTalk project in Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="937b8-121">在**属性页**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="937b8-121">In the **Property Pages** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="937b8-122">在左窗格中，展开**通用属性**，然后单击程序集。</span><span class="sxs-lookup"><span data-stu-id="937b8-122">In the left pane, expand **Common Properties**, and then click Assembly.</span></span>  
  
    2.  <span data-ttu-id="937b8-123">在右窗格中，在**强名称**类别中，为**程序集密钥文件**属性，提供你先前创建的程序集密钥文件的路径。</span><span class="sxs-lookup"><span data-stu-id="937b8-123">In the right pane, under the **Strong name** category, for the **Assembly Key File** property, provide the path to the assembly key file you created earlier.</span></span>  
  
    3.  <span data-ttu-id="937b8-124">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="937b8-124">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="937b8-125">在解决方案资源管理器，右键单击解决方案名称，然后单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="937b8-125">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="937b8-126">已成功生成解决方案后，右键单击解决方案名称，然后单击**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="937b8-126">After the solution successfully builds, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="937b8-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="937b8-127">Next Steps</span></span>  
 <span data-ttu-id="937b8-128">创建和配置 WCF 自定义接收端口并将其配置为使用基于 WCF 的 SAP 系统从接收到的 Idoc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]中所述，[步骤 2： 配置 WCF 自定义单向接收端口](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="937b8-128">Create and configure a WCF-Custom receive port and configure it to receive IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], as described in [Step 2: Configure a WCF-Custom One-way Receive Port](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="937b8-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="937b8-129">See Also</span></span>  
 [<span data-ttu-id="937b8-130">教程 4： 迁移 SAP 接收 IDOC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="937b8-130">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)