---
title: "上下文属性视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- Context Property view [Tracking Profile Editor]
- Tracking Profile Editor, Context Property view
- message schemas, XML messages
ms.assetid: 17a21b86-995c-4dc2-9a3c-1309837d0b9b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a0f3a1d507e1440f67cd5f9e4afa18bff0b52a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="context-property-view"></a><span data-ttu-id="6dea5-102">上下文属性视图</span><span class="sxs-lookup"><span data-stu-id="6dea5-102">Context Property View</span></span>
<span data-ttu-id="6dea5-103">“上下文属性”视图显示与该属性相关联的 XML 消息的架构。</span><span class="sxs-lookup"><span data-stu-id="6dea5-103">The Context Property view displays the schema of the XML message associated with the property.</span></span> <span data-ttu-id="6dea5-104">可以从“业务流程调度”视图中的某些形状的快捷菜单访问此视图。</span><span class="sxs-lookup"><span data-stu-id="6dea5-104">The view is available from the shortcut menu for some of the shapes in the Orchestration Schedule view.</span></span>  
  
## <a name="working-with-the-context-property-view"></a><span data-ttu-id="6dea5-105">使用上下文属性视图</span><span class="sxs-lookup"><span data-stu-id="6dea5-105">Working with the Context Property view</span></span>  
 <span data-ttu-id="6dea5-106">通过单击选择你的上下文属性视图**选择事件源**按钮并单击**选择上下文属性**菜单项。</span><span class="sxs-lookup"><span data-stu-id="6dea5-106">You select your Context Property view by clicking the **Select Event Source** button and clicking the **Select Context Property** menu item.</span></span> <span data-ttu-id="6dea5-107">然后，从已知上下文属性列表中选择一个上下文属性，以加载该属性的架构。</span><span class="sxs-lookup"><span data-stu-id="6dea5-107">You then choose a context property from the list of known context properties to load the schema for that property.</span></span> <span data-ttu-id="6dea5-108">选择属性后，可以将相关架构中的元素拖到活动的数据项文件夹，以指示您希望从此操作的消息内的特定 XPath 表达式提取这些数据。</span><span class="sxs-lookup"><span data-stu-id="6dea5-108">Once you select the property, you can drag elements from the associated schema to the data item folders of the activity, thus indicating you want to extract that data from specific XPath expression inside the message at this action.</span></span>  
  
 <span data-ttu-id="6dea5-109">可以从业务流程调度视图中打开上下文属性视图，方法是右键单击包含上下文属性的形状。</span><span class="sxs-lookup"><span data-stu-id="6dea5-109">You can open context property views from the orchestration schedule view by right-clicking a shape that contains a context property.</span></span> <span data-ttu-id="6dea5-110">这将打开上下文菜单，从中你可以单击**上下文属性架构**菜单项以检索与图形相关联的上下文属性的列表。</span><span class="sxs-lookup"><span data-stu-id="6dea5-110">This will open a context menu from which you can click the **Context Property Schema** menu item to retrieve a list of context properties associated with the shape.</span></span>  
  
 <span data-ttu-id="6dea5-111">可用的上下文属性的列表可能非常大。</span><span class="sxs-lookup"><span data-stu-id="6dea5-111">The list of available context properties can be extensive.</span></span> <span data-ttu-id="6dea5-112">如果你知道，而你要搜索的属性名称的一部分，您可以键入**中字符串**文本框中，然后单击**搜索**按钮。</span><span class="sxs-lookup"><span data-stu-id="6dea5-112">If you know part of the name of the property for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="6dea5-113">搜索结果中将只显示那些包含您所输入的部分字符串的属性。</span><span class="sxs-lookup"><span data-stu-id="6dea5-113">This will select only those properties that contain the partial string you have entered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6dea5-114">当选择从“上下文属性”视图映射时，可供选择的属性架构的列表为在 BizTalk Server 安装中配置的各个属性架构的完整列表。</span><span class="sxs-lookup"><span data-stu-id="6dea5-114">When you choose to map from the Context Properties view, the list of potential property schemas is a complete list of every property schema configured in your BizTalk Server installation.</span></span>  <span data-ttu-id="6dea5-115">您必须知道，提供的架构对您要处理的流程在运行中所使用的 BizTalk Server 的功能不敏感。</span><span class="sxs-lookup"><span data-stu-id="6dea5-115">You must aware that the schemas presented are not sensitive to which features in BizTalk Server are used by the running process on which you are working.</span></span> <span data-ttu-id="6dea5-116">例如，当从上下文属性映射时，可以从提供的架构列表中选择 SOAP 属性的架构，但是正在运行的流程本身可能不使用 SOAP。</span><span class="sxs-lookup"><span data-stu-id="6dea5-116">For example, you can select a schema for SOAP properties from the list of schemas offered when mapping from Context Properties, but the running process itself may not use SOAP.</span></span> <span data-ttu-id="6dea5-117">任何自未使用的属性映射的 BAM 活动项都会导致 BAM 捕获空数据。</span><span class="sxs-lookup"><span data-stu-id="6dea5-117">Any BAM activity item mapped from an unused property results in null or empty data being captured by BAM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dea5-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dea5-118">See Also</span></span>  
 <span data-ttu-id="6dea5-119">[源事件视图是什么？](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="6dea5-119">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="6dea5-120">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="6dea5-120">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)