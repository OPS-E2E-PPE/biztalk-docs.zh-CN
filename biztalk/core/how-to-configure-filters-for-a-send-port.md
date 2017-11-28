---
title: "如何配置发送端口的筛选器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filters, configuring
- filters, send ports
- configuring, filters
- managing [send ports], configuring
- send ports, configuring
- send ports, filters
- managing [send ports], filters
ms.assetid: ad13ca8e-bb1d-4449-8163-49dd9d5d92f8
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7845b6189f86054ba9661ea450575a2dcfe47953
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-filters-for-a-send-port"></a><span data-ttu-id="c123e-102">如何为发送端口配置筛选器</span><span class="sxs-lookup"><span data-stu-id="c123e-102">How to Configure Filters for a Send Port</span></span>
<span data-ttu-id="c123e-103">本主题将介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台为发送端口配置筛选器。</span><span class="sxs-lookup"><span data-stu-id="c123e-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure filters for a send port.</span></span> <span data-ttu-id="c123e-104">您可以使用筛选器来创建简单消息传送或基于内容的路由 (CBR) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c123e-104">You can use filters to create simple messaging or content-based routing (CBR) applications.</span></span> <span data-ttu-id="c123e-105">筛选器可以设置消息属性或字段的条件，这些条件决定哪些消息将被路由到发送端口。</span><span class="sxs-lookup"><span data-stu-id="c123e-105">A filter sets conditions for message properties or fields that determine which messages are routed to the send port.</span></span> <span data-ttu-id="c123e-106">筛选器不筛选由业务流程路由到发送端口的消息。</span><span class="sxs-lookup"><span data-stu-id="c123e-106">A filter does not filter the messages that an orchestration routes to the send port.</span></span>  
  
 <span data-ttu-id="c123e-107">您可以创建一个或多个筛选器表达式，表达式包含消息属性、运算符以及使用此运算符根据该属性进行验证的值。</span><span class="sxs-lookup"><span data-stu-id="c123e-107">You can create one or more filter expressions, which consist of a message property, an operator, and a value that is validated against the property by using the operator.</span></span>  
  
 <span data-ttu-id="c123e-108">例如，您可以创建如下所示的表达式：</span><span class="sxs-lookup"><span data-stu-id="c123e-108">For example, you might create an expression like the following:</span></span>  
  
 <span data-ttu-id="c123e-109">MSMQ.MsgID = 1</span><span class="sxs-lookup"><span data-stu-id="c123e-109">MSMQ.MsgID = 1</span></span>  
  
 <span data-ttu-id="c123e-110">使用此筛选器，发送端口组将只订阅 MSMQ 消息 ID 为 1 的消息。</span><span class="sxs-lookup"><span data-stu-id="c123e-110">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  
  
 <span data-ttu-id="c123e-111">您可以创建其他表达式，并指定该表达式与其他表达式有 AND 或 OR 关系，例如：</span><span class="sxs-lookup"><span data-stu-id="c123e-111">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  
  
 <span data-ttu-id="c123e-112">MSMQ.MsgID = 1 OR</span><span class="sxs-lookup"><span data-stu-id="c123e-112">MSMQ.MsgID = 1 OR</span></span>  
  
 <span data-ttu-id="c123e-113">SMTP.From = MyServer</span><span class="sxs-lookup"><span data-stu-id="c123e-113">SMTP.From = MyServer</span></span>  
  
 <span data-ttu-id="c123e-114">在这种情况下，发送端口组将订阅 MSMQ 消息 ID 为 1 或发自名为 MyServer 的 SMTP 服务器的所有消息。</span><span class="sxs-lookup"><span data-stu-id="c123e-114">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c123e-115">如果您在一个应用程序中为发送端口创建了筛选器，此应用程序使用另一个应用程序中的属性架构，然后将第一个应用程序导入到新 BizTalk 组中，则您将收到缺少架构的警告，并且在安装和启动该应用程序时筛选功能将无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="c123e-115">If you create a filter for a send port in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started.</span></span> <span data-ttu-id="c123e-116">解决这个问题的方法是：先导入包含该架构的应用程序，然后再安装不包含该架构的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c123e-116">You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c123e-117">通过使用本主题中的过程，应用程序开发人员可以在开发过程中配置为发送端口的筛选器。</span><span class="sxs-lookup"><span data-stu-id="c123e-117">The application developer can configure filters for a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c123e-118">先决条件</span><span class="sxs-lookup"><span data-stu-id="c123e-118">Prerequisites</span></span>  
 <span data-ttu-id="c123e-119">若要执行本主题中的步骤，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="c123e-119">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="c123e-120">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c123e-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-filters-for-a-send-port"></a><span data-ttu-id="c123e-121">为发送端口配置筛选器</span><span class="sxs-lookup"><span data-stu-id="c123e-121">To configure filters for a send port</span></span>  
  
