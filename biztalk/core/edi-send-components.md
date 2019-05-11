---
title: EDI 发送组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce270db-a573-48b3-be15-0178a5b7785b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9afcc401b800fab7b549ac9bc4c53ae7502b8caa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350276"
---
# <a name="edi-send-components"></a><span data-ttu-id="02c95-102">EDI 发送组件</span><span class="sxs-lookup"><span data-stu-id="02c95-102">EDI Send Components</span></span>
<span data-ttu-id="02c95-103">管道和 EDI/AS2 消息不是此主题处理 EDI 消息中所述的管道组件。</span><span class="sxs-lookup"><span data-stu-id="02c95-103">The pipeline and pipeline components described in this topic process EDI messages that are not EDI/AS2 messages.</span></span> <span data-ttu-id="02c95-104">有关发送 EDI/AS2 或 EDI/AS2 消息的信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。</span><span class="sxs-lookup"><span data-stu-id="02c95-104">For information about the sending of EDI/AS2 or non-EDI/AS2 messages, see [AS2 Send Components](../core/as2-send-components.md).</span></span> <span data-ttu-id="02c95-105">请注意，AS2 发送组件还执行 EDI 处理除 AS2 处理。</span><span class="sxs-lookup"><span data-stu-id="02c95-105">Note that AS2 send components perform EDI processing in addition to AS2 processing.</span></span>  
  
## <a name="edi-send-pipeline"></a><span data-ttu-id="02c95-106">EDI 发送管道</span><span class="sxs-lookup"><span data-stu-id="02c95-106">EDI Send Pipeline</span></span>  
 <span data-ttu-id="02c95-107">EDI 发送处理工作都在下列 EDISend 管道。</span><span class="sxs-lookup"><span data-stu-id="02c95-107">EDI send processing is performed in the following EDISend pipeline.</span></span> <span data-ttu-id="02c95-108">此管道安装在`Microsoft.BizTalk.Edi.EdiPipelines.dll`在[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="02c95-108">This pipeline is installed in `Microsoft.BizTalk.Edi.EdiPipelines.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="02c95-109">**EDISend 管道**</span><span class="sxs-lookup"><span data-stu-id="02c95-109">**EDISend Pipeline**</span></span>  
  
 <span data-ttu-id="02c95-110">此管道生成和发送 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="02c95-110">This pipeline generates and sends EDI messages.</span></span> <span data-ttu-id="02c95-111">它不会处理通过 HTTP 接收 AS2 编码的 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="02c95-111">It does not process AS2-encoded EDI messages received over HTTP.</span></span> <span data-ttu-id="02c95-112">通过 AS2 管道执行 AS2 编码的 EDI 消息的处理。</span><span class="sxs-lookup"><span data-stu-id="02c95-112">Processing of AS2-encoded EDI messages is performed by an AS2 pipeline.</span></span> <span data-ttu-id="02c95-113">AS2 发送管道使用相同的组件来处理和 EDI 管道使用 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="02c95-113">The AS2 send pipelines use the same components to process EDI messages as the EDI pipeline uses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02c95-114">不支持从业务流程中运行 EDISend 管道。</span><span class="sxs-lookup"><span data-stu-id="02c95-114">Running the EDISend pipeline from an orchestration is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02c95-115">AS2EDISend 管道生成，并通过 AS2 传输发送 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="02c95-115">The AS2EDISend pipeline generates and sends EDI messages over AS2 transport.</span></span> <span data-ttu-id="02c95-116">有关详细信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。</span><span class="sxs-lookup"><span data-stu-id="02c95-116">For more information, see [AS2 Send Components](../core/as2-send-components.md).</span></span>  
  
 <span data-ttu-id="02c95-117">管道由 EDI 组装器管道组件组成：</span><span class="sxs-lookup"><span data-stu-id="02c95-117">The pipeline consists of the EDI Assembler pipeline component:</span></span>  
  
## <a name="edi-send-pipeline-component"></a><span data-ttu-id="02c95-118">EDI 发送管道组件</span><span class="sxs-lookup"><span data-stu-id="02c95-118">EDI Send Pipeline Component</span></span>  
 <span data-ttu-id="02c95-119">EDISend 管道使用 EDI 组装器管道组件。</span><span class="sxs-lookup"><span data-stu-id="02c95-119">The EDISend pipeline uses the EDI Assembler pipeline component.</span></span> <span data-ttu-id="02c95-120">此组件安装在`Microsoft.BizTalk.Edi.PipelineComponents.dll`中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]管道组件\\。</span><span class="sxs-lookup"><span data-stu-id="02c95-120">This component is installed in `Microsoft.BizTalk.Edi.PipelineComponents.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="02c95-121">EDI 组装器 EDISend 管道中执行的大多数处理 EDI 编码的交换。</span><span class="sxs-lookup"><span data-stu-id="02c95-121">The EDI Assembler performs most processing of EDI-encoded interchanges in the EDISend Pipeline.</span></span> <span data-ttu-id="02c95-122">有关 EDI 组装器如何处理 EDI 消息的信息，请参阅[EDI 组装器的工作原理](../core/how-the-edi-assembler-works.md)。</span><span class="sxs-lookup"><span data-stu-id="02c95-122">For information about how the EDI Assembler processes EDI messages, see [How the EDI Assembler Works](../core/how-the-edi-assembler-works.md).</span></span>