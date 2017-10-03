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
# <a name="lesson-2-receive-and-filter-notifications"></a>第 2 课： 接收和筛选器通知
在本课程中，在开始创建业务流程，它接收的更改通知**员工**表。 业务流程收到通知后，它将提取的通知和通知类型是否为插入操作上类型**员工**表，"if"条件用于执行后续的任务。 在本课程中，你将执行以下任务：  
  
1.  添加单向接收端口和**接收**形状上的与业务流程，用于接收通知消息。  
  
2.  添加**表达式**包含 xpath 查询以提取通知的类型的形状。  
  
3.  已知的通知类型后，通过来添加筛选器业务流程包括**确定**形状。 此形状决定是否通知用于进行插入通知，然后执行后续操作。 如果通知不适用于插入操作，业务流程不执行任何操作。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 添加业务流程形状可以接收通知](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)  
  
-   [步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)  
  
-   [步骤 3： 添加筛选器插入通知](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)