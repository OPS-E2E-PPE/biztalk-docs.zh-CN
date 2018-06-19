---
title: 如何将 BizTalk Framework 反汇编程序管道组件配置 |Microsoft 文档
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
ms.openlocfilehash: 07fefb577e5322fa303a1a1476a976b453adb083
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249189"
---
# <a name="how-to-configure-the-biztalk-framework-disassembler-pipeline-component"></a><span data-ttu-id="ed170-102">如何将 BizTalk Framework 反汇编程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="ed170-102">How to Configure the BizTalk Framework Disassembler Pipeline Component</span></span>
<span data-ttu-id="ed170-103">BizTalk 框架拆装器管道组件应在接收管道的拆装阶段使用。</span><span class="sxs-lookup"><span data-stu-id="ed170-103">The BizTalk Framework Disassembler pipeline component should be used in the Disassemble stage of a receive pipeline.</span></span>  
  
### <a name="to-configure-the-properties-for-the-biztalk-framework-disassembler-pipeline-component"></a><span data-ttu-id="ed170-104">配置 BizTalk 框架拆装器管道组件的属性</span><span class="sxs-lookup"><span data-stu-id="ed170-104">To configure the properties for the BizTalk Framework Disassembler pipeline component</span></span>  
  
1.  <span data-ttu-id="ed170-105">将 BizTalk 框架拆装器管道组件拖入接收管道的拆装阶段。</span><span class="sxs-lookup"><span data-stu-id="ed170-105">Drag the BizTalk Framework Disassembler pipeline component into the Disassemble stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="ed170-106">在属性窗口中，在**管道组件属性**部分中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="ed170-106">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="ed170-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ed170-107">Use this</span></span>|<span data-ttu-id="ed170-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ed170-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ed170-109">**允许无法识别的消息**</span><span class="sxs-lookup"><span data-stu-id="ed170-109">**Allow unrecognized message**</span></span>|<span data-ttu-id="ed170-110">指示是否允许不具有可识别的架构通过反汇编程序传递的消息。</span><span class="sxs-lookup"><span data-stu-id="ed170-110">Indicates whether to allow messages that do not have a recognized schema to be passed through the disassembler.</span></span><br /><br /> <span data-ttu-id="ed170-111">默认值： **False**</span><span class="sxs-lookup"><span data-stu-id="ed170-111">Default value: **False**</span></span>|  
    |<span data-ttu-id="ed170-112">**文档架构**</span><span class="sxs-lookup"><span data-stu-id="ed170-112">**Document schemas**</span></span>|<span data-ttu-id="ed170-113">指明要应用于文档的一个或多个架构的命名空间和类型名。</span><span class="sxs-lookup"><span data-stu-id="ed170-113">Indicates the namespace and typename of the schema or schemas to be applied to the document.</span></span> <span data-ttu-id="ed170-114">有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="ed170-114">For more information, see [How to Use the Schema Collection Property Editor](../core/how-to-use-the-schema-collection-property-editor.md).</span></span><br /><br /> <span data-ttu-id="ed170-115">此属性中指定的架构应具有唯一目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="ed170-115">Schemas specified in this property should have unique target namespaces.</span></span> <span data-ttu-id="ed170-116">如果有任何架构的命名空间与之相同，则对文档实例的验证将可能无法按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="ed170-116">If any of the schemas have the same namespace, the validation of the document instances may not work as expected.</span></span> <span data-ttu-id="ed170-117">如果多个架构必须使用同一命名空间，则应为每个架构创建单独的管道，并为每个 BizTalk 框架拆装器管道组件指定一个架构，或者使用一个管道但不将任何架构指定为 BizTalk 框架拆装器管道组件的参数。</span><span class="sxs-lookup"><span data-stu-id="ed170-117">If schemas must have the same namespace, you should either create a separate pipeline for each schema and specify one schema per BizTalk Framework Disassembler pipeline component or use one pipeline but do not specify any schemas as parameters for the BizTalk Framework Disassembler pipeline component.</span></span><br /><br /> <span data-ttu-id="ed170-118">默认值：空集合</span><span class="sxs-lookup"><span data-stu-id="ed170-118">Default value: Empty collection</span></span>|  
    |<span data-ttu-id="ed170-119">**信封架构**</span><span class="sxs-lookup"><span data-stu-id="ed170-119">**Envelope schemas**</span></span>|<span data-ttu-id="ed170-120">指明要应用于信封的一个或多个架构的命名空间和类型名。</span><span class="sxs-lookup"><span data-stu-id="ed170-120">Indicates the namespace and typename of the schema or schemas to be applied to the envelope.</span></span> <span data-ttu-id="ed170-121">有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="ed170-121">For more information, see [How to Use the Schema Collection Property Editor](../core/how-to-use-the-schema-collection-property-editor.md).</span></span><br /><br /> <span data-ttu-id="ed170-122">此属性中指定的架构应具有唯一目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="ed170-122">Schemas specified in this property should have unique target namespaces.</span></span> <span data-ttu-id="ed170-123">如果有任何架构的命名空间与之相同，则对文档实例的验证将可能无法按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="ed170-123">If any of the schemas have the same namespace, the validation of the document instances may not work as expected.</span></span> <span data-ttu-id="ed170-124">如果多个架构必须使用同一命名空间，则应为每个架构创建单独的管道，并为每个 BizTalk 框架拆装器管道组件指定一个架构，或者使用一个管道但不将任何架构指定为 BizTalk 框架拆装器管道组件的参数。</span><span class="sxs-lookup"><span data-stu-id="ed170-124">If schemas must have the same namespace, you should either create a separate pipeline for each schema and specify one schema per BizTalk Framework Disassembler pipeline component or use one pipeline but do not specify any schemas as parameters for the BizTalk Framework Disassembler pipeline component.</span></span><br /><br /> <span data-ttu-id="ed170-125">默认值：空集合</span><span class="sxs-lookup"><span data-stu-id="ed170-125">Default value: Empty collection</span></span>|  
    |<span data-ttu-id="ed170-126">**验证文档结构**</span><span class="sxs-lookup"><span data-stu-id="ed170-126">**Validate document structure**</span></span>|<span data-ttu-id="ed170-127">当**True**，执行到反汇编程序，包括包络线的传入消息验证。</span><span class="sxs-lookup"><span data-stu-id="ed170-127">When **True**, performs a validation of the incoming message to the disassembler, including the envelopes.</span></span> <span data-ttu-id="ed170-128">**注意：** 时**True**，如果你指定两个或多个架构，可能会收到"两个或多个所选架构共享相同的目标命名空间"的错误**文档架构**或**信封架构**属性。</span><span class="sxs-lookup"><span data-stu-id="ed170-128">**Note:**  When **True**, you may receive a "Two or more of the selected schema share the same target namespace" error if you specify two or more schemas for the **Document schemas** or **Envelope schemas** properties.</span></span> <br /><br /> <span data-ttu-id="ed170-129">默认值： **False**</span><span class="sxs-lookup"><span data-stu-id="ed170-129">Default value: **False**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed170-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed170-130">See Also</span></span>  
 <span data-ttu-id="ed170-131">[BizTalk Framework 反汇编程序管道组件](../core/biztalk-framework-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="ed170-131">[BizTalk Framework Disassembler Pipeline Component](../core/biztalk-framework-disassembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="ed170-132">[配置本机管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="ed170-132">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="ed170-133">[管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="ed170-133">[Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="ed170-134">配置本机管道组件</span><span class="sxs-lookup"><span data-stu-id="ed170-134">Configuring Native Pipeline Components</span></span>](../core/configuring-native-pipeline-components.md)