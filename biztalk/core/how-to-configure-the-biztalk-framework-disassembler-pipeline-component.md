---
title: 如何配置 BizTalk 框架拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- disassembly stage, pipelines
- receive pipelines, disassembly stage
- BizTalk Framework Disassembler [pipeline component], configuring
ms.assetid: a5599bcb-dbee-46a5-a91d-3c54f901cd30
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46ce50dc68f7a11cd63c7244c9abcb6930a08f3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341140"
---
# <a name="how-to-configure-the-biztalk-framework-disassembler-pipeline-component"></a><span data-ttu-id="6a89a-102">如何配置 BizTalk 框架拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="6a89a-102">How to Configure the BizTalk Framework Disassembler Pipeline Component</span></span>
<span data-ttu-id="6a89a-103">BizTalk 框架拆装器管道组件应在接收管道的拆装阶段中使用。</span><span class="sxs-lookup"><span data-stu-id="6a89a-103">The BizTalk Framework Disassembler pipeline component should be used in the Disassemble stage of a receive pipeline.</span></span>  
  
### <a name="to-configure-the-properties-for-the-biztalk-framework-disassembler-pipeline-component"></a><span data-ttu-id="6a89a-104">若要配置 BizTalk 框架拆装器管道组件的属性</span><span class="sxs-lookup"><span data-stu-id="6a89a-104">To configure the properties for the BizTalk Framework Disassembler pipeline component</span></span>  
  
