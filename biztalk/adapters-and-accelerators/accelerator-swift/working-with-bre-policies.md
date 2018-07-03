---
title: 使用 BRE 策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BRE policies, about BRE policies
- BRE policies
ms.assetid: 4470f2b3-6891-46d7-9ba1-848f90d0767d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdb05d6f11d0d4d4f4ef5fd990d05c51b5e0df64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968950"
---
# <a name="working-with-bre-policies"></a><span data-ttu-id="ae22e-102">使用 BRE 策略</span><span class="sxs-lookup"><span data-stu-id="ae22e-102">Working with BRE Policies</span></span>
<span data-ttu-id="ae22e-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]验证 SWIFT 消息通过使用业务规则引擎 (BRE) 策略，如中所述*SWIFT 参考指南*。</span><span class="sxs-lookup"><span data-stu-id="ae22e-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] validates SWIFT messages by using Business Rule Engine (BRE) polices, as described in the *SWIFT Reference Guide*.</span></span> <span data-ttu-id="ae22e-104">这些策略包括：</span><span class="sxs-lookup"><span data-stu-id="ae22e-104">These policies include the following:</span></span>  

- <span data-ttu-id="ae22e-105">格式设置</span><span class="sxs-lookup"><span data-stu-id="ae22e-105">Formatting</span></span>  

- <span data-ttu-id="ae22e-106">值范围</span><span class="sxs-lookup"><span data-stu-id="ae22e-106">Value range</span></span>  

- <span data-ttu-id="ae22e-107">有效的列表条目</span><span class="sxs-lookup"><span data-stu-id="ae22e-107">Valid list entries</span></span>  

- <span data-ttu-id="ae22e-108">相应的错误代码的网络规则</span><span class="sxs-lookup"><span data-stu-id="ae22e-108">Network rules with corresponding error codes</span></span>  

- <span data-ttu-id="ae22e-109">可以从消息内容进行验证的使用规则</span><span class="sxs-lookup"><span data-stu-id="ae22e-109">Usage rules that can be validated from the message content</span></span>  

  <span data-ttu-id="ae22e-110">这些策略不包括不依赖于消息内容或任何跨消息验证的常规做法。</span><span class="sxs-lookup"><span data-stu-id="ae22e-110">These policies do not include general practices that are not dependent on the message content, or any cross-message validations.</span></span>  

  <span data-ttu-id="ae22e-111">消息 （和标头和尾部） 的 XSD 架构实现基本字段可选性和基数，同时实现 SWIFT 基本 Types.xsd 架构的格式设置引用的消息架构。</span><span class="sxs-lookup"><span data-stu-id="ae22e-111">The XSD schema for the message (and header and trailer) implements basic field optionality and cardinality, while the message schema that implements formatting references the SWIFT Base Types.xsd schema.</span></span> <span data-ttu-id="ae22e-112">用于每种消息类型的两个特定策略定义与每个消息关联的规则：</span><span class="sxs-lookup"><span data-stu-id="ae22e-112">Two specific policies for each message type define the rules associated with each message:</span></span>  

- <span data-ttu-id="ae22e-113">主机策略 (MT*xxx*_Master_Policy.xml)</span><span class="sxs-lookup"><span data-stu-id="ae22e-113">Master policy (MT*xxx*_Master_Policy.xml)</span></span>  

