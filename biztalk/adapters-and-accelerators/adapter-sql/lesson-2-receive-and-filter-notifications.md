---
title: "第 2 课： 接收和筛选器通知 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5ec679c-1c67-4bf4-aa88-0787373343f5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f28d0479510078b3717d68f99976808ee19aa7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-receive-and-filter-notifications"></a><span data-ttu-id="5c921-102">第 2 课： 接收和筛选器通知</span><span class="sxs-lookup"><span data-stu-id="5c921-102">Lesson 2: Receive and Filter Notifications</span></span>
<span data-ttu-id="5c921-103">在本课程中，在开始创建业务流程，它接收的更改通知**员工**表。</span><span class="sxs-lookup"><span data-stu-id="5c921-103">In this lesson, you start creating an orchestration that receives notifications for changes to the **Employee** table.</span></span> <span data-ttu-id="5c921-104">业务流程收到通知后，它将提取的通知和通知类型是否为插入操作上类型**员工**表，"if"条件用于执行后续的任务。</span><span class="sxs-lookup"><span data-stu-id="5c921-104">After the orchestration receives the notification, it extracts the type of notification and if the notification type is for an Insert operation on the **Employee** table, an “if” condition is used to perform subsequent tasks.</span></span> <span data-ttu-id="5c921-105">在本课程中，你将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5c921-105">In this lesson, you will perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="5c921-106">添加单向接收端口和**接收**形状上的与业务流程，用于接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="5c921-106">Add a one-way receive port and a **Receive** shape to the orchestration to receive the notification message.</span></span>  
  
2.  <span data-ttu-id="5c921-107">添加**表达式**包含 xpath 查询以提取通知的类型的形状。</span><span class="sxs-lookup"><span data-stu-id="5c921-107">Add an **Expression** shape that contains an xpath query to extract the type of notification.</span></span>  
  
3.  <span data-ttu-id="5c921-108">已知的通知类型后，通过来添加筛选器业务流程包括**确定**形状。</span><span class="sxs-lookup"><span data-stu-id="5c921-108">After the notification type is known, add a filter to the orchestration by including a **Decide** shape.</span></span> <span data-ttu-id="5c921-109">此形状决定是否通知用于进行插入通知，然后执行后续操作。</span><span class="sxs-lookup"><span data-stu-id="5c921-109">This shape decides whether the notification is for an Insert notification and then performs subsequent operations.</span></span> <span data-ttu-id="5c921-110">如果通知不适用于插入操作，业务流程不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="5c921-110">If the notification is not for an Insert operation, the orchestration does not do anything.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c921-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="5c921-111">In This Section</span></span>  
  
-   [<span data-ttu-id="5c921-112">步骤 1： 添加业务流程形状可以接收通知</span><span class="sxs-lookup"><span data-stu-id="5c921-112">Step 1: Add Orchestration Shapes to Receive Notification</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)  
  
-   [<span data-ttu-id="5c921-113">步骤 2： 从通知消息中提取通知类型</span><span class="sxs-lookup"><span data-stu-id="5c921-113">Step 2: Extract Notification Type from Notification Message</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)  
  
-   [<span data-ttu-id="5c921-114">步骤 3： 添加筛选器插入通知</span><span class="sxs-lookup"><span data-stu-id="5c921-114">Step 3: Add a Filter for Insert Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)