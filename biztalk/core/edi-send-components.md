---
title: "EDI 发送组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fce270db-a573-48b3-be15-0178a5b7785b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5520a0c1dd0a6ef7e42818314a9f87733aebcb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-send-components"></a><span data-ttu-id="0fce0-102">EDI 发送组件</span><span class="sxs-lookup"><span data-stu-id="0fce0-102">EDI Send Components</span></span>
<span data-ttu-id="0fce0-103">本主题中介绍的管道和管道组件用于处理不是 EDI/AS2 消息的 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="0fce0-103">The pipeline and pipeline components described in this topic process EDI messages that are not EDI/AS2 messages.</span></span> <span data-ttu-id="0fce0-104">有关发送 EDI/AS2 或非 EDI/AS2 消息的信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。</span><span class="sxs-lookup"><span data-stu-id="0fce0-104">For information about the sending of EDI/AS2 or non-EDI/AS2 messages, see [AS2 Send Components](../core/as2-send-components.md).</span></span> <span data-ttu-id="0fce0-105">请注意，除 AS2 处理以外，AS2 发送组件还执行 EDI 处理。</span><span class="sxs-lookup"><span data-stu-id="0fce0-105">Note that AS2 send components perform EDI processing in addition to AS2 processing.</span></span>  
  
## <a name="edi-send-pipeline"></a><span data-ttu-id="0fce0-106">EDI 发送管道</span><span class="sxs-lookup"><span data-stu-id="0fce0-106">EDI Send Pipeline</span></span>  
 <span data-ttu-id="0fce0-107">EDI 发送处理工作都将在下列 EDISend 管道中进行。</span><span class="sxs-lookup"><span data-stu-id="0fce0-107">EDI send processing is performed in the following EDISend pipeline.</span></span> <span data-ttu-id="0fce0-108">该管道安装在 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 下的 `Microsoft.BizTalk.Edi.EdiPipelines.dll` 中。</span><span class="sxs-lookup"><span data-stu-id="0fce0-108">This pipeline is installed in `Microsoft.BizTalk.Edi.EdiPipelines.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="0fce0-109">**EDISend 管道**</span><span class="sxs-lookup"><span data-stu-id="0fce0-109">**EDISend Pipeline**</span></span>  
  
 <span data-ttu-id="0fce0-110">此管道将生成和发送 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="0fce0-110">This pipeline generates and sends EDI messages.</span></span> <span data-ttu-id="0fce0-111">但不会处理通过 HTTP 接收的 AS2 编码的 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="0fce0-111">It does not process AS2-encoded EDI messages received over HTTP.</span></span> <span data-ttu-id="0fce0-112">AS2 编码的 EDI 消息的处理是通过 AS2 管道执行的。</span><span class="sxs-lookup"><span data-stu-id="0fce0-112">Processing of AS2-encoded EDI messages is performed by an AS2 pipeline.</span></span> <span data-ttu-id="0fce0-113">AS2 发送管道和 EDI 管道使用相同的组件来处理 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="0fce0-113">The AS2 send pipelines use the same components to process EDI messages as the EDI pipeline uses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fce0-114">不支持从业务流程中运行 EDISend 管道。</span><span class="sxs-lookup"><span data-stu-id="0fce0-114">Running the EDISend pipeline from an orchestration is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fce0-115">AS2EDISend 管道通过 AS2 传输生成和发送 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="0fce0-115">The AS2EDISend pipeline generates and sends EDI messages over AS2 transport.</span></span> <span data-ttu-id="0fce0-116">有关详细信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。</span><span class="sxs-lookup"><span data-stu-id="0fce0-116">For more information, see [AS2 Send Components](../core/as2-send-components.md).</span></span>  
  
 <span data-ttu-id="0fce0-117">该管道由 EDI 组装器管道组件组成：</span><span class="sxs-lookup"><span data-stu-id="0fce0-117">The pipeline consists of the EDI Assembler pipeline component:</span></span>  
  
## <a name="edi-send-pipeline-component"></a><span data-ttu-id="0fce0-118">EDI 发送管道组件</span><span class="sxs-lookup"><span data-stu-id="0fce0-118">EDI Send Pipeline Component</span></span>  
 <span data-ttu-id="0fce0-119">EDISend 管道使用 EDI 组装器管道组件。</span><span class="sxs-lookup"><span data-stu-id="0fce0-119">The EDISend pipeline uses the EDI Assembler pipeline component.</span></span> <span data-ttu-id="0fce0-120">此组件安装在`Microsoft.BizTalk.Edi.PipelineComponents.dll`中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]管道组件\\。</span><span class="sxs-lookup"><span data-stu-id="0fce0-120">This component is installed in `Microsoft.BizTalk.Edi.PipelineComponents.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="0fce0-121">对 EDISend 管道中的 EDI 编码交换的处理大部分是由 EDI 组装器执行的。</span><span class="sxs-lookup"><span data-stu-id="0fce0-121">The EDI Assembler performs most processing of EDI-encoded interchanges in the EDISend Pipeline.</span></span> <span data-ttu-id="0fce0-122">有关如何 EDI 汇编器处理 EDI 消息的信息，请参阅[EDI 汇编程序的工作原理](../core/how-the-edi-assembler-works.md)。</span><span class="sxs-lookup"><span data-stu-id="0fce0-122">For information about how the EDI Assembler processes EDI messages, see [How the EDI Assembler Works](../core/how-the-edi-assembler-works.md).</span></span>