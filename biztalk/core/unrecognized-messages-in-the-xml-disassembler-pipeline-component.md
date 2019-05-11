---
title: 无法识别的消息中 XML 拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Allow Unrecognized Messages property
- XMLNorm.AllowUnrecognizedMessage property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], unrecognized messages
ms.assetid: 5a6be3a8-0bac-426a-bf0b-5091191091de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c09d381a74b8f5083b600de73b72ac3c4d4da00d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400831"
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="af355-102">XML 拆装器管道组件中无法识别的消息</span><span class="sxs-lookup"><span data-stu-id="af355-102">Unrecognized Messages in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="af355-103">XML 拆装器组件可能会处理一条消息"无法识别"在以下情况下：</span><span class="sxs-lookup"><span data-stu-id="af355-103">The XML Disassembler component may handle a message as "unrecognized" in the following cases:</span></span>  
  
- <span data-ttu-id="af355-104">带任何正文、 空白正文、 正文中的空数据接收一条 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="af355-104">An XML message is received with no body, an empty body, or empty data in the body.</span></span>  
  
- <span data-ttu-id="af355-105">收到一条 XML 消息，但没有架构部署它。</span><span class="sxs-lookup"><span data-stu-id="af355-105">An XML message is received but no schema is deployed for it.</span></span>  
  
  <span data-ttu-id="af355-106">根据处理无法识别的消息**允许无法识别的消息**属性 (或在**XMLNorm.AllowUnrecognizedMessage**消息上下文属性)。</span><span class="sxs-lookup"><span data-stu-id="af355-106">An unrecognized message is handled based on the **Allow Unrecognized Messages** property (or on the **XMLNorm.AllowUnrecognizedMessage** property on the message context).</span></span>  
  
  <span data-ttu-id="af355-107">如果**允许无法识别的消息**设置为**True**，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="af355-107">If **Allow Unrecognized Messages** is set to **True**, the following occurs:</span></span>  
  
- <span data-ttu-id="af355-108">带任何正文、 正文为空，或为空中的数据正文传递的消息通过 XML 拆装器保持不变。</span><span class="sxs-lookup"><span data-stu-id="af355-108">A message with no body, an empty/null body, or with empty/null data in the body passes unchanged through the XML Disassembler.</span></span>  
  
- <span data-ttu-id="af355-109">没有关联的已部署的架构传递的 XML 文档原封不动地通过 XML 拆装器。</span><span class="sxs-lookup"><span data-stu-id="af355-109">An XML document with no associated deployed schema passes unchanged through the XML Disassembler.</span></span>  
  
- <span data-ttu-id="af355-110">由 XML 拆装器而不考虑架构是否显式组件属性中引用或架构解析过程中找到，具有与之关联的已部署的架构的 XML 文档进行处理。</span><span class="sxs-lookup"><span data-stu-id="af355-110">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
  <span data-ttu-id="af355-111">如果**允许无法识别的消息**设置为**False**，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="af355-111">If **Allow Unrecognized Messages** is set to **False**, the following occurs:</span></span>  
  
- <span data-ttu-id="af355-112">通过 XML 拆装器不传递任何正文、 正文为空或正文中的数据为空的消息。</span><span class="sxs-lookup"><span data-stu-id="af355-112">A message with no body or an empty/null body or with empty/null data in the body is not passed through the XML Disassembler.</span></span>  
  
- <span data-ttu-id="af355-113">没有与它关联的已部署的架构的 XML 文档不通过拆装器。</span><span class="sxs-lookup"><span data-stu-id="af355-113">An XML document that does not have a deployed schema associated with it is not passed through the disassembler.</span></span> <span data-ttu-id="af355-114">报告错误并挂起该消息，如有可能。</span><span class="sxs-lookup"><span data-stu-id="af355-114">An error is reported and the message is suspended, if possible.</span></span>  
  
- <span data-ttu-id="af355-115">由 XML 拆装器而不考虑架构是否显式组件属性中引用或架构解析过程中找到，具有与之关联的已部署的架构的 XML 文档进行处理。</span><span class="sxs-lookup"><span data-stu-id="af355-115">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
  <span data-ttu-id="af355-116">默认情况下，XML 拆装器不允许无法识别的消息。</span><span class="sxs-lookup"><span data-stu-id="af355-116">By default, the XML Disassembler does not allow unrecognized messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af355-117">非 XML 消息不会处理 XML 拆装器而不考虑**允许无法识别的消息**属性设置。</span><span class="sxs-lookup"><span data-stu-id="af355-117">Non-XML messages are not processed by the XML Disassembler regardless of the **Allow Unrecognized Messages** property setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af355-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="af355-118">See Also</span></span>  
 <span data-ttu-id="af355-119">[XML 拆装器管道组件](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="af355-119">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="af355-120">如何配置 XML 拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="af355-120">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)