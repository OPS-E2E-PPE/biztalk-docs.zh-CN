---
title: 如何向 BizTalk 项目添加适配器元数据 |Microsoft Docs
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
ms.openlocfilehash: 0f06b60b1dce1b0b9df785d25552f688f7793858
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387312"
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a><span data-ttu-id="4d2d2-102">如何向 BizTalk 项目添加适配器元数据</span><span class="sxs-lookup"><span data-stu-id="4d2d2-102">How to Add Adapter Metadata to a BizTalk Project</span></span>
<span data-ttu-id="4d2d2-103">添加适配器元数据向导，可向 BizTalk 项目添加适配器元数据。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-103">The Add Adapter Metadata Wizard enables you to add adapter metadata to a BizTalk project.</span></span> <span data-ttu-id="4d2d2-104">此数据包括架构、 消息类型和从业务流程的适配器通信所需的端口类型。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-104">This data includes schemas, message types, and port types needed to communicate with an adapter from an orchestration.</span></span> <span data-ttu-id="4d2d2-105">对应用程序适配器，例如 FTP，对应于这些应用程序适配器到系统的请求架构中使用添加适配器元数据向导。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-105">Use the Add Adapter Metadata Wizard with application adapters, such as FTP, to pull schemas corresponding to these application adapters into the system.</span></span> <span data-ttu-id="4d2d2-106">请注意，如 HTTP 传输适配器通常不会使用架构。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-106">Note that transport adapters such as HTTP do not typically use schemas.</span></span>  
  
 <span data-ttu-id="4d2d2-107">以下过程将引导你完成添加适配器元数据的一般步骤。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-107">The following procedure walks you through the generic steps to add metadata for an adapter.</span></span>  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a><span data-ttu-id="4d2d2-108">若要向 BizTalk 项目添加适配器元数据</span><span class="sxs-lookup"><span data-stu-id="4d2d2-108">To add adapter metadata to a BizTalk project</span></span>  
  
1. <span data-ttu-id="4d2d2-109">在你[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，请在解决方案资源管理器，右键单击你的项目，单击**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-109">In your [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, in Solution Explorer, right-click your project, click **Add**, and then click **Add Generated Items**.</span></span>  
  
2. <span data-ttu-id="4d2d2-110">在中**添加生成的项- \<** <em>项目名称</em>**\>** 对话框中，在**模板**部分中，选择**添加适配器**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-110">In the **Add Generated Items - \<**<em>Project name</em>**\>** dialog box, in the **Templates** section, select **Add Adapter**, and then click **Open**.</span></span>  
  
3. <span data-ttu-id="4d2d2-111">在添加适配器元数据向导中，在**选择适配器**页上，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-111">In the Add Adapter Metadata Wizard, on the **Select Adapter** page, do the following.</span></span>  
  
   |<span data-ttu-id="4d2d2-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4d2d2-112">Use this</span></span>|<span data-ttu-id="4d2d2-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4d2d2-113">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="4d2d2-114">适配器列表框</span><span class="sxs-lookup"><span data-stu-id="4d2d2-114">Adapter list box</span></span>|<span data-ttu-id="4d2d2-115">选择要添加到项目的已注册的适配器。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-115">Select the registered adapter to add to the project.</span></span>|  
   |<span data-ttu-id="4d2d2-116">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d2d2-116">SQL Server</span></span>|<span data-ttu-id="4d2d2-117">输入 BizTalk 数据库服务器名称。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-117">Enter the BizTalk database server name.</span></span>|  
   |<span data-ttu-id="4d2d2-118">“数据库”</span><span class="sxs-lookup"><span data-stu-id="4d2d2-118">Database</span></span>|<span data-ttu-id="4d2d2-119">显示所选的服务器的 BizTalk 管理数据库的列表。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-119">Displays the list of BizTalk Management databases for the chosen server.</span></span>|  
   |<span data-ttu-id="4d2d2-120">Port</span><span class="sxs-lookup"><span data-stu-id="4d2d2-120">Port</span></span>|<span data-ttu-id="4d2d2-121">可选。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-121">Optional.</span></span> <span data-ttu-id="4d2d2-122">显示端口创建并存储在 BizTalk 管理数据库的列表。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-122">Displays the list of ports created and stored in the BizTalk Management database.</span></span> <span data-ttu-id="4d2d2-123">显示仅配置为使用所选适配器的端口。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-123">Only ports configured to work with the selected adapter are shown.</span></span>|  
  
    <span data-ttu-id="4d2d2-124">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-124">Click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4d2d2-125">尝试添加的生成的架构包含的字符**System.XML.XMLConvert**类不支持编译错误的结果。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-125">Attempting to add generated schemas that contain characters that the **System.XML.XMLConvert** class does not support results in a compilation error.</span></span>  
  
4. <span data-ttu-id="4d2d2-126">如果在使用静态适配器**选择导入的服务**页上，从树视图中，选择可用的服务的一组，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-126">If you are using a static adapter, on the **Select Services to Import** page, select a set of available services from the tree view, and then click **Finish**.</span></span>  
  
    <span data-ttu-id="4d2d2-127">（或者）</span><span class="sxs-lookup"><span data-stu-id="4d2d2-127">–Or–</span></span>  
  
    <span data-ttu-id="4d2d2-128">如果您使用的是动态适配器，请按照自定义用户界面来完成该向导中的步骤。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-128">If you are using a dynamic adapter, follow the steps in the custom user interface to complete the wizard.</span></span>  
  
   <span data-ttu-id="4d2d2-129">在完成向导后[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]列出了在解决方案资源管理器中的.odx 和.xsd 文件。</span><span class="sxs-lookup"><span data-stu-id="4d2d2-129">After you complete the wizard, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] lists the .odx and .xsd files in Solution Explorer.</span></span>