1.  <span data-ttu-id="c123e-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c123e-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c123e-123">在控制台树中，展开要为其配置发送端口筛选器的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c123e-123">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure send port filters.</span></span>  
  
3.  <span data-ttu-id="c123e-124">展开**发送端口**，右键单击发送端口，请单击**属性**，然后单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="c123e-124">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Filters**.</span></span>  
  
4.  <span data-ttu-id="c123e-125">下表中所述配置筛选器，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c123e-125">Configure filters as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="c123e-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c123e-126">Use this</span></span>|<span data-ttu-id="c123e-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c123e-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c123e-128">**删除**</span><span class="sxs-lookup"><span data-stu-id="c123e-128">**Delete**</span></span>|<span data-ttu-id="c123e-129">单击此项可删除所选的筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="c123e-129">Click to delete the selected filter expression.</span></span>|  
    |<span data-ttu-id="c123e-130">**上移**</span><span class="sxs-lookup"><span data-stu-id="c123e-130">**Move Up**</span></span>|<span data-ttu-id="c123e-131">单击此项可在筛选器表达式序列中向上移动所选的属性。</span><span class="sxs-lookup"><span data-stu-id="c123e-131">Click to move the selected property ahead in the filter expression sequence.</span></span>|  
    |<span data-ttu-id="c123e-132">**下移**</span><span class="sxs-lookup"><span data-stu-id="c123e-132">**Move Down**</span></span>|<span data-ttu-id="c123e-133">单击此项可在筛选器表达式序列中向下移动所选的属性。</span><span class="sxs-lookup"><span data-stu-id="c123e-133">Click to move the selected property down in the filter expression sequence.</span></span>|  
    |<span data-ttu-id="c123e-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="c123e-134">**Property**</span></span>|<span data-ttu-id="c123e-135">在列表中，单击要在此筛选器表达式中使用的消息属性。</span><span class="sxs-lookup"><span data-stu-id="c123e-135">In the list, click a message property to use in this filter expression.</span></span>|  
    |<span data-ttu-id="c123e-136">**运算符**</span><span class="sxs-lookup"><span data-stu-id="c123e-136">**Operator**</span></span>|<span data-ttu-id="c123e-137">为表达式键入或选择运算符。</span><span class="sxs-lookup"><span data-stu-id="c123e-137">Type or select the operator for the expression.</span></span>|  
    |<span data-ttu-id="c123e-138">**值**</span><span class="sxs-lookup"><span data-stu-id="c123e-138">**Value**</span></span>|<span data-ttu-id="c123e-139">键入要根据该属性验证的值。</span><span class="sxs-lookup"><span data-stu-id="c123e-139">Type the value to validate against the property.</span></span> <span data-ttu-id="c123e-140">不同属性类型可接受的值类型不同。</span><span class="sxs-lookup"><span data-stu-id="c123e-140">The accepted value type varies according to the type of property.</span></span> <span data-ttu-id="c123e-141">若要查看某个属性可接受哪些类型的值，请将鼠标悬停在该属性上。</span><span class="sxs-lookup"><span data-stu-id="c123e-141">To see what type of value is accepted for a property, hover your mouse over the property.</span></span> <span data-ttu-id="c123e-142">下面是可接受的值：Int：(Integer) ，它必须是整数。</span><span class="sxs-lookup"><span data-stu-id="c123e-142">Acceptable values are as follows: Int: (Integer) This must be a whole number.</span></span> <span data-ttu-id="c123e-143">字符串： 一个字符串。</span><span class="sxs-lookup"><span data-stu-id="c123e-143">String: A character string.</span></span> <span data-ttu-id="c123e-144">dateTime： 日期和/或时间。NET 支持的格式。</span><span class="sxs-lookup"><span data-stu-id="c123e-144">dateTime: A date and/or time in .NET-supported format.</span></span> <span data-ttu-id="c123e-145">有关 .NET 支持的时间格式的详细信息，请参阅 .NET Frameworks 帮助中的“DateTimeFormatInfo 类”。</span><span class="sxs-lookup"><span data-stu-id="c123e-145">For more information about .NET-supported time formats, see "DateTimeFormatInfo Class" in .NET Frameworks Help.</span></span>|  
    |<span data-ttu-id="c123e-146">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="c123e-146">**Group by**</span></span>|<span data-ttu-id="c123e-147">选择**和**或**或**以指示这与其他筛选器表达式之间的关系。</span><span class="sxs-lookup"><span data-stu-id="c123e-147">Select **And** or **Or** to indicate the relationship between this and other filter expressions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c123e-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c123e-148">See Also</span></span>  
 [<span data-ttu-id="c123e-149">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="c123e-149">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)