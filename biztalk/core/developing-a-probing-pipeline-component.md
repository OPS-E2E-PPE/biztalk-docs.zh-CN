---
title: 开发探测管道组件 |Microsoft 文档
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
ms.openlocfilehash: 8081c31fc781cd2d1cbc291587f358376a033d66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240677"
---
# <a name="developing-a-probing-pipeline-component"></a><span data-ttu-id="8299f-102">开发探测的管道组件</span><span class="sxs-lookup"><span data-stu-id="8299f-102">Developing a Probing Pipeline Component</span></span>
<span data-ttu-id="8299f-103">任何管道组件 （常规、 组装，或分解） 可以实现`IProbeMessage`接口如果它必须支持探测功能的消息。</span><span class="sxs-lookup"><span data-stu-id="8299f-103">Any pipeline component (general, assembling, or disassembling) can implement the `IProbeMessage` interface if it must support message probing functionality.</span></span> <span data-ttu-id="8299f-104">探测组件用于中具有的管道阶段**匹配**执行模式。</span><span class="sxs-lookup"><span data-stu-id="8299f-104">A probing component is used in the pipeline stages that have **FirstMatch** execution mode.</span></span> <span data-ttu-id="8299f-105">在此类阶段中，BizTalk 消息引擎将消息的开始部分提供给组件，以便确定组件是否识别该消息的格式。</span><span class="sxs-lookup"><span data-stu-id="8299f-105">In such stages, the BizTalk Messaging Engine gives the beginning part of the message to the component to determine if the component recognizes the format of the message.</span></span> <span data-ttu-id="8299f-106">如果组件识别格式，则会将整个消息交给此组件进行处理。</span><span class="sxs-lookup"><span data-stu-id="8299f-106">If the component recognizes the format, the entire message is given to the component for processing.</span></span>  
  
 <span data-ttu-id="8299f-107">**IProbeMessage**接口公开一个方法，**探测**，这使组件可以检查消息的开头部分。</span><span class="sxs-lookup"><span data-stu-id="8299f-107">The **IProbeMessage** interface exposes a single method, **Probe**, which enables the component to check the beginning part of the message.</span></span> <span data-ttu-id="8299f-108">返回值确定此组件是否已运行。</span><span class="sxs-lookup"><span data-stu-id="8299f-108">The return value determines whether this component is run.</span></span> <span data-ttu-id="8299f-109">以下步骤说明了 BizTalk 消息引擎如何运行需要识别的阶段：</span><span class="sxs-lookup"><span data-stu-id="8299f-109">The following steps outline how the BizTalk Messaging Engine runs a stage that requires recognition:</span></span>  
  
1.  <span data-ttu-id="8299f-110">如果阶段不包含任何组件，则该阶段不运行，消息交给随后的阶段进行处理。</span><span class="sxs-lookup"><span data-stu-id="8299f-110">If the stage does not contain any components, the stage is not run and the message is given to the subsequent stages for processing.</span></span>  
  
2.  <span data-ttu-id="8299f-111">检查组件是否实现**IProbeMessage**接口。</span><span class="sxs-lookup"><span data-stu-id="8299f-111">Check if the component implements the **IProbeMessage** interface.</span></span> <span data-ttu-id="8299f-112">如果没有，消息引擎将调用该组件。</span><span class="sxs-lookup"><span data-stu-id="8299f-112">If not, the Messaging Engine invokes the component.</span></span> <span data-ttu-id="8299f-113">阶段处理完成，消息交给下一个阶段。</span><span class="sxs-lookup"><span data-stu-id="8299f-113">The stage processing is done and the message is given to the next stage.</span></span>  
  
3.  <span data-ttu-id="8299f-114">**探测**调用方法。</span><span class="sxs-lookup"><span data-stu-id="8299f-114">The **Probe** method is invoked.</span></span> <span data-ttu-id="8299f-115">如果返回值为**True**，运行该组件。</span><span class="sxs-lookup"><span data-stu-id="8299f-115">If the return value is **True**, the component is run.</span></span> <span data-ttu-id="8299f-116">然后，阶段处理完成，消息交给下一个阶段。</span><span class="sxs-lookup"><span data-stu-id="8299f-116">Then the stage processing is done and the message is given to a next stage.</span></span>  
  
4.  <span data-ttu-id="8299f-117">消息引擎获取阶段中的下一个组件。</span><span class="sxs-lookup"><span data-stu-id="8299f-117">The Messaging Engine gets the next component in the stage.</span></span> <span data-ttu-id="8299f-118">如果没有其他组件并且所有组件都尚未运行，则生成一个错误，提示您管道处理失败。</span><span class="sxs-lookup"><span data-stu-id="8299f-118">If there are no more components and none of the components have been run, it generates an error that pipeline processing has failed.</span></span> <span data-ttu-id="8299f-119">如果没有其他组件并且至少有一个已运行，则处理完成。</span><span class="sxs-lookup"><span data-stu-id="8299f-119">If there are no more components and at least one component has been run, the processing is done.</span></span>  
  
 <span data-ttu-id="8299f-120">如果某一阶段不需要识别 (例如，执行模式是**所有**)，消息引擎时，将调用该组件而无需为第一个查询**IProbeMessage**接口和调用**探测**方法。</span><span class="sxs-lookup"><span data-stu-id="8299f-120">If a stage does not require recognition (for example, the execution mode is **All**), the Messaging Engine invokes the component without first querying for the **IProbeMessage** interface and calling the **Probe** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8299f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8299f-121">See Also</span></span>  
 <span data-ttu-id="8299f-122">[开发的常规管道组件](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="8299f-122">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="8299f-123">[开发组装的管道组件](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="8299f-123">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="8299f-124">[开发分解的管道组件](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="8299f-124">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="8299f-125">[从管道组件的报告错误](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="8299f-125">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="8299f-126">[配置本机管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="8299f-126">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="8299f-127">部署管道组件</span><span class="sxs-lookup"><span data-stu-id="8299f-127">Deploying Pipeline Components</span></span>](../core/deploying-pipeline-components.md)