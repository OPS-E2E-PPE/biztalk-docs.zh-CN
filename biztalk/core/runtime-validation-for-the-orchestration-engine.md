---
title: 业务流程引擎的运行时验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, assemblies
- orchestrations, validating
- validating, orchestration engine
- schemas, validating
- correlations, validating
- validating, schemas
- orchestration engine, runtime validation
- assemblies, validating
- validating, correlations
- validating, orchestrations
- validating
ms.assetid: f6085889-05d6-4eba-a528-9d034c4e4225
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e53adb5aa42c7dfe23df50707754bde200ea838a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269261"
---
# <a name="runtime-validation-for-the-orchestration-engine"></a><span data-ttu-id="b4fd1-102">业务流程引擎的运行时验证</span><span class="sxs-lookup"><span data-stu-id="b4fd1-102">Runtime Validation for the Orchestration Engine</span></span>
<span data-ttu-id="b4fd1-103">您可以配置业务流程引擎，使其执行各种运行时验证，这些验证可帮助您测试业务流程并诊断可能出现的配置错误或数据错误。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-103">You can configure the orchestration engine to perform various runtime validations that can help you test your orchestration and diagnose configuration or data errors that might arise.</span></span>  
  
 <span data-ttu-id="b4fd1-104">您可以在 BTSNTSvc.exe.config 中设置标志。BTSNTSvc.exe.config 是一个配置文件，您可以在 BTSNTSvc.exe 所在的目录（通常在 BizTalk 部署目录中）中创建或编辑该文件。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-104">You can set flags in BTSNTSvc.exe.config, a configuration file that you can create or edit in the same directory as BTSNTSvc.exe (normally in the BizTalk deployment directory).</span></span> <span data-ttu-id="b4fd1-105">可以在 BTSNTSvc.exe.config 文件中设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="b4fd1-105">You can set the following flags in the BTSNTSvc.exe.config file:</span></span>  
  
-   <span data-ttu-id="b4fd1-106">如果你设置**ValidateAssemblies**标志切换为`True`，引擎将尝试加载所有程序集引用的业务流程的和失败将引发时的即时依赖程序集Microsoft.XLANGs.Core.AssemblyValidationException。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-106">If you set the **ValidateAssemblies** flag to `True`, the engine tries to load all assemblies referenced by immediate dependent assemblies of an orchestration and upon failure throws Microsoft.XLANGs.Core.AssemblyValidationException.</span></span>  
  
-   <span data-ttu-id="b4fd1-107">如果你设置**ValidateSchemas**标志切换为`True`，引擎使用 System.Xml.XmlValidatingReader 来验证每个表示消息部件类型的架构和在失败时引发 System.Xml.XmlException。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-107">If you set the **ValidateSchemas** flag to `True`, the engine uses System.Xml.XmlValidatingReader to validate every schema representing a message part type and upon failure throws System.Xml.XmlException.</span></span>  
  
-   <span data-ttu-id="b4fd1-108">如果你设置**ValidateCorrelations**标志切换为`True`，引擎验证，并行护航队列之一接收该匹配项具有相同的相关属性值，并在失败时引发的所有消息Microsoft.XLANGs.Core.CorrelationValidationException。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-108">If you set the **ValidateCorrelations** flag to `True`, the engine verifies that in a parallel convoy all messages that match one of the convoy receives have the same correlation property values and upon failure throws Microsoft.XLANGs.Core.CorrelationValidationException.</span></span>  
  
