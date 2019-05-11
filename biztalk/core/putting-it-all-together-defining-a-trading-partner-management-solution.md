---
title: 配合使用：定义贸易合作伙伴管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4219312a-c4b5-45f3-b77b-d5cc4f1a1ca4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b56ba4f5bf6918f9a2499135c25ad7526a90c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398338"
---
# <a name="putting-it-all-together-defining-a-trading-partner-management-solution"></a><span data-ttu-id="c4b3f-102">配合使用：定义贸易合作伙伴管理解决方案</span><span class="sxs-lookup"><span data-stu-id="c4b3f-102">Putting it all Together: Defining a Trading Partner Management Solution</span></span>
<span data-ttu-id="c4b3f-103">现在，我们已经了解不同类型的构建 TPM 解决方案中的组件，让我们了解一下典型 TPM 解决方案和其他构建基块如何协同工作的流。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-103">Now that we have understood about the different types of components in building a TPM solution, let us understand the flow of a typical TPM solution and how the different building blocks work together.</span></span> <span data-ttu-id="c4b3f-104">本部分还列出了对 TPM 解决方案建模一些最佳的做法。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-104">This section also lists some best practices for modeling a TPM solution.</span></span>  
  
 <span data-ttu-id="c4b3f-105">用于创建 TPM 解决方案的典型流包括以下：</span><span class="sxs-lookup"><span data-stu-id="c4b3f-105">A typical flow for creating a TPM solution would include the following:</span></span>  
  
1. <span data-ttu-id="c4b3f-106">创建合作伙伴，用于表示参与商业贸易的的所有组织。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-106">Create partners representing all the organizations involved in a business trade.</span></span> <span data-ttu-id="c4b3f-107">例如，如果有业务交易中涉及的两个业务组织，您必须创建为每个贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-107">For example, if there are two business organizations involved in a business trade, you must create a trading partner for each of them.</span></span> <span data-ttu-id="c4b3f-108">有关如何创建贸易合作伙伴的说明，请参阅[配置常规参与方属性](../core/configuring-general-party-properties.md)或[配置常规参与方属性 (AS2)](../core/configuring-general-party-properties-as2.md)</span><span class="sxs-lookup"><span data-stu-id="c4b3f-108">For instructions on how to create trading partners, see [Configuring General Party Properties](../core/configuring-general-party-properties.md) or [Configuring General Party Properties (AS2)](../core/configuring-general-party-properties-as2.md)</span></span>  
  
