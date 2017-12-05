---
title: "如何关闭全局跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eae3059a-cbdd-47c4-84cd-edfb5480b9fa
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c143d19e6071ca4f9ce488ae936082db86dc84dc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-turn-off-global-tracking"></a><span data-ttu-id="86448-102">如何关闭全局跟踪</span><span class="sxs-lookup"><span data-stu-id="86448-102">How to Turn Off Global Tracking</span></span>
<span data-ttu-id="86448-103">默认情况下，安装 BizTalk Server 时，被启用全局跟踪。</span><span class="sxs-lookup"><span data-stu-id="86448-103">By default, global tracking is enabled when you install BizTalk Server.</span></span> <span data-ttu-id="86448-104">BizTalk 跟踪 (BizTalkDTADb) 数据库的大小随着 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 处理系统上的数据而增大。</span><span class="sxs-lookup"><span data-stu-id="86448-104">The BizTalk Tracking (BizTalkDTADb) database grows in size as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes data on your system.</span></span> <span data-ttu-id="86448-105">如果 BizTalk 跟踪数据库的大小导致磁盘性能下降，则可以从跟踪数据库中清除数据。</span><span class="sxs-lookup"><span data-stu-id="86448-105">If the size of the BizTalk Tracking database causes poor disk performance, you can purge the data from the Tracking database.</span></span> <span data-ttu-id="86448-106">如果存在通过清除 BizTalk 跟踪数据库暂时得以解决的性能问题，并且希望对 BizTalk 进行控制以便不再收集跟踪信息，则可能要考虑禁用全局跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="86448-106">If you are having performance issues that are momentarily addressed by purging the BizTalk tracking database, and you want to configure BizTalk to no longer collect tracking information, you may want to consider turning off global tracking.</span></span>  
  
 <span data-ttu-id="86448-107">很重要的一点是，关闭全局跟踪会禁用整个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="86448-107">It is important to understand that turning off global tracking disables the tracking interceptors for the entire [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="86448-108">这意味着 BizTalk 将不跟踪其跟踪表中的事件。</span><span class="sxs-lookup"><span data-stu-id="86448-108">This means that BizTalk will not track events in its tracking tables.</span></span> <span data-ttu-id="86448-109">或者，您可以针对单个事件关闭跟踪。</span><span class="sxs-lookup"><span data-stu-id="86448-109">Alternatively, you can turn off tracking for individual events.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86448-110">如果正在使用业务活动监视 (BAM)，则即使禁用全局跟踪，也应保留一个专门的跟踪主机。</span><span class="sxs-lookup"><span data-stu-id="86448-110">If you are using Business Activity Monitoring (BAM), you should maintain a dedicated tracking host, even if you disable global tracking.</span></span> <span data-ttu-id="86448-111">这是由于 BAM 事件会使用跟踪数据解码服务 (TDDS)。</span><span class="sxs-lookup"><span data-stu-id="86448-111">This is because BAM events use the Tracking Data Decode Service (TDDS).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="86448-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="86448-112">Prerequisites</span></span>  
 <span data-ttu-id="86448-113">若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="86448-113">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-turn-off-global-tracking-sql-server-2008"></a><span data-ttu-id="86448-114">若要关闭全局跟踪 (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="86448-114">To turn off global tracking (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="86448-115">在 SQL 服务器上承载 BizTalk 跟踪 (BizTalkDTADb) 数据库，单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="86448-115">On the SQL server that hosts the BizTalk Tracking (BizTalkDTADb) database, click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="86448-116">在**连接到服务器**对话框中，验证服务器名称和身份验证，，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="86448-116">In the **Connect to Server** dialog box, verify the server name and authentication, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="86448-117">在 Microsoft SQL Server Management Studio，在**对象资源管理器**，展开\<*计算机名称*\>，展开**数据库**，展开**BizTalkMgmtDb**，展开**表**，右键单击**adm_Group**，然后单击**打开表**。</span><span class="sxs-lookup"><span data-stu-id="86448-117">In Microsoft SQL Server Management Studio, in **Object Explorer**, expand \<*computer name*\>, expand **Databases**, expand **BizTalkMgmtDb**, expand **Tables**, right-click **adm_Group**, and then click **Open Table**.</span></span>  
  
4.  <span data-ttu-id="86448-118">在表查看器中，水平滚动直到找到**GlobalTrackingOption**。</span><span class="sxs-lookup"><span data-stu-id="86448-118">In the table viewer, scroll horizontally until you find **GlobalTrackingOption**.</span></span>  
  
5.  <span data-ttu-id="86448-119">在**GlobalTrackingOption**列中，将值从 1 更改为 0，若要关闭此功能，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="86448-119">In the **GlobalTrackingOption** column, change the value from 1 to 0, to turn off this feature, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="86448-120">关闭 Microsoft SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="86448-120">Close Microsoft SQL Server Management Studio.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="86448-121">必须重新启动 BizTalk 主机，此更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="86448-121">You must restart your BizTalk hosts for the change to take effect.</span></span>  
  
7.  <span data-ttu-id="86448-122">单击**启动**，单击**程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="86448-122">Click **Start**, click **Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
8.  <span data-ttu-id="86448-123">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**托管实例**。</span><span class="sxs-lookup"><span data-stu-id="86448-123">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span>  
  
9. <span data-ttu-id="86448-124">在细节窗格中，右键单击每个主机，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="86448-124">In the details pane, right-click each host, and then click **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86448-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86448-125">See Also</span></span>  
 <span data-ttu-id="86448-126">[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="86448-126">[Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span></span>  
 <span data-ttu-id="86448-127">[如何从 BizTalk 跟踪数据库清除数据](../core/how-to-purge-data-from-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="86448-127">[How to Purge Data from the BizTalk Tracking Database](../core/how-to-purge-data-from-the-biztalk-tracking-database.md) </span></span>  
 [<span data-ttu-id="86448-128">如何从 BizTalk 跟踪数据库手动清除数据</span><span class="sxs-lookup"><span data-stu-id="86448-128">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)