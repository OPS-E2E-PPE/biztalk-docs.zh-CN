---
title: 消息传送属性视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- message schemas, properties
- Messaging Property view [Tracking Profile Editor]
- Tracking Profile Editor, Messaging Property view
- message schemas, XML messages
ms.assetid: 80d040e9-d58b-41d1-b26d-19aff4d3126b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fb3e9461b695579d2168fb321d38ff9de380bda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394491"
---
# <a name="messaging-property-view"></a><span data-ttu-id="18f48-102">消息传送属性视图</span><span class="sxs-lookup"><span data-stu-id="18f48-102">Messaging Property View</span></span>
<span data-ttu-id="18f48-103">消息传送属性视图显示与属性关联的 XML 消息的架构。</span><span class="sxs-lookup"><span data-stu-id="18f48-103">The Messaging Property view displays the schema of the XML message associated with the property.</span></span> <span data-ttu-id="18f48-104">该视图是可从某些业务流程调度视图中的形状的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="18f48-104">The view is available from the shortcut menu for some of the shapes in the Orchestration Schedule view.</span></span>  
  
## <a name="working-with-messaging-properties"></a><span data-ttu-id="18f48-105">使用消息传送属性</span><span class="sxs-lookup"><span data-stu-id="18f48-105">Working with messaging properties</span></span>  
 <span data-ttu-id="18f48-106">通过单击选择消息传送属性视图**选择事件源**按钮，单击**选择消息属性**菜单项。</span><span class="sxs-lookup"><span data-stu-id="18f48-106">You select your Messaging Property view by clicking the **Select Event Source** button and clicking the **Select Message Property** menu item.</span></span> <span data-ttu-id="18f48-107">然后选择要从中选择架构的消息属性。</span><span class="sxs-lookup"><span data-stu-id="18f48-107">You then choose a message property from which to select a schema.</span></span> <span data-ttu-id="18f48-108">一旦选择架构，您可以将元素从此架构到活动的数据项文件夹以指示您希望此操作的消息内的特定 XPath 表达式提取这些特定的数据。</span><span class="sxs-lookup"><span data-stu-id="18f48-108">Once you select the schema, you can drag elements from this schema to the data item folders of the activity, thus indicating that you want to extract that particular data from specific XPath expressions inside the message at this action.</span></span>  
  
 <span data-ttu-id="18f48-109">可以通过右键单击包含消息负载的形状从业务流程调度视图打开消息属性视图。</span><span class="sxs-lookup"><span data-stu-id="18f48-109">You can open message property views from the Orchestration Schedule view by right-clicking a shape that contains a message payload.</span></span> <span data-ttu-id="18f48-110">这将打开上下文菜单，单击要检索的负载与形状相关联的列表的消息负载菜单项。</span><span class="sxs-lookup"><span data-stu-id="18f48-110">This will open a context menu from which you can click the Message Payload menu item to retrieve a list of payloads associated with the shape.</span></span>  
  
 <span data-ttu-id="18f48-111">可用的消息属性的列表可能非常大。</span><span class="sxs-lookup"><span data-stu-id="18f48-111">The list of available message properties can be extensive.</span></span> <span data-ttu-id="18f48-112">如果您知道要搜索的业务流程的名称的一部分，您可以键入**字符串中**文本框中，然后单击**搜索**按钮。</span><span class="sxs-lookup"><span data-stu-id="18f48-112">If you know part of the name of the orchestration for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="18f48-113">这将选择包含您输入的部分字符串这些消息属性。</span><span class="sxs-lookup"><span data-stu-id="18f48-113">This will select only those message properties that contain the partial string you have entered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f48-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="18f48-114">See Also</span></span>  
 <span data-ttu-id="18f48-115">[什么是源事件视图？](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="18f48-115">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="18f48-116">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="18f48-116">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)