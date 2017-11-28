---
title: "如何添加作用域形状 4 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding, Scope shapes
- Scope shape, adding
ms.assetid: 4ed56ada-a656-40b1-b34a-0c0803c01216
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a81bb85412784616d185b64ee39f1e777d19fea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="dbc73-102">如何添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="dbc73-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="dbc73-103">请按照这些步骤添加**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="dbc73-103">Follow these steps to add a **Scope** shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="dbc73-104">添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="dbc73-104">To add a scope shape</span></span>  
  
1.  <span data-ttu-id="dbc73-105">右键单击下箭头**ReceiveFromIn**端口，请指向**插入形状**，然后单击**作用域**。</span><span class="sxs-lookup"><span data-stu-id="dbc73-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     <span data-ttu-id="dbc73-106">在作用域形状中，你将可能具有错误的操作。</span><span class="sxs-lookup"><span data-stu-id="dbc73-106">In the Scope shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="dbc73-107">例如，在 SQLExecute 业务流程中添加发送、接收和发送端口。</span><span class="sxs-lookup"><span data-stu-id="dbc73-107">For example, add a send, a receive and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="dbc73-108">在此示例中，将向服务器发送消息。</span><span class="sxs-lookup"><span data-stu-id="dbc73-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="dbc73-109">服务器发出响应，</span><span class="sxs-lookup"><span data-stu-id="dbc73-109">SERVER gives a response.</span></span> <span data-ttu-id="dbc73-110">它运行业务流程的其余部分，并将返回到 OutFile 端口的信息。</span><span class="sxs-lookup"><span data-stu-id="dbc73-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="dbc73-111">在作用域形状中，设置**事务**到**无**。</span><span class="sxs-lookup"><span data-stu-id="dbc73-111">In the Scope shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="dbc73-112">在作用域形状右击并选择**新异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="dbc73-112">Right-click inside the Scope shape and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="dbc73-113">这将创建**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="dbc73-113">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="dbc73-114">如果从后端，则会发生异常，则将它捕获在**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="dbc73-114">If an exception occurs from the back-end, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="dbc73-115">在**捕获异常**块中，你必须添加的逻辑。</span><span class="sxs-lookup"><span data-stu-id="dbc73-115">In the **Catch Exception** block, you must add the logic.</span></span>  
    <span data-ttu-id="dbc73-116">必须设置的最重要逻辑是你希望收到的错误消息的类型。</span><span class="sxs-lookup"><span data-stu-id="dbc73-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc73-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbc73-117">See Also</span></span>  
 [<span data-ttu-id="dbc73-118">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="dbc73-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling4.md)