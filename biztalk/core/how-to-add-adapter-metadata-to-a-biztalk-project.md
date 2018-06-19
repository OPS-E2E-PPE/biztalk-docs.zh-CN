---
title: 如何将适配器元数据添加到 BizTalk 项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e439e5bf-94b3-4582-bacc-b058e6eb8e17
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75aea1f23236d448f6efaa451d45663352fb3083
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969059"
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a><span data-ttu-id="bbebe-102">如何将适配器元数据添加到 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="bbebe-102">How to Add Adapter Metadata to a BizTalk Project</span></span>
<span data-ttu-id="bbebe-103">使用“添加适配器元数据”向导可向 BizTalk 项目添加适配器元数据。</span><span class="sxs-lookup"><span data-stu-id="bbebe-103">The Add Adapter Metadata Wizard enables you to add adapter metadata to a BizTalk project.</span></span> <span data-ttu-id="bbebe-104">此数据包括与业务流程中的适配器通信所需的架构、消息类型和端口类型。</span><span class="sxs-lookup"><span data-stu-id="bbebe-104">This data includes schemas, message types, and port types needed to communicate with an adapter from an orchestration.</span></span> <span data-ttu-id="bbebe-105">对应用程序适配器（例如 FTP）使用“添加适配器元数据”向导，将对应于这些应用程序适配器的架构拖入系统。</span><span class="sxs-lookup"><span data-stu-id="bbebe-105">Use the Add Adapter Metadata Wizard with application adapters, such as FTP, to pull schemas corresponding to these application adapters into the system.</span></span> <span data-ttu-id="bbebe-106">请注意，传输适配器（如 HTTP）通常不使用架构。</span><span class="sxs-lookup"><span data-stu-id="bbebe-106">Note that transport adapters such as HTTP do not typically use schemas.</span></span>  
  
 <span data-ttu-id="bbebe-107">以下过程可引导您完成添加适配器元数据的一般步骤。</span><span class="sxs-lookup"><span data-stu-id="bbebe-107">The following procedure walks you through the generic steps to add metadata for an adapter.</span></span>  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a><span data-ttu-id="bbebe-108">向 BizTalk 项目添加适配器元数据</span><span class="sxs-lookup"><span data-stu-id="bbebe-108">To add adapter metadata to a BizTalk project</span></span>  
  
1.  <span data-ttu-id="bbebe-109">在你[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，请在解决方案资源管理器，右键单击你的项目，单击**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="bbebe-109">In your [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, in Solution Explorer, right-click your project, click **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="bbebe-110">在**添加生成的项的\<** *项目名称* **\>** 对话框中，在**模板**部分中，选择**添加适配器**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="bbebe-110">In the **Add Generated Items - \<***Project name***\>** dialog box, in the **Templates** section, select **Add Adapter**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="bbebe-111">在添加适配器元数据向导中，在**选择适配器**页上，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="bbebe-111">In the Add Adapter Metadata Wizard, on the **Select Adapter** page, do the following.</span></span>  
  
    |<span data-ttu-id="bbebe-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="bbebe-112">Use this</span></span>|<span data-ttu-id="bbebe-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="bbebe-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="bbebe-114">适配器列表框</span><span class="sxs-lookup"><span data-stu-id="bbebe-114">Adapter list box</span></span>|<span data-ttu-id="bbebe-115">选择要添加到项目的已注册的适配器。</span><span class="sxs-lookup"><span data-stu-id="bbebe-115">Select the registered adapter to add to the project.</span></span>|  
    |<span data-ttu-id="bbebe-116">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bbebe-116">SQL Server</span></span>|<span data-ttu-id="bbebe-117">输入 BizTalk 数据库服务器名称。</span><span class="sxs-lookup"><span data-stu-id="bbebe-117">Enter the BizTalk database server name.</span></span>|  
    |<span data-ttu-id="bbebe-118">数据库</span><span class="sxs-lookup"><span data-stu-id="bbebe-118">Database</span></span>|<span data-ttu-id="bbebe-119">显示用于所选服务器的 BizTalk 管理数据库的列表。</span><span class="sxs-lookup"><span data-stu-id="bbebe-119">Displays the list of BizTalk Management databases for the chosen server.</span></span>|  
    |<span data-ttu-id="bbebe-120">端口</span><span class="sxs-lookup"><span data-stu-id="bbebe-120">Port</span></span>|<span data-ttu-id="bbebe-121">可选。</span><span class="sxs-lookup"><span data-stu-id="bbebe-121">Optional.</span></span> <span data-ttu-id="bbebe-122">显示在 BizTalk 管理数据库中创建和存储的端口的列表。</span><span class="sxs-lookup"><span data-stu-id="bbebe-122">Displays the list of ports created and stored in the BizTalk Management database.</span></span> <span data-ttu-id="bbebe-123">只显示配置为使用所选适配器的端口。</span><span class="sxs-lookup"><span data-stu-id="bbebe-123">Only ports configured to work with the selected adapter are shown.</span></span>|  
  
     <span data-ttu-id="bbebe-124">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="bbebe-124">Click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bbebe-125">尝试添加包含的生成的架构字符数**System.XML.XMLConvert**类不支持在编译错误的结果。</span><span class="sxs-lookup"><span data-stu-id="bbebe-125">Attempting to add generated schemas that contain characters that the **System.XML.XMLConvert** class does not support results in a compilation error.</span></span>  
  
4.  <span data-ttu-id="bbebe-126">如果你使用的静态的适配器，在**选择服务添加到导入**页上，从树视图中，选择可用服务的一组，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="bbebe-126">If you are using a static adapter, on the **Select Services to Import** page, select a set of available services from the tree view, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="bbebe-127">- 或者 -</span><span class="sxs-lookup"><span data-stu-id="bbebe-127">–Or–</span></span>  
  
     <span data-ttu-id="bbebe-128">如果使用的是动态适配器，请遵照自定义用户界面中的步骤完成向导。</span><span class="sxs-lookup"><span data-stu-id="bbebe-128">If you are using a dynamic adapter, follow the steps in the custom user interface to complete the wizard.</span></span>  
  
 <span data-ttu-id="bbebe-129">完成向导之后，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 将在“解决方案资源管理器”中列出 .odx 和 .xsd 文件。</span><span class="sxs-lookup"><span data-stu-id="bbebe-129">After you complete the wizard, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] lists the .odx and .xsd files in Solution Explorer.</span></span>