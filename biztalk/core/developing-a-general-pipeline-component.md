---
title: 开发常规管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63f5d8d1-30fb-4a1e-b4bd-2be07b618b20
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7debc394b29676b15f330a8b5c22fbfe4656d0a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351544"
---
# <a name="developing-a-general-pipeline-component"></a><span data-ttu-id="c9fec-102">开发常规管道组件</span><span class="sxs-lookup"><span data-stu-id="c9fec-102">Developing a General Pipeline Component</span></span>

## <a name="interfaces"></a><span data-ttu-id="c9fec-103">界面</span><span class="sxs-lookup"><span data-stu-id="c9fec-103">Interfaces</span></span>
<span data-ttu-id="c9fec-104">常规管道组件是.NET 或 COM 组件，可实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="c9fec-104">A general pipeline component is a .NET or COM component that implements the following interfaces:</span></span>  
  
- <span data-ttu-id="c9fec-105">IBaseComponent 接口 (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c9fec-105">IBaseComponent Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
- <span data-ttu-id="c9fec-106">IComponent 接口 (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c9fec-106">IComponent Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
- <span data-ttu-id="c9fec-107">IComponentUI 接口 (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c9fec-107">IComponentUI Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
- [<span data-ttu-id="c9fec-108">IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="c9fec-108">IPersistPropertyBag</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.ipersistpropertybag)
  
  <span data-ttu-id="c9fec-109">常规管道组件从 BizTalk 消息引擎获取一条消息、 处理它，并返回到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎。</span><span class="sxs-lookup"><span data-stu-id="c9fec-109">A general pipeline component gets one message from the BizTalk Messaging Engine, processes it, and returns it to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine.</span></span> <span data-ttu-id="c9fec-110">常规组件也可以实现，以便它们不向服务器返回的消息。</span><span class="sxs-lookup"><span data-stu-id="c9fec-110">General components can also be implemented so that they do not return messages to the server.</span></span> <span data-ttu-id="c9fec-111">此类组件称为使用组件，因为该组件接收消息，而不生成任何结果消息。</span><span class="sxs-lookup"><span data-stu-id="c9fec-111">Such components are called consuming components because the component receives messages but does not produce any result messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9fec-112">自定义管道组件应从输入消息复制到输出消息任何其他部分。</span><span class="sxs-lookup"><span data-stu-id="c9fec-112">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="c9fec-113">这会保留它们在管道中做进一步处理。</span><span class="sxs-lookup"><span data-stu-id="c9fec-113">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="more-pipeline-resources"></a><span data-ttu-id="c9fec-114">更多管道资源</span><span class="sxs-lookup"><span data-stu-id="c9fec-114">More pipeline resources</span></span>
 <span data-ttu-id="c9fec-115">[开发汇编程序管道组件](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c9fec-115">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="c9fec-116">[开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c9fec-116">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="c9fec-117">[开发探测管道组件](../core/developing-a-probing-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c9fec-117">[Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md) </span></span>  
 <span data-ttu-id="c9fec-118">[报告来自管道组件的错误](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c9fec-118">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="c9fec-119">[配置本地管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c9fec-119">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="c9fec-120">[部署管道组件](../core/deploying-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c9fec-120">[Deploying Pipeline Components](../core/deploying-pipeline-components.md) </span></span>  
 [<span data-ttu-id="c9fec-121">CustomComponent（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="c9fec-121">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)