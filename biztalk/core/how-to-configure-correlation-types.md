---
title: 如何配置相关类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, correlation types
- correlation types, configuring
- correlation types, deleting
- configuring, correlation types
ms.assetid: cfae4d2e-ec79-45c8-93b3-799dc5e0576e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69770055b1d373b355bfd853e26bf463aab1858d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341495"
---
# <a name="how-to-configure-correlation-types"></a><span data-ttu-id="67367-102">如何配置相关类型</span><span class="sxs-lookup"><span data-stu-id="67367-102">How to Configure Correlation Types</span></span>
<span data-ttu-id="67367-103">您使用**相关性属性**对话框以添加或删除相关类型属性。</span><span class="sxs-lookup"><span data-stu-id="67367-103">You use the **Correlation Properties** dialog box to add or remove properties from a correlation type.</span></span> <span data-ttu-id="67367-104">相关类型列出相关集中使用的发送和接收活动，以确保与业务流程在运行时的正确实例的传入消息正确相关联的属性。</span><span class="sxs-lookup"><span data-stu-id="67367-104">The correlation type lists the properties in a correlation set which are used by Send and Receive activities to make sure that incoming messages are properly correlated with the right instances of an orchestration at run time.</span></span>  
  
 <span data-ttu-id="67367-105">在对话框中，每个包含的属性列表有两个窗格。</span><span class="sxs-lookup"><span data-stu-id="67367-105">There are two panes in the dialog box, each containing a list of properties.</span></span> <span data-ttu-id="67367-106">左窗格中，"可用属性"包含的所有项目中定义的或它引用的属性的树视图。</span><span class="sxs-lookup"><span data-stu-id="67367-106">The left pane, "Available Properties", contains a tree view of all of the properties that are defined in your project or referenced by it.</span></span> <span data-ttu-id="67367-107">默认情况下显示的属性是系统属性，BizTalk Server 定义的但还可以在属性架构中定义您自己的属性。</span><span class="sxs-lookup"><span data-stu-id="67367-107">The properties that appear by default are system properties, defined by BizTalk Server, but you can also define your own properties in a property schema.</span></span> <span data-ttu-id="67367-108">有关创建属性架构的详细信息，请参阅[属性架构](../core/property-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="67367-108">For more information about creating property schemas, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67367-109">然后可以在相关类型中使用这些，则必须升级架构属性。</span><span class="sxs-lookup"><span data-stu-id="67367-109">Schema properties must be promoted before they can be used in a correlation type.</span></span> <span data-ttu-id="67367-110">有关详细信息，请参阅[升级属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="67367-110">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
### <a name="to-add-and-configure-a-correlation-type"></a><span data-ttu-id="67367-111">若要添加和配置相关类型</span><span class="sxs-lookup"><span data-stu-id="67367-111">To add and configure a correlation type</span></span>  
  
-   <span data-ttu-id="67367-112">在业务流程视图窗口中，右键单击**相关类型**，然后单击**新相关类型**。</span><span class="sxs-lookup"><span data-stu-id="67367-112">In the Orchestration View window, right-click **Correlation Types** and then click **New Correlation Type**.</span></span>  
  
     <span data-ttu-id="67367-113">**相关性属性**弹出对话框。</span><span class="sxs-lookup"><span data-stu-id="67367-113">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="67367-114">添加你想要在相关类型中包含的属性。</span><span class="sxs-lookup"><span data-stu-id="67367-114">Add properties that you want to include in your correlation type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67367-115">如果访问**相关性属性**对话框直接从相关集，如果尚不存在，将创建相关集相关类型。</span><span class="sxs-lookup"><span data-stu-id="67367-115">If you access the **Correlation Properties** dialog box directly from a correlation set, a correlation type for the correlation set is created if one does not already exist.</span></span> <span data-ttu-id="67367-116">所做的更改将保存到新的相关类型和相关集将配置为使用新的相关类型。</span><span class="sxs-lookup"><span data-stu-id="67367-116">Your changes will be saved to the new correlation type, and the correlation set will be configured to use the new correlation type.</span></span> <span data-ttu-id="67367-117">如果该相关集已存在相关类型并进行更改，将修改相关类型。</span><span class="sxs-lookup"><span data-stu-id="67367-117">If a correlation type already existed for the correlation set and you make changes, the correlation type will be modified.</span></span>  
  
### <a name="to-remove-a-correlation-type"></a><span data-ttu-id="67367-118">若要删除某一相关类型</span><span class="sxs-lookup"><span data-stu-id="67367-118">To remove a correlation type</span></span>  
  
-   <span data-ttu-id="67367-119">在业务流程视图窗口中，右键单击你想要删除，然后单击相关类型**删除**。</span><span class="sxs-lookup"><span data-stu-id="67367-119">In the Orchestration View window, right-click the correlation type you want to remove and then click **Delete**.</span></span>