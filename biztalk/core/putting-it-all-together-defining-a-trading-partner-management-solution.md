---
title: "综合： 定义一个贸易合作伙伴管理解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4219312a-c4b5-45f3-b77b-d5cc4f1a1ca4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea32fba8e9e57d7a0549a680b06e08d5bf8e087f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="putting-it-all-together-defining-a-trading-partner-management-solution"></a><span data-ttu-id="d44f8-102">综合： 定义一个贸易合作伙伴管理解决方案</span><span class="sxs-lookup"><span data-stu-id="d44f8-102">Putting it all Together: Defining a Trading Partner Management Solution</span></span>
<span data-ttu-id="d44f8-103">既然我们已经了解了构建 TPM 解决方案所需的不同类型的组件，现在让我们再了解一下典型 TPM 解决方案流以及不同的生成块如何一起工作。</span><span class="sxs-lookup"><span data-stu-id="d44f8-103">Now that we have understood about the different types of components in building a TPM solution, let us understand the flow of a typical TPM solution and how the different building blocks work together.</span></span> <span data-ttu-id="d44f8-104">此部分还列出了一些用于对 TPM 解决方案建模的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="d44f8-104">This section also lists some best practices for modeling a TPM solution.</span></span>  
  
 <span data-ttu-id="d44f8-105">用于创建 TPM 解决方案的典型流程包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="d44f8-105">A typical flow for creating a TPM solution would include the following:</span></span>  
  
1.  <span data-ttu-id="d44f8-106">创建表示业务交易中涉及的所有组织的合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="d44f8-106">Create partners representing all the organizations involved in a business trade.</span></span> <span data-ttu-id="d44f8-107">例如，如果业务交易中涉及两个业务组织，您必须为每个业务组织创建一个贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="d44f8-107">For example, if there are two business organizations involved in a business trade, you must create a trading partner for each of them.</span></span> <span data-ttu-id="d44f8-108">有关如何创建贸易合作伙伴的说明，请参阅[配置常规参与方属性](../core/configuring-general-party-properties.md)或[配置常规参与方属性 (AS2)](../core/configuring-general-party-properties-as2.md)</span><span class="sxs-lookup"><span data-stu-id="d44f8-108">For instructions on how to create trading partners, see [Configuring General Party Properties](../core/configuring-general-party-properties.md) or [Configuring General Party Properties (AS2)](../core/configuring-general-party-properties-as2.md)</span></span>  
  
2.  <span data-ttu-id="d44f8-109">对于组织中的每个业务部门，在代表业务部门的合作伙伴内创建一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="d44f8-109">For each business division within an organization, create a profile within the partner representing the business division.</span></span> <span data-ttu-id="d44f8-110">例如，如果某个组织有“采购”和“供应”业务部门，则每个部门都必须表示为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="d44f8-110">For example, if an organization has “Purchase” and “Supplies” business divisions, each of these divisions must be represented as a business profile in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d44f8-111">另外，您不但要为代表组织的合作伙伴创建业务配置文件，还要为您与之进行交易的合作伙伴创建业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="d44f8-111">Also, you must create the business profiles not just for the partner representing your organization but also the partner with which you trade.</span></span> <span data-ttu-id="d44f8-112">有关如何创建业务配置文件的说明，请参阅[配置业务配置文件属性](../core/configuring-business-profile-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d44f8-112">For instructions on how to create business profiles, see [Configuring Business Profile Properties](../core/configuring-business-profile-properties.md).</span></span>  
  
3.  <span data-ttu-id="d44f8-113">对于每个业务配置文件，定义包含消息编码设置和消息协议设置的 B2B 协议设置。</span><span class="sxs-lookup"><span data-stu-id="d44f8-113">For each business profile, define the B2B protocol settings that include the message encoding setting and the message protocol settings.</span></span> <span data-ttu-id="d44f8-114">这些设置定义如何对 B2B 消息进行编码以及如何在两个业务配置文件之间传输 B2B 消息。</span><span class="sxs-lookup"><span data-stu-id="d44f8-114">These settings define how the B2B messages are encoded and transported between two business profiles.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d44f8-115">指定协议设置在此阶段是可选的。</span><span class="sxs-lookup"><span data-stu-id="d44f8-115">Specifying protocol settings is optional at this stage.</span></span> <span data-ttu-id="d44f8-116">您可以直接将协议设置添加为贸易合作伙伴协议的一部分。</span><span class="sxs-lookup"><span data-stu-id="d44f8-116">You can directly add the protocol settings as part of the trading partner agreement.</span></span>  
  
