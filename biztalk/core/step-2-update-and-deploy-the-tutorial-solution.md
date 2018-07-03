---
title: 步骤 2： 更新和部署教程解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d03adfdd-1160-4e8c-a564-3acb2ecd0476
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 714b76ac87b183daa30740268e1a306217d5d13d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998878"
---
# <a name="step-2-update-and-deploy-the-tutorial-solution"></a><span data-ttu-id="87ae5-102">步骤 2： 更新和部署教程解决方案</span><span class="sxs-lookup"><span data-stu-id="87ae5-102">Step 2: Update and Deploy the Tutorial Solution</span></span>
<span data-ttu-id="87ae5-103">![步骤 2 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span><span class="sxs-lookup"><span data-stu-id="87ae5-103">![Step 2 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span></span>  
  
 <span data-ttu-id="87ae5-104">在此步骤中，你将更新为本教程提供的解决方案，然后生成并部署教程程序集。</span><span class="sxs-lookup"><span data-stu-id="87ae5-104">In this step you update the solution provided for this tutorial, and then build and deploy the tutorial assembly.</span></span> <span data-ttu-id="87ae5-105">为了实现本教程的目标，已创建必要的架构、自定义发送管道和映射。</span><span class="sxs-lookup"><span data-stu-id="87ae5-105">For the purposes of this tutorial, the necessary schema, custom send pipeline, and map have already been created.</span></span> <span data-ttu-id="87ae5-106">映射用于将 850 EDI 数据转换为订单系统所需的格式。</span><span class="sxs-lookup"><span data-stu-id="87ae5-106">The map is used to convert the 850 EDI data into the format required by your Order System.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="87ae5-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="87ae5-107">Prerequisites</span></span>  
 <span data-ttu-id="87ae5-108">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="87ae5-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-enable-the-edi-inbound-processing-solution-to-be-built-in-visual-studio"></a><span data-ttu-id="87ae5-109">允许在 Visual Studio 中生成 EDI 入站处理解决方案</span><span class="sxs-lookup"><span data-stu-id="87ae5-109">To enable the EDI Inbound Processing solution to be built in Visual Studio</span></span>  
  
1. <span data-ttu-id="87ae5-110">启动**Microsoft Visual Studio**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="87ae5-110">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="87ae5-111">如果你不以管理员权限启动 Visual Studio，则向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署解决方案时，可能会收到错误。</span><span class="sxs-lookup"><span data-stu-id="87ae5-111">If you do not start Visual Studio with administrator privileges, you will get an error while deploying the solution to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="87ae5-112">在 Visual Studio 中，单击**文件**，依次指向**打开**，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="87ae5-112">In Visual Studio, click **File**, point to **Open**, and then click **Project/Solution**.</span></span> <span data-ttu-id="87ae5-113">将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial，选择**EDI Inbound Processing.sln**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="87ae5-113">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial, select **EDI Inbound Processing.sln**, and then click **Open**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="87ae5-114">本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="87ae5-114">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="87ae5-115">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="87ae5-115">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
3. <span data-ttu-id="87ae5-116">右键单击**Inbound_EDI**项目在解决方案资源管理器中，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="87ae5-116">Right-click the **Inbound_EDI** project in the Solution Explorer, and then select **Properties**.</span></span>  
  
4. <span data-ttu-id="87ae5-117">在控制台树中的**Inbound_EDI 属性页**对话框中，选择**部署**并在**Server**字段确保输入您的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="87ae5-117">In the console tree of the **Inbound_EDI Property Pages** dialog box, select  **Deployment** and in the **Server** field ensure that your computer name is entered.</span></span>  
  
5. <span data-ttu-id="87ae5-118">在控制台树中，单击**签名**，然后选择**程序集签名**。</span><span class="sxs-lookup"><span data-stu-id="87ae5-118">In the console tree, click **Signing** and then select **Sign the assembly**.</span></span> <span data-ttu-id="87ae5-119">有关**选择一个强密钥名称的文件**，选择\<**新建...** \>并输入**keyfile.snk**作为**密钥文件名称**。</span><span class="sxs-lookup"><span data-stu-id="87ae5-119">For **Choose a strong key name file**, select \<**New…**\> and enter  **keyfile.snk** as the **Key file name**.</span></span> <span data-ttu-id="87ae5-120">清除**保护密钥文件使用密码**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="87ae5-120">Clear **Protect my key file with a password** and then click **OK**.</span></span>  
  
6. <span data-ttu-id="87ae5-121">关闭**Inbound_EDI 属性页**对话框。</span><span class="sxs-lookup"><span data-stu-id="87ae5-121">Close the **Inbound_EDI Property Pages** dialog box.</span></span>  
  
### <a name="to-deploy-the-project"></a><span data-ttu-id="87ae5-122">若要将项目部署</span><span class="sxs-lookup"><span data-stu-id="87ae5-122">To deploy the project</span></span>  
  
1. <span data-ttu-id="87ae5-123">在解决方案资源管理器中双击**X12_00401_850.xsd**架构。</span><span class="sxs-lookup"><span data-stu-id="87ae5-123">In Solution Explorer, double-click the **X12_00401_850.xsd** schema.</span></span> <span data-ttu-id="87ae5-124">确认已打开该映射。</span><span class="sxs-lookup"><span data-stu-id="87ae5-124">Confirm that it opens.</span></span>  
  
2. <span data-ttu-id="87ae5-125">在解决方案资源管理器中双击**Inbound4010850_to_OrderFile.btm**映射。</span><span class="sxs-lookup"><span data-stu-id="87ae5-125">In Solution Explorer, double-click the **Inbound4010850_to_OrderFile.btm** map.</span></span> <span data-ttu-id="87ae5-126">确认已打开该映射。</span><span class="sxs-lookup"><span data-stu-id="87ae5-126">Confirm that it opens.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="87ae5-127">项目中的 Inbound4010850_to_OrderFile.btm 映射将入站 850 测试消息中的数据映射到传送给 OrderSystem 文件夹 (\toOrderSystem) 的出站 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="87ae5-127">The Inbound4010850_to_OrderFile.btm map in the project maps the data in the inbound 850 test message to the outbound XML file delivered to the OrderSystem folder (\toOrderSystem).</span></span>  
  
3. <span data-ttu-id="87ae5-128">在解决方案资源管理器中右键单击**Inbound_EDI**项目，然后选择**生成**以生成项目。</span><span class="sxs-lookup"><span data-stu-id="87ae5-128">In Solution Explorer, right-click the **Inbound_EDI** project and select **Build** to build the project.</span></span>  
  
4. <span data-ttu-id="87ae5-129">在解决方案资源管理器中右键单击**Inbound_EDI**项目，然后选择**部署**来部署项目。</span><span class="sxs-lookup"><span data-stu-id="87ae5-129">In Solution Explorer, right-click the **Inbound_EDI** project and select **Deploy** to deploy the project.</span></span>  
  
5. <span data-ttu-id="87ae5-130">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**， \< **所有项目**\> ，然后选择**资源**。</span><span class="sxs-lookup"><span data-stu-id="87ae5-130">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, \<**All Artifacts**\> and then select **Resources**.</span></span> <span data-ttu-id="87ae5-131">确认**Inbound_EDI**列出的程序集。</span><span class="sxs-lookup"><span data-stu-id="87ae5-131">Verify that the **Inbound_EDI** assembly is listed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="87ae5-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="87ae5-132">Next Steps</span></span>  
 <span data-ttu-id="87ae5-133">为你的组织配置参与方和业务配置文件 (**OrderSystem**)，如中所述[步骤 3： 为你的组织配置参与方和业务配置文件](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)</span><span class="sxs-lookup"><span data-stu-id="87ae5-133">You configure a party and business profile for your organization (**OrderSystem**), as described in [Step 3: Configure a Party and Business Profile for Your Organization](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87ae5-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="87ae5-134">See Also</span></span>  
 [<span data-ttu-id="87ae5-135">步骤 1：EDI 接口开发人员教程的准备工作</span><span class="sxs-lookup"><span data-stu-id="87ae5-135">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)