-   <span data-ttu-id="b4fd1-109">如果你设置**ExtendedLogging**标志切换为`True`，引擎 Microsoft.XLANGs.BaseTypes.PublishMessageException 未能发布它的消息的信息中显示的提升的属性。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-109">If you set the **ExtendedLogging** flag to `True`, the engine displays the promoted properties in the information for Microsoft.XLANGs.BaseTypes.PublishMessageException for the message that failed to publish.</span></span>  
  
 <span data-ttu-id="b4fd1-110">如果要禁用验证，请从配置文件中完全删除标志。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-110">If you want to disable a validation, remove the flag entirely from the configuration file.</span></span> <span data-ttu-id="b4fd1-111">所有验证都启用时，引擎将验证程序集、架构和相关。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-111">When all validations are on, the engine will validate assemblies, schemas, and correlation.</span></span> <span data-ttu-id="b4fd1-112">有关详细信息和 BTSNTSvc.exe.config 的示例，请参阅[业务流程引擎配置](../core/orchestration-engine-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-112">For more information and examples of BTSNTSvc.exe.config, see [Orchestration Engine Configuration](../core/orchestration-engine-configuration.md).</span></span>  
  
## <a name="validate-assemblies"></a><span data-ttu-id="b4fd1-113">验证程序集</span><span class="sxs-lookup"><span data-stu-id="b4fd1-113">Validate Assemblies</span></span>  
 <span data-ttu-id="b4fd1-114">业务流程引擎将验证业务流程引用的所有程序集是否可用。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-114">The orchestration engine will verify that any assemblies referenced by the orchestration are available.</span></span> <span data-ttu-id="b4fd1-115">为了使验证成功，在激活业务流程的第一个实例时，所有引用的程序集都必须在全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-115">For the validation to succeed, all referenced assemblies must be in the Global Assembly Cache (GAC) when the first instance of the orchestration is activated.</span></span> <span data-ttu-id="b4fd1-116">如果验证失败，则将在应用程序日志中记录错误并挂起业务流程。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-116">If the validation fails, an error will be logged to the application log and the orchestration will be suspended.</span></span>  
  
## <a name="validate-schemas"></a><span data-ttu-id="b4fd1-117">验证架构</span><span class="sxs-lookup"><span data-stu-id="b4fd1-117">Validate Schemas</span></span>  
 <span data-ttu-id="b4fd1-118">只要分配了 XSD 部分，业务流程引擎就会针对其架构验证该部分的数据。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-118">Any time an XSD part is assigned, the orchestration engine will validate the part's data against its schema.</span></span> <span data-ttu-id="b4fd1-119">如果验证失败，则将在应用程序日志中记录错误并引发异常。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-119">If the validation fails, the error will be logged to the application log and an exception will be thrown.</span></span>  
  
## <a name="validate-correlation"></a><span data-ttu-id="b4fd1-120">验证相关</span><span class="sxs-lookup"><span data-stu-id="b4fd1-120">Validate Correlation</span></span>  
 <span data-ttu-id="b4fd1-121">业务流程引擎将确认：为具有给定业务流程实例的相关指定的属性值反映在从该业务流程实例发送的所有消息中。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-121">The orchestration engine will confirm that the property values that are specified for correlation with a given instance of an orchestration are reflected in any messages that are sent from that orchestration instance.</span></span> <span data-ttu-id="b4fd1-122">如果**validateCorrelation**未设置，引擎将假定发送的消息包含正确的相关值，并将执行任何检查。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-122">If **validateCorrelation** is not set, the engine will assume that the sent message contains the correct correlation values, and no check will be performed.</span></span>  
  
 <span data-ttu-id="b4fd1-123">如果任何相关验证失败，则引擎将在应用程序日志中记录错误，并引发类型的异常**CorrelationValidationException**。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-123">If any correlation validation fails, the engine will log an error to the application log and throw an exception of type **CorrelationValidationException**.</span></span>  
  
 <span data-ttu-id="b4fd1-124">默认情况下， **validateCorrelation**未设置。</span><span class="sxs-lookup"><span data-stu-id="b4fd1-124">By default, **validateCorrelation** is not set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fd1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4fd1-125">See Also</span></span>  
 <span data-ttu-id="b4fd1-126">[调试业务流程](../core/debugging-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="b4fd1-126">[Debugging Orchestrations](../core/debugging-orchestrations.md) </span></span>  
 [<span data-ttu-id="b4fd1-127">业务流程引擎配置</span><span class="sxs-lookup"><span data-stu-id="b4fd1-127">Orchestration Engine Configuration</span></span>](../core/orchestration-engine-configuration.md)