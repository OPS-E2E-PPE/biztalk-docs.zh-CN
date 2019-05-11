---
title: 接收位置中断后接收 Oracle 数据库更改通知 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22ad6da2-2979-4158-b1d1-d54095223af9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b918d225dcc85cf48d805ace4700f954a8b4a808
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376233"
---
# <a name="receive-oracle-database-change-notifications-after-a-receive-location-breakdown"></a><span data-ttu-id="455f5-102">接收位置中断后接收 Oracle 数据库更改通知</span><span class="sxs-lookup"><span data-stu-id="455f5-102">Receive Oracle Database change notifications after a receive location breakdown</span></span>
<span data-ttu-id="455f5-103">请考虑必须 ACCOUNTACTIVITY 表发生更改时接收数据库更改通知消息的 BizTalk 应用程序的方案。</span><span class="sxs-lookup"><span data-stu-id="455f5-103">Consider a scenario where you have a BizTalk application that receives database change notification messages when changes are made to the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="455f5-104">如果接收位置配置的一部分的 BizTalk 应用程序细分的同时记录添加到 ACCOUNTACTIVITY 表，则收不到最近添加的记录的通知。</span><span class="sxs-lookup"><span data-stu-id="455f5-104">If the receive location configured as part of the BizTalk application breaks down, and simultaneously records are added into the ACCOUNTACTIVITY table, you will not receive notifications for the recently added records.</span></span> <span data-ttu-id="455f5-105">您还不知道当接收位置再次可用时。</span><span class="sxs-lookup"><span data-stu-id="455f5-105">You will also not know when the receive location is available again.</span></span> <span data-ttu-id="455f5-106">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开的绑定属性， **NotifyOnListenerStart**，可以配置为接收到通知，接收位置已恢复。</span><span class="sxs-lookup"><span data-stu-id="455f5-106">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes a binding property, **NotifyOnListenerStart**, that you can configure to get a notification that the receive location has recovered.</span></span> <span data-ttu-id="455f5-107">可以指定以下值： **NotifyOnListenerStart**绑定属性：</span><span class="sxs-lookup"><span data-stu-id="455f5-107">You can specify the following values for the **NotifyOnListenerStart** binding property:</span></span>  
  
- <span data-ttu-id="455f5-108">将此属性设置为 **，则返回 True**，接收通知，告知接收位置是否可用，就立即接收位置恢复。</span><span class="sxs-lookup"><span data-stu-id="455f5-108">Set this property to **True**, to receive a notification informing that the receive location is available, as soon as the receive location recovers.</span></span>  
  
- <span data-ttu-id="455f5-109">将此属性设置为**False**，以便不会收到已恢复的接收位置，接收位置恢复后通知告知。</span><span class="sxs-lookup"><span data-stu-id="455f5-109">Set this property to **False**, to not receive a notification informing that the receive location has recovered, after the receive location recovers.</span></span>  
  
  <span data-ttu-id="455f5-110">默认值是 **，则返回 True**。</span><span class="sxs-lookup"><span data-stu-id="455f5-110">Default is **True**.</span></span>  
  
## <a name="configuring-the-oracle-database-adapter-behavior"></a><span data-ttu-id="455f5-111">配置 Oracle 数据库适配器行为</span><span class="sxs-lookup"><span data-stu-id="455f5-111">Configuring the Oracle Database Adapter Behavior</span></span>  
 <span data-ttu-id="455f5-112">两种方法不需要执行任何特定的任务生成的元数据时或在配置 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="455f5-112">For either of the approaches, you do not need to perform any specific tasks while generating metadata or while configuring the BizTalk application.</span></span> <span data-ttu-id="455f5-113">只需设置**NotifyOnListenerStart**绑定属性相应地在 WCF 自定义或 Wcf-oracledb 上接收位置。</span><span class="sxs-lookup"><span data-stu-id="455f5-113">You only need to set the **NotifyOnListenerStart** binding property accordingly on the WCF-Custom or WCF-OracleDB receive location.</span></span> <span data-ttu-id="455f5-114">若要创建的 BizTalk 应用程序，必须执行一组相同的任务，如中所述[接收 Oracle 数据库更改通知以增量方式使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="455f5-114">To create the BizTalk application, you must perform the same set of tasks as described in [Receiving Oracle Database Change Notifications Incrementally Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md).</span></span> <span data-ttu-id="455f5-115">但是，在配置 BizTalk 应用程序中使用时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，可以尝试更改的值**NotifyOnListenerStart**属性绑定，请参阅在两个配置中的差异。</span><span class="sxs-lookup"><span data-stu-id="455f5-115">However, when configuring the BizTalk application using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can try changing the value of **NotifyOnListenerStart** binding property and see the difference in the two configurations.</span></span>  
  
 <span data-ttu-id="455f5-116">下图演示了如何基于的值接收通知**NotifyOnListenerStart**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="455f5-116">The following figure demonstrates how the notifications are received based on the value of the **NotifyOnListenerStart** binding property.</span></span>  
  
 <span data-ttu-id="455f5-117">![为通知配置 SQL 适配器](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")</span><span class="sxs-lookup"><span data-stu-id="455f5-117">![Configure SQL Adapter for notifications](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")</span></span>  
  
 <span data-ttu-id="455f5-118">请注意，在第一个方案中，当**NotifyOnListenerStart**设置为**True**和向下的接收位置时向数据库表中插入记录，适配器仅向你发送当接收位置出现时的通知消息。</span><span class="sxs-lookup"><span data-stu-id="455f5-118">Note that in the first scenario, when the **NotifyOnListenerStart** is set to **True** and records are inserted into the database table while the receive location was down, the adapter only sends you a notification message when the receive location comes up.</span></span> <span data-ttu-id="455f5-119">适配器不执行任何操作来处理向下的接收位置时插入的记录。</span><span class="sxs-lookup"><span data-stu-id="455f5-119">The adapter does not perform any operation to process the records that were inserted while the receive location was down.</span></span> <span data-ttu-id="455f5-120">适配器客户端必须实现相关逻辑来处理记录时已关闭的接收位置插入其应用程序中。</span><span class="sxs-lookup"><span data-stu-id="455f5-120">The adapter client must implement the relevant logic in their application to process the records that were inserted while the receive location was down.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="455f5-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="455f5-121">See Also</span></span>  
 [<span data-ttu-id="455f5-122">使用 BizTalk Server 的 Oracle 数据库更改通知的接收</span><span class="sxs-lookup"><span data-stu-id="455f5-122">Receiving Oracle Database Change Notifications Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)