2. <span data-ttu-id="c4b3f-109">对于组织中每个业务部门，创建代表业务部门的合作伙伴内的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-109">For each business division within an organization, create a profile within the partner representing the business division.</span></span> <span data-ttu-id="c4b3f-110">例如，如果组织有"购买"和"供应"业务部门，每个部门必须表示为业务配置文件中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-110">For example, if an organization has “Purchase” and “Supplies” business divisions, each of these divisions must be represented as a business profile in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c4b3f-111">此外，您必须不只是为表示你的组织，但也与之进行交易的合作伙伴的合作伙伴创建业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-111">Also, you must create the business profiles not just for the partner representing your organization but also the partner with which you trade.</span></span> <span data-ttu-id="c4b3f-112">有关如何创建业务配置文件的说明，请参阅[配置业务配置文件属性](../core/configuring-business-profile-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-112">For instructions on how to create business profiles, see [Configuring Business Profile Properties](../core/configuring-business-profile-properties.md).</span></span>  
  
3. <span data-ttu-id="c4b3f-113">对于每个业务配置文件中，定义包含消息编码设置和消息协议设置的 B2B 协议设置。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-113">For each business profile, define the B2B protocol settings that include the message encoding setting and the message protocol settings.</span></span> <span data-ttu-id="c4b3f-114">这些设置定义如何编码和两个业务配置文件之间传输 B2B 消息。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-114">These settings define how the B2B messages are encoded and transported between two business profiles.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c4b3f-115">指定协议设置在此阶段是可选。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-115">Specifying protocol settings is optional at this stage.</span></span> <span data-ttu-id="c4b3f-116">作为贸易合作伙伴协议的一部分，可以直接添加协议设置。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-116">You can directly add the protocol settings as part of the trading partner agreement.</span></span>  
  
4. <span data-ttu-id="c4b3f-117">定义两个业务配置文件都同意交换消息时使用的编码和/或消息传送协议的业务配置文件之间创建贸易合作伙伴协议 (TPA)。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-117">Create Trading Partner Agreements (TPA) between the business profiles that define the encoding and/or messaging protocols the two business profiles agree to use while exchanging messages.</span></span> <span data-ttu-id="c4b3f-118">有关如何创建协议的说明，请参阅[配置特定于 X12 的协议属性](../core/configuring-x12-specific-agreement-properties.md)，[配置特定于 EDIFACT 的协议属性](../core/configuring-edifact-specific-agreement-properties.md)，或[配置 AS2协议属性](../core/configuring-as2-agreement-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-118">For instructions on how to create agreements, see [Configuring X12-Specific Agreement Properties](../core/configuring-x12-specific-agreement-properties.md), [Configuring EDIFACT-Specific Agreement Properties](../core/configuring-edifact-specific-agreement-properties.md), or [Configuring AS2 Agreement Properties](../core/configuring-as2-agreement-properties.md).</span></span>  
  
   <span data-ttu-id="c4b3f-119">通过执行上述任务应已创建 TPM 解决方案以与您的贸易合作伙伴交换 B2B 消息。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-119">By performing the above set of tasks you would have created TPM solution to exchange B2B messages with your trading partner.</span></span>  
  
## <a name="where-do-i-start"></a><span data-ttu-id="c4b3f-120">如何开始？</span><span class="sxs-lookup"><span data-stu-id="c4b3f-120">Where do I Start?</span></span>  
 <span data-ttu-id="c4b3f-121">您可以首先通过以下各节：</span><span class="sxs-lookup"><span data-stu-id="c4b3f-121">You can start by going through the following sections:</span></span>  
  
-   <span data-ttu-id="c4b3f-122">在特定于 X12 的教程[教程 2:EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-122">X12-specific tutorial at [Tutorial 2: EDI Interface Developer Tutorial](../core/tutorial-2-edi-interface-developer-tutorial.md).</span></span>  
  
-   <span data-ttu-id="c4b3f-123">在特定于 AS2 教程[教程 3:AS2 教程](../core/tutorial-3-as2-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-123">AS2-specific tutorial at [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  
  
-   <span data-ttu-id="c4b3f-124">X12-和 EDIFACT-在特定演练[开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-124">X12- and EDIFACT-specific walkthroughs under [Developing and Configuring BizTalk Server EDI Solutions](../core/developing-and-configuring-biztalk-server-edi-solutions.md).</span></span>  
  
-   <span data-ttu-id="c4b3f-125">在特定于 AS2 的演练[开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-125">AS2-specific walkthroughs under [Developing and Configuring BizTalk Server AS2 Solutions](../core/developing-and-configuring-biztalk-server-as2-solutions.md).</span></span>  
  
-   <span data-ttu-id="c4b3f-126">创建参与方、 配置文件和协议用于 X12 和 EDIFACT 消息传送在按照的说明[配置 EDI 属性](../core/configuring-edi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-126">Create parties, profiles, and agreements for X12 and EDIFACT messaging by following instructions at [Configuring EDI Properties](../core/configuring-edi-properties.md).</span></span>  
  
-   <span data-ttu-id="c4b3f-127">创建参与方、 配置文件，以及按说明操作，在消息传送 as2 协议[配置 AS2 属性](../core/configuring-as2-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b3f-127">Create parties, profiles, and agreements for AS2 messaging by following instructions at [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b3f-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b3f-128">See Also</span></span>  
 [<span data-ttu-id="c4b3f-129">贸易合作伙伴管理解决方案的构建基块</span><span class="sxs-lookup"><span data-stu-id="c4b3f-129">Building Blocks of a Trading Partner Management Solution</span></span>](../core/building-blocks-of-a-trading-partner-management-solution.md)