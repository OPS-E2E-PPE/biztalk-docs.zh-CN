---
title: "消息属性视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- message schemas, properties
- Messaging Property view [Tracking Profile Editor]
- Tracking Profile Editor, Messaging Property view
- message schemas, XML messages
ms.assetid: 80d040e9-d58b-41d1-b26d-19aff4d3126b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1be1498cd3766863b9f5b2e3a37ae419d4bafc8a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="messaging-property-view"></a><span data-ttu-id="e1dac-102">“消息传送属性”视图</span><span class="sxs-lookup"><span data-stu-id="e1dac-102">Messaging Property View</span></span>
<span data-ttu-id="e1dac-103">“消息传送属性”视图显示与该属性相关联的 XML 消息的架构。</span><span class="sxs-lookup"><span data-stu-id="e1dac-103">The Messaging Property view displays the schema of the XML message associated with the property.</span></span> <span data-ttu-id="e1dac-104">可以从“业务流程调度”视图中的某些形状的快捷菜单访问此视图。</span><span class="sxs-lookup"><span data-stu-id="e1dac-104">The view is available from the shortcut menu for some of the shapes in the Orchestration Schedule view.</span></span>  
  
## <a name="working-with-messaging-properties"></a><span data-ttu-id="e1dac-105">使用消息传送属性</span><span class="sxs-lookup"><span data-stu-id="e1dac-105">Working with messaging properties</span></span>  
 <span data-ttu-id="e1dac-106">通过单击选择你的消息属性视图**选择事件源**按钮并单击**选择消息属性**菜单项。</span><span class="sxs-lookup"><span data-stu-id="e1dac-106">You select your Messaging Property view by clicking the **Select Event Source** button and clicking the **Select Message Property** menu item.</span></span> <span data-ttu-id="e1dac-107">然后选择从中选择架构的消息属性。</span><span class="sxs-lookup"><span data-stu-id="e1dac-107">You then choose a message property from which to select a schema.</span></span> <span data-ttu-id="e1dac-108">选择架构后，可以将此架构中的元素拖到活动的数据项文件夹，以此表明要在此操作中从消息内的特定 XPath 表达式提取这些数据。</span><span class="sxs-lookup"><span data-stu-id="e1dac-108">Once you select the schema, you can drag elements from this schema to the data item folders of the activity, thus indicating that you want to extract that particular data from specific XPath expressions inside the message at this action.</span></span>  
  
 <span data-ttu-id="e1dac-109">可以从“业务流程调度”视图中打开消息属性视图，方法是右键单击包含消息负载的形状，</span><span class="sxs-lookup"><span data-stu-id="e1dac-109">You can open message property views from the Orchestration Schedule view by right-clicking a shape that contains a message payload.</span></span> <span data-ttu-id="e1dac-110">此操作将打开一个上下文菜单，单击其中的“消息负载”菜单项来检索与此形状相关联的负载的列表。</span><span class="sxs-lookup"><span data-stu-id="e1dac-110">This will open a context menu from which you can click the Message Payload menu item to retrieve a list of payloads associated with the shape.</span></span>  
  
 <span data-ttu-id="e1dac-111">可用的消息属性的列表可能非常大。</span><span class="sxs-lookup"><span data-stu-id="e1dac-111">The list of available message properties can be extensive.</span></span> <span data-ttu-id="e1dac-112">如果你知道业务流程，而你要搜索的名称的一部分，您可以键入**中字符串**文本框中，然后单击**搜索**按钮。</span><span class="sxs-lookup"><span data-stu-id="e1dac-112">If you know part of the name of the orchestration for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="e1dac-113">搜索结果中将只显示那些包含您所输入的部分字符串的消息属性。</span><span class="sxs-lookup"><span data-stu-id="e1dac-113">This will select only those message properties that contain the partial string you have entered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1dac-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1dac-114">See Also</span></span>  
 <span data-ttu-id="e1dac-115">[源事件视图是什么？](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="e1dac-115">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="e1dac-116">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="e1dac-116">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)