- <span data-ttu-id="ae22e-114">验证策略 (MT*xxx*_Validation_Policy.xml)</span><span class="sxs-lookup"><span data-stu-id="ae22e-114">Validation policy (MT*xxx*_Validation_Policy.xml)</span></span>  

  <span data-ttu-id="ae22e-115">每种消息类型的主策略调用应用于该消息类型的特定策略。</span><span class="sxs-lookup"><span data-stu-id="ae22e-115">The master policy for each message type invokes the specific policies that apply to that message type.</span></span> <span data-ttu-id="ae22e-116">这些特定的策略包括特殊字段检查的常见函数实现中，网络规则，并使用规则。</span><span class="sxs-lookup"><span data-stu-id="ae22e-116">These specific policies include special field checks that common functions implement, network rules, and usage rules.</span></span> <span data-ttu-id="ae22e-117">消息的主策略是运行该消息的第一个策略。</span><span class="sxs-lookup"><span data-stu-id="ae22e-117">The master policy for the message is the first policy run for that message.</span></span> <span data-ttu-id="ae22e-118">策略列表包括消息类型的验证策略。</span><span class="sxs-lookup"><span data-stu-id="ae22e-118">The list of policies includes the validation policy for the message type.</span></span> <span data-ttu-id="ae22e-119">每个主策略已构造"如果此消息类型，然后运行的策略列表"。</span><span class="sxs-lookup"><span data-stu-id="ae22e-119">Each master policy has the construct "if this message type, then run the list of policies".</span></span>  

  <span data-ttu-id="ae22e-120">每种消息类型的验证策略列出了其他外部规则实现，如域代码的单个字段检查，或使用特定词汇的字段。</span><span class="sxs-lookup"><span data-stu-id="ae22e-120">The validation policy for each message type lists the single-field checks that other external rules implement, such as field codes, or uses a specific vocabulary for the field.</span></span> <span data-ttu-id="ae22e-121">这些单独的规则有两个或多个消息，在通常通用，因为它们是特定于字段的。</span><span class="sxs-lookup"><span data-stu-id="ae22e-121">These individual rules are generally common across two or more messages, because they are field-specific.</span></span> <span data-ttu-id="ae22e-122">BRE 词汇 A4SWIFT_Codelists 不编程代码中，提供允许的字段值。</span><span class="sxs-lookup"><span data-stu-id="ae22e-122">The A4SWIFT_Codelists in the BRE vocabulary, not programming code, provide the allowed field values.</span></span>  

  <span data-ttu-id="ae22e-123">*SWIFT 参考指南*单独实现每个网络规则。</span><span class="sxs-lookup"><span data-stu-id="ae22e-123">The *SWIFT Reference Guide* implements each of the network rules independently.</span></span> <span data-ttu-id="ae22e-124">每个网络规则解决的一套消息类型*SWIFT 参考指南*定义。</span><span class="sxs-lookup"><span data-stu-id="ae22e-124">Each network rule addresses the set of message types that the *SWIFT Reference Guide* defines.</span></span>  

  <span data-ttu-id="ae22e-125">A4SWIFT 安装时，A4SWIFT 安装程序不会安装规则。</span><span class="sxs-lookup"><span data-stu-id="ae22e-125">A4SWIFT Setup does not install rules when it installs A4SWIFT.</span></span> <span data-ttu-id="ae22e-126">您选择的架构，并生成和部署程序集后，你可以使用 BRE 部署实用工具用于选择和部署架构集中的相应规则。</span><span class="sxs-lookup"><span data-stu-id="ae22e-126">After you select the schemas, and build and deploy an assembly, you can use the BRE Deployment Utility to select and deploy the appropriate rules for the schema set.</span></span> <span data-ttu-id="ae22e-127">若要部署的所选消息的规则，运行该实用程序，并选择相关的程序集。</span><span class="sxs-lookup"><span data-stu-id="ae22e-127">To deploy the rules for the selected messages, run the utility and select the relevant assemblies.</span></span> <span data-ttu-id="ae22e-128">该工具选择相应的主策略、 验证策略和任何被引用的网络或其他规则。</span><span class="sxs-lookup"><span data-stu-id="ae22e-128">The tool selects the corresponding master policies, validation policies, and any referenced network or other rules.</span></span>  

  <span data-ttu-id="ae22e-129">A4SWIFT A4SWIFT 规则相关联词汇的两种的类型。</span><span class="sxs-lookup"><span data-stu-id="ae22e-129">A4SWIFT associates two types of vocabularies with A4SWIFT rules.</span></span> <span data-ttu-id="ae22e-130">第一个词汇是 A4SWIFT_Codelist，其中包含各种代码列表值。</span><span class="sxs-lookup"><span data-stu-id="ae22e-130">The first vocabulary is A4SWIFT_Codelist, which contains the various code-list values.</span></span> <span data-ttu-id="ae22e-131">第二个词汇是 A4SWIFT_Functions。</span><span class="sxs-lookup"><span data-stu-id="ae22e-131">The second vocabulary is A4SWIFT_Functions.</span></span> <span data-ttu-id="ae22e-132">这些词汇是[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]用于逻辑验证和计算的类。</span><span class="sxs-lookup"><span data-stu-id="ae22e-132">These vocabularies are [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] classes for logic validations and calculations.</span></span>  

  <span data-ttu-id="ae22e-133">可以通过将 BRE 验证配置参数设置为 true 来调用 A4SWIFT 拆装器在接收管道中，规则。</span><span class="sxs-lookup"><span data-stu-id="ae22e-133">You can invoke the rules by the A4SWIFT disassembler in a receive pipeline, by setting the BRE validation configuration parameter to true.</span></span> <span data-ttu-id="ae22e-134">此外可以调用业务流程中的规则。</span><span class="sxs-lookup"><span data-stu-id="ae22e-134">You can also invoke the rules from an orchestration.</span></span> <span data-ttu-id="ae22e-135">不能调用通过 A4SWIFT 组装器 (ASM) 的规则。</span><span class="sxs-lookup"><span data-stu-id="ae22e-135">You cannot invoke the rules by the A4SWIFT assembler (ASM).</span></span> <span data-ttu-id="ae22e-136">必须使用业务流程或接收管道来验证针对该架构的实例并调用规则。</span><span class="sxs-lookup"><span data-stu-id="ae22e-136">You must use an orchestration or receive pipeline to validate the instance against the schema and invoke the rules.</span></span>  

  <span data-ttu-id="ae22e-137">如果消息未能通过架构验证或业务规则，A4SWIFT 准备错误集合，其中包含找到的错误的说明及其相对值的指示在错误中的字段或发生错误的消息中的位置。</span><span class="sxs-lookup"><span data-stu-id="ae22e-137">If a message fails either schema validation or a business rule, A4SWIFT prepares an error collection that contains a description of the errors found and an indication of the field in error or the position in the message where the error occurred.</span></span> <span data-ttu-id="ae22e-138">有关详细信息，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="ae22e-138">For more information, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  

  <span data-ttu-id="ae22e-139">可以将其他规则添加到 A4SWIFT 提供的集合。</span><span class="sxs-lookup"><span data-stu-id="ae22e-139">You can add additional rules to the set that A4SWIFT provides.</span></span> <span data-ttu-id="ae22e-140">例如，如果您采用影响一组新的消息的市场实践组规则，可以实现包括所需的一个或多个新验证的主策略的新版本。</span><span class="sxs-lookup"><span data-stu-id="ae22e-140">For example, if you adopt a market practice group rule that affects a new set of messages, you can implement a new version of the master policy that includes one or more new validations, as required.</span></span> <span data-ttu-id="ae22e-141">同样，如果施加额外的单个字段检查，您可以将这些检查添加到消息验证策略的新版本。</span><span class="sxs-lookup"><span data-stu-id="ae22e-141">Similarly, if you impose additional single-field checks, you can add these checks to a new version of the message validation policy.</span></span> <span data-ttu-id="ae22e-142">您可以实现新的验证作为新的规则或词汇函数。</span><span class="sxs-lookup"><span data-stu-id="ae22e-142">You can implement the new validation as a new rule or as a vocabulary function.</span></span>  

  <span data-ttu-id="ae22e-143">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="ae22e-143">This section contains:</span></span>  

