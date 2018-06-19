---
title: 如何添加错误 Message2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fault messages, adding
- messages, fault messages
ms.assetid: 8f1b40af-2c75-4167-8b62-a86b791907c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dee8a1fca0e30a96b6a714b5c717c0638bc8144
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246453"
---
# <a name="how-to-add-a-fault-message"></a><span data-ttu-id="871e3-102">如何添加错误消息</span><span class="sxs-lookup"><span data-stu-id="871e3-102">How to Add a Fault Message</span></span>
<span data-ttu-id="871e3-103">创建通向后端系统的端口时，该端口中包含了请求和响应通信。</span><span class="sxs-lookup"><span data-stu-id="871e3-103">When you create a port to the back-end system, it contains a request and a response.</span></span> <span data-ttu-id="871e3-104">您必须添加一个信息，以便您可以将其分配给故障。</span><span class="sxs-lookup"><span data-stu-id="871e3-104">You must add a message so that you can assign it to the fault.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="871e3-105">添加错误消息</span><span class="sxs-lookup"><span data-stu-id="871e3-105">To add a fault message</span></span>  
  
1.  <span data-ttu-id="871e3-106">在**业务流程视图**窗口中，右键单击**消息**，然后选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="871e3-106">In the **Orchestration View** window, right-click **Messages**, and select **New Message**.</span></span>  
  
     <span data-ttu-id="871e3-107">由此将创建 Message_3，您可将其明确分配给该错误。</span><span class="sxs-lookup"><span data-stu-id="871e3-107">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="871e3-108">右键单击 Message_3，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="871e3-108">Right-click Message_3, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="871e3-109">在**属性**对话框中，设置**消息类型**。</span><span class="sxs-lookup"><span data-stu-id="871e3-109">In the **Properties** dialog box, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="871e3-110">选择 **.NET 类**，然后选择**SystemString**。</span><span class="sxs-lookup"><span data-stu-id="871e3-110">Select **.NET Classes** and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="871e3-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="871e3-111">See Also</span></span>  
 [<span data-ttu-id="871e3-112">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="871e3-112">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)