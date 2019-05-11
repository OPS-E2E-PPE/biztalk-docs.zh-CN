---
title: 适配器和 BizTalk Server 中的加速器 |Microsoft Docs
description: 所有适配器和加速器在 BizTalk 中，包括内置适配器、 BAP、 HL7、 Swift、 RosettaNet、 FileAct 和交互的概述
caps.latest.revision: 3
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df7f26a1-e47b-4323-b9f0-58842c55a6f8
ms.author: mandia
ms.openlocfilehash: 5d1d43e53a385f8b2116845fac0a4303f4ec388d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367346"
---
# <a name="adapters-and-accelerators-in-biztalk-server"></a><span data-ttu-id="8a4f1-103">适配器和 BizTalk Server 中的加速器</span><span class="sxs-lookup"><span data-stu-id="8a4f1-103">Adapters and Accelerators in BizTalk Server</span></span>
 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8a4f1-104">包括不同的适配器和加速器，以便创建接收数据，并将数据发送到不同的服务和 LOB 系统应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-104">includes different adapters and accelerators for you to create applications that receive data, and send data to different services and LOB systems.</span></span> 
 
<span data-ttu-id="8a4f1-105">本部分介绍不同的适配器和加速器适用于[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-105">This section describes the different adapters and accelerators available with  [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

## <a name="out-of-the-box-adapters"></a><span data-ttu-id="8a4f1-106">开箱适配器</span><span class="sxs-lookup"><span data-stu-id="8a4f1-106">Out-of-the-box adapters</span></span>
<span data-ttu-id="8a4f1-107">在安装 BizTalk Server 时，您还会安装可供使用的内置适配器。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-107">When you install BizTalk Server, you also install the built-in adapters that are ready to be used.</span></span> <span data-ttu-id="8a4f1-108">一些这些适配器包括文件、 FTP、 MQ Series、 服务总线、 逻辑应用、 POP3、 SharePoint 和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-108">Some of these adapters include File, FTP, MQ Series, Service Bus, Logic Apps, POP3, SharePoint, and more.</span></span>

<span data-ttu-id="8a4f1-109">**[使用适配器](../core/using-adapters.md)列出了所有这些问题，并还演示如何使用每个适配器。**</span><span class="sxs-lookup"><span data-stu-id="8a4f1-109">**[Using Adapters](../core/using-adapters.md) lists all of them, and also shows you how to use each adapter.**</span></span>
 
## <a name="biztalk-adapter-pack"></a><span data-ttu-id="8a4f1-110">BizTalk 适配器包</span><span class="sxs-lookup"><span data-stu-id="8a4f1-110">BizTalk Adapter Pack</span></span>
<span data-ttu-id="8a4f1-111">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并提供了基于 WCF 的适配器，以连接您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 Oracle、 SAP、 Siebel 和 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-111">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] is included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and provides WCF-based adapters to connect your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to Oracle, SAP, Siebel, and SQL Server.</span></span> <span data-ttu-id="8a4f1-112">此外可以创建使用你自己的基于 WCF 的适配器[!INCLUDE[afproductnameshort_md](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-112">You can also create your own WCF-based adapters using the [!INCLUDE[afproductnameshort_md](../includes/afproductnameshort-md.md)].</span></span> 

<span data-ttu-id="8a4f1-113">**请参阅[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)来安装和配置这些适配器，单步执行教程和方案中，创建应用程序使用不同的适配器，并获取清楚地了解如何基于 WCF 的服务处理消息。**</span><span class="sxs-lookup"><span data-stu-id="8a4f1-113">**See [BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md) to install and configure these adapters, step through tutorials and scenarios, create applications using the different adapters, and get a good idea of how WCF-based services process messages.**</span></span>

## <a name="adapters-for-enterprise-applications"></a><span data-ttu-id="8a4f1-114">用于企业应用程序适配器</span><span class="sxs-lookup"><span data-stu-id="8a4f1-114">Adapters for Enterprise Applications</span></span>
<span data-ttu-id="8a4f1-115">这些适配器所含[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-115">These adapters are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="8a4f1-116">使用这些适配器将使用 JD Edwards EnterpriseOne，JD Edwards OneWorld 的 BizTalk Server、 PeopleSoft Enterprise、 TIBCO Enterprise Message Service 和 TIBCO Rendezvous 连接。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-116">Use these adapters to connect your BizTalk Server with JD Edwards EnterpriseOne, JD Edwards OneWorld, PeopleSoft Enterprise, TIBCO Enterprise Message Service, and TIBCO Rendezvous.</span></span>

<span data-ttu-id="8a4f1-117">**请参阅[企业应用程序的 BizTalk 适配器](biztalk-adapters-for-enterprise-applications.md)若要安装和配置这些适配器，单步执行教程和方案中，创建使用不同的适配器，以及更多的应用程序。**</span><span class="sxs-lookup"><span data-stu-id="8a4f1-117">**See [BizTalk Adapter for Enterprise Applications](biztalk-adapters-for-enterprise-applications.md) to install and configure these adapters, step through tutorials and scenarios, create applications using the different adapters, and more.**</span></span> 


## <a name="fileact-and-interact"></a><span data-ttu-id="8a4f1-118">FileAct 和交互</span><span class="sxs-lookup"><span data-stu-id="8a4f1-118">FileAct and InterAct</span></span>
<span data-ttu-id="8a4f1-119">[!INCLUDE[swift_adapter_md](../includes/swift-adapter-md.md)]附带[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并提供之间的连接你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]和社会全球 Interbank 金融电信 (SWIFT) Secure IP Network (SIPN) 有关。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-119">The [!INCLUDE[swift_adapter_md](../includes/swift-adapter-md.md)] are included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and provide connectivity between your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] and the Society for Worldwide Interbank Financial Telecommunication (SWIFT) Secure IP Network (SIPN).</span></span> 

<span data-ttu-id="8a4f1-120">FileAct 适配器提供了安全且可靠的文件，并对这些文件相关的信息的交换。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-120">The FileAct adapter provides secure and reliable exchange of files, and information pertaining to those files.</span></span> 

<span data-ttu-id="8a4f1-121">InterAct 适配器提供了安全且可靠的单个结构化的财务消息的交换。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-121">The InterAct adapter provides secure and reliable exchange of individual structured financial messages.</span></span> 

<span data-ttu-id="8a4f1-122">**请参阅[FileAct 和 InterAct](../adapters-and-accelerators/fileact-interact/microsoft-biztalk-server-fileact-and-interact-adapters-documentation.md)来安装和配置这些适配器，单步执行一些教程和方案，并充分了解体系结构。**</span><span class="sxs-lookup"><span data-stu-id="8a4f1-122">**See [FileAct and InterAct](../adapters-and-accelerators/fileact-interact/microsoft-biztalk-server-fileact-and-interact-adapters-documentation.md) to install and configure these adapters, step through some tutorials and scenarios, and get a good understanding of the architecture.**</span></span> 

## <a name="hl7"></a><span data-ttu-id="8a4f1-123">HL7</span><span class="sxs-lookup"><span data-stu-id="8a4f1-123">HL7</span></span>

<span data-ttu-id="8a4f1-124">[!INCLUDE[btaBTAHL7NoNumber_md](../includes/btabtahl7nonumber-md.md)]附带[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并提供之间的连接在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]和卫生保健计算机应用程序基于运行状况级别 7 (HL7) 标准。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-124">The [!INCLUDE[btaBTAHL7NoNumber_md](../includes/btabtahl7nonumber-md.md)] is included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and provides connectivity between your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] and health care computer applications based on the Health Level Seven (HL7) standard.</span></span>

<span data-ttu-id="8a4f1-125">**请参阅[HL7](../adapters-and-accelerators/accelerator-hl7/microsoft-biztalk-accelerator-for-hl7-documentation.md)来安装和配置的适配器，单步执行几个教程和方案，了解该适配器的工作原理，并使用不同的功能，包括架构、 确认、 批处理、 验证和的详细信息。**</span><span class="sxs-lookup"><span data-stu-id="8a4f1-125">**See [HL7](../adapters-and-accelerators/accelerator-hl7/microsoft-biztalk-accelerator-for-hl7-documentation.md) to install and configure the adapter, step through several tutorials and scenarios, learn how the adapter works, and use the different features, including schemas, acknowledgments, batching, validation, and more.**</span></span>

## <a name="rosettanet"></a><span data-ttu-id="8a4f1-126">RosettaNet</span><span class="sxs-lookup"><span data-stu-id="8a4f1-126">RosettaNet</span></span>
<span data-ttu-id="8a4f1-127">BizTalk Accelerator for RosettaNet (BTARN) 是包含在 BizTalk Server，并简化了开发和部署的 RosettaNet 基于标准的集成解决方案。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-127">The BizTalk Accelerator for RosettaNet (BTARN) is included with BizTalk Server, and streamlines the development and deployment of RosettaNet standards-based integration solutions.</span></span> <span data-ttu-id="8a4f1-128">BTARN 支持 RosettaNet 实现框架 (RNIF);这是一种开放式网络应用程序框架，使业务合作伙伴能够协同运行 RosettaNet 合作伙伴接口流程 (Pip)。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-128">BTARN supports the RosettaNet Implementation Framework (RNIF); which is an open network application framework that enables business partners to collaboratively run RosettaNet Partner Interface Processes (PIPs).</span></span> 

<span data-ttu-id="8a4f1-129">**请参阅[RosettaNet](../adapters-and-accelerators/accelerator-rosettanet/microsoft-biztalk-accelerator-for-rosettanet-documentation.md)若要了解有关此加速器，并使用与 BizTalk Server 解决方案的详细信息。**</span><span class="sxs-lookup"><span data-stu-id="8a4f1-129">**See [RosettaNet](../adapters-and-accelerators/accelerator-rosettanet/microsoft-biztalk-accelerator-for-rosettanet-documentation.md) to learn more about this accelerator, and using it with your BizTalk Server solutions.**</span></span> 

## <a name="swift"></a><span data-ttu-id="8a4f1-130">SWIFT</span><span class="sxs-lookup"><span data-stu-id="8a4f1-130">SWIFT</span></span>
<span data-ttu-id="8a4f1-131">[!INCLUDE[btaA4SWIFTNoVersion_md](../includes/btaa4swiftnoversion-md.md)]附带[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并提供之间的连接在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]和社会的全球 Interbank 金融电信 (SWIFT) 消息格式。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-131">The [!INCLUDE[btaA4SWIFTNoVersion_md](../includes/btaa4swiftnoversion-md.md)] is included with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and provides connectivity between your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] and the Society for Worldwide Interbank Financial Telecommunication (SWIFT) message formats.</span></span>

<span data-ttu-id="8a4f1-132">使用与适配器[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，客户、 合作伙伴和系统集成商可以简化开发、 部署和支持的核心金融服务应用程序基础结构和业务流程的集成解决方案。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-132">Using the adapter with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], customers, partners, and system integrators can streamline the development, deployment, and support of integration solutions for core financial services application infrastructure and business processes.</span></span>

<span data-ttu-id="8a4f1-133">**请参阅[SWIFT](../adapters-and-accelerators/accelerator-swift/microsoft-biztalk-accelerator-for-swift-documentation.md)若要安装和配置该适配器，单步执行一些教程，并使用消息修复、 FIN 响应和 FRR 项目和的详细信息。**</span><span class="sxs-lookup"><span data-stu-id="8a4f1-133">**See [SWIFT](../adapters-and-accelerators/accelerator-swift/microsoft-biztalk-accelerator-for-swift-documentation.md) to install and configure the adapter, step through some tutorials, and use the message repair, FIN response and FRR artifacts, and more.**</span></span>

## <a name="get-some-help"></a><span data-ttu-id="8a4f1-134">获取帮助</span><span class="sxs-lookup"><span data-stu-id="8a4f1-134">Get some help</span></span> 
<span data-ttu-id="8a4f1-135">获取一些帮助，并帮助中的其他人[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]论坛[ http://go.microsoft.com/fwlink/p/?LinkId=87695 ](http://go.microsoft.com/fwlink/p/?LinkId=87695)。</span><span class="sxs-lookup"><span data-stu-id="8a4f1-135">Get some help, and help others in the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] forums at [http://go.microsoft.com/fwlink/p/?LinkId=87695](http://go.microsoft.com/fwlink/p/?LinkId=87695).</span></span>