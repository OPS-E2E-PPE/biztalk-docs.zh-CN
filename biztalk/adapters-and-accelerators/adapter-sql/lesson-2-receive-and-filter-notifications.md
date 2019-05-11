---
title: 第 2 课：接收和筛选通知 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5ec679c-1c67-4bf4-aa88-0787373343f5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d2814065e188f72d42b444e04ad11ace0194d6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368871"
---
# <a name="lesson-2-receive-and-filter-notifications"></a><span data-ttu-id="1f7de-102">第 2 课：接收和筛选通知</span><span class="sxs-lookup"><span data-stu-id="1f7de-102">Lesson 2: Receive and Filter Notifications</span></span>
<span data-ttu-id="1f7de-103">在本课中，在开始创建业务流程接收到的更改通知**员工**表。</span><span class="sxs-lookup"><span data-stu-id="1f7de-103">In this lesson, you start creating an orchestration that receives notifications for changes to the **Employee** table.</span></span> <span data-ttu-id="1f7de-104">业务流程收到通知后，它将提取的通知和通知类型是否为插入操作上的类型**员工**表中，将"if"条件用于执行后续任务。</span><span class="sxs-lookup"><span data-stu-id="1f7de-104">After the orchestration receives the notification, it extracts the type of notification and if the notification type is for an Insert operation on the **Employee** table, an “if” condition is used to perform subsequent tasks.</span></span> <span data-ttu-id="1f7de-105">在本课中，将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="1f7de-105">In this lesson, you will perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="1f7de-106">添加一个单向接收端口和一个**接收**形状添加到业务流程，以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="1f7de-106">Add a one-way receive port and a **Receive** shape to the orchestration to receive the notification message.</span></span>  
  
2.  <span data-ttu-id="1f7de-107">添加**表达式**包含 xpath 查询来提取的通知类型的形状。</span><span class="sxs-lookup"><span data-stu-id="1f7de-107">Add an **Expression** shape that contains an xpath query to extract the type of notification.</span></span>  
  
3.  <span data-ttu-id="1f7de-108">已知的通知类型后，添加筛选器向业务流程通过包括**判定**形状。</span><span class="sxs-lookup"><span data-stu-id="1f7de-108">After the notification type is known, add a filter to the orchestration by including a **Decide** shape.</span></span> <span data-ttu-id="1f7de-109">此形状决定是否通知是插入通知，然后执行后续操作。</span><span class="sxs-lookup"><span data-stu-id="1f7de-109">This shape decides whether the notification is for an Insert notification and then performs subsequent operations.</span></span> <span data-ttu-id="1f7de-110">如果该通知不用于插入操作，业务流程不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="1f7de-110">If the notification is not for an Insert operation, the orchestration does not do anything.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f7de-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="1f7de-111">In This Section</span></span>  
  
-   [<span data-ttu-id="1f7de-112">步骤 1：将业务流程形状添加到接收通知</span><span class="sxs-lookup"><span data-stu-id="1f7de-112">Step 1: Add Orchestration Shapes to Receive Notification</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)  
  
-   [<span data-ttu-id="1f7de-113">步骤 2：从通知消息中提取通知类型</span><span class="sxs-lookup"><span data-stu-id="1f7de-113">Step 2: Extract Notification Type from Notification Message</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)  
  
-   [<span data-ttu-id="1f7de-114">步骤 3：为插入通知添加筛选器</span><span class="sxs-lookup"><span data-stu-id="1f7de-114">Step 3: Add a Filter for Insert Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)