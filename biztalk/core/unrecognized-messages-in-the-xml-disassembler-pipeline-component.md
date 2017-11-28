---
title: "无法识别的消息中 XML 反汇编程序管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Allow Unrecognized Messages property
- XMLNorm.AllowUnrecognizedMessage property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], unrecognized messages
ms.assetid: 5a6be3a8-0bac-426a-bf0b-5091191091de
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d82396002ff9d35484af5f0000dc3468c8ad37fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="78eb4-102">无法识别的消息中 XML 反汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="78eb4-102">Unrecognized Messages in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="78eb4-103">如果出现以下情况，则 XML 拆装器组件可将消息作为“无法识别”进行处理：</span><span class="sxs-lookup"><span data-stu-id="78eb4-103">The XML Disassembler component may handle a message as "unrecognized" in the following cases:</span></span>  
  
-   <span data-ttu-id="78eb4-104">收到不带任何正文、正文为空或正文中的数据为空的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="78eb4-104">An XML message is received with no body, an empty body, or empty data in the body.</span></span>  
  
-   <span data-ttu-id="78eb4-105">收到 XML 消息，但未为该消息部署任何架构。</span><span class="sxs-lookup"><span data-stu-id="78eb4-105">An XML message is received but no schema is deployed for it.</span></span>  
  
 <span data-ttu-id="78eb4-106">无法识别的消息处理基于**允许无法识别的消息**属性 (或在**XMLNorm.AllowUnrecognizedMessage**消息上下文属性)。</span><span class="sxs-lookup"><span data-stu-id="78eb4-106">An unrecognized message is handled based on the **Allow Unrecognized Messages** property (or on the **XMLNorm.AllowUnrecognizedMessage** property on the message context).</span></span>  
  
 <span data-ttu-id="78eb4-107">如果**允许无法识别的消息**设置为**True**，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="78eb4-107">If **Allow Unrecognized Messages** is set to **True**, the following occurs:</span></span>  
  
-   <span data-ttu-id="78eb4-108">不带任何正文、正文为空或正文中的数据为空的消息将不做更改地通过 XML 拆装器。</span><span class="sxs-lookup"><span data-stu-id="78eb4-108">A message with no body, an empty/null body, or with empty/null data in the body passes unchanged through the XML Disassembler.</span></span>  
  
-   <span data-ttu-id="78eb4-109">没有与其相关联的已部署架构的 XML 文档将不做更改地通过 XML 拆装器。</span><span class="sxs-lookup"><span data-stu-id="78eb4-109">An XML document with no associated deployed schema passes unchanged through the XML Disassembler.</span></span>  
  
-   <span data-ttu-id="78eb4-110">具有与其相关联的已部署架构的 XML 文档将由 XML 拆装器进行处理，而不管是否在组件属性中显式引用了该架构或是否在架构解析的过程中发现了该架构。</span><span class="sxs-lookup"><span data-stu-id="78eb4-110">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
 <span data-ttu-id="78eb4-111">如果**允许无法识别的消息**设置为**False**，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="78eb4-111">If **Allow Unrecognized Messages** is set to **False**, the following occurs:</span></span>  
  
-   <span data-ttu-id="78eb4-112">不带任何正文、正文为空或正文中的数据为空的消息将不会通过 XML 拆装器。</span><span class="sxs-lookup"><span data-stu-id="78eb4-112">A message with no body or an empty/null body or with empty/null data in the body is not passed through the XML Disassembler.</span></span>  
  
-   <span data-ttu-id="78eb4-113">没有与其相关联的已部署架构的 XML 文档将不会通过 XML 拆装器。</span><span class="sxs-lookup"><span data-stu-id="78eb4-113">An XML document that does not have a deployed schema associated with it is not passed through the disassembler.</span></span> <span data-ttu-id="78eb4-114">如果可能，将会报告错误并挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="78eb4-114">An error is reported and the message is suspended, if possible.</span></span>  
  
-   <span data-ttu-id="78eb4-115">具有与其相关联的已部署架构的 XML 文档将由 XML 拆装器进行处理，而不管是否在组件属性中显式引用了该架构或是否在架构解析的过程中发现了该架构。</span><span class="sxs-lookup"><span data-stu-id="78eb4-115">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
 <span data-ttu-id="78eb4-116">默认情况下，XML 拆装器将不允许无法识别的消息。</span><span class="sxs-lookup"><span data-stu-id="78eb4-116">By default, the XML Disassembler does not allow unrecognized messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78eb4-117">无论采用何种 XML 反汇编程序不处理非 XML 消息**允许无法识别的消息**属性设置。</span><span class="sxs-lookup"><span data-stu-id="78eb4-117">Non-XML messages are not processed by the XML Disassembler regardless of the **Allow Unrecognized Messages** property setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78eb4-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78eb4-118">See Also</span></span>  
 <span data-ttu-id="78eb4-119">[XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="78eb4-119">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="78eb4-120">如何将 XML 反汇编程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="78eb4-120">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)