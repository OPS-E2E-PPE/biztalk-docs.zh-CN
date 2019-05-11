---
title: 使用 Oracle E-business Suite 中配置事务隔离级别和事务超时 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db3d64ad-037d-486a-bdde-45c8199613f1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df2c95ae4ecaae987f0a8e706952a7b86e36eb45
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375663"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-e-business-suite"></a><span data-ttu-id="ae968-102">使用 Oracle E-business Suite 中配置事务隔离级别和事务超时</span><span class="sxs-lookup"><span data-stu-id="ae968-102">Configure transaction isolation level and transaction timeout with Oracle E-Business Suite</span></span>
<span data-ttu-id="ae968-103">执行 （轮询和通知） 的入站的操作时使用[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，您应适当地配置事务隔离级别和事务超时值。</span><span class="sxs-lookup"><span data-stu-id="ae968-103">While performing inbound operations (Polling and Notification) using the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you should appropriately configure the transaction isolation level and the transaction timeout values.</span></span> <span data-ttu-id="ae968-104">若要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="ae968-104">To do this:</span></span>  

1. <span data-ttu-id="ae968-105">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ae968-105">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="ae968-106">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ae968-106">In the console tree, expand the **BizTalk Group**, and then expand **Applications**.</span></span>  

3. <span data-ttu-id="ae968-107">生成元数据使用后已部署的 BizTalk 应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ae968-107">Expand the BizTalk application that you have deployed after generating the metadata using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  

4. <span data-ttu-id="ae968-108">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="ae968-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

5. <span data-ttu-id="ae968-109">在中**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="ae968-109">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  

6. <span data-ttu-id="ae968-110">在左窗格中**接收端口属性**对话框中，单击**接收位置**，然后单击**新建**在右窗格中，可以定义新的接收位置。</span><span class="sxs-lookup"><span data-stu-id="ae968-110">In the left pane of the **Receive Port Properties** dialog box, click **Receive Locations**, and then click **New** in the right pane to define a new receive location.</span></span>  

7. <span data-ttu-id="ae968-111">在中**接收位置属性**对话框中，单击**WCF 自定义**中**类型**列表。</span><span class="sxs-lookup"><span data-stu-id="ae968-111">In the **Receive Location Properties** dialog box, click **WCF-Custom** in the **Type** list.</span></span>  

8. <span data-ttu-id="ae968-112">单击**配置**相邻**类型**列表。</span><span class="sxs-lookup"><span data-stu-id="ae968-112">Click **Configure** adjacent to the **Type** list.</span></span>  

9. <span data-ttu-id="ae968-113">在中**Wcf-custom 传输属性**对话框中，单击**行为**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ae968-113">In the **WCF-Custom Transport Properties** dialog box, click the **Behavior** tab.</span></span>  

10. <span data-ttu-id="ae968-114">在中**行为**列表中，右键单击**ServiceBehavior**，然后单击**将扩展添加**。</span><span class="sxs-lookup"><span data-stu-id="ae968-114">In the **Behavior** list, right-click **ServiceBehavior**, and click **Add extension**.</span></span>  

11. <span data-ttu-id="ae968-115">在中**选择行为扩展**对话框中，选择**oracleEBSAdapterInboundTransactionBehavior**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ae968-115">In the **Select Behavior Extension** dialog box, select **oracleEBSAdapterInboundTransactionBehavior**, and click **OK**.</span></span>  

12. <span data-ttu-id="ae968-116">在左窗格中**Wcf-custom 传输属性**，选择**oracleEBSAdapterInboundTransactionBehavior**服务**ServiceBehavior**。</span><span class="sxs-lookup"><span data-stu-id="ae968-116">In the left pane of the **WCF-Custom Transport Properties**, select the **oracleEBSAdapterInboundTransactionBehavior** service under **ServiceBehavior**.</span></span>  

13. <span data-ttu-id="ae968-117">在右窗格中**Wcf-custom 传输属性**，指定相应的值**transactionIsolationLevel**并**transactionTimeout**参数。</span><span class="sxs-lookup"><span data-stu-id="ae968-117">In the right pane of the **WCF-Custom Transport Properties**, specify appropriate values for the **transactionIsolationLevel** and **transactionTimeout** parameters.</span></span> <span data-ttu-id="ae968-118">您可以选择任意下列事务隔离级别：**可序列化**， **RepeatableRead**， **ReadCommitted**， **ReadUncommitted**，**快照**， **混沌测试**，并**未指定**。</span><span class="sxs-lookup"><span data-stu-id="ae968-118">You can select any of the following transaction isolation levels: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Snapshot**, **Chaos**, and **Unspecified**.</span></span> <span data-ttu-id="ae968-119">有关这些事务隔离级别的信息，请参阅**成员**在部分[ http://go.microsoft.com/fwlink/?LinkId=126983 ](http://go.microsoft.com/fwlink/?LinkId=126983)。</span><span class="sxs-lookup"><span data-stu-id="ae968-119">For information about these transaction isolation levels, see the **Members** section at [http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983).</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="ae968-120">Oracle E-business Suite 支持仅以下两个事务隔离级别：ReadCommitted 和可序列化。</span><span class="sxs-lookup"><span data-stu-id="ae968-120">Oracle E-Business Suite supports only the following two transaction isolation levels: ReadCommitted and Serializable.</span></span>  

     <span data-ttu-id="ae968-121">![设置事务隔离级别](../../adapters-and-accelerators/adapter-oracle-ebs/media/2bafbb9d-4daa-43c0-abcb-35220e6a3cb5.gif "2bafbb9d-4daa-43c0-abcb-35220e6a3cb5")</span><span class="sxs-lookup"><span data-stu-id="ae968-121">![Setting Transaction Isolation Level](../../adapters-and-accelerators/adapter-oracle-ebs/media/2bafbb9d-4daa-43c0-abcb-35220e6a3cb5.gif "2bafbb9d-4daa-43c0-abcb-35220e6a3cb5")</span></span>  

14. <span data-ttu-id="ae968-122">单击**确定**中**Wcf-custom 传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="ae968-122">Click **OK** in the **WCF-Custom Transport Properties** dialog box.</span></span>  

15. <span data-ttu-id="ae968-123">单击**确定**中打开的对话框以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ae968-123">Click **OK** in the open dialog boxes to save the changes.</span></span>