4.  <span data-ttu-id="d44f8-117">在定义编码的业务配置文件和/或两个业务配置文件同意在交换消息时使用的消息传递协议之间创建贸易合作伙伴协议 (TPA)。</span><span class="sxs-lookup"><span data-stu-id="d44f8-117">Create Trading Partner Agreements (TPA) between the business profiles that define the encoding and/or messaging protocols the two business profiles agree to use while exchanging messages.</span></span> <span data-ttu-id="d44f8-118">有关如何创建协议的说明，请参阅[配置 X12 特定协议属性](../core/configuring-x12-specific-agreement-properties.md)，[配置 EDIFACT 特定协议属性](../core/configuring-edifact-specific-agreement-properties.md)，或[配置 AS2协议属性](../core/configuring-as2-agreement-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d44f8-118">For instructions on how to create agreements, see [Configuring X12-Specific Agreement Properties](../core/configuring-x12-specific-agreement-properties.md), [Configuring EDIFACT-Specific Agreement Properties](../core/configuring-edifact-specific-agreement-properties.md), or [Configuring AS2 Agreement Properties](../core/configuring-as2-agreement-properties.md).</span></span>  
  
 <span data-ttu-id="d44f8-119">通过执行上述的任务，您已经创建 TPM 解决方案以与您的贸易合作伙伴交换 B2B 消息。</span><span class="sxs-lookup"><span data-stu-id="d44f8-119">By performing the above set of tasks you would have created TPM solution to exchange B2B messages with your trading partner.</span></span>  
  
## <a name="where-do-i-start"></a><span data-ttu-id="d44f8-120">其中开始？</span><span class="sxs-lookup"><span data-stu-id="d44f8-120">Where do I Start?</span></span>  
 <span data-ttu-id="d44f8-121">您可以通过浏览以下部分开始：</span><span class="sxs-lookup"><span data-stu-id="d44f8-121">You can start by going through the following sections:</span></span>  
  
-   <span data-ttu-id="d44f8-122">在 X12 特定教程[教程 2: EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="d44f8-122">X12-specific tutorial at [Tutorial 2: EDI Interface Developer Tutorial](../core/tutorial-2-edi-interface-developer-tutorial.md).</span></span>  
  
-   <span data-ttu-id="d44f8-123">AS2 特定本教程[教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="d44f8-123">AS2-specific tutorial at [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  
  
-   <span data-ttu-id="d44f8-124">X12-和 EDIFACT-下的特定演练[开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="d44f8-124">X12- and EDIFACT-specific walkthroughs under [Developing and Configuring BizTalk Server EDI Solutions](../core/developing-and-configuring-biztalk-server-edi-solutions.md).</span></span>  
  
-   <span data-ttu-id="d44f8-125">AS2 特定演练下的[开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="d44f8-125">AS2-specific walkthroughs under [Developing and Configuring BizTalk Server AS2 Solutions](../core/developing-and-configuring-biztalk-server-as2-solutions.md).</span></span>  
  
-   <span data-ttu-id="d44f8-126">创建方、 配置文件和的 X12 和 EDIFACT 消息传送按照说明在协议[配置 EDI 属性](../core/configuring-edi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d44f8-126">Create parties, profiles, and agreements for X12 and EDIFACT messaging by following instructions at [Configuring EDI Properties](../core/configuring-edi-properties.md).</span></span>  
  
-   <span data-ttu-id="d44f8-127">创建方、 配置文件和的 AS2 协议在按照说明消息传送[配置 AS2 属性](../core/configuring-as2-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d44f8-127">Create parties, profiles, and agreements for AS2 messaging by following instructions at [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44f8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d44f8-128">See Also</span></span>  
 [<span data-ttu-id="d44f8-129">贸易合作伙伴管理解决方案的构建基块</span><span class="sxs-lookup"><span data-stu-id="d44f8-129">Building Blocks of a Trading Partner Management Solution</span></span>](../core/building-blocks-of-a-trading-partner-management-solution.md)