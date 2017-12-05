---
title: "使用动态数据验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic data validation
- validating, dynamic data
ms.assetid: 8dac7f74-92a7-447c-97bf-b1f3ce39b614
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3387117648329828c9276545eafddca6872c4aa2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="using-dynamic-data-validation"></a><span data-ttu-id="0ce6f-102">使用动态数据验证</span><span class="sxs-lookup"><span data-stu-id="0ce6f-102">Using Dynamic Data Validation</span></span>
<span data-ttu-id="0ce6f-103">动态数据验证的一个重要部分正在验证针对动态数据，其中包括验证的消息格式和消息内容的消息内容。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-103">An important part of dynamic data validation is validating message content against dynamic data, which includes validating the message format and the message content.</span></span> <span data-ttu-id="0ce6f-104">文档架构，其中[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server XSD 文件中实现、 定义和验证消息格式。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-104">A document schema, which [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server implements in an XSD file, defines and validates message formats.</span></span> <span data-ttu-id="0ce6f-105">业务规则定义消息内容，其中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]通过业务规则引擎策略验证。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-105">Business rules define message content, which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] validates through Business Rule Engine policies.</span></span> <span data-ttu-id="0ce6f-106">内容验证可以包括确认消息实例中的数据与可能随相对频率发生变化的数据匹配。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-106">Content validation can include confirmation that data in the message instance matches data that may change with relative frequency.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="0ce6f-107">[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]以动态方式实现这种类型的验证，以便你可以更新在生产环境中，此数据，而无需重新编译代码，或关闭服务。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-107">[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] implements this type of validation in a dynamic manner, so that you can update this data in a production environment, without having to recompile code or shut down services.</span></span>  
  
## <a name="validate-and-expose-data"></a><span data-ttu-id="0ce6f-108">验证和公开这样的数据</span><span class="sxs-lookup"><span data-stu-id="0ce6f-108">Validate and Expose Data</span></span>  
 <span data-ttu-id="0ce6f-109">在执行动态数据验证 (DDV) 有两个步骤：</span><span class="sxs-lookup"><span data-stu-id="0ce6f-109">There are two steps in performing Dynamic Data Validation (DDV):</span></span>  
  
-   <span data-ttu-id="0ce6f-110">公开的数据。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-110">Expose the data.</span></span>  
  
-   <span data-ttu-id="0ce6f-111">将使用该数据的验证规则的应用。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-111">Apply validation rules using that data.</span></span>  
  
 <span data-ttu-id="0ce6f-112">DDV 提供用于存储、 公开，和缓存动态数据的以下支持：</span><span class="sxs-lookup"><span data-stu-id="0ce6f-112">DDV provides the following support for storing, exposing, and caching dynamic data:</span></span>  
  
-   <span data-ttu-id="0ce6f-113">业务规则引擎或消息类执行验证。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-113">The Business Rule Engine or Message Class performs validation.</span></span>  
  
-   <span data-ttu-id="0ce6f-114">业务规则引擎公开数据通过数据库表列词汇。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-114">The Business Rule Engine exposes data through the Database table column vocabulary.</span></span> <span data-ttu-id="0ce6f-115">业务规则引擎通过实现从管道或业务流程中运行的规则集验证针对消息此动态数据。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-115">The Business Rule Engine validates this dynamic data against messages by implementing a rule set that runs from a pipeline or orchestration.</span></span>  
  
-   <span data-ttu-id="0ce6f-116">现有的 SQL 接口，如 SQL 企业管理器和查询分析器中，在设计时是被动的公开动态数据。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-116">Existing SQL interfaces, such as SQL Enterprise Manager and Query Analyzer, expose dynamic data that is passive at design time.</span></span>  
  
-   <span data-ttu-id="0ce6f-117">业务规则引擎数据库表列词汇定义显示在运行时动态数据。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-117">The Business Rule Engine database table column vocabulary definition exposes dynamic data at run time.</span></span>  
  
-   <span data-ttu-id="0ce6f-118">业务规则引擎在运行时公开消息实例数据。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-118">The Business Rule Engine exposes message instance data at run time.</span></span>  
  
-   <span data-ttu-id="0ce6f-119">业务规则引擎 XML 文档词汇定义在设计时显示消息实例数据。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-119">A Business Rules Engine XML document vocabulary definition exposes message instance data at design time.</span></span>  
  
-   <span data-ttu-id="0ce6f-120">您可将规则在设计时在业务规则编辑器用户界面或直接在业务规则语言 (BRL) XML 文本编辑器中。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-120">You can compose rules at design time in the Business Rule Composer user interface or directly in Business Rules Language (BRL) XML in a text editor.</span></span>  
  
 <span data-ttu-id="0ce6f-121">有关业务规则和业务规则引擎的详细信息，请参阅"开发与业务规则"BizTalk Server 帮助中。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-121">For more information about business rules and the Business Rule Engine, see "Developing with Business Rules" in BizTalk Server Help.</span></span>  
  
## <a name="extending-ddv"></a><span data-ttu-id="0ce6f-122">扩展 DDV</span><span class="sxs-lookup"><span data-stu-id="0ce6f-122">Extending DDV</span></span>  
 <span data-ttu-id="0ce6f-123">如果您更改 HL7 基于跨字段验证或数据类型验证，则必须将记录以下两项操作：</span><span class="sxs-lookup"><span data-stu-id="0ce6f-123">If you change HL7-based cross-field validation or data type validation, you must note two things:</span></span>  
  
-   <span data-ttu-id="0ce6f-124">如果修改现有规则，你不需要重新部署。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-124">If you modify an existing rule, you do not need to redeploy.</span></span>  
  
-   <span data-ttu-id="0ce6f-125">如果你创建或删除管道组件会影响新规则，然后你必须重新编译。</span><span class="sxs-lookup"><span data-stu-id="0ce6f-125">If you create or delete a new rule that a pipeline component affects, then you must recompile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce6f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ce6f-126">See Also</span></span>  
 <span data-ttu-id="0ce6f-127">[编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="0ce6f-127">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 [<span data-ttu-id="0ce6f-128">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="0ce6f-128">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)