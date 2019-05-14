---
title: 上下文属性视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- Context Property view [Tracking Profile Editor]
- Tracking Profile Editor, Context Property view
- message schemas, XML messages
ms.assetid: 17a21b86-995c-4dc2-9a3c-1309837d0b9b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b622c9a82bb199b066dc75b77822a4f0c2e06bdb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390315"
---
# <a name="context-property-view"></a><span data-ttu-id="a7088-102">上下文属性视图</span><span class="sxs-lookup"><span data-stu-id="a7088-102">Context Property View</span></span>
<span data-ttu-id="a7088-103">上下文属性视图显示与属性关联的 XML 消息的架构。</span><span class="sxs-lookup"><span data-stu-id="a7088-103">The Context Property view displays the schema of the XML message associated with the property.</span></span> <span data-ttu-id="a7088-104">该视图是可从某些业务流程调度视图中的形状的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="a7088-104">The view is available from the shortcut menu for some of the shapes in the Orchestration Schedule view.</span></span>  
  
## <a name="working-with-the-context-property-view"></a><span data-ttu-id="a7088-105">使用上下文属性视图</span><span class="sxs-lookup"><span data-stu-id="a7088-105">Working with the Context Property view</span></span>  
 <span data-ttu-id="a7088-106">通过单击选择上下文属性视图**选择事件源**按钮，单击**选择上下文属性**菜单项。</span><span class="sxs-lookup"><span data-stu-id="a7088-106">You select your Context Property view by clicking the **Select Event Source** button and clicking the **Select Context Property** menu item.</span></span> <span data-ttu-id="a7088-107">然后从已知的上下文属性，若要加载该属性架构列表中选择上下文属性。</span><span class="sxs-lookup"><span data-stu-id="a7088-107">You then choose a context property from the list of known context properties to load the schema for that property.</span></span> <span data-ttu-id="a7088-108">一旦您选择的属性，您可以将元素从关联的架构到活动的数据项文件夹以指示您希望从此操作的消息内的特定 XPath 表达式提取这些数据。</span><span class="sxs-lookup"><span data-stu-id="a7088-108">Once you select the property, you can drag elements from the associated schema to the data item folders of the activity, thus indicating you want to extract that data from specific XPath expression inside the message at this action.</span></span>  
  
 <span data-ttu-id="a7088-109">通过右键单击包含上下文属性的形状，可以从业务流程调度视图中打开上下文属性视图。</span><span class="sxs-lookup"><span data-stu-id="a7088-109">You can open context property views from the orchestration schedule view by right-clicking a shape that contains a context property.</span></span> <span data-ttu-id="a7088-110">这将打开一个上下文菜单，你可以单击**上下文属性架构**菜单项来检索与形状相关联的上下文属性的列表。</span><span class="sxs-lookup"><span data-stu-id="a7088-110">This will open a context menu from which you can click the **Context Property Schema** menu item to retrieve a list of context properties associated with the shape.</span></span>  
  
 <span data-ttu-id="a7088-111">可用的上下文属性的列表可能非常大。</span><span class="sxs-lookup"><span data-stu-id="a7088-111">The list of available context properties can be extensive.</span></span> <span data-ttu-id="a7088-112">如果您知道要搜索的属性名称的一部分，您可以键入**字符串中**文本框中，然后单击**搜索**按钮。</span><span class="sxs-lookup"><span data-stu-id="a7088-112">If you know part of the name of the property for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="a7088-113">这将选择包含您输入的部分字符串的那些属性。</span><span class="sxs-lookup"><span data-stu-id="a7088-113">This will select only those properties that contain the partial string you have entered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7088-114">当你选择从上下文属性视图映射时，潜在属性架构的列表是在 BizTalk Server 安装中配置每个属性架构的完整列表。</span><span class="sxs-lookup"><span data-stu-id="a7088-114">When you choose to map from the Context Properties view, the list of potential property schemas is a complete list of every property schema configured in your BizTalk Server installation.</span></span>  <span data-ttu-id="a7088-115">您必须知道提供的架构不敏感到 BizTalk Server 中的哪些功能由正在运行的进程在其使用。</span><span class="sxs-lookup"><span data-stu-id="a7088-115">You must aware that the schemas presented are not sensitive to which features in BizTalk Server are used by the running process on which you are working.</span></span> <span data-ttu-id="a7088-116">例如，您可以从提供的上下文属性映射时的架构的列表中选择 SOAP 属性的架构，但正在运行的进程本身可能不使用 SOAP。</span><span class="sxs-lookup"><span data-stu-id="a7088-116">For example, you can select a schema for SOAP properties from the list of schemas offered when mapping from Context Properties, but the running process itself may not use SOAP.</span></span> <span data-ttu-id="a7088-117">映射中未使用的属性会导致 bam 捕获的 null 或为空数据的任何 BAM 活动项。</span><span class="sxs-lookup"><span data-stu-id="a7088-117">Any BAM activity item mapped from an unused property results in null or empty data being captured by BAM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7088-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7088-118">See Also</span></span>  
 <span data-ttu-id="a7088-119">[什么是源事件视图？](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="a7088-119">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="a7088-120">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="a7088-120">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)