---
title: 如何为发送端口组配置筛选器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filters, configuring
- filters, send port groups
- send port groups, filters
- send port groups, configuring
- configuring, send port groups
- managing [send port groups], filters
- managing [send port groups], configuring
ms.assetid: 4c4bb408-5146-4740-a1d4-0ee72ec123fb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1960c8587f77be4f974095f5f663dba81bcb8f9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970574"
---
# <a name="how-to-configure-filters-for-a-send-port-group"></a><span data-ttu-id="6a9c1-102">如何为发送端口组配置筛选器</span><span class="sxs-lookup"><span data-stu-id="6a9c1-102">How to Configure Filters for a Send Port Group</span></span>
<span data-ttu-id="6a9c1-103">本主题将介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台为发送端口组配置一个或多个筛选器。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure one or more filters for a send port group.</span></span> <span data-ttu-id="6a9c1-104">您可以使用筛选器来创建简单消息传送或基于内容的路由 (CBR) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-104">You can use filters to create simple messaging or content-based routing (CBR) applications.</span></span> <span data-ttu-id="6a9c1-105">筛选器可以设置消息属性或字段的条件，这些条件决定哪些消息将被路由到发送端口组。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-105">A filter sets conditions for message properties or fields that determine which messages are routed to the send port group.</span></span> <span data-ttu-id="6a9c1-106">筛选器不筛选由业务流程路由到发送端口组的消息。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-106">A filter does not filter the messages that an orchestration routes to the send port group.</span></span>  
  
 <span data-ttu-id="6a9c1-107">您可以创建一个或多个筛选器表达式，表达式包含消息属性、运算符以及使用此运算符根据该属性进行验证的值。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-107">You can create one or more filter expressions, which consist of a message property, an operator, and a value that is validated against the property by using the operator.</span></span>  
  
 <span data-ttu-id="6a9c1-108">例如，您可以创建如下所示的表达式：</span><span class="sxs-lookup"><span data-stu-id="6a9c1-108">For example, you might create an expression like the following:</span></span>  
  
 <span data-ttu-id="6a9c1-109">MSMQ.MsgID = 1</span><span class="sxs-lookup"><span data-stu-id="6a9c1-109">MSMQ.MsgID = 1</span></span>  
  
 <span data-ttu-id="6a9c1-110">使用此筛选器，发送端口组将只订阅 MSMQ 消息 ID 为 1 的消息。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-110">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  
  
 <span data-ttu-id="6a9c1-111">您可以创建其他表达式，并指定该表达式与其他表达式有 AND 或 OR 关系，例如：</span><span class="sxs-lookup"><span data-stu-id="6a9c1-111">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  
  
 <span data-ttu-id="6a9c1-112">MSMQ.MsgID = 1 OR</span><span class="sxs-lookup"><span data-stu-id="6a9c1-112">MSMQ.MsgID = 1 OR</span></span>  
  
 <span data-ttu-id="6a9c1-113">SMTP.From = MyServer</span><span class="sxs-lookup"><span data-stu-id="6a9c1-113">SMTP.From = MyServer</span></span>  
  
 <span data-ttu-id="6a9c1-114">在这种情况下，发送端口组将订阅 MSMQ 消息 ID 为 1 或发自名为 MyServer 的 SMTP 服务器的所有消息。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-114">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a9c1-115">如果您在一个应用程序中为发送端口组创建了筛选器，此应用程序使用另一个应用程序中的属性架构，然后将第一个应用程序导入到新 BizTalk 组中，则您将收到缺少架构的警告，并且在安装和启动该应用程序时筛选功能将无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-115">If you create a filter for a send port group in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started.</span></span> <span data-ttu-id="6a9c1-116">解决这个问题的方法是：先导入包含该架构的应用程序，然后再安装不包含该架构的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-116">You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a9c1-117">应用程序开发人员可以通过在开发过程中使用本主题中的过程来为发送端口组配置筛选器。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-117">The application developer can configure filters for a send port group during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6a9c1-118">必要條件</span><span class="sxs-lookup"><span data-stu-id="6a9c1-118">Prerequisites</span></span>  
 <span data-ttu-id="6a9c1-119">若要执行本主题中的步骤，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-119">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="6a9c1-120">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-filters-for-a-send-port-group"></a><span data-ttu-id="6a9c1-121">为发送端口组配置筛选器</span><span class="sxs-lookup"><span data-stu-id="6a9c1-121">To configure filters for a send port group</span></span>  
  