1.  <span data-ttu-id="6a89a-105">将 BizTalk 框架拆装器管道组件拖至接收管道的拆装阶段。</span><span class="sxs-lookup"><span data-stu-id="6a89a-105">Drag the BizTalk Framework Disassembler pipeline component into the Disassemble stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="6a89a-106">在属性窗口中**管道组件属性**部分中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="6a89a-106">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="6a89a-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6a89a-107">Use this</span></span>|<span data-ttu-id="6a89a-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6a89a-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6a89a-109">**允许无法识别的消息**</span><span class="sxs-lookup"><span data-stu-id="6a89a-109">**Allow unrecognized message**</span></span>|<span data-ttu-id="6a89a-110">指示是否允许没有可识别的架构通过拆装器传递的消息。</span><span class="sxs-lookup"><span data-stu-id="6a89a-110">Indicates whether to allow messages that do not have a recognized schema to be passed through the disassembler.</span></span><br /><br /> <span data-ttu-id="6a89a-111">默认值：**False**</span><span class="sxs-lookup"><span data-stu-id="6a89a-111">Default value: **False**</span></span>|  
    |<span data-ttu-id="6a89a-112">**文档架构**</span><span class="sxs-lookup"><span data-stu-id="6a89a-112">**Document schemas**</span></span>|<span data-ttu-id="6a89a-113">指示命名空间和类型名或多个架构应用于文档。</span><span class="sxs-lookup"><span data-stu-id="6a89a-113">Indicates the namespace and typename of the schema or schemas to be applied to the document.</span></span> <span data-ttu-id="6a89a-114">有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="6a89a-114">For more information, see [How to Use the Schema Collection Property Editor](../core/how-to-use-the-schema-collection-property-editor.md).</span></span><br /><br /> <span data-ttu-id="6a89a-115">此属性中指定的架构应具有唯一目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="6a89a-115">Schemas specified in this property should have unique target namespaces.</span></span> <span data-ttu-id="6a89a-116">如果具有相同的命名空间的任何架构，对文档实例的验证可能不会按预期工作。</span><span class="sxs-lookup"><span data-stu-id="6a89a-116">If any of the schemas have the same namespace, the validation of the document instances may not work as expected.</span></span> <span data-ttu-id="6a89a-117">如果架构必须具有相同的命名空间，您应创建单独的管道为每个架构和指定每个 BizTalk 框架拆装器管道组件的一个架构，或使用一个管道但不是指定任何架构作为参数的 BizTalk框架拆装器管道组件。</span><span class="sxs-lookup"><span data-stu-id="6a89a-117">If schemas must have the same namespace, you should either create a separate pipeline for each schema and specify one schema per BizTalk Framework Disassembler pipeline component or use one pipeline but do not specify any schemas as parameters for the BizTalk Framework Disassembler pipeline component.</span></span><br /><br /> <span data-ttu-id="6a89a-118">默认值：空集合</span><span class="sxs-lookup"><span data-stu-id="6a89a-118">Default value: Empty collection</span></span>|  
    |<span data-ttu-id="6a89a-119">**信封架构**</span><span class="sxs-lookup"><span data-stu-id="6a89a-119">**Envelope schemas**</span></span>|<span data-ttu-id="6a89a-120">指示命名空间和类型名或多个要应用于信封的架构。</span><span class="sxs-lookup"><span data-stu-id="6a89a-120">Indicates the namespace and typename of the schema or schemas to be applied to the envelope.</span></span> <span data-ttu-id="6a89a-121">有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="6a89a-121">For more information, see [How to Use the Schema Collection Property Editor](../core/how-to-use-the-schema-collection-property-editor.md).</span></span><br /><br /> <span data-ttu-id="6a89a-122">此属性中指定的架构应具有唯一目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="6a89a-122">Schemas specified in this property should have unique target namespaces.</span></span> <span data-ttu-id="6a89a-123">如果具有相同的命名空间的任何架构，对文档实例的验证可能不会按预期工作。</span><span class="sxs-lookup"><span data-stu-id="6a89a-123">If any of the schemas have the same namespace, the validation of the document instances may not work as expected.</span></span> <span data-ttu-id="6a89a-124">如果架构必须具有相同的命名空间，您应创建单独的管道为每个架构和指定每个 BizTalk 框架拆装器管道组件的一个架构，或使用一个管道但不是指定任何架构作为参数的 BizTalk框架拆装器管道组件。</span><span class="sxs-lookup"><span data-stu-id="6a89a-124">If schemas must have the same namespace, you should either create a separate pipeline for each schema and specify one schema per BizTalk Framework Disassembler pipeline component or use one pipeline but do not specify any schemas as parameters for the BizTalk Framework Disassembler pipeline component.</span></span><br /><br /> <span data-ttu-id="6a89a-125">默认值：空集合</span><span class="sxs-lookup"><span data-stu-id="6a89a-125">Default value: Empty collection</span></span>|  
    |<span data-ttu-id="6a89a-126">**验证文档结构**</span><span class="sxs-lookup"><span data-stu-id="6a89a-126">**Validate document structure**</span></span>|<span data-ttu-id="6a89a-127">当 **，则返回 True**，执行的传入消息和拆装器，包括信封验证。</span><span class="sxs-lookup"><span data-stu-id="6a89a-127">When **True**, performs a validation of the incoming message to the disassembler, including the envelopes.</span></span> <span data-ttu-id="6a89a-128">**注意：** 当 **，则返回 True**，如果指定两个或多个架构，可能会收到错误"两个或多个所选架构共享同一目标命名空间"**文档架构**或**信封架构**属性。</span><span class="sxs-lookup"><span data-stu-id="6a89a-128">**Note:**  When **True**, you may receive a "Two or more of the selected schema share the same target namespace" error if you specify two or more schemas for the **Document schemas** or **Envelope schemas** properties.</span></span> <br /><br /> <span data-ttu-id="6a89a-129">默认值：**False**</span><span class="sxs-lookup"><span data-stu-id="6a89a-129">Default value: **False**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a89a-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a89a-130">See Also</span></span>  
 <span data-ttu-id="6a89a-131">[BizTalk 框架拆装器管道组件](../core/biztalk-framework-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="6a89a-131">[BizTalk Framework Disassembler Pipeline Component](../core/biztalk-framework-disassembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="6a89a-132">[配置本地管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="6a89a-132">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="6a89a-133">[Pipelines-assemblerdisassembler （BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="6a89a-133">[Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="6a89a-134">配置本地管道组件</span><span class="sxs-lookup"><span data-stu-id="6a89a-134">Configuring Native Pipeline Components</span></span>](../core/configuring-native-pipeline-components.md)