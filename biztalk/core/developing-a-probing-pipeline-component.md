---
title: 开发探测管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], probing
- IProbeMessage interface
- pipeline interfaces, IProbeMessage
ms.assetid: c3da467d-5270-4c7f-9c38-ce9989bf1b63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54da9d0433b0ca416e5c0da797a4d4c8678aab8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389454"
---
# <a name="developing-a-probing-pipeline-component"></a><span data-ttu-id="b50d6-102">开发探测管道组件</span><span class="sxs-lookup"><span data-stu-id="b50d6-102">Developing a Probing Pipeline Component</span></span>
<span data-ttu-id="b50d6-103">任何管道组件 （一般、 组装或拆装） 都可以实现`IProbeMessage`接口是否必须支持消息探测功能。</span><span class="sxs-lookup"><span data-stu-id="b50d6-103">Any pipeline component (general, assembling, or disassembling) can implement the `IProbeMessage` interface if it must support message probing functionality.</span></span> <span data-ttu-id="b50d6-104">探测组件用于具有的管道阶段**第一个匹配**执行模式。</span><span class="sxs-lookup"><span data-stu-id="b50d6-104">A probing component is used in the pipeline stages that have **FirstMatch** execution mode.</span></span> <span data-ttu-id="b50d6-105">在此类阶段中，BizTalk 消息引擎的消息的开始部分提供给组件，以便确定组件是否识别的消息的格式。</span><span class="sxs-lookup"><span data-stu-id="b50d6-105">In such stages, the BizTalk Messaging Engine gives the beginning part of the message to the component to determine if the component recognizes the format of the message.</span></span> <span data-ttu-id="b50d6-106">如果组件识别格式，则整个消息交给此组件进行处理。</span><span class="sxs-lookup"><span data-stu-id="b50d6-106">If the component recognizes the format, the entire message is given to the component for processing.</span></span>  
  
 <span data-ttu-id="b50d6-107">**IProbeMessage**接口公开单个方法**探测**，这使组件可以检查消息的开始部分。</span><span class="sxs-lookup"><span data-stu-id="b50d6-107">The **IProbeMessage** interface exposes a single method, **Probe**, which enables the component to check the beginning part of the message.</span></span> <span data-ttu-id="b50d6-108">返回值确定是否运行此组件。</span><span class="sxs-lookup"><span data-stu-id="b50d6-108">The return value determines whether this component is run.</span></span> <span data-ttu-id="b50d6-109">以下步骤概述了 BizTalk 消息引擎如何运行需要识别的阶段：</span><span class="sxs-lookup"><span data-stu-id="b50d6-109">The following steps outline how the BizTalk Messaging Engine runs a stage that requires recognition:</span></span>  
  
1. <span data-ttu-id="b50d6-110">如果阶段不包含任何组件，则不会运行阶段和消息交给随后的阶段进行处理。</span><span class="sxs-lookup"><span data-stu-id="b50d6-110">If the stage does not contain any components, the stage is not run and the message is given to the subsequent stages for processing.</span></span>  
  
2. <span data-ttu-id="b50d6-111">检查组件是否实现**IProbeMessage**接口。</span><span class="sxs-lookup"><span data-stu-id="b50d6-111">Check if the component implements the **IProbeMessage** interface.</span></span> <span data-ttu-id="b50d6-112">如果没有，消息引擎调用该组件。</span><span class="sxs-lookup"><span data-stu-id="b50d6-112">If not, the Messaging Engine invokes the component.</span></span> <span data-ttu-id="b50d6-113">阶段处理完成，消息交给下一个阶段。</span><span class="sxs-lookup"><span data-stu-id="b50d6-113">The stage processing is done and the message is given to the next stage.</span></span>  
  
3. <span data-ttu-id="b50d6-114">**探测**调用方法。</span><span class="sxs-lookup"><span data-stu-id="b50d6-114">The **Probe** method is invoked.</span></span> <span data-ttu-id="b50d6-115">如果返回值是 **，则返回 True**，该组件已运行。</span><span class="sxs-lookup"><span data-stu-id="b50d6-115">If the return value is **True**, the component is run.</span></span> <span data-ttu-id="b50d6-116">然后阶段处理完成，并将消息提供给下一个阶段。</span><span class="sxs-lookup"><span data-stu-id="b50d6-116">Then the stage processing is done and the message is given to a next stage.</span></span>  
  
4. <span data-ttu-id="b50d6-117">消息引擎获取阶段中的下一个组件。</span><span class="sxs-lookup"><span data-stu-id="b50d6-117">The Messaging Engine gets the next component in the stage.</span></span> <span data-ttu-id="b50d6-118">如果没有更多组件，并且所有组件已运行，则将生成错误的管道处理失败。</span><span class="sxs-lookup"><span data-stu-id="b50d6-118">If there are no more components and none of the components have been run, it generates an error that pipeline processing has failed.</span></span> <span data-ttu-id="b50d6-119">如果没有更多组件并且至少一个组件都已运行，在处理完成。</span><span class="sxs-lookup"><span data-stu-id="b50d6-119">If there are no more components and at least one component has been run, the processing is done.</span></span>  
  
   <span data-ttu-id="b50d6-120">如果阶段不需要识别 (例如，执行模式是**所有**)，消息引擎调用组件，而无需为第一个查询**IProbeMessage**接口并调用**探测**方法。</span><span class="sxs-lookup"><span data-stu-id="b50d6-120">If a stage does not require recognition (for example, the execution mode is **All**), the Messaging Engine invokes the component without first querying for the **IProbeMessage** interface and calling the **Probe** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b50d6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="b50d6-121">See Also</span></span>  
 <span data-ttu-id="b50d6-122">[开发常规管道组件](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="b50d6-122">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="b50d6-123">[开发汇编程序管道组件](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="b50d6-123">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="b50d6-124">[开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="b50d6-124">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="b50d6-125">[报告来自管道组件的错误](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="b50d6-125">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="b50d6-126">[配置本地管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="b50d6-126">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="b50d6-127">部署管道组件</span><span class="sxs-lookup"><span data-stu-id="b50d6-127">Deploying Pipeline Components</span></span>](../core/deploying-pipeline-components.md)