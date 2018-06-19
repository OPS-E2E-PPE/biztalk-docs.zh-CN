---
title: 开发组合管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IComponentUI interface, assembling
- IBaseComponent interface, assembling
- pipeline interfaces, IBaseComponent
- pipeline components [custom], interfaces
- pipeline interfaces, IComponentUI
- IAssemblerComponent interface, assembling
- pipeline interfaces, IAssemblerComponent
- pipeline components [custom], assembling
ms.assetid: 2f85421d-2010-4a36-82b5-ea8016f8aa99
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8de06a815e1c5a6bf71700ad373ae3f278b3a9a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239613"
---
# <a name="developing-an-assembling-pipeline-component"></a><span data-ttu-id="4884d-102">开发组装的管道组件</span><span class="sxs-lookup"><span data-stu-id="4884d-102">Developing an Assembling Pipeline Component</span></span>
<span data-ttu-id="4884d-103">组装管道组件是一种 .NET 或 COM 组件，它在输入端接收若干消息，在输出端生成一个消息。</span><span class="sxs-lookup"><span data-stu-id="4884d-103">An assembling pipeline component is a .NET or COM component that receives several messages on input and produces one message on output.</span></span> <span data-ttu-id="4884d-104">组装组件用于将若干单独的文档收集到消息交换批中。</span><span class="sxs-lookup"><span data-stu-id="4884d-104">Assembling components are used to collect individual documents into the message interchange batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4884d-105">未使用程序集功能，因此 BizTalk Server 始终将一个文档传递到组件输入。</span><span class="sxs-lookup"><span data-stu-id="4884d-105">Assembly functionality is not used, so BizTalk Server always passes one document to the component input.</span></span>  
  
 <span data-ttu-id="4884d-106">组装组件必须实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="4884d-106">An assembling component must implement the following interfaces:</span></span>  
  
-   `IBaseComponent`  
  
-   `IAssemblerComponent`
  
-   `IComponentUI`
  
-   <span data-ttu-id="4884d-107">**IPersistPropertyBag。**</span><span class="sxs-lookup"><span data-stu-id="4884d-107">**IPersistPropertyBag .**</span></span> <span data-ttu-id="4884d-108">有关此接口的信息，请参阅 .NET Framework SDK 文档。</span><span class="sxs-lookup"><span data-stu-id="4884d-108">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4884d-109">自定义管道组件应将输入消息的所有附加部分复制到输出消息。</span><span class="sxs-lookup"><span data-stu-id="4884d-109">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="4884d-110">这样可以在管道中对它们作进一步处理。</span><span class="sxs-lookup"><span data-stu-id="4884d-110">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4884d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4884d-111">See Also</span></span>  
 <span data-ttu-id="4884d-112">[开发的常规管道组件](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="4884d-112">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="4884d-113">[开发分解的管道组件](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="4884d-113">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="4884d-114">[开发探测的管道组件](../core/developing-a-probing-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="4884d-114">[Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md) </span></span>  
 <span data-ttu-id="4884d-115">[从管道组件的报告错误](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="4884d-115">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="4884d-116">[配置本机管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="4884d-116">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="4884d-117">[部署管道组件](../core/deploying-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="4884d-117">[Deploying Pipeline Components](../core/deploying-pipeline-components.md) </span></span>  
 [<span data-ttu-id="4884d-118">CustomComponent （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="4884d-118">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)