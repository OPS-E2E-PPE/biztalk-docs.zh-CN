---
title: 跟踪数据库的大小调整准则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, performance
- Tracking database, size
- Tracking Analysis Server database [BAM]
- performance, Tracking database
ms.assetid: 2188bee5-c0dd-4448-bd4a-4ffb2a0c79f1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c21ce436ac194c06481f80e80c4add3f70f48872
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313926"
---
# <a name="tracking-database-sizing-guidelines"></a><span data-ttu-id="bee3c-102">跟踪数据库的大小调整准则</span><span class="sxs-lookup"><span data-stu-id="bee3c-102">Tracking Database Sizing Guidelines</span></span>
<span data-ttu-id="bee3c-103">本部分介绍在 BizTalk 跟踪 (BizTalkDTADb) 数据库调整大小考虑事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bee3c-103">This section describes sizing considerations for the BizTalk Tracking (BizTalkDTADb) database in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="bee3c-104">它介绍了如何使用公式和消息变量来确定如何大型 BizTalk 跟踪数据库将处于给定的一段时间，并提供如何应用这些公式的具体示例。</span><span class="sxs-lookup"><span data-stu-id="bee3c-104">It explains how to use equations and message variables to determine how large the BizTalk Tracking database will become over a given period of time, and provides specific examples of how to apply the equations.</span></span> <span data-ttu-id="bee3c-105">这提供了 BizTalk 消息、 跟踪设置和跟踪数据库之间粗略的相互关系大小。</span><span class="sxs-lookup"><span data-stu-id="bee3c-105">This provides the rough co-relation between BizTalk messages, tracking settings and the tracking database size.</span></span> <span data-ttu-id="bee3c-106">不考虑帐户中的跟踪表; 的索引大小等其他因素的 SQL Server您可能想要考虑合理的乘数以便说明这些因素。</span><span class="sxs-lookup"><span data-stu-id="bee3c-106">It does not take into account other SQL Server factors such as index size in the tracking tables; you may want to consider reasonable multipliers to account for those factors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bee3c-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="bee3c-107">In This Section</span></span>  
  
-   [<span data-ttu-id="bee3c-108">使用消息变量调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="bee3c-108">Using Message Variables to Size the Tracking Database</span></span>](../core/using-message-variables-to-size-the-tracking-database.md)  
  
-   [<span data-ttu-id="bee3c-109">调整跟踪数据库来跟踪消息正文大小</span><span class="sxs-lookup"><span data-stu-id="bee3c-109">Sizing the Tracking Database to Track Message Bodies</span></span>](../core/sizing-the-tracking-database-to-track-message-bodies.md)  
  
-   [<span data-ttu-id="bee3c-110">方案 1：为简单 BizTalk 消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="bee3c-110">Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages</span></span>](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)  
  
-   [<span data-ttu-id="bee3c-111">方案 2：为业务流程中消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="bee3c-111">Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations</span></span>](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)  
  
-   [<span data-ttu-id="bee3c-112">方案 3:为发送到分发列表的消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="bee3c-112">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)  
  
-   [<span data-ttu-id="bee3c-113">方案 4:为所有消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="bee3c-113">Scenario 4: Sizing the Tracking Database for all Messages</span></span>](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)  
  
## <a name="see-also"></a><span data-ttu-id="bee3c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bee3c-114">See Also</span></span>  
 <span data-ttu-id="bee3c-115">[跟踪数据库中的记录大小](../core/record-size-in-tracking-databases.md) </span><span class="sxs-lookup"><span data-stu-id="bee3c-115">[Record Size in Tracking Databases](../core/record-size-in-tracking-databases.md) </span></span>  
 [<span data-ttu-id="bee3c-116">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="bee3c-116">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)