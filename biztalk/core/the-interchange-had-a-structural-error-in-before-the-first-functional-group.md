---
title: "交换中有一种结构错误的第一个功能组之前 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12202148-0a32-464e-8dbd-d01b9ba530eb
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d5ab490de214f53e85ea32c1b243456f837c72e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-interchange-had-a-structural-error-in-before-the-first-functional-group"></a>交换中有一种结构错误的第一个功能组之前
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12InterchangeStructuralErrorBefore1stGroup|  
|消息正文|Id 为"{0}"，发件人 id {1} 交换，接收方 id {2} 在中之前第一个功能组的结构化错误|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于以下原因之一，导致接收管道无法处理传入的交换：  
  
-   交换的 ISA 和 IEA 段或者第一个功能组中发生结构错误，因此交换不符合适用的架构。  
  
-   未部署 X12ServiceSchema（在 BaseArtifacts.dll 中）。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   让交换的发送方更改 ISA 和/或 IEA 段或者第一个功能组，以便它符合适用的架构，然后重新发送交换。  
  
-   确保 BaseArtifacts.dll 包含 X12ServiceSchema 并且已部署。 可以通过打开 BizTalk Server 管理控制台，打开“BizTalk EDI 应用程序”节点和“架构”节点，然后验证是否列出了 X12ServiceSchema 来执行此操作。