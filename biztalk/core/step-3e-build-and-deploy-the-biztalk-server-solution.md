---
title: 步骤 3e： 生成并部署 BizTalk Server 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfc382b-ed4a-4401-9343-be1bffd747c9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abe1a747057852bae5d404ccfb3272ca9712948b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969094"
---
# <a name="step-3e-build-and-deploy-the-biztalk-server-solution"></a><span data-ttu-id="ab00e-102">步骤 3e： 生成并部署 BizTalk Server 解决方案</span><span class="sxs-lookup"><span data-stu-id="ab00e-102">Step 3e: Build and Deploy the BizTalk Server Solution</span></span>
<span data-ttu-id="ab00e-103">在本主题中，我们将部署两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目 (**BtsSalesforceIntegration**并**CustomPipeline**)，我们在前面步骤中创建。</span><span class="sxs-lookup"><span data-stu-id="ab00e-103">In this topic, we’ll deploy the two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects (**BtsSalesforceIntegration** and **CustomPipeline**) that we created in the earlier steps.</span></span>  
  
### <a name="to-build-and-deploy-the-biztalk-server-projects"></a><span data-ttu-id="ab00e-104">生成和部署 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="ab00e-104">To build and deploy the BizTalk Server projects</span></span>  
  
1. <span data-ttu-id="ab00e-105">在解决方案资源管理器，右键单击**BtsSalesforceIntegration** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="ab00e-105">In the Solution Explorer, right-click the **BtsSalesforceIntegration**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="ab00e-106">在中**部署**选项卡上，对于**应用程序名称**，输入**SalesforceIntegration**。</span><span class="sxs-lookup"><span data-stu-id="ab00e-106">In the **Deployment** tab, for **Application Name**, enter **SalesforceIntegration**.</span></span> <span data-ttu-id="ab00e-107">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="ab00e-107">Click **Save**.</span></span>  
  
3. <span data-ttu-id="ab00e-108">同样，用鼠标右键单击**CustomPipeline** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，然后单击**属性**，然后在**部署**选项卡上，为**应用程序名称**属性，输入**SalesforceIntegration**试。</span><span class="sxs-lookup"><span data-stu-id="ab00e-108">Similarly, right-click the **CustomPipeline**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, click **Properties**, and in the **Deployment** tab, for the **Application Name** property, enter **SalesforceIntegration** again.</span></span> <span data-ttu-id="ab00e-109">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="ab00e-109">Click **Save**.</span></span> <span data-ttu-id="ab00e-110">这可确保自定义管道组件部署到同一个应用程序作为**BtsSalesforceIntegration**项目。</span><span class="sxs-lookup"><span data-stu-id="ab00e-110">This ensures that the custom pipeline component is deployed to the same application as the **BtsSalesforceIntegration** project.</span></span>  
  
4. <span data-ttu-id="ab00e-111">右键单击解决方案名称，在解决方案资源管理器，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ab00e-111">Right-click the solution name in the Solution Explorer, and click **Properties**.</span></span> <span data-ttu-id="ab00e-112">在解决方案属性页对话框中，单击**配置属性**，并确认**构建**和**部署**选中的复选框均适用**BtsSalesforceIntegration**并**CustomPipeline**项目。</span><span class="sxs-lookup"><span data-stu-id="ab00e-112">In the Solution Property Pages dialog box, click **Configuration Properties**, and verify that the **Build** and **Deploy** check boxes are selected both for **BtsSalesforceIntegration** and **CustomPipeline** projects.</span></span>  
  
5. <span data-ttu-id="ab00e-113">右键单击解决方案资源管理器中的解决方案名称，然后单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="ab00e-113">Right-click the solution name in the Solution Explorer and then click **Build Solution**.</span></span> <span data-ttu-id="ab00e-114">成功生成后，再次右键单击解决方案名称，然后依次**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="ab00e-114">After the solution builds successfully, right-click the solution name again, and then click **Deploy Solution**.</span></span> <span data-ttu-id="ab00e-115">此时，该解决方案将部署到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ab00e-115">The solution is deployed to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab00e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab00e-116">See Also</span></span>  
 [<span data-ttu-id="ab00e-117">步骤 3：在 Visual Studio 中创建 BizTalk Server 解决方案</span><span class="sxs-lookup"><span data-stu-id="ab00e-117">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)