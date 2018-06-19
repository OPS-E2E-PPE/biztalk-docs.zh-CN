---
title: 如何将消息添加 Exception1 |Microsoft 文档
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
ms.openlocfilehash: b60bfdfb222761aadd54b6c32567dfa6821355ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246589"
---
# <a name="how-to-add-a-message-for-an-exception"></a><span data-ttu-id="44396-102">如何将消息添加到为异常</span><span class="sxs-lookup"><span data-stu-id="44396-102">How to Add a Message for an Exception</span></span>
<span data-ttu-id="44396-103">以下主题介绍如何添加异常消息。</span><span class="sxs-lookup"><span data-stu-id="44396-103">The following topic describes how to add a message for an exception.</span></span>  
  
### <a name="to-add-a-message-for-an-exception"></a><span data-ttu-id="44396-104">为异常添加消息</span><span class="sxs-lookup"><span data-stu-id="44396-104">To add a message for an exception</span></span>  
  
1.  <span data-ttu-id="44396-105">在**业务流程视图**窗口中，右键单击**消息**和选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="44396-105">In the **Orchestration View** window, right-click **Messages** and select **New Message**.</span></span>  
  
     <span data-ttu-id="44396-106">由此将创建 Message_3，您可将其明确分配给该错误。</span><span class="sxs-lookup"><span data-stu-id="44396-106">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="44396-107">右键单击**Message_3**和选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="44396-107">Right-click **Message_3** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="44396-108">在**属性**窗口中，设置**消息类型**。</span><span class="sxs-lookup"><span data-stu-id="44396-108">In the **Properties** window, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="44396-109">选择 **.Net 类**，然后选择**SystemString**。</span><span class="sxs-lookup"><span data-stu-id="44396-109">Select **.Net Classes**, and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44396-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44396-110">See Also</span></span>  
 [<span data-ttu-id="44396-111">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="44396-111">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)