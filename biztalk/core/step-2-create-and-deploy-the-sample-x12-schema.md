---
title: 第 2 步：创建和部署示例 X12 架构 |Microsoft Docs
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
ms.openlocfilehash: a99083a5b0d4cc416f611e94ac35039921c8deba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392767"
---
# <a name="step-2-create-and-deploy-the-sample-x12-schema"></a><span data-ttu-id="834be-102">第 2 步：创建和部署示例 X12 架构</span><span class="sxs-lookup"><span data-stu-id="834be-102">Step 2: Create and Deploy the Sample X12 Schema</span></span>
<span data-ttu-id="834be-103">![步骤 2 时 11](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")</span><span class="sxs-lookup"><span data-stu-id="834be-103">![Step 2 of 11](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")</span></span>  
  
 <span data-ttu-id="834be-104">在此步骤中，将生成和部署提供了一个示例 EDI X 12 是通过 AS2 传输的过程的传入 EDI X 12 交换所需的架构的项目。</span><span class="sxs-lookup"><span data-stu-id="834be-104">In this step, you build and deploy the project that provides a sample EDI X12 schema that is required to process the incoming EDI X12 interchange transported over AS2.</span></span> <span data-ttu-id="834be-105">对于本教程，该架构为 X12_00401_864.xsd。</span><span class="sxs-lookup"><span data-stu-id="834be-105">For this tutorial, that schema is X12_00401_864.xsd.</span></span> <span data-ttu-id="834be-106">不需要更改项目随 AS2 教程;只需生成它。</span><span class="sxs-lookup"><span data-stu-id="834be-106">You do not need to change the project that is shipped with the AS2 tutorial; you just need to build it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="834be-107">在文件夹中存储的架构文件 X12_00401_864.xsd 本教程使用[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas。</span><span class="sxs-lookup"><span data-stu-id="834be-107">The schema file X12_00401_864.xsd that this tutorial uses is stored in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas.</span></span> <span data-ttu-id="834be-108">它已添加到架构项目将生成和部署在此步骤。</span><span class="sxs-lookup"><span data-stu-id="834be-108">It has already been added to the Schemas project that you will build and deploy in this step.</span></span> <span data-ttu-id="834be-109">此架构是通过执行文件夹中的 MicrosoftEdiXsdTemplates.exe 下载到您的计算机上的 X12_00401_864.xsd 文件不同[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI。</span><span class="sxs-lookup"><span data-stu-id="834be-109">This schema is different from the X12_00401_864.xsd file downloaded onto your computer by executing MicrosoftEdiXsdTemplates.exe in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span></span> <span data-ttu-id="834be-110">如果使用已添加到 Schemas.btproj 的 X12_00401_864.xsd 文件，本教程才有效。</span><span class="sxs-lookup"><span data-stu-id="834be-110">The tutorial will only work if you use the X12_00401_864.xsd file that has been added to Schemas.btproj.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="834be-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="834be-111">Prerequisites</span></span>  
 <span data-ttu-id="834be-112">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="834be-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-and-deploy-the-sample-x12-schema"></a><span data-ttu-id="834be-113">若要创建和部署示例 X12 架构</span><span class="sxs-lookup"><span data-stu-id="834be-113">To create and deploy the sample X12 schema</span></span>  
  
1. <span data-ttu-id="834be-114">启动**Microsoft Visual Studio**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="834be-114">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
2. <span data-ttu-id="834be-115">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.sln。</span><span class="sxs-lookup"><span data-stu-id="834be-115">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.sln.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="834be-116">本主题假定你已从对 BizTalk EDI 应用程序，其中包含 EDI 架构、 管道和业务流程应用程序中添加了一个引用。</span><span class="sxs-lookup"><span data-stu-id="834be-116">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="834be-117">如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="834be-117">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
3. <span data-ttu-id="834be-118">右键单击架构项目中，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="834be-118">Right-click the Schemas project, and then click **Properties**.</span></span> <span data-ttu-id="834be-119">单击**签名**项目设计器中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="834be-119">Click the **Signing** tab in project designer.</span></span> <span data-ttu-id="834be-120">检查**为程序集签名**复选框，为**选择一个强密钥名称的文件**，选择**\<新建...\>** 并输入`Schemas.snk`。</span><span class="sxs-lookup"><span data-stu-id="834be-120">Check the **Sign the Assembly** checkbox, for **Choose a strong key name file**, select **\<New…\>** and enter `Schemas.snk`.</span></span> <span data-ttu-id="834be-121">清除**保护密钥文件使用密码**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="834be-121">Clear **Protect my key file with a password** and then click **OK**.</span></span> <span data-ttu-id="834be-122">关闭项目属性对话框并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="834be-122">Close the project properties dialog and save the changes.</span></span>  
  
4. <span data-ttu-id="834be-123">生成并部署 Schemas.btproj。</span><span class="sxs-lookup"><span data-stu-id="834be-123">Build and deploy Schemas.btproj.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="834be-124">后续步骤</span><span class="sxs-lookup"><span data-stu-id="834be-124">Next Steps</span></span>  
 <span data-ttu-id="834be-125">配置参与方和业务配置文件为你的组织 (Contoso)，如中所述[步骤 3:为你的组织配置参与方和业务配置文件](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)。</span><span class="sxs-lookup"><span data-stu-id="834be-125">You configure a party and business profile for your organization (Contoso), as described in [Step 3: Configure a Party and Business Profile for Your Organization](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="834be-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="834be-126">See Also</span></span>  
 [<span data-ttu-id="834be-127">EDI 文档架构</span><span class="sxs-lookup"><span data-stu-id="834be-127">EDI Document Schemas</span></span>](../core/edi-document-schemas.md)