---
title: 管理 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, examples
- utilities, SSOMANAGE
- examples, SSO
- SSOMANAGE command line utility
ms.assetid: f738e344-4d81-4557-b399-68b59c413245
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a62fe56bed210669625c9fff4c76315d1eb4546
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022867"
---
# <a name="manage-biztalk-server-sample"></a><span data-ttu-id="61032-102">管理 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="61032-102">Manage (BizTalk Server Sample)</span></span>
<span data-ttu-id="61032-103">管理单一登录 (SSO) 示例演示如何构造能用于 ssomanage.exe 命令行实用工具的 .xml 文件以执行以下类型的管理操作：</span><span class="sxs-lookup"><span data-stu-id="61032-103">The Manage Single Sign-On (SSO) sample demonstrates how to construct .xml files that you can use with the ssomanage.exe command-line utility to perform the following types of administration operations:</span></span>  
  
- <span data-ttu-id="61032-104">在 SSO 系统级别更新全局信息</span><span class="sxs-lookup"><span data-stu-id="61032-104">Update global information at the SSO system level</span></span>  
  
- <span data-ttu-id="61032-105">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="61032-105">Create affiliate applications</span></span>  
  
- <span data-ttu-id="61032-106">创建用户映射</span><span class="sxs-lookup"><span data-stu-id="61032-106">Create user mappings</span></span>  
  
  <span data-ttu-id="61032-107">有关企业单一登录的概念信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="61032-107">For conceptual information about Enterprise Single Sign-On, see [Using SSO](../core/using-sso.md).</span></span>  
  
  <span data-ttu-id="61032-108">有关演示如何以编程方式配置 SSO，例如创建关联应用程序和用户映射的示例，请参阅[HTTPSSO （BizTalk Server 示例）](../core/httpsso-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="61032-108">For a sample that shows how to programmatically configure SSO, such as creating affiliate applications and user mappings, see [HTTPSSO (BizTalk Server Sample)](../core/httpsso-biztalk-server-sample.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="61032-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="61032-109">What This Sample Does</span></span>  
 <span data-ttu-id="61032-110">本示例为上述操作类型中的每一种类型都提供了一对 XSD 和示例 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="61032-110">This sample includes pairs of XSD and sample .xml files for each of these types of operations.</span></span> <span data-ttu-id="61032-111">示例 .xml 文件中的值是无效的。</span><span class="sxs-lookup"><span data-stu-id="61032-111">The values in the sample .xml files are not valid.</span></span> <span data-ttu-id="61032-112">必须更改这些值，使其与您的特定需求相适应。</span><span class="sxs-lookup"><span data-stu-id="61032-112">You must make changes to the values that are appropriate to your specific requirements.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="61032-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="61032-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="61032-114">*\<示例路径\>* \SSO\Manage\\</span><span class="sxs-lookup"><span data-stu-id="61032-114">*\<Samples Path\>* \SSO\Manage\\</span></span>  
  
 <span data-ttu-id="61032-115">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="61032-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="61032-116">文件</span><span class="sxs-lookup"><span data-stu-id="61032-116">File(s)</span></span>|<span data-ttu-id="61032-117">Description</span><span class="sxs-lookup"><span data-stu-id="61032-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61032-118">AffiliateApplication.xml、GlobalInfo.xml、UserMapping.xml</span><span class="sxs-lookup"><span data-stu-id="61032-118">AffiliateApplication.xml, GlobalInfo.xml, UserMapping.xml</span></span>|<span data-ttu-id="61032-119">示例 .xml 文件，在进行修改之后，可以将它们作为参数传递给命令行实用工具 ssomanage.exe。</span><span class="sxs-lookup"><span data-stu-id="61032-119">Sample .xml files that you can, after modification, pass as arguments to the command-line utility ssomanage.exe.</span></span>|  
|<span data-ttu-id="61032-120">AffiliateApplication.xsd、GlobalInfo.xsd、UserMapping.xsd</span><span class="sxs-lookup"><span data-stu-id="61032-120">AffiliateApplication.xsd, GlobalInfo.xsd, UserMapping.xsd</span></span>|<span data-ttu-id="61032-121">与 .xml 文件对应的架构文件，全面描述了架构可能包含的元素和属性。</span><span class="sxs-lookup"><span data-stu-id="61032-121">Schema files for the corresponding .xml files, providing complete descriptions of their possible elements and attributes.</span></span> <span data-ttu-id="61032-122">可使用这些文件验证从其他来源收到的对应 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="61032-122">You can use these files to validate corresponding .xml files received from other sources.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="61032-123">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="61032-123">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="61032-124">由于本示例仅包括 XML 架构定义语言 (XSD) 和 .xml 文件，您可以修改后者并将其传递给命令行实用工具 ssomanage.exe，本示例中无需生成任何内容。</span><span class="sxs-lookup"><span data-stu-id="61032-124">Because this sample consists of only XML Schema definition language (XSD) and .xml files, the latter of which you can modify and then pass to the command-line utility ssomanage.exe, there is nothing to build in this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="61032-125">运行本示例</span><span class="sxs-lookup"><span data-stu-id="61032-125">Running This Sample</span></span>  
 <span data-ttu-id="61032-126">本示例包含了示例 .xml 文件，可用于在以下三种不同模式下运行命令行实用工具 ssomanage.exe：</span><span class="sxs-lookup"><span data-stu-id="61032-126">This sample includes sample .xml files for running the command-line utility ssomanage.exe in the following three different modes:</span></span>  
  
- <span data-ttu-id="61032-127">**更新在 SSO 系统级别的全局信息。**</span><span class="sxs-lookup"><span data-stu-id="61032-127">**Update global information at the SSO system level.**</span></span> <span data-ttu-id="61032-128">若要执行此种类型的操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="61032-128">To perform this type of operation, perform the following steps:</span></span>  
  
  1. <span data-ttu-id="61032-129">根据您的特定配置的需要，编辑 GlobalInfo.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="61032-129">Edit the file GlobalInfo.xml as required for your specific configuration.</span></span>  
  
  2. <span data-ttu-id="61032-130">使用适当的参数运行命令行实用工具 ssomanage.exe，如下所示：</span><span class="sxs-lookup"><span data-stu-id="61032-130">Run the ssomanage.exe command-line utility with the appropriate arguments, as follows:</span></span>  
  
     ```  
     ssomanage –updatedb GlobalInfo.xml  
     ```  
  
     <span data-ttu-id="61032-131">确保根据您的环境对 GlobalInfo.xml 文件中的值进行了编辑。</span><span class="sxs-lookup"><span data-stu-id="61032-131">Ensure that you edit the values in the file GlobalInfo.xml to match your environment.</span></span> <span data-ttu-id="61032-132">例如，SSO 管理员帐户必须是一个有效的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="61032-132">For example, the SSO Admin account must be a valid Windows account.</span></span> <span data-ttu-id="61032-133">SSO 管理员帐户和 SSO 关联管理员帐户都必须是 Windows 的全局域组帐户。</span><span class="sxs-lookup"><span data-stu-id="61032-133">Both the SSO Admin account and SSO Affiliate Admin account must be Windows Global Domain Group accounts.</span></span>  
  
- <span data-ttu-id="61032-134">**创建关联应用程序。**</span><span class="sxs-lookup"><span data-stu-id="61032-134">**Create affiliate applications.**</span></span> <span data-ttu-id="61032-135">若要执行此种类型的操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="61032-135">To perform this type of operation, perform the following steps:</span></span>  
  
- <span data-ttu-id="61032-136">根据您的特定配置的需要，编辑 AffiliateApplication.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="61032-136">Edit the file AffiliateApplication.xml as required for your specific configuration.</span></span>  
  
  - <span data-ttu-id="61032-137">使用适当的参数，运行命令行实用工具 ssomanage.exe，如下所示：</span><span class="sxs-lookup"><span data-stu-id="61032-137">Run the command-line utility ssomanage.exe with the appropriate arguments, as follows:</span></span>  
  
    ```  
    ssomanage –createapps AffiliateApplication.xml  
    ```  
  
    <span data-ttu-id="61032-138">可以同时创建多个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="61032-138">You can create more than one affiliate application at the same time.</span></span>  
  
- <span data-ttu-id="61032-139">**创建用户映射。**</span><span class="sxs-lookup"><span data-stu-id="61032-139">**Create user mappings.**</span></span> <span data-ttu-id="61032-140">若要执行此种类型的操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="61032-140">To perform this type of operation, perform the following steps:</span></span>  
  
  1. <span data-ttu-id="61032-141">根据您的特定配置的需要，编辑 UserMapping.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="61032-141">Edit the file UserMapping.xmlas required for your specific configuration.</span></span>  
  
  2. <span data-ttu-id="61032-142">使用适当的参数，运行命令行实用工具 ssomanage.exe，如下所示：</span><span class="sxs-lookup"><span data-stu-id="61032-142">Run the command-line utility ssomanage.exe with the appropriate arguments, as follows:</span></span>  
  
     ```  
     ssomanage –createmappings UserMapping.xml  
     ```  
  
     <span data-ttu-id="61032-143">可以同时为一个或多个关联应用程序创建多个映射。</span><span class="sxs-lookup"><span data-stu-id="61032-143">You can create more than one mapping for one or more affiliate applications at the same time.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="61032-144">注释</span><span class="sxs-lookup"><span data-stu-id="61032-144">Comments</span></span>  
 <span data-ttu-id="61032-145">在修改了本示例提供的示例 .xml 文件之后，特别是在此类更改涉及到在这些文件中添加敏感信息的情况下，请确保这些文件在文件系统中能得到很好的保护。</span><span class="sxs-lookup"><span data-stu-id="61032-145">After making changes to the sample .xml files provided with this sample, especially where such changes involve including sensitive information in the files, ensure that these files are well protected in your file system.</span></span> <span data-ttu-id="61032-146">例如，应确保没有将这些文件误放到某个共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="61032-146">For example, ensure that they are not inadvertently placed in a folder that is shared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61032-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="61032-147">See Also</span></span>  
 [<span data-ttu-id="61032-148">SSO（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="61032-148">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)