---
title: 如何添加事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, transactions
- transactions, adding
ms.assetid: 25385c20-3025-4cf1-bc1f-ef266e081bad
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3a4fcb1116e5b4a0cd3a8b62dc1283abc3215c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009966"
---
# <a name="how-to-add-a-transaction"></a><span data-ttu-id="fb307-102">如何添加事务</span><span class="sxs-lookup"><span data-stu-id="fb307-102">How to Add a Transaction</span></span>
<span data-ttu-id="fb307-103">请按照以下步骤添加事务。</span><span class="sxs-lookup"><span data-stu-id="fb307-103">Follow these steps to add a transaction.</span></span>  
  
### <a name="to-add-a-transaction"></a><span data-ttu-id="fb307-104">添加事务</span><span class="sxs-lookup"><span data-stu-id="fb307-104">To add a transaction</span></span>  
  
1. <span data-ttu-id="fb307-105">单击**事务**选项卡。</span><span class="sxs-lookup"><span data-stu-id="fb307-105">Click the **Transactions** tab.</span></span>  
  
2. <span data-ttu-id="fb307-106">单击**添加事务**。</span><span class="sxs-lookup"><span data-stu-id="fb307-106">Click **Add Transaction**.</span></span>  
  
3. <span data-ttu-id="fb307-107">单击**添加新值**。</span><span class="sxs-lookup"><span data-stu-id="fb307-107">Click **Add a New Value**.</span></span> <span data-ttu-id="fb307-108">输入以下信息，并单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="fb307-108">Enter the following information, and then click **Add**.</span></span>  
  
   1. <span data-ttu-id="fb307-109">**节点名称：** 验证是否为**MSEXTERNAL**。</span><span class="sxs-lookup"><span data-stu-id="fb307-109">**Node Name:** Verify that this is **MSEXTERNAL**.</span></span>  
  
   2. <span data-ttu-id="fb307-110">**事务类型：** 验证是否为**出站异步**。</span><span class="sxs-lookup"><span data-stu-id="fb307-110">**Transaction Type:** Verify that this is **Outbound Asynchronous**.</span></span>  
  
   3. <span data-ttu-id="fb307-111">**请求消息：** 输入`LOCATION_SYNC`。</span><span class="sxs-lookup"><span data-stu-id="fb307-111">**Request Message:** Enter `LOCATION_SYNC`.</span></span>  
  
   4. <span data-ttu-id="fb307-112">**请求消息版本：** 输入`VERSION_1`。</span><span class="sxs-lookup"><span data-stu-id="fb307-112">**Request Message Version:** Enter `VERSION_1`.</span></span>  
  
      <span data-ttu-id="fb307-113">![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")</span><span class="sxs-lookup"><span data-stu-id="fb307-113">![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")</span></span>  
  
4. <span data-ttu-id="fb307-114">上**交易详情**选项卡上，验证以下设置：</span><span class="sxs-lookup"><span data-stu-id="fb307-114">On the **Transaction Detail** tab, verify the following settings:</span></span>  
  
   1. <span data-ttu-id="fb307-115">**状态：** 活动。</span><span class="sxs-lookup"><span data-stu-id="fb307-115">**Status:** Active.</span></span>  
  
   2. <span data-ttu-id="fb307-116">**路由：** 隐式。</span><span class="sxs-lookup"><span data-stu-id="fb307-116">**Routing:** Implicit.</span></span>  
  
      <span data-ttu-id="fb307-117">![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")</span><span class="sxs-lookup"><span data-stu-id="fb307-117">![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")</span></span>  
  
5. <span data-ttu-id="fb307-118">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="fb307-118">Click **Save**.</span></span>  
  
6. <span data-ttu-id="fb307-119">单击**返回到事务列表**链接。</span><span class="sxs-lookup"><span data-stu-id="fb307-119">Click the **Return to Transaction List** link.</span></span>  
  
    <span data-ttu-id="fb307-120">事务会出现在事务列表中。</span><span class="sxs-lookup"><span data-stu-id="fb307-120">The transaction appears in the list of transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb307-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb307-121">See Also</span></span>  
 [<span data-ttu-id="fb307-122">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="fb307-122">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)