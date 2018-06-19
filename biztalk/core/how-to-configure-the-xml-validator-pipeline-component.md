---
title: 如何将 XML 验证程序管道组件配置 |Microsoft 文档
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
ms.openlocfilehash: 821ad6a1353c0aa29866fd36fe84a7ea6317690b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248381"
---
# <a name="how-to-configure-the-xml-validator-pipeline-component"></a><span data-ttu-id="0c93b-102">如何将 XML 验证程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="0c93b-102">How to Configure the XML Validator Pipeline Component</span></span>
<span data-ttu-id="0c93b-103">XML 验证器管道组件可以用于发送或接收管道的任何阶段（除了拆装或组装）。</span><span class="sxs-lookup"><span data-stu-id="0c93b-103">The XML Validator pipeline component can be used in any stage (except Disassemble or Assemble) in a send or receive pipeline.</span></span>  
  
### <a name="to-configure-the-properties-for-the-xml-validator-pipeline-component"></a><span data-ttu-id="0c93b-104">配置 XML 验证器管道组件的属性</span><span class="sxs-lookup"><span data-stu-id="0c93b-104">To configure the properties for the XML Validator pipeline component</span></span>  
  
1.  <span data-ttu-id="0c93b-105">将 XML 验证器管道组件拖至接收管道的验证阶段。</span><span class="sxs-lookup"><span data-stu-id="0c93b-105">Drag the XML Validator pipeline component into the Validate stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="0c93b-106">在属性窗口中，在**管道组件属性**部分中，以下设置。</span><span class="sxs-lookup"><span data-stu-id="0c93b-106">In the Properties window, in the **Pipeline Component Properties** section, set the following.</span></span>  
  
    |<span data-ttu-id="0c93b-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0c93b-107">Use this</span></span>|<span data-ttu-id="0c93b-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0c93b-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0c93b-109">**文档架构**</span><span class="sxs-lookup"><span data-stu-id="0c93b-109">**Document schemas**</span></span>|<span data-ttu-id="0c93b-110">指明要应用于文档的一个或多个架构的命名空间和类型名。</span><span class="sxs-lookup"><span data-stu-id="0c93b-110">Indicates the namespace and typename of the schema or schemas to be applied to the document.</span></span> <span data-ttu-id="0c93b-111">有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="0c93b-111">For more information, see [How to Use the Schema Collection Property Editor](../core/how-to-use-the-schema-collection-property-editor.md).</span></span> <span data-ttu-id="0c93b-112">如果未指定架构，则将使用消息的目标命名空间和根元素名称信息来执行运行时架构发现。</span><span class="sxs-lookup"><span data-stu-id="0c93b-112">If no schemas are specified, the run-time schema discovery will be done by using the message's target namespace and root element name information.</span></span> <span data-ttu-id="0c93b-113">**注意：** 如果你指定两个或多个架构，可能会收到"两个或多个所选架构共享相同的目标命名空间"的错误**文档架构**属性。</span><span class="sxs-lookup"><span data-stu-id="0c93b-113">**Note:**  You may receive a "Two or more of the selected schema share the same target namespace" error if you specify two or more schemas for the **Document schemas** property.</span></span> <br /><br /> <span data-ttu-id="0c93b-114">默认值：空集合</span><span class="sxs-lookup"><span data-stu-id="0c93b-114">Default value: Empty collection</span></span>|  
    |<span data-ttu-id="0c93b-115">可恢复的交换处理</span><span class="sxs-lookup"><span data-stu-id="0c93b-115">Recoverable Interchange Processing</span></span>|<span data-ttu-id="0c93b-116">当"false"时-表示 （是否已挂起任何包含的消息失败，整个交换），作为一个单元验证整个交换。</span><span class="sxs-lookup"><span data-stu-id="0c93b-116">When "false" - indicates that entire interchange is validated as a unit (if any contained message fails, entire interchange is suspended).</span></span><br /><br /> <span data-ttu-id="0c93b-117">当"true"时-表示中交换, 的消息提取单独的验证程序的某些传播通过消息传递途径和其他挂起的可能性。</span><span class="sxs-lookup"><span data-stu-id="0c93b-117">When "true" - indicates that messages within interchange are extracted individually by validator with possibility of some propagating through messaging pathway and others being suspended.</span></span><br /><br /> <span data-ttu-id="0c93b-118">可恢复的交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="0c93b-118">For more information on recoverable interchange processing, see [Recoverable Interchange Processing](../core/recoverable-interchange-processing.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c93b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c93b-119">See Also</span></span>  
 <span data-ttu-id="0c93b-120">[XML 验证程序管道组件](../core/xml-validator-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="0c93b-120">[XML Validator Pipeline Component](../core/xml-validator-pipeline-component.md) </span></span>  
 [<span data-ttu-id="0c93b-121">配置本机管道组件</span><span class="sxs-lookup"><span data-stu-id="0c93b-121">Configuring Native Pipeline Components</span></span>](../core/configuring-native-pipeline-components.md)