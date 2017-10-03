---
title: "静态的设计时适配器配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 332723a4-e39d-43f5-af4d-bf9f56496535
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8337e4f53afe22ccbde0e1d1d2a6437d280011d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="static-design-time-adapter-configuration"></a><span data-ttu-id="97e2b-102">静态的设计时适配器配置</span><span class="sxs-lookup"><span data-stu-id="97e2b-102">Static Design-Time Adapter Configuration</span></span>
<span data-ttu-id="97e2b-103">适配器的设计时部分负责定义所有可用属性并且验证用户输入。</span><span class="sxs-lookup"><span data-stu-id="97e2b-103">The design-time part of the adapter is responsible for defining all the available properties and for validating user input.</span></span> <span data-ttu-id="97e2b-104">在静态设计时配置中，适配器使用默认用户界面 (UI) 显示和编辑其属性。</span><span class="sxs-lookup"><span data-stu-id="97e2b-104">In a static design-time configuration the adapter uses the default user interface (UI) for displaying and editing its properties.</span></span>  
  
 <span data-ttu-id="97e2b-105">本部分介绍如何实现您的自定义适配器的静态设计时配置功能。</span><span class="sxs-lookup"><span data-stu-id="97e2b-105">This section explains how to implement static design-time configuration capability for your custom adapter.</span></span> <span data-ttu-id="97e2b-106">您决定做出的更改将基于要与适配器通信的应用程序的需要，以及该适配器需要实现的逻辑。</span><span class="sxs-lookup"><span data-stu-id="97e2b-106">The changes you decide to make will be based on the needs of the applications with which the adapter communicates and the logic that the adapter needs to implement.</span></span> <span data-ttu-id="97e2b-107">指向章节的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用时提供帮助描述了这些步骤中更多详细信息或提供其他背景信息。</span><span class="sxs-lookup"><span data-stu-id="97e2b-107">Links to sections of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help that describe these steps in more detail or provide additional background are provided when available.</span></span> <span data-ttu-id="97e2b-108">此外，本部分还指出了示例文件适配器文档中提供相关示例的位置。</span><span class="sxs-lookup"><span data-stu-id="97e2b-108">Additionally it calls out the places in the sample file adapter documentation that provide relevant examples.</span></span>  
  
## <a name="guidelines-for-the-static-development-process"></a><span data-ttu-id="97e2b-109">有关静态开发过程的准则</span><span class="sxs-lookup"><span data-stu-id="97e2b-109">Guidelines for the Static Development Process</span></span>  
 <span data-ttu-id="97e2b-110">下面的列表提供了有助于在适配器中构建静态设计时功能的建议。</span><span class="sxs-lookup"><span data-stu-id="97e2b-110">The following list provides recommendations for building static design-time functionality into your adapter.</span></span> <span data-ttu-id="97e2b-111">开发过程中，您不必执行全部步骤，也无需严格依照顺序执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="97e2b-111">During development you may not need to do all of these steps, nor execute them in a rigid sequence.</span></span>  
  
1.  <span data-ttu-id="97e2b-112">创建适配器配置需求以及您需要设置的配置参数的列表。</span><span class="sxs-lookup"><span data-stu-id="97e2b-112">Create a list of adapter configuration requirements and configuration parameters that you need to set.</span></span> <span data-ttu-id="97e2b-113">如果要对所有接收位置和发送端口全局性地使用这些参数，请在处理程序架构配置文件中指定这些参数。</span><span class="sxs-lookup"><span data-stu-id="97e2b-113">If the parameters are globally used for all receive locations and send ports, specify them in the handler schema configuration file.</span></span> <span data-ttu-id="97e2b-114">如果参数特定于端口或位置，请在发送端口和接收位置配置文件中指定这些参数。</span><span class="sxs-lookup"><span data-stu-id="97e2b-114">If they are port or location specific, configure them in the send port and receive location configuration files.</span></span>  
  
