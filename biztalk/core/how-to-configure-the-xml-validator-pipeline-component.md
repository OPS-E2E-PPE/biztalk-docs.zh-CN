---
title: 如何配置 XML 验证器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Validator [pipeline component]
- send pipelines, validating
- pipeline components, XML Validator
- receive pipelines, validating
ms.assetid: 3b3becaf-703c-4399-a5ed-e7082e31e6e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89c136079a6283fe5e2eebd063718f97008029fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340226"
---
# <a name="how-to-configure-the-xml-validator-pipeline-component"></a><span data-ttu-id="2182e-102">如何配置 XML 验证器管道组件</span><span class="sxs-lookup"><span data-stu-id="2182e-102">How to Configure the XML Validator Pipeline Component</span></span>
<span data-ttu-id="2182e-103">XML 验证器管道组件可在任何阶段 （除了拆装或组装） 在发送或接收管道。</span><span class="sxs-lookup"><span data-stu-id="2182e-103">The XML Validator pipeline component can be used in any stage (except Disassemble or Assemble) in a send or receive pipeline.</span></span>  
  
### <a name="to-configure-the-properties-for-the-xml-validator-pipeline-component"></a><span data-ttu-id="2182e-104">若要配置 XML 验证器管道组件的属性</span><span class="sxs-lookup"><span data-stu-id="2182e-104">To configure the properties for the XML Validator pipeline component</span></span>  
  
1.  <span data-ttu-id="2182e-105">将 XML 验证器管道组件拖至接收管道的验证阶段。</span><span class="sxs-lookup"><span data-stu-id="2182e-105">Drag the XML Validator pipeline component into the Validate stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="2182e-106">在属性窗口中**管道组件属性**部分中，进行以下设置。</span><span class="sxs-lookup"><span data-stu-id="2182e-106">In the Properties window, in the **Pipeline Component Properties** section, set the following.</span></span>  
  
    |<span data-ttu-id="2182e-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="2182e-107">Use this</span></span>|<span data-ttu-id="2182e-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="2182e-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="2182e-109">**文档架构**</span><span class="sxs-lookup"><span data-stu-id="2182e-109">**Document schemas**</span></span>|<span data-ttu-id="2182e-110">指示命名空间和类型名或多个架构应用于文档。</span><span class="sxs-lookup"><span data-stu-id="2182e-110">Indicates the namespace and typename of the schema or schemas to be applied to the document.</span></span> <span data-ttu-id="2182e-111">有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="2182e-111">For more information, see [How to Use the Schema Collection Property Editor](../core/how-to-use-the-schema-collection-property-editor.md).</span></span> <span data-ttu-id="2182e-112">如果未指定架构，运行时架构发现将通过使用消息的目标命名空间和根元素名称信息。</span><span class="sxs-lookup"><span data-stu-id="2182e-112">If no schemas are specified, the run-time schema discovery will be done by using the message's target namespace and root element name information.</span></span> <span data-ttu-id="2182e-113">**注意：** 如果指定两个或多个架构，可能会收到错误"两个或多个所选架构共享同一目标命名空间"**文档架构：** 属性。</span><span class="sxs-lookup"><span data-stu-id="2182e-113">**Note:**  You may receive a "Two or more of the selected schema share the same target namespace" error if you specify two or more schemas for the **Document schemas** property.</span></span> <br /><br /> <span data-ttu-id="2182e-114">默认值：空集合</span><span class="sxs-lookup"><span data-stu-id="2182e-114">Default value: Empty collection</span></span>|  
    |<span data-ttu-id="2182e-115">可恢复交换处理</span><span class="sxs-lookup"><span data-stu-id="2182e-115">Recoverable Interchange Processing</span></span>|<span data-ttu-id="2182e-116">如果为"false"-，指示 （如果任何包含的消息失败，整个交换被挂起），作为一个单元验证整个交换。</span><span class="sxs-lookup"><span data-stu-id="2182e-116">When "false" - indicates that entire interchange is validated as a unit (if any contained message fails, entire interchange is suspended).</span></span><br /><br /> <span data-ttu-id="2182e-117">如果为"true"的指示，交换中的消息分别提取，验证程序使用的某些传播通过消息传送路径和其他人被挂起。</span><span class="sxs-lookup"><span data-stu-id="2182e-117">When "true" - indicates that messages within interchange are extracted individually by validator with possibility of some propagating through messaging pathway and others being suspended.</span></span><br /><br /> <span data-ttu-id="2182e-118">可恢复交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="2182e-118">For more information on recoverable interchange processing, see [Recoverable Interchange Processing](../core/recoverable-interchange-processing.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2182e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="2182e-119">See Also</span></span>  
 <span data-ttu-id="2182e-120">[XML 验证器管道组件](../core/xml-validator-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="2182e-120">[XML Validator Pipeline Component](../core/xml-validator-pipeline-component.md) </span></span>  
 [<span data-ttu-id="2182e-121">配置本地管道组件</span><span class="sxs-lookup"><span data-stu-id="2182e-121">Configuring Native Pipeline Components</span></span>](../core/configuring-native-pipeline-components.md)