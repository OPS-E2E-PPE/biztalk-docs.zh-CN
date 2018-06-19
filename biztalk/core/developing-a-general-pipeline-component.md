---
title: 开发的常规管道组件 |Microsoft 文档
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
ms.openlocfilehash: 44b85992eb0691b7f27ec1a52812d986429d9e31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239213"
---
# <a name="developing-a-general-pipeline-component"></a><span data-ttu-id="6de55-102">开发的常规管道组件</span><span class="sxs-lookup"><span data-stu-id="6de55-102">Developing a General Pipeline Component</span></span>

## <a name="interfaces"></a><span data-ttu-id="6de55-103">界面</span><span class="sxs-lookup"><span data-stu-id="6de55-103">Interfaces</span></span>
<span data-ttu-id="6de55-104">常规管道组件是一种 .NET 或 COM 组件，可实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="6de55-104">A general pipeline component is a .NET or COM component that implements the following interfaces:</span></span>  
  
-   <span data-ttu-id="6de55-105">IBaseComponent 接口 (COM)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6de55-105">IBaseComponent Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   <span data-ttu-id="6de55-106">为 IComponent 接口 (COM)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6de55-106">IComponent Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   <span data-ttu-id="6de55-107">IComponentUI 接口 (COM)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6de55-107">IComponentUI Interface (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="6de55-108">IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="6de55-108">IPersistPropertyBag</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.ipersistpropertybag)
  
 <span data-ttu-id="6de55-109">常规管道组件从 BizTalk 消息引擎获取一条消息，然后处理该消息，并将已处理的消息返回到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎。</span><span class="sxs-lookup"><span data-stu-id="6de55-109">A general pipeline component gets one message from the BizTalk Messaging Engine, processes it, and returns it to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine.</span></span> <span data-ttu-id="6de55-110">常规组件也可被实现，以便它们不再将消息返回到服务器。</span><span class="sxs-lookup"><span data-stu-id="6de55-110">General components can also be implemented so that they do not return messages to the server.</span></span> <span data-ttu-id="6de55-111">这样的组件称为使用组件，因为这类组件只接收消息，而不生成任何结果消息。</span><span class="sxs-lookup"><span data-stu-id="6de55-111">Such components are called consuming components because the component receives messages but does not produce any result messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6de55-112">自定义管道组件应将输入消息的所有附加部分复制到输出消息。</span><span class="sxs-lookup"><span data-stu-id="6de55-112">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="6de55-113">这样可以在管道中对它们作进一步处理。</span><span class="sxs-lookup"><span data-stu-id="6de55-113">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="more-pipeline-resources"></a><span data-ttu-id="6de55-114">管道的更多资源</span><span class="sxs-lookup"><span data-stu-id="6de55-114">More pipeline resources</span></span>
 <span data-ttu-id="6de55-115">[开发组装的管道组件](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="6de55-115">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="6de55-116">[开发分解的管道组件](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="6de55-116">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="6de55-117">[开发探测的管道组件](../core/developing-a-probing-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="6de55-117">[Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md) </span></span>  
 <span data-ttu-id="6de55-118">[从管道组件的报告错误](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="6de55-118">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="6de55-119">[配置本机管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="6de55-119">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 <span data-ttu-id="6de55-120">[部署管道组件](../core/deploying-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="6de55-120">[Deploying Pipeline Components](../core/deploying-pipeline-components.md) </span></span>  
 [<span data-ttu-id="6de55-121">CustomComponent （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="6de55-121">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)