2.  <span data-ttu-id="97e2b-115">修改各适配器属性页，说明所有新的配置参数。</span><span class="sxs-lookup"><span data-stu-id="97e2b-115">Modify the adapter property pages to account for any new configuration parameters.</span></span> <span data-ttu-id="97e2b-116">有关此步骤的信息，请参阅[适配器配置架构](../core/adapter-configuration-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="97e2b-116">For information about this step, see [Adapter Configuration Schemas](../core/adapter-configuration-schemas.md).</span></span>  
  
3.  <span data-ttu-id="97e2b-117">使用“添加适配器元数据”向导修改架构类别的树视图。</span><span class="sxs-lookup"><span data-stu-id="97e2b-117">Modify the tree view of the schema categories by using the Add Adapter Metadata Wizard.</span></span> <span data-ttu-id="97e2b-118">有关此步骤的详细信息，请参阅[添加适配器元数据向导中的架构类别](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)</span><span class="sxs-lookup"><span data-stu-id="97e2b-118">For more information about this step, see [Schema Categories in the Add Adapter Metadata Wizard](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)</span></span>  
  
4.  <span data-ttu-id="97e2b-119">修改示例代码，将架构作为 Web Services 描述语言 (WSDL) 文件返回。</span><span class="sxs-lookup"><span data-stu-id="97e2b-119">Modify the sample code to return schemas as Web Services Description Language (WSDL) files.</span></span> <span data-ttu-id="97e2b-120">有关此步骤的详细信息，请参阅[静态适配器 IStaticAdapterConfig 接口](../core/static-adapter-istaticadapterconfig-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="97e2b-120">For more information about this step, see [Static Adapter IStaticAdapterConfig Interface](../core/static-adapter-istaticadapterconfig-interface.md).</span></span>  
  
5.  <span data-ttu-id="97e2b-121">修改现有的 WSDL 文件，或者创建新的 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="97e2b-121">Modify the existing WSDL files or create new WSDL files.</span></span> <span data-ttu-id="97e2b-122">有关此步骤的详细信息，请参阅[适配器 WSDL 文件](../core/adapter-wsdl-files.md)。</span><span class="sxs-lookup"><span data-stu-id="97e2b-122">For more information about this step, see [Adapter WSDL Files](../core/adapter-wsdl-files.md).</span></span>  
  
6.  <span data-ttu-id="97e2b-123">修改示例代码，以返回适配器所需的但未包含在 WSDL 文件中的附加 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="97e2b-123">Modify the sample code to return additional XSD files needed by the adapter that are not included in the WSDL files.</span></span> <span data-ttu-id="97e2b-124">有关此步骤的详细信息，请参阅[适配器 GetSchema 方法](../core/adapter-getschema-method.md)。</span><span class="sxs-lookup"><span data-stu-id="97e2b-124">For more information about this step, see [Adapter GetSchema Method](../core/adapter-getschema-method.md).</span></span>  
  
7.  <span data-ttu-id="97e2b-125">修改适配器注册表项并运行适配器注册表文件。</span><span class="sxs-lookup"><span data-stu-id="97e2b-125">Modify the adapter registry keys and run the adapter registry file.</span></span> <span data-ttu-id="97e2b-126">有关此步骤的详细信息，请参阅[适配器注册文件](../core/adapter-registration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="97e2b-126">For more information about this step, see [Adapter Registration File](../core/adapter-registration-file.md).</span></span>  
  
8.  <span data-ttu-id="97e2b-127">安装适配器放置于静态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97e2b-127">Install the static adapter into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="97e2b-128">有关此步骤的详细信息，请参阅[到 BizTalk Server 中安装适配器](../core/install-the-adapter-into-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="97e2b-128">For more information about this step, see [Install the Adapter into BizTalk Server](../core/install-the-adapter-into-biztalk-server.md).</span></span>  
  
9. <span data-ttu-id="97e2b-129">测试对适配器属性页所做的更改。</span><span class="sxs-lookup"><span data-stu-id="97e2b-129">Test the changes made to the adapter property pages.</span></span> <span data-ttu-id="97e2b-130">重新生成适配器，以测试在“添加适配器元数据”向导中出现的 UI。</span><span class="sxs-lookup"><span data-stu-id="97e2b-130">Rebuild the adapter to test the UI that appears in the Add Adapter Metadata Wizard.</span></span> <span data-ttu-id="97e2b-131">有关此步骤的详细信息，请参阅[生成和测试适配器项目](../core/build-and-test-the-adapter-project.md)</span><span class="sxs-lookup"><span data-stu-id="97e2b-131">For more information about this step, see [Build and Test the Adapter Project](../core/build-and-test-the-adapter-project.md)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="97e2b-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="97e2b-132">In This Section</span></span>  
  
-   [<span data-ttu-id="97e2b-133">静态适配器 IStaticAdapterConfig 接口</span><span class="sxs-lookup"><span data-stu-id="97e2b-133">Static Adapter IStaticAdapterConfig Interface</span></span>](../core/static-adapter-istaticadapterconfig-interface.md)  
  
-   [<span data-ttu-id="97e2b-134">架构中的类别添加适配器元数据向导</span><span class="sxs-lookup"><span data-stu-id="97e2b-134">Schema Categories in the Add Adapter Metadata Wizard</span></span>](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)