1. <span data-ttu-id="6a9c1-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="6a9c1-123">在控制台树中，展开要为其配置发送端口组筛选器的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-123">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure a send port group filter.</span></span>  
  
3. <span data-ttu-id="6a9c1-124">单击**发送端口组**，右键单击该发送端口组，单击**属性**，然后单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-124">Click **Send Port Groups**, right-click the send port group, click **Properties**, and then click **Filters**.</span></span>  
  
4. <span data-ttu-id="6a9c1-125">下表中所述配置筛选器，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-125">Configure filters as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="6a9c1-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6a9c1-126">Use this</span></span>|<span data-ttu-id="6a9c1-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6a9c1-127">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="6a9c1-128">**删除**</span><span class="sxs-lookup"><span data-stu-id="6a9c1-128">**Delete**</span></span>|<span data-ttu-id="6a9c1-129">单击此项可删除所选的筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-129">Click to delete the selected filter expression.</span></span>|  
   |<span data-ttu-id="6a9c1-130">**上移**</span><span class="sxs-lookup"><span data-stu-id="6a9c1-130">**Move Up**</span></span>|<span data-ttu-id="6a9c1-131">单击此项可在筛选器表达式序列中向上移动所选的属性。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-131">Click to move the selected property ahead in the filter expression sequence.</span></span>|  
   |<span data-ttu-id="6a9c1-132">**“下移”**</span><span class="sxs-lookup"><span data-stu-id="6a9c1-132">**Move Down**</span></span>|<span data-ttu-id="6a9c1-133">单击此项可在筛选器表达式序列中向下移动所选的属性。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-133">Click to move the selected property down in the filter expression sequence.</span></span>|  
   |<span data-ttu-id="6a9c1-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="6a9c1-134">**Property**</span></span>|<span data-ttu-id="6a9c1-135">在列表中，单击要在此筛选器表达式中使用的消息属性。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-135">In the list, click a message property to use in this filter expression.</span></span>|  
   |<span data-ttu-id="6a9c1-136">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="6a9c1-136">**Operator**</span></span>|<span data-ttu-id="6a9c1-137">为表达式键入或选择运算符。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-137">Type or select the operator for the expression.</span></span>|  
   |<span data-ttu-id="6a9c1-138">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="6a9c1-138">**Value**</span></span>|<span data-ttu-id="6a9c1-139">键入要根据该属性验证的值。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-139">Type the value to validate against the property.</span></span> <span data-ttu-id="6a9c1-140">不同属性类型可接受的值类型不同。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-140">The accepted value type varies according to the type of property.</span></span> <span data-ttu-id="6a9c1-141">若要查看某个属性可接受哪些类型的值，请将鼠标悬停在该属性上。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-141">To see what type of value is accepted for a property, hover your mouse over the property.</span></span> <span data-ttu-id="6a9c1-142">下面是可接受的值：Int：(Integer) ，它必须是整数。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-142">Acceptable values are as follows: Int: (Integer) This must be a whole number.</span></span> <span data-ttu-id="6a9c1-143">字符串： 一个字符串。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-143">String: A character string.</span></span> <span data-ttu-id="6a9c1-144">dateTime： 日期和/或时间。NET 支持的格式。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-144">dateTime: A date and/or time in .NET-supported format.</span></span> <span data-ttu-id="6a9c1-145">有关 .NET 支持的时间格式的详细信息，请参阅 .NET Frameworks 帮助中的“DateTimeFormatInfo 类”。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-145">For more information about .NET-supported time formats, see "DateTimeFormatInfo Class" in .NET Frameworks Help.</span></span>|  
   |<span data-ttu-id="6a9c1-146">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="6a9c1-146">**Group by**</span></span>|<span data-ttu-id="6a9c1-147">选择**并**或**或**以指示筛选器表达式之间的关系。</span><span class="sxs-lookup"><span data-stu-id="6a9c1-147">Select **And** or **Or** to indicate the relationship between filter expressions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a9c1-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a9c1-148">See Also</span></span>  
 [<span data-ttu-id="6a9c1-149">创建和配置发送端口组</span><span class="sxs-lookup"><span data-stu-id="6a9c1-149">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)