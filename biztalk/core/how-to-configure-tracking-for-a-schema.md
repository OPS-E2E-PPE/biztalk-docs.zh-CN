---
title: 如何为架构配置跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6505f2cb60d60ef5b4e66e8d6460cf12c70a5a38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340163"
---
# <a name="how-to-configure-tracking-for-a-schema"></a><span data-ttu-id="03a29-102">如何为架构配置跟踪</span><span class="sxs-lookup"><span data-stu-id="03a29-102">How to Configure Tracking for a Schema</span></span>
<span data-ttu-id="03a29-103">本主题介绍如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台为架构配置跟踪。</span><span class="sxs-lookup"><span data-stu-id="03a29-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a schema.</span></span> <span data-ttu-id="03a29-104">若要配置跟踪，请指定你想要的查询视图中查看的消息属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台上组中心页。</span><span class="sxs-lookup"><span data-stu-id="03a29-104">To configure tracking, you specify the properties of the messages that you want to view in the query views of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console Group Hub page.</span></span>  
  
 <span data-ttu-id="03a29-105">有关创建和使用查询的详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="03a29-105">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="03a29-106">有关消息事件和服务实例跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)。</span><span class="sxs-lookup"><span data-stu-id="03a29-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="03a29-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="03a29-107">Prerequisites</span></span>  
 <span data-ttu-id="03a29-108">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="03a29-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="03a29-109">你想要只查看跟踪选项，可以以 BizTalk Server Operators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="03a29-109">To you want to view tracking options only, you can be logged on as a member of the BizTalk Server Operators group.</span></span> <span data-ttu-id="03a29-110">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="03a29-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-schema"></a><span data-ttu-id="03a29-111">为架构配置跟踪</span><span class="sxs-lookup"><span data-stu-id="03a29-111">To configure tracking for a schema</span></span>  
  
1. <span data-ttu-id="03a29-112">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="03a29-112">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="03a29-113">在控制台树中，展开**BizTalk Server 管理**，展开包含您要为其配置跟踪，的架构的 BizTalk 组，然后展开包含该架构的应用程序。</span><span class="sxs-lookup"><span data-stu-id="03a29-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema for which you want to configure tracking, and then expand the application containing the schema.</span></span>  
  
3. <span data-ttu-id="03a29-114">单击**架构**，右键单击该架构，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="03a29-114">Click **Schemas**, right-click the schema, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="03a29-115">在左窗格中，单击**跟踪**。</span><span class="sxs-lookup"><span data-stu-id="03a29-115">In the left pane, click **Tracking**.</span></span>  
  
5. <span data-ttu-id="03a29-116">执行下述操作以指定要用于跟踪消息的属性之一，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="03a29-116">Do one of the following to specify which properties to use for tracking messages, and then click **OK**:</span></span>  
  
   -   <span data-ttu-id="03a29-117">选择**选择所有消息属性**复选框以使用所有列出的属性。</span><span class="sxs-lookup"><span data-stu-id="03a29-117">Select the **Select all message properties** check box to use all the listed properties.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="03a29-118">此复选框可仅对包含升级的属性的架构。</span><span class="sxs-lookup"><span data-stu-id="03a29-118">This check box is available only for schemas that contain promoted properties.</span></span>  
  
   -   <span data-ttu-id="03a29-119">选中你想要使用的每个属性的复选框。</span><span class="sxs-lookup"><span data-stu-id="03a29-119">Select the check box of each property that you want to use.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="03a29-120">这是仅适用于包含升级的属性的架构。</span><span class="sxs-lookup"><span data-stu-id="03a29-120">This is available only for schemas that contain promoted properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03a29-121">应选择所需选项，如跟踪消息将会为您的系统的性能和存储开销。</span><span class="sxs-lookup"><span data-stu-id="03a29-121">You should select only the options you need, as tracking messages creates performance and storage overhead for your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a29-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="03a29-122">See Also</span></span>  
 [<span data-ttu-id="03a29-123">管理架构</span><span class="sxs-lookup"><span data-stu-id="03a29-123">Managing Schemas</span></span>](../core/managing-schemas.md)