---
title: 如何添加事务 |Microsoft 文档
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
ms.openlocfilehash: 24c67a9c76ae87f2355bb0ea4638d3bd156cda6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246813"
---
# <a name="how-to-add-a-transaction"></a><span data-ttu-id="4bb10-102">如何添加事务</span><span class="sxs-lookup"><span data-stu-id="4bb10-102">How to Add a Transaction</span></span>
<span data-ttu-id="4bb10-103">请按照以下步骤添加事务。</span><span class="sxs-lookup"><span data-stu-id="4bb10-103">Follow these steps to add a transaction.</span></span>  
  
### <a name="to-add-a-transaction"></a><span data-ttu-id="4bb10-104">添加事务</span><span class="sxs-lookup"><span data-stu-id="4bb10-104">To add a transaction</span></span>  
  
1.  <span data-ttu-id="4bb10-105">单击**事务**选项卡。</span><span class="sxs-lookup"><span data-stu-id="4bb10-105">Click the **Transactions** tab.</span></span>  
  
2.  <span data-ttu-id="4bb10-106">单击**添加事务**。</span><span class="sxs-lookup"><span data-stu-id="4bb10-106">Click **Add Transaction**.</span></span>  
  
3.  <span data-ttu-id="4bb10-107">单击**添加新值**。</span><span class="sxs-lookup"><span data-stu-id="4bb10-107">Click **Add a New Value**.</span></span> <span data-ttu-id="4bb10-108">输入以下信息，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="4bb10-108">Enter the following information, and then click **Add**.</span></span>  
  
    1.  <span data-ttu-id="4bb10-109">**节点名称：** 验证，这是**MSEXTERNAL**。</span><span class="sxs-lookup"><span data-stu-id="4bb10-109">**Node Name:** Verify that this is **MSEXTERNAL**.</span></span>  
  
    2.  <span data-ttu-id="4bb10-110">**事务类型：** 验证，这是**出站异步**。</span><span class="sxs-lookup"><span data-stu-id="4bb10-110">**Transaction Type:** Verify that this is **Outbound Asynchronous**.</span></span>  
  
    3.  <span data-ttu-id="4bb10-111">**请求消息：** 输入`LOCATION_SYNC`。</span><span class="sxs-lookup"><span data-stu-id="4bb10-111">**Request Message:** Enter `LOCATION_SYNC`.</span></span>  
  
    4.  <span data-ttu-id="4bb10-112">**请求消息版本：** 输入`VERSION_1`。</span><span class="sxs-lookup"><span data-stu-id="4bb10-112">**Request Message Version:** Enter `VERSION_1`.</span></span>  
  
     ![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")  
  
4.  <span data-ttu-id="4bb10-113">上**事务详细信息**选项卡上，验证以下设置：</span><span class="sxs-lookup"><span data-stu-id="4bb10-113">On the **Transaction Detail** tab, verify the following settings:</span></span>  
  
    1.  <span data-ttu-id="4bb10-114">**状态：** 活动。</span><span class="sxs-lookup"><span data-stu-id="4bb10-114">**Status:** Active.</span></span>  
  
    2.  <span data-ttu-id="4bb10-115">**路由：** 隐式。</span><span class="sxs-lookup"><span data-stu-id="4bb10-115">**Routing:** Implicit.</span></span>  
  
     ![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")  
  
5.  <span data-ttu-id="4bb10-116">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="4bb10-116">Click **Save**.</span></span>  
  
6.  <span data-ttu-id="4bb10-117">单击**返回到事务列表**链接。</span><span class="sxs-lookup"><span data-stu-id="4bb10-117">Click the **Return to Transaction List** link.</span></span>  
  
     <span data-ttu-id="4bb10-118">事务会出现在事务列表中。</span><span class="sxs-lookup"><span data-stu-id="4bb10-118">The transaction appears in the list of transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb10-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bb10-119">See Also</span></span>  
 [<span data-ttu-id="4bb10-120">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="4bb10-120">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)