---
title: 开发组装管道组件 |Microsoft Docs
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
ms.openlocfilehash: ff36bac9dc5f14048e7d448f912f72c243146b8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389427"
---
# <a name="developing-an-assembling-pipeline-component"></a><span data-ttu-id="c5f77-102">开发汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="c5f77-102">Developing an Assembling Pipeline Component</span></span>
<span data-ttu-id="c5f77-103">汇编程序管道组件是一种.NET 或 COM 组件接收输入的多条消息并生成输出一条消息。</span><span class="sxs-lookup"><span data-stu-id="c5f77-103">An assembling pipeline component is a .NET or COM component that receives several messages on input and produces one message on output.</span></span> <span data-ttu-id="c5f77-104">组装组件用于到消息交换批中收集的各个文档。</span><span class="sxs-lookup"><span data-stu-id="c5f77-104">Assembling components are used to collect individual documents into the message interchange batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5f77-105">不使用程序集功能，因此 BizTalk Server 始终将一个文档传递到组件输入。</span><span class="sxs-lookup"><span data-stu-id="c5f77-105">Assembly functionality is not used, so BizTalk Server always passes one document to the component input.</span></span>  
  
 <span data-ttu-id="c5f77-106">组装组件必须实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="c5f77-106">An assembling component must implement the following interfaces:</span></span>  
  
-   `IBaseComponent`  
  
-   `IAssemblerComponent`
  
-   `IComponentUI`
  
-   <span data-ttu-id="c5f77-107">**IPersistPropertyBag。**</span><span class="sxs-lookup"><span data-stu-id="c5f77-107">**IPersistPropertyBag .**</span></span> <span data-ttu-id="c5f77-108">请参阅此接口的.NET Framework SDK 文档。</span><span class="sxs-lookup"><span data-stu-id="c5f77-108">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5f77-109">自定义管道组件应从输入消息复制到输出消息任何其他部分。</span><span class="sxs-lookup"><span data-stu-id="c5f77-109">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="c5f77-110">这会保留它们在管道中做进一步处理。</span><span class="sxs-lookup"><span data-stu-id="c5f77-110">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f77-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5f77-111">See Also</span></span>  
 <span data-ttu-id="c5f77-112">[开发常规管道组件](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c5f77-112">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="c5f77-113">[开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c5f77-113">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="c5f77-114">[开发探测管道组件](../core/developing-a-probing-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c5f77-114">[Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md) </span></span>  
 <span data-ttu-id="c5f77-115">[报告来自管道组件的错误](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c5f77-115">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="c5f77-116">[配置本地管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c5f77-116">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="c5f77-117">[部署管道组件](../core/deploying-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c5f77-117">[Deploying Pipeline Components](../core/deploying-pipeline-components.md) </span></span>  
 [<span data-ttu-id="c5f77-118">CustomComponent（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="c5f77-118">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)