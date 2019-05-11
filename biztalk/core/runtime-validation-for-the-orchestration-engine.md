---
title: 业务流程引擎的运行时验证 |Microsoft Docs
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
ms.openlocfilehash: 89423ce9b08aee8ed500b599a912f898c7284968
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393970"
---
# <a name="runtime-validation-for-the-orchestration-engine"></a><span data-ttu-id="5fcd3-102">业务流程引擎的运行时验证</span><span class="sxs-lookup"><span data-stu-id="5fcd3-102">Runtime Validation for the Orchestration Engine</span></span>
<span data-ttu-id="5fcd3-103">可以配置业务流程引擎来执行各种可帮助您测试您的业务流程并诊断配置或数据发生的错误的可能的运行时验证。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-103">You can configure the orchestration engine to perform various runtime validations that can help you test your orchestration and diagnose configuration or data errors that might arise.</span></span>  
  
 <span data-ttu-id="5fcd3-104">您可以在 BTSNTSvc.exe.config，可以创建或编辑在 BTSNTSvc.exe 所在的目录 （通常在 BizTalk 部署目录中） 中的配置文件中设置标志。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-104">You can set flags in BTSNTSvc.exe.config, a configuration file that you can create or edit in the same directory as BTSNTSvc.exe (normally in the BizTalk deployment directory).</span></span> <span data-ttu-id="5fcd3-105">您可以在 BTSNTSvc.exe.config 文件中设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5fcd3-105">You can set the following flags in the BTSNTSvc.exe.config file:</span></span>  
  
- <span data-ttu-id="5fcd3-106">如果您设置**ValidateAssemblies**标记，用于`True`，引擎将尝试加载引用的业务流程，失败，则会引发的直接依存程序集的所有程序集Microsoft.XLANGs.Core.AssemblyValidationException。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-106">If you set the **ValidateAssemblies** flag to `True`, the engine tries to load all assemblies referenced by immediate dependent assemblies of an orchestration and upon failure throws Microsoft.XLANGs.Core.AssemblyValidationException.</span></span>  
  
- <span data-ttu-id="5fcd3-107">如果您设置**ValidateSchemas**标记，用于`True`，引擎使用 System.Xml.XmlValidatingReader 验证表示消息部分类型的每个架构和失败，则引发 System.Xml.XmlException。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-107">If you set the **ValidateSchemas** flag to `True`, the engine uses System.Xml.XmlValidatingReader to validate every schema representing a message part type and upon failure throws System.Xml.XmlException.</span></span>  
  
- <span data-ttu-id="5fcd3-108">如果您设置**ValidateCorrelations**标记，用于`True`，该引擎将验证，在并行保护一个保护接收相匹配具有相同的相关属性值，并在失败时引发的所有消息Microsoft.XLANGs.Core.CorrelationValidationException。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-108">If you set the **ValidateCorrelations** flag to `True`, the engine verifies that in a parallel convoy all messages that match one of the convoy receives have the same correlation property values and upon failure throws Microsoft.XLANGs.Core.CorrelationValidationException.</span></span>  
  
- <span data-ttu-id="5fcd3-109">如果您设置**ExtendedLogging**标记，用于`True`，引擎失败，若要发布的消息的 microsoft.xlangs.basetypes.publishmessageexception 信息中显示的已升级的属性。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-109">If you set the **ExtendedLogging** flag to `True`, the engine displays the promoted properties in the information for Microsoft.XLANGs.BaseTypes.PublishMessageException for the message that failed to publish.</span></span>  
  
  <span data-ttu-id="5fcd3-110">如果你想要禁用验证，请从配置文件中完全删除标志。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-110">If you want to disable a validation, remove the flag entirely from the configuration file.</span></span> <span data-ttu-id="5fcd3-111">打开所有验证时，引擎将验证程序集、 架构和关联。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-111">When all validations are on, the engine will validate assemblies, schemas, and correlation.</span></span> <span data-ttu-id="5fcd3-112">有关详细信息和 BTSNTSvc.exe.config 的示例，请参阅[业务流程引擎配置](../core/orchestration-engine-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-112">For more information and examples of BTSNTSvc.exe.config, see [Orchestration Engine Configuration](../core/orchestration-engine-configuration.md).</span></span>  
  
## <a name="validate-assemblies"></a><span data-ttu-id="5fcd3-113">验证程序集</span><span class="sxs-lookup"><span data-stu-id="5fcd3-113">Validate Assemblies</span></span>  
 <span data-ttu-id="5fcd3-114">业务流程引擎将验证由业务流程引用的任何程序集可用。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-114">The orchestration engine will verify that any assemblies referenced by the orchestration are available.</span></span> <span data-ttu-id="5fcd3-115">验证成功，所有引用的程序集必须是全局程序集缓存 (GAC) 中激活该业务流程的第一个实例时。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-115">For the validation to succeed, all referenced assemblies must be in the Global Assembly Cache (GAC) when the first instance of the orchestration is activated.</span></span> <span data-ttu-id="5fcd3-116">如果验证失败，错误将记录到应用程序日志，并且会挂起业务流程。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-116">If the validation fails, an error will be logged to the application log and the orchestration will be suspended.</span></span>  
  
## <a name="validate-schemas"></a><span data-ttu-id="5fcd3-117">验证架构</span><span class="sxs-lookup"><span data-stu-id="5fcd3-117">Validate Schemas</span></span>  
 <span data-ttu-id="5fcd3-118">只要分配了 XSD 部分，业务流程引擎将验证针对其架构的一部分的数据。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-118">Any time an XSD part is assigned, the orchestration engine will validate the part's data against its schema.</span></span> <span data-ttu-id="5fcd3-119">如果验证失败，将在应用程序日志记录错误并将引发异常。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-119">If the validation fails, the error will be logged to the application log and an exception will be thrown.</span></span>  
  
## <a name="validate-correlation"></a><span data-ttu-id="5fcd3-120">验证相关</span><span class="sxs-lookup"><span data-stu-id="5fcd3-120">Validate Correlation</span></span>  
 <span data-ttu-id="5fcd3-121">业务流程引擎将确认指定为实现与业务流程的给定实例关联的属性值将反映在从该业务流程实例发送任何消息。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-121">The orchestration engine will confirm that the property values that are specified for correlation with a given instance of an orchestration are reflected in any messages that are sent from that orchestration instance.</span></span> <span data-ttu-id="5fcd3-122">如果**validateCorrelation**未设置，则引擎将假定发送的消息包含正确的相关值，并将执行任何检查。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-122">If **validateCorrelation** is not set, the engine will assume that the sent message contains the correct correlation values, and no check will be performed.</span></span>  
  
 <span data-ttu-id="5fcd3-123">如果任一相关验证失败，则引擎将在应用程序日志中记录错误并引发类型的异常**为 CorrelationValidationException**。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-123">If any correlation validation fails, the engine will log an error to the application log and throw an exception of type **CorrelationValidationException**.</span></span>  
  
 <span data-ttu-id="5fcd3-124">默认情况下**validateCorrelation**未设置。</span><span class="sxs-lookup"><span data-stu-id="5fcd3-124">By default, **validateCorrelation** is not set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fcd3-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fcd3-125">See Also</span></span>  
 <span data-ttu-id="5fcd3-126">[调试业务流程](../core/debugging-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="5fcd3-126">[Debugging Orchestrations](../core/debugging-orchestrations.md) </span></span>  
 [<span data-ttu-id="5fcd3-127">业务流程引擎配置</span><span class="sxs-lookup"><span data-stu-id="5fcd3-127">Orchestration Engine Configuration</span></span>](../core/orchestration-engine-configuration.md)