---
title: "如何配置相关类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, correlation types
- correlation types, configuring
- correlation types, deleting
- configuring, correlation types
ms.assetid: cfae4d2e-ec79-45c8-93b3-799dc5e0576e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 646ac7dafd5207a2558e45252077efe2d9616a70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-correlation-types"></a><span data-ttu-id="8fcb5-102">如何配置相关类型</span><span class="sxs-lookup"><span data-stu-id="8fcb5-102">How to Configure Correlation Types</span></span>
<span data-ttu-id="8fcb5-103">你使用**相关性属性**对话框中添加或删除相关类型的属性。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-103">You use the **Correlation Properties** dialog box to add or remove properties from a correlation type.</span></span> <span data-ttu-id="8fcb5-104">相关类型列出相关集中的属性，发送活动和接收活动使用这些属性来确保在运行时将传入消息与业务流程的正确实例相关联。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-104">The correlation type lists the properties in a correlation set which are used by Send and Receive activities to make sure that incoming messages are properly correlated with the right instances of an orchestration at run time.</span></span>  
  
 <span data-ttu-id="8fcb5-105">该对话框中有两个窗格，每个窗格都包含一个属性列表。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-105">There are two panes in the dialog box, each containing a list of properties.</span></span> <span data-ttu-id="8fcb5-106">左侧窗格的是“可用属性”，包含您项目中定义或引用的所有属性的树视图。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-106">The left pane, "Available Properties", contains a tree view of all of the properties that are defined in your project or referenced by it.</span></span> <span data-ttu-id="8fcb5-107">默认情况下显示的属性为系统属性，是 BizTalk Server 定义的，但您也可以在属性架构中定义您自己的属性。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-107">The properties that appear by default are system properties, defined by BizTalk Server, but you can also define your own properties in a property schema.</span></span> <span data-ttu-id="8fcb5-108">有关创建属性架构的详细信息，请参阅[属性架构](../core/property-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-108">For more information about creating property schemas, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fcb5-109">架构属性必须升级，才能在相关类型中使用。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-109">Schema properties must be promoted before they can be used in a correlation type.</span></span> <span data-ttu-id="8fcb5-110">有关详细信息，请参阅[提升属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-110">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
### <a name="to-add-and-configure-a-correlation-type"></a><span data-ttu-id="8fcb5-111">添加和配置相关类型</span><span class="sxs-lookup"><span data-stu-id="8fcb5-111">To add and configure a correlation type</span></span>  
  
-   <span data-ttu-id="8fcb5-112">在业务流程视图窗口中，右键单击**相关性类型**，然后单击**新相关类型**。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-112">In the Orchestration View window, right-click **Correlation Types** and then click **New Correlation Type**.</span></span>  
  
     <span data-ttu-id="8fcb5-113">**相关性属性**弹出对话框。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-113">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="8fcb5-114">添加要包含在相关类型中的属性。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-114">Add properties that you want to include in your correlation type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8fcb5-115">如果你访问**相关性属性**对话框直接从相关设置，如果尚不存在创建关联集的相关类型。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-115">If you access the **Correlation Properties** dialog box directly from a correlation set, a correlation type for the correlation set is created if one does not already exist.</span></span> <span data-ttu-id="8fcb5-116">您的更改将被保存到新相关类型中，且相关集将被配置为使用该新相关类型。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-116">Your changes will be saved to the new correlation type, and the correlation set will be configured to use the new correlation type.</span></span> <span data-ttu-id="8fcb5-117">如果该相关集已有相关类型，则您的更改将会修改该相关类型。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-117">If a correlation type already existed for the correlation set and you make changes, the correlation type will be modified.</span></span>  
  
### <a name="to-remove-a-correlation-type"></a><span data-ttu-id="8fcb5-118">删除相关类型</span><span class="sxs-lookup"><span data-stu-id="8fcb5-118">To remove a correlation type</span></span>  
  
-   <span data-ttu-id="8fcb5-119">在业务流程视图窗口中，右键单击你想要删除，然后单击相关类型**删除**。</span><span class="sxs-lookup"><span data-stu-id="8fcb5-119">In the Orchestration View window, right-click the correlation type you want to remove and then click **Delete**.</span></span>