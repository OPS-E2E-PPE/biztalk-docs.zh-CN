---
title: "如何配置跟踪架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, configuring
- managing [schemas], configuring
- configuring [HAT tracking], schemas
- configuring, schemas
- configuring, tracking
- HAT, schemas
- managing [schemas], tracking
- schemas, tracking
- tracking, configuring
- tracking, schemas
ms.assetid: b5f69c98-8824-43b1-8f21-d84b60ac5431
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e15cb2210062901786b179ec75fe3880dea660b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-schema"></a><span data-ttu-id="48f77-102">如何为架构配置跟踪</span><span class="sxs-lookup"><span data-stu-id="48f77-102">How to Configure Tracking for a Schema</span></span>
<span data-ttu-id="48f77-103">本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台为架构配置跟踪。</span><span class="sxs-lookup"><span data-stu-id="48f77-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a schema.</span></span> <span data-ttu-id="48f77-104">若要配置跟踪，请指定要在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的“组中心”页的查询视图中查看的消息属性。</span><span class="sxs-lookup"><span data-stu-id="48f77-104">To configure tracking, you specify the properties of the messages that you want to view in the query views of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console Group Hub page.</span></span>  
  
 <span data-ttu-id="48f77-105">有关创建和使用查询的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="48f77-105">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="48f77-106">有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。</span><span class="sxs-lookup"><span data-stu-id="48f77-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="48f77-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="48f77-107">Prerequisites</span></span>  
 <span data-ttu-id="48f77-108">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="48f77-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="48f77-109">若只查看跟踪选项，则可以 BizTalk Server Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="48f77-109">To you want to view tracking options only, you can be logged on as a member of the BizTalk Server Operators group.</span></span> <span data-ttu-id="48f77-110">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="48f77-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-schema"></a><span data-ttu-id="48f77-111">为架构配置跟踪</span><span class="sxs-lookup"><span data-stu-id="48f77-111">To configure tracking for a schema</span></span>  
  
1.  <span data-ttu-id="48f77-112">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="48f77-112">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="48f77-113">在控制台树中，展开**BizTalk Server 管理**，展开包含你想要配置跟踪的架构的 BizTalk 组，然后展开包含架构的应用程序。</span><span class="sxs-lookup"><span data-stu-id="48f77-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema for which you want to configure tracking, and then expand the application containing the schema.</span></span>  
  
3.  <span data-ttu-id="48f77-114">单击**架构**，右键单击的架构，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="48f77-114">Click **Schemas**, right-click the schema, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="48f77-115">在左窗格中，单击**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="48f77-115">In the left pane, click **Tracking**.</span></span>  
  
5.  <span data-ttu-id="48f77-116">执行下列操作来指定的属性，用于跟踪消息，其中一项，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="48f77-116">Do one of the following to specify which properties to use for tracking messages, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="48f77-117">选择**选择所有消息属性**复选框以将所有列出的属性。</span><span class="sxs-lookup"><span data-stu-id="48f77-117">Select the **Select all message properties** check box to use all the listed properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="48f77-118">此复选框仅对包含升级属性的架构可用。</span><span class="sxs-lookup"><span data-stu-id="48f77-118">This check box is available only for schemas that contain promoted properties.</span></span>  
  
    -   <span data-ttu-id="48f77-119">选中所要使用的每个属性的复选框。</span><span class="sxs-lookup"><span data-stu-id="48f77-119">Select the check box of each property that you want to use.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="48f77-120">这是仅适用于包含提升的属性的架构。</span><span class="sxs-lookup"><span data-stu-id="48f77-120">This is available only for schemas that contain promoted properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48f77-121">您只应选择您所需要选项，因为跟踪消息将会增加系统的性能和存储的开销。</span><span class="sxs-lookup"><span data-stu-id="48f77-121">You should select only the options you need, as tracking messages creates performance and storage overhead for your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f77-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48f77-122">See Also</span></span>  
 [<span data-ttu-id="48f77-123">管理架构</span><span class="sxs-lookup"><span data-stu-id="48f77-123">Managing Schemas</span></span>](../core/managing-schemas.md)