- [<span data-ttu-id="ae22e-144">启用银行标识代码验证</span><span class="sxs-lookup"><span data-stu-id="ae22e-144">Enabling Validation of Bank Identifier Codes</span></span>](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)  

- [<span data-ttu-id="ae22e-145">在 A4SWIFT 数据库中管理 Bicplus 表</span><span class="sxs-lookup"><span data-stu-id="ae22e-145">Managing the Bicplus Table in the A4SWIFT Database</span></span>](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)  

- [<span data-ttu-id="ae22e-146">在金额字段验证中支持前导零</span><span class="sxs-lookup"><span data-stu-id="ae22e-146">Supporting Leading Zeros in Amount Field Validations</span></span>](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md)  

- [<span data-ttu-id="ae22e-147">为金额验证设置偏移量</span><span class="sxs-lookup"><span data-stu-id="ae22e-147">Setting Offsets for Amount Validation</span></span>](../../adapters-and-accelerators/accelerator-swift/setting-offsets-for-amount-validation.md)  

- [<span data-ttu-id="ae22e-148">删除使用规则验证</span><span class="sxs-lookup"><span data-stu-id="ae22e-148">Removing Usage Rule Validation</span></span>](../../adapters-and-accelerators/accelerator-swift/removing-usage-rule-validation.md)
