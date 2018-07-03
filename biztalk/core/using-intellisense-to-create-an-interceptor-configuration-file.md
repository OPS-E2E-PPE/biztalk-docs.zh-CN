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
ms.openlocfilehash: 1d6df002c51bbcc51a3cb714e389a0f453a0693c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011350"
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a><span data-ttu-id="a8e84-102">使用 IntelliSense 创建侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="a8e84-102">Using IntelliSense to Create an Interceptor Configuration File</span></span>
<span data-ttu-id="a8e84-103">可以使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的 IntelliSense 和架构验证来帮助您构造从架构上来说有效的侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="a8e84-103">You can use IntelliSense and schema validation in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to help you construct interceptor configuration files that are schematically valid.</span></span> <span data-ttu-id="a8e84-104">BAM 管理实用工具根据基本侦听器配置架构验证您的侦听器配置文件，如果此文件无效，则不部署该架构。</span><span class="sxs-lookup"><span data-stu-id="a8e84-104">The BAM management utility validates your interceptor configuration file against the base interceptor configuration schema and, if the file is not valid, does not deploy the schema.</span></span> <span data-ttu-id="a8e84-105">如果文件通过了根据基本侦听器配置架构进行的验证，则在运行时会根据特定于技术的架构（如 [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] 架构或 [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 架构）对其进行验证，如果出错，则不进行侦听。</span><span class="sxs-lookup"><span data-stu-id="a8e84-105">If the file passes validation against the base interceptor configuration schema, it is validated against technology-specific schemas like the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] schema or the [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] schema during run time and if errors are encountered, no interception will occur.</span></span> <span data-ttu-id="a8e84-106">构造侦听器配置文件时，可以通过使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的架构验证来避免这些错误。</span><span class="sxs-lookup"><span data-stu-id="a8e84-106">You can avoid these errors by using schema validation in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] when constructing your interceptor configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8e84-107">示例 BAM 侦听器配置 XSD 文件与 SDK 文件一起安装。</span><span class="sxs-lookup"><span data-stu-id="a8e84-107">The sample BAM interceptor configuration XSD files are installed with the SDK files.</span></span> <span data-ttu-id="a8e84-108">它们位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs：</span><span class="sxs-lookup"><span data-stu-id="a8e84-108">They can be found at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs:</span></span>  
> 
> - <span data-ttu-id="a8e84-109">CommonInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="a8e84-109">CommonInterceptorConfiguration.xsd</span></span>  
>   -   <span data-ttu-id="a8e84-110">WcfInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="a8e84-110">WcfInterceptorConfiguration.xsd</span></span>  
>   -   <span data-ttu-id="a8e84-111">WorkflowInterceptorConfiguration.xsd</span><span class="sxs-lookup"><span data-stu-id="a8e84-111">WorkflowInterceptorConfiguration.xsd</span></span>  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a><span data-ttu-id="a8e84-112">获取侦听器架构的副本</span><span class="sxs-lookup"><span data-stu-id="a8e84-112">To obtain a copy of the interceptor schemas</span></span>  
  
1. <span data-ttu-id="a8e84-113">打开记事本或其他文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="a8e84-113">Open Notepad or another text editor.</span></span>  
  
2. <span data-ttu-id="a8e84-114">导航到[侦听器配置架构](../core/interceptor-configuration-schema.md)主题。</span><span class="sxs-lookup"><span data-stu-id="a8e84-114">Navigate to the [Interceptor Configuration Schema](../core/interceptor-configuration-schema.md) topic.</span></span>  
  
3. <span data-ttu-id="a8e84-115">将内容粘贴到新文档中打开的文本编辑器，然后将该文件保存为文本文件使用名称**CommonInterceptorConfiguration.xsd** （或您自己选择的一个） 到您的硬盘。</span><span class="sxs-lookup"><span data-stu-id="a8e84-115">Paste the contents into a new document in the open text editor, and then save the file as a text file using the name **CommonInterceptorConfiguration.xsd** (or one of your own choosing) to your hard disk.</span></span>  
  
4. <span data-ttu-id="a8e84-116">重复这些步骤[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]架构和[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]架构主题使用的文件名**WorkflowInterceptorConfiguration.xsd**并**WcfInterceptorConfiguration.xsd**或名称你自己的选择。</span><span class="sxs-lookup"><span data-stu-id="a8e84-116">Repeat these steps for the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] schema and [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] schema topics using the file names **WorkflowInterceptorConfiguration.xsd** and **WcfInterceptorConfiguration.xsd** or names of your own choosing.</span></span>  
  
### <a name="to-use-intellisense-with-your-interceptor-configuration-file"></a><span data-ttu-id="a8e84-117">将 IntelliSense 用于侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="a8e84-117">To use IntelliSense with your interceptor configuration file</span></span>  
  
1. <span data-ttu-id="a8e84-118">打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a8e84-118">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="a8e84-119">单击**文件**，单击**新建**，然后单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="a8e84-119">Click **File**, click **New**, and then click **File**.</span></span>  
  
3. <span data-ttu-id="a8e84-120">在中**新的文件**对话框中，选择**XML 文件**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="a8e84-120">In the **New File** dialog box, select **XML File** and then click **Open**.</span></span>  
  
4. <span data-ttu-id="a8e84-121">查看通过右键单击编辑窗格中，然后单击属性窗格**属性**。</span><span class="sxs-lookup"><span data-stu-id="a8e84-121">View the Properties pane by right-clicking the edit pane, and then clicking **Properties**.</span></span>  
  
5. <span data-ttu-id="a8e84-122">在属性窗格中单击**架构**，然后单击省略号 (**...**).</span><span class="sxs-lookup"><span data-stu-id="a8e84-122">In the Properties pane, click **Schemas**, and then click the ellipsis (**…**).</span></span>  
  
6. <span data-ttu-id="a8e84-123">在中**XML 架构**对话框中，单击**添加**，然后导航到的位置的该架构，然后选择**CommonInterceptorConfiguration.xsd**和**WcfInterceptorConfiguration.xsd**如果你正在使用[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]侦听器配置文件，或**WorkflowInterceptorConfiguration.xsd**如果你正在使用[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="a8e84-123">In the **XML Schemas** dialog box, click **Add** and then navigate to the location of the schemas and select **CommonInterceptorConfiguration.xsd** and **WcfInterceptorConfiguration.xsd** if you are working with a [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] interceptor configuration file, or **WorkflowInterceptorConfiguration.xsd** if you are working with a [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] interceptor configuration file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a8e84-124">如果使用其他名称保存这些文件，请改为选择那些文件。</span><span class="sxs-lookup"><span data-stu-id="a8e84-124">If you saved the files using different names, select those files instead.</span></span>  
  
7. <span data-ttu-id="a8e84-125">现在，打开侦听器配置文件时，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 将对其进行验证，并在您创建和修改该文件时提供 IntelliSense 帮助。</span><span class="sxs-lookup"><span data-stu-id="a8e84-125">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] will now validate your interceptor configuration file when it is opened and supply IntelliSense help as you create and modify the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e84-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8e84-126">See Also</span></span>  
 <span data-ttu-id="a8e84-127">[Windows Workflow Foundation 架构](../core/windows-workflow-foundation-schema.md) </span><span class="sxs-lookup"><span data-stu-id="a8e84-127">[Windows Workflow Foundation Schema](../core/windows-workflow-foundation-schema.md) </span></span>  
 [<span data-ttu-id="a8e84-128">Windows Communication Foundation 架构</span><span class="sxs-lookup"><span data-stu-id="a8e84-128">Windows Communication Foundation Schema</span></span>](../core/windows-communication-foundation-schema.md)