---
title: 如何关闭全局跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae3059a-cbdd-47c4-84cd-edfb5480b9fa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e4b12b84ed107c07055a75ace23fea368040935
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383620"
---
# <a name="how-to-turn-off-global-tracking"></a><span data-ttu-id="56db5-102">如何禁用全局跟踪</span><span class="sxs-lookup"><span data-stu-id="56db5-102">How to Turn Off Global Tracking</span></span>
<span data-ttu-id="56db5-103">默认情况下，安装 BizTalk Server 时启用全局跟踪。</span><span class="sxs-lookup"><span data-stu-id="56db5-103">By default, global tracking is enabled when you install BizTalk Server.</span></span> <span data-ttu-id="56db5-104">BizTalk 跟踪 (BizTalkDTADb) 数据库的速度增长的大小随着[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理您的系统上的数据。</span><span class="sxs-lookup"><span data-stu-id="56db5-104">The BizTalk Tracking (BizTalkDTADb) database grows in size as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes data on your system.</span></span> <span data-ttu-id="56db5-105">如果 BizTalk 跟踪数据库的大小导致磁盘性能下降，可以从跟踪数据库中清除数据。</span><span class="sxs-lookup"><span data-stu-id="56db5-105">If the size of the BizTalk Tracking database causes poor disk performance, you can purge the data from the Tracking database.</span></span> <span data-ttu-id="56db5-106">如果您遇到暂时解决通过清除 BizTalk 跟踪数据库的性能问题，并且你想要配置 BizTalk，不再收集跟踪信息，你可能想要考虑禁用全局跟踪。</span><span class="sxs-lookup"><span data-stu-id="56db5-106">If you are having performance issues that are momentarily addressed by purging the BizTalk tracking database, and you want to configure BizTalk to no longer collect tracking information, you may want to consider turning off global tracking.</span></span>  
  
 <span data-ttu-id="56db5-107">务必了解，关闭全局跟踪会禁用整个的跟踪侦听器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。</span><span class="sxs-lookup"><span data-stu-id="56db5-107">It is important to understand that turning off global tracking disables the tracking interceptors for the entire [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="56db5-108">这意味着 BizTalk 将不跟踪其跟踪表中的事件。</span><span class="sxs-lookup"><span data-stu-id="56db5-108">This means that BizTalk will not track events in its tracking tables.</span></span> <span data-ttu-id="56db5-109">或者，你可以关闭对各个事件的跟踪。</span><span class="sxs-lookup"><span data-stu-id="56db5-109">Alternatively, you can turn off tracking for individual events.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56db5-110">如果使用业务活动监视 (BAM)，您应维护专用的跟踪主机，即使禁用全局跟踪。</span><span class="sxs-lookup"><span data-stu-id="56db5-110">If you are using Business Activity Monitoring (BAM), you should maintain a dedicated tracking host, even if you disable global tracking.</span></span> <span data-ttu-id="56db5-111">这是因为 BAM 事件会使用跟踪数据解码服务 (TDDS)。</span><span class="sxs-lookup"><span data-stu-id="56db5-111">This is because BAM events use the Tracking Data Decode Service (TDDS).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="56db5-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="56db5-112">Prerequisites</span></span>  
 <span data-ttu-id="56db5-113">您必须是 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="56db5-113">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-turn-off-global-tracking-sql-server-2008"></a><span data-ttu-id="56db5-114">若要关闭全局跟踪 (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="56db5-114">To turn off global tracking (SQL Server 2008)</span></span>  
  
1. <span data-ttu-id="56db5-115">在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL server，单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="56db5-115">On the SQL server that hosts the BizTalk Tracking (BizTalkDTADb) database, click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="56db5-116">在中**连接到服务器**对话框中，验证服务器名称和身份验证，然后单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="56db5-116">In the **Connect to Server** dialog box, verify the server name and authentication, and then click **Connect**.</span></span>  
  
3. <span data-ttu-id="56db5-117">在 Microsoft SQL Server Management Studio，在**对象资源管理器**，展开\<*计算机名称*\>，展开**数据库**，展开**BizTalkMgmtDb**，展开**表**，右键单击**adm_Group**，然后单击**打开表**。</span><span class="sxs-lookup"><span data-stu-id="56db5-117">In Microsoft SQL Server Management Studio, in **Object Explorer**, expand \<*computer name*\>, expand **Databases**, expand **BizTalkMgmtDb**, expand **Tables**, right-click **adm_Group**, and then click **Open Table**.</span></span>  
  
4. <span data-ttu-id="56db5-118">在表查看器中，水平滚动直至找到**GlobalTrackingOption**。</span><span class="sxs-lookup"><span data-stu-id="56db5-118">In the table viewer, scroll horizontally until you find **GlobalTrackingOption**.</span></span>  
  
5. <span data-ttu-id="56db5-119">在中**GlobalTrackingOption**列中，将值从 1 更改为 0，若要关闭此功能，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="56db5-119">In the **GlobalTrackingOption** column, change the value from 1 to 0, to turn off this feature, and then press ENTER.</span></span>  
  
6. <span data-ttu-id="56db5-120">关闭 Microsoft SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="56db5-120">Close Microsoft SQL Server Management Studio.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="56db5-121">您必须重新启动 BizTalk 主机的更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="56db5-121">You must restart your BizTalk hosts for the change to take effect.</span></span>  
  
7. <span data-ttu-id="56db5-122">单击**启动**，单击**程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="56db5-122">Click **Start**, click **Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
8. <span data-ttu-id="56db5-123">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="56db5-123">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span>  
  
9. <span data-ttu-id="56db5-124">在细节窗格中，右键单击每个主机，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="56db5-124">In the details pane, right-click each host, and then click **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56db5-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="56db5-125">See Also</span></span>  
 <span data-ttu-id="56db5-126">[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="56db5-126">[Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span></span>  
 <span data-ttu-id="56db5-127">[如何从 BizTalk 跟踪数据库中清除数据](../core/how-to-purge-data-from-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="56db5-127">[How to Purge Data from the BizTalk Tracking Database](../core/how-to-purge-data-from-the-biztalk-tracking-database.md) </span></span>  
 [<span data-ttu-id="56db5-128">如何从 BizTalk 跟踪数据库中手动清除数据</span><span class="sxs-lookup"><span data-stu-id="56db5-128">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)