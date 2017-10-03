---
title: "使用 SQL 配置事务隔离级别和事务超时 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55355272-60c0-49e4-b37e-9198458ab305
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e75d63118c24602439434c9c7ba281fa9cbc7805
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-sql"></a><span data-ttu-id="09b02-102">使用 SQL 配置事务隔离级别和事务超时</span><span class="sxs-lookup"><span data-stu-id="09b02-102">Configure Transaction Isolation Level and Transaction Timeout with SQL</span></span>
<span data-ttu-id="09b02-103">执行 （轮询和通知） 的入站的操作时使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你应适当地配置事务的隔离级别和事务超时值。</span><span class="sxs-lookup"><span data-stu-id="09b02-103">While performing inbound operations (Polling and Notification) using the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you should appropriately configure the transaction isolation level and the transaction timeout values.</span></span> <span data-ttu-id="09b02-104">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="09b02-104">To do this:</span></span>  
  
1.  <span data-ttu-id="09b02-105">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="09b02-105">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="09b02-106">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="09b02-106">In the console tree, expand the **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="09b02-107">展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="09b02-107">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
4.  <span data-ttu-id="09b02-108">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="09b02-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
5.  <span data-ttu-id="09b02-109">在**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="09b02-109">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="09b02-110">在左窗格中**接收端口属性**对话框中，单击**接收位置**，然后单击**新建**在右窗格中可以定义新接收位置。</span><span class="sxs-lookup"><span data-stu-id="09b02-110">In the left pane of the **Receive Port Properties** dialog box, click **Receive Locations**, and then click **New** in the right pane to define a new receive location.</span></span>  
  
7.  <span data-ttu-id="09b02-111">在**接收位置属性**对话框中，单击**WCF 自定义**中**类型**列表。</span><span class="sxs-lookup"><span data-stu-id="09b02-111">In the **Receive Location Properties** dialog box, click **WCF-Custom** in the **Type** list.</span></span>  
  
8.  <span data-ttu-id="09b02-112">单击**配置**靠近**类型**列表。</span><span class="sxs-lookup"><span data-stu-id="09b02-112">Click **Configure** adjacent to the **Type** list.</span></span>  
  
9. <span data-ttu-id="09b02-113">在**WCF 自定义传输属性**对话框中，单击**行为**选项卡。</span><span class="sxs-lookup"><span data-stu-id="09b02-113">In the **WCF-Custom Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
10. <span data-ttu-id="09b02-114">在**行为**列表中，右键单击**ServiceBehavior**，然后单击**将扩展添加**。</span><span class="sxs-lookup"><span data-stu-id="09b02-114">In the **Behavior** list, right-click **ServiceBehavior**, and click **Add extension**.</span></span>  
  
11. <span data-ttu-id="09b02-115">在**选择行为扩展**对话框中，选择**sqlAdapterInboundTransactionBehavior**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="09b02-115">In the **Select Behavior Extension** dialog box, select **sqlAdapterInboundTransactionBehavior**, and click **OK**.</span></span>  
  
12. <span data-ttu-id="09b02-116">在左窗格中**WCF 自定义传输属性**，选择**sqlAdapterInboundTransactionBehavior**服务下**ServiceBehavior**。</span><span class="sxs-lookup"><span data-stu-id="09b02-116">In the left pane of the **WCF-Custom Transport Properties**, select the **sqlAdapterInboundTransactionBehavior** service under **ServiceBehavior**.</span></span> <span data-ttu-id="09b02-117">用于接收 （入站的操作消息），用户可以使用 sqlAdapterInboundTransactionBehavior 控制的隔离级别和默认值是**ReadCommitted**。</span><span class="sxs-lookup"><span data-stu-id="09b02-117">For receive (Inbound operation message), one can use the sqlAdapterInboundTransactionBehavior to control the isolation level and the default value is **ReadCommitted**.</span></span>  
  
13. <span data-ttu-id="09b02-118">在右窗格中**WCF 自定义传输属性**，指定适当的值为**transactionIsolationLevel**和**transactionTimeout**参数。</span><span class="sxs-lookup"><span data-stu-id="09b02-118">In the right pane of the **WCF-Custom Transport Properties**, specify appropriate values for the **transactionIsolationLevel** and **transactionTimeout** parameters.</span></span> <span data-ttu-id="09b02-119">您可以选择任一以下事务隔离级别： **Serializable**， **RepeatableRead**， **ReadCommitted**， **ReadUncommitted**，**快照**，**混沌**，和**未指定**。</span><span class="sxs-lookup"><span data-stu-id="09b02-119">You can select any of the following transaction isolation levels: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Snapshot**, **Chaos**, and **Unspecified**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="09b02-120">事务隔离级别的默认值是**Serializable**为入站和出站操作 WCF SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="09b02-120">The default value of Transaction Isolation Level is **Serializable** for the WCF-SQL adapter for both inbound and outbound operations.</span></span> <span data-ttu-id="09b02-121">有关这些事务隔离级别的信息，请参阅**成员**部分[隔离级别枚举](http://go.microsoft.com/fwlink/?LinkId=126983)(http://go.microsoft.com/fwlink/?LinkId=126983)。</span><span class="sxs-lookup"><span data-stu-id="09b02-121">For information about these transaction isolation levels, see the **Members** section at [Isolation Level Enumeration](http://go.microsoft.com/fwlink/?LinkId=126983) (http://go.microsoft.com/fwlink/?LinkId=126983).</span></span>  
  
     <span data-ttu-id="09b02-122">![将事务隔离级别，设置](../../adapters-and-accelerators/adapter-sql/media/b39c180e-ca9f-48ca-9550-f4837826d00e.gif "b39c180e-ca9f-48ca-9550-f4837826d00e")</span><span class="sxs-lookup"><span data-stu-id="09b02-122">![Setting Transaction Isolation Level](../../adapters-and-accelerators/adapter-sql/media/b39c180e-ca9f-48ca-9550-f4837826d00e.gif "b39c180e-ca9f-48ca-9550-f4837826d00e")</span></span>  
  
14. <span data-ttu-id="09b02-123">单击**确定**中**WCF 自定义传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="09b02-123">Click **OK** in the **WCF-Custom Transport Properties** dialog box.</span></span>  
  
15. <span data-ttu-id="09b02-124">单击**确定**中打开对话框以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="09b02-124">Click **OK** in the open dialog boxes to save the changes.</span></span>