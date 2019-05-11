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
# <a name="lesson-2-receive-and-filter-notifications"></a>第 2 课：接收和筛选通知
在本课中，在开始创建业务流程接收到的更改通知**员工**表。 业务流程收到通知后，它将提取的通知和通知类型是否为插入操作上的类型**员工**表中，将"if"条件用于执行后续任务。 在本课中，将执行以下任务：  
  
1.  添加一个单向接收端口和一个**接收**形状添加到业务流程，以接收通知消息。  
  
2.  添加**表达式**包含 xpath 查询来提取的通知类型的形状。  
  
3.  已知的通知类型后，添加筛选器向业务流程通过包括**判定**形状。 此形状决定是否通知是插入通知，然后执行后续操作。 如果该通知不用于插入操作，业务流程不会执行任何操作。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：将业务流程形状添加到接收通知](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)  
  
-   [步骤 2：从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)  
  
-   [步骤 3：为插入通知添加筛选器](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)