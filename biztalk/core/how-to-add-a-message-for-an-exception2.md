---
title: "如何将消息添加 Exception2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- messages, exceptions
- exception handling, adding messages
- fault messages, adding
ms.assetid: 9d8a3801-78cd-4c18-8deb-3fbe4a49a2f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b2c314684094e73cb6d663bcf2183ffc3eccae5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-message-for-an-exception"></a><span data-ttu-id="28f21-102">如何将消息添加到为异常</span><span class="sxs-lookup"><span data-stu-id="28f21-102">How to Add a Message for an Exception</span></span>
<span data-ttu-id="28f21-103">当你首次创建到后端系统的端口时，它包含请求和响应。</span><span class="sxs-lookup"><span data-stu-id="28f21-103">When you first create a port to the back-end system, it contains a request and a response.</span></span> <span data-ttu-id="28f21-104">您必须添加一个信息，以便您可以将其分配给故障。</span><span class="sxs-lookup"><span data-stu-id="28f21-104">You must add a message so that you can assign it to the fault.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="28f21-105">添加错误消息</span><span class="sxs-lookup"><span data-stu-id="28f21-105">To add a fault message</span></span>  
  
1.  <span data-ttu-id="28f21-106">在**业务流程视图**窗口中，右键单击**消息**，然后选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="28f21-106">In the **Orchestration View** window, right-click **Messages**, and then select **New Message**.</span></span>  
  
     <span data-ttu-id="28f21-107">由此将创建 Message_3，您可将其明确分配给该错误。</span><span class="sxs-lookup"><span data-stu-id="28f21-107">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="28f21-108">右键单击**Message_3**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="28f21-108">Right-click **Message_3**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="28f21-109">设置**消息类型**，如下所示： 选择**.NET 类**，然后选择**系统、 字符串**</span><span class="sxs-lookup"><span data-stu-id="28f21-109">Set the **Message Type** as follows: select **.NET Classes**, and then select **System,String**</span></span>  
  
 ![](../core/media/jdeoneworld-03-addscope.gif "JdeOneWorld_03_addscope")  
  
## <a name="see-also"></a><span data-ttu-id="28f21-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28f21-110">See Also</span></span>  
 [<span data-ttu-id="28f21-111">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="28f21-111">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)