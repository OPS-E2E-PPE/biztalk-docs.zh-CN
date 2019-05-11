---
title: 如何将消息添加为 Exception1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- messages, exceptions
- faults, adding messages
ms.assetid: e087db39-e745-47d4-a888-0b82a9f855c8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7064b77beebdbfdb0fdfc54cf3ba2daa769e08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343780"
---
# <a name="how-to-add-a-message-for-an-exception"></a><span data-ttu-id="d9184-102">如何添加异常的消息</span><span class="sxs-lookup"><span data-stu-id="d9184-102">How to Add a Message for an Exception</span></span>
<span data-ttu-id="d9184-103">以下主题介绍如何添加异常的消息。</span><span class="sxs-lookup"><span data-stu-id="d9184-103">The following topic describes how to add a message for an exception.</span></span>  
  
### <a name="to-add-a-message-for-an-exception"></a><span data-ttu-id="d9184-104">若要添加的异常消息</span><span class="sxs-lookup"><span data-stu-id="d9184-104">To add a message for an exception</span></span>  
  
1.  <span data-ttu-id="d9184-105">在中**业务流程视图**窗口中，右键单击**消息**，然后选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="d9184-105">In the **Orchestration View** window, right-click **Messages** and select **New Message**.</span></span>  
  
     <span data-ttu-id="d9184-106">这将创建 Message_3，您可以将其分配特定于该错误。</span><span class="sxs-lookup"><span data-stu-id="d9184-106">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="d9184-107">右键单击**Message_3** ，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="d9184-107">Right-click **Message_3** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="d9184-108">在中**属性**窗口中，将**消息类型**。</span><span class="sxs-lookup"><span data-stu-id="d9184-108">In the **Properties** window, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="d9184-109">选择 **.Net 类**，然后选择**SystemString**。</span><span class="sxs-lookup"><span data-stu-id="d9184-109">Select **.Net Classes**, and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9184-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9184-110">See Also</span></span>  
 [<span data-ttu-id="d9184-111">使用 BizTalk Server 的异常处理</span><span class="sxs-lookup"><span data-stu-id="d9184-111">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)