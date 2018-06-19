---
title: 步骤 2： 创建并部署示例 X12 架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5862168-6621-40ab-8c97-3f317530d34e
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57c95ac64637027b5d39699a42e8fac93c003697
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974467"
---
# <a name="step-2-create-and-deploy-the-sample-x12-schema"></a><span data-ttu-id="269a4-102">步骤 2： 创建并部署示例 X12 架构</span><span class="sxs-lookup"><span data-stu-id="269a4-102">Step 2: Create and Deploy the Sample X12 Schema</span></span>
<span data-ttu-id="269a4-103">![步骤 2，共 11](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")</span><span class="sxs-lookup"><span data-stu-id="269a4-103">![Step 2 of 11](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")</span></span>  
  
 <span data-ttu-id="269a4-104">在本步骤中，你将生成和部署提供一个示例 EDI X12 架构的项目，该架构是处理通过 AS2 传输的传入 EDI X12 交换所必需的。</span><span class="sxs-lookup"><span data-stu-id="269a4-104">In this step, you build and deploy the project that provides a sample EDI X12 schema that is required to process the incoming EDI X12 interchange transported over AS2.</span></span> <span data-ttu-id="269a4-105">对于本教程，该架构为 X12_00401_864.xsd。</span><span class="sxs-lookup"><span data-stu-id="269a4-105">For this tutorial, that schema is X12_00401_864.xsd.</span></span> <span data-ttu-id="269a4-106">无需更改 AS2 教程附带的项目，只需对它执行生成操作即可。</span><span class="sxs-lookup"><span data-stu-id="269a4-106">You do not need to change the project that is shipped with the AS2 tutorial; you just need to build it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="269a4-107">本教程使用的架构文件 X12_00401_864.xsd 存储在文件夹 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\AS2 Tutorial\Schemas 中。</span><span class="sxs-lookup"><span data-stu-id="269a4-107">The schema file X12_00401_864.xsd that this tutorial uses is stored in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas.</span></span> <span data-ttu-id="269a4-108">它已经添加到你要在本步骤中生成和部署的“架构”项目中。</span><span class="sxs-lookup"><span data-stu-id="269a4-108">It has already been added to the Schemas project that you will build and deploy in this step.</span></span> <span data-ttu-id="269a4-109">此架构与通过执行文件夹 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 中的 MicrosoftEdiXsdTemplates.exe 下载到你计算机上的 X12_00401_864.xsd 文件不同。</span><span class="sxs-lookup"><span data-stu-id="269a4-109">This schema is different from the X12_00401_864.xsd file downloaded onto your computer by executing MicrosoftEdiXsdTemplates.exe in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span></span> <span data-ttu-id="269a4-110">仅当使用已添加到 Schemas.btproj 的 X12_00401_864.xsd 文件时，本教程才适用。</span><span class="sxs-lookup"><span data-stu-id="269a4-110">The tutorial will only work if you use the X12_00401_864.xsd file that has been added to Schemas.btproj.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="269a4-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="269a4-111">Prerequisites</span></span>  
 <span data-ttu-id="269a4-112">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="269a4-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-and-deploy-the-sample-x12-schema"></a><span data-ttu-id="269a4-113">创建和部署示例 X12 架构</span><span class="sxs-lookup"><span data-stu-id="269a4-113">To create and deploy the sample X12 schema</span></span>  
  
1.  <span data-ttu-id="269a4-114">启动**Microsoft Visual Studio**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="269a4-114">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
2.  <span data-ttu-id="269a4-115">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开解决方案 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\AS2 Tutorial\Schemas\Schemas.sln。</span><span class="sxs-lookup"><span data-stu-id="269a4-115">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.sln.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="269a4-116">本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="269a4-116">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="269a4-117">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="269a4-117">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
3.  <span data-ttu-id="269a4-118">右键单击架构项目中，并依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="269a4-118">Right-click the Schemas project, and then click **Properties**.</span></span> <span data-ttu-id="269a4-119">单击**签名**项目设计器中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="269a4-119">Click the **Signing** tab in project designer.</span></span> <span data-ttu-id="269a4-120">检查**对程序集签名**复选框，为**选择强密钥名称文件**，选择**\<新建...\>** 并输入`Schemas.snk`。</span><span class="sxs-lookup"><span data-stu-id="269a4-120">Check the **Sign the Assembly** checkbox, for **Choose a strong key name file**, select **\<New…\>** and enter `Schemas.snk`.</span></span> <span data-ttu-id="269a4-121">清除**保护我使用密码的密钥文件**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="269a4-121">Clear **Protect my key file with a password** and then click **OK**.</span></span> <span data-ttu-id="269a4-122">关闭项目属性对话框并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="269a4-122">Close the project properties dialog and save the changes.</span></span>  
  
4.  <span data-ttu-id="269a4-123">生成并部署 Schemas.btproj。</span><span class="sxs-lookup"><span data-stu-id="269a4-123">Build and deploy Schemas.btproj.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="269a4-124">后续步骤</span><span class="sxs-lookup"><span data-stu-id="269a4-124">Next Steps</span></span>  
 <span data-ttu-id="269a4-125">配置当事方和业务配置文件为你的组织 (Contoso) 中所述[步骤 3： 将方和业务配置文件配置为你的组织](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)。</span><span class="sxs-lookup"><span data-stu-id="269a4-125">You configure a party and business profile for your organization (Contoso), as described in [Step 3: Configure a Party and Business Profile for Your Organization](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269a4-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="269a4-126">See Also</span></span>  
 [<span data-ttu-id="269a4-127">EDI 文档架构</span><span class="sxs-lookup"><span data-stu-id="269a4-127">EDI Document Schemas</span></span>](../core/edi-document-schemas.md)