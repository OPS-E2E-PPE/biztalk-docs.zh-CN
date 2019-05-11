---
title: 使用 IntelliSense 创建侦听器配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 349ea1bf-a5d1-4464-bf4b-d8746c622377
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 502b9f1d213a9440bb19820f9998604267045a44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396853"
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a><span data-ttu-id="ffef6-102">使用 IntelliSense 创建侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="ffef6-102">Using IntelliSense to Create an Interceptor Configuration File</span></span>
<span data-ttu-id="ffef6-103">可以使用中的 IntelliSense 和架构验证[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]来帮助您构造从架构上来说有效的侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="ffef6-103">You can use IntelliSense and schema validation in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to help you construct interceptor configuration files that are schematically valid.</span></span> <span data-ttu-id="ffef6-104">BAM 管理实用程序验证侦听器配置文件根据基本侦听器配置架构，并且如果文件不是有效的不会部署架构。</span><span class="sxs-lookup"><span data-stu-id="ffef6-104">The BAM management utility validates your interceptor configuration file against the base interceptor configuration schema and, if the file is not valid, does not deploy the schema.</span></span> <span data-ttu-id="ffef6-105">如果该文件通过了根据基本侦听器配置架构进行验证，它根据等特定于技术的架构验证[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]架构或[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]架构在运行时，如果遇到错误，将没有拦截会出现。</span><span class="sxs-lookup"><span data-stu-id="ffef6-105">If the file passes validation against the base interceptor configuration schema, it is validated against technology-specific schemas like the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] schema or the [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] schema during run time and if errors are encountered, no interception will occur.</span></span> <span data-ttu-id="ffef6-106">可以通过使用中的架构验证来避免这些错误[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]构造侦听器配置文件时。</span><span class="sxs-lookup"><span data-stu-id="ffef6-106">You can avoid these errors by using schema validation in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] when constructing your interceptor configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffef6-107">示例 BAM 侦听器配置 XSD 文件已安装的 SDK 文件。</span><span class="sxs-lookup"><span data-stu-id="ffef6-107">The sample BAM interceptor configuration XSD files are installed with the SDK files.</span></span> <span data-ttu-id="ffef6-108">它们可以位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs:</span><span class="sxs-lookup"><span data-stu-id="ffef6-108">They can be found at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs:</span></span>  
> 
> - <span data-ttu-id="ffef6-109">CommonInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="ffef6-109">CommonInterceptorConfiguration.xsd</span></span>  
>   -   <span data-ttu-id="ffef6-110">WcfInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="ffef6-110">WcfInterceptorConfiguration.xsd</span></span>  
>   -   <span data-ttu-id="ffef6-111">WorkflowInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="ffef6-111">WorkflowInterceptorConfiguration.xsd</span></span>  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a><span data-ttu-id="ffef6-112">若要获取侦听器架构的副本</span><span class="sxs-lookup"><span data-stu-id="ffef6-112">To obtain a copy of the interceptor schemas</span></span>  
  
1. <span data-ttu-id="ffef6-113">打开记事本或其他文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="ffef6-113">Open Notepad or another text editor.</span></span>  
  
2. <span data-ttu-id="ffef6-114">导航到[侦听器配置架构](../core/interceptor-configuration-schema.md)主题。</span><span class="sxs-lookup"><span data-stu-id="ffef6-114">Navigate to the [Interceptor Configuration Schema](../core/interceptor-configuration-schema.md) topic.</span></span>  
  
3. <span data-ttu-id="ffef6-115">将内容粘贴到新文档中打开的文本编辑器，然后将该文件保存为文本文件使用名称**CommonInterceptorConfiguration.xsd** （或您自己选择的一个） 到您的硬盘。</span><span class="sxs-lookup"><span data-stu-id="ffef6-115">Paste the contents into a new document in the open text editor, and then save the file as a text file using the name **CommonInterceptorConfiguration.xsd** (or one of your own choosing) to your hard disk.</span></span>  
  
4. <span data-ttu-id="ffef6-116">重复这些步骤[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]架构和[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]架构主题使用的文件名**WorkflowInterceptorConfiguration.xsd**并**WcfInterceptorConfiguration.xsd**或名称你自己的选择。</span><span class="sxs-lookup"><span data-stu-id="ffef6-116">Repeat these steps for the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] schema and [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] schema topics using the file names **WorkflowInterceptorConfiguration.xsd** and **WcfInterceptorConfiguration.xsd** or names of your own choosing.</span></span>  
  
### <a name="to-use-intellisense-with-your-interceptor-configuration-file"></a><span data-ttu-id="ffef6-117">将 IntelliSense 用于侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="ffef6-117">To use IntelliSense with your interceptor configuration file</span></span>  
  
1. <span data-ttu-id="ffef6-118">打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ffef6-118">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="ffef6-119">单击**文件**，单击**新建**，然后单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="ffef6-119">Click **File**, click **New**, and then click **File**.</span></span>  
  
3. <span data-ttu-id="ffef6-120">在中**新的文件**对话框中，选择**XML 文件**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="ffef6-120">In the **New File** dialog box, select **XML File** and then click **Open**.</span></span>  
  
4. <span data-ttu-id="ffef6-121">查看通过右键单击编辑窗格中，然后单击属性窗格**属性**。</span><span class="sxs-lookup"><span data-stu-id="ffef6-121">View the Properties pane by right-clicking the edit pane, and then clicking **Properties**.</span></span>  
  
5. <span data-ttu-id="ffef6-122">在属性窗格中单击**架构**，然后单击省略号 (**...**).</span><span class="sxs-lookup"><span data-stu-id="ffef6-122">In the Properties pane, click **Schemas**, and then click the ellipsis (**…**).</span></span>  
  
6. <span data-ttu-id="ffef6-123">在中**XML 架构**对话框中，单击**添加**，然后导航到的位置的该架构，然后选择**CommonInterceptorConfiguration.xsd**和**WcfInterceptorConfiguration.xsd**如果你正在使用[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]侦听器配置文件，或**WorkflowInterceptorConfiguration.xsd**如果你正在使用[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="ffef6-123">In the **XML Schemas** dialog box, click **Add** and then navigate to the location of the schemas and select **CommonInterceptorConfiguration.xsd** and **WcfInterceptorConfiguration.xsd** if you are working with a [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] interceptor configuration file, or **WorkflowInterceptorConfiguration.xsd** if you are working with a [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] interceptor configuration file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ffef6-124">如果保存使用不同的名称的文件，请改为选择这些文件。</span><span class="sxs-lookup"><span data-stu-id="ffef6-124">If you saved the files using different names, select those files instead.</span></span>  
  
7. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="ffef6-125">现在打开时验证您的侦听器配置文件，并在创建和修改该文件提供 IntelliSense 帮助。</span><span class="sxs-lookup"><span data-stu-id="ffef6-125">will now validate your interceptor configuration file when it is opened and supply IntelliSense help as you create and modify the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffef6-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffef6-126">See Also</span></span>  
 <span data-ttu-id="ffef6-127">[Windows Workflow Foundation 架构](../core/windows-workflow-foundation-schema.md) </span><span class="sxs-lookup"><span data-stu-id="ffef6-127">[Windows Workflow Foundation Schema](../core/windows-workflow-foundation-schema.md) </span></span>  
 [<span data-ttu-id="ffef6-128">Windows Communication Foundation 架构</span><span class="sxs-lookup"><span data-stu-id="ffef6-128">Windows Communication Foundation Schema</span></span>](../core/windows-communication-foundation-schema.md)