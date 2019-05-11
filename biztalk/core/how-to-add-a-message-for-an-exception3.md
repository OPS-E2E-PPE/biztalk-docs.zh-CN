---
title: 如何将消息添加为 Exception3 |Microsoft Docs
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
ms.assetid: 920f9b4d-e002-457c-ad44-f41bf2600e06
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23c2f0fd7b761bb5eeaa3a9ec276de2f2d1ef897
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343788"
---
# <a name="how-to-add-a-message-for-an-exception"></a><span data-ttu-id="42929-102">如何添加异常的消息</span><span class="sxs-lookup"><span data-stu-id="42929-102">How to Add a Message for an Exception</span></span>
<span data-ttu-id="42929-103">请按照这些步骤添加错误消息。</span><span class="sxs-lookup"><span data-stu-id="42929-103">Follow these steps to add a fault with a message.</span></span>  
  
### <a name="to-add-a-message-for-an-exception"></a><span data-ttu-id="42929-104">若要添加的异常消息</span><span class="sxs-lookup"><span data-stu-id="42929-104">To add a message for an exception</span></span>  
  
1.  <span data-ttu-id="42929-105">在中**业务流程视图**窗口中，右键单击**消息**，然后选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="42929-105">In the **Orchestration View** window, right-click **Messages** and select **New Message**.</span></span>  
  
     <span data-ttu-id="42929-106">这将创建 Message_3，您可以将其分配特定于该错误。</span><span class="sxs-lookup"><span data-stu-id="42929-106">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="42929-107">右键单击**Message_3** ，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="42929-107">Right-click **Message_3** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="42929-108">在中**属性**对话框中，将**消息类型**。</span><span class="sxs-lookup"><span data-stu-id="42929-108">In the **Properties** dialog box, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="42929-109">选择 **.NET 类**，然后选择**SystemString**。</span><span class="sxs-lookup"><span data-stu-id="42929-109">Select **.NET Classes**, and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42929-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="42929-110">See Also</span></span>  
 [<span data-ttu-id="42929-111">使用 BizTalk Server 的异常处理</span><span class="sxs-lookup"><span data-stu-id="42929-111">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling4.md)