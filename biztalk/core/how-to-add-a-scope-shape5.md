---
title: 如何添加作用域 Shape5 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, Scope shapes
- Scope shape, adding
ms.assetid: 1e16eda1-c4bd-4428-a477-78c453aeb1aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35301e9e3cd66ab26d06208501c535b73305f5a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343395"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="79245-102">如何添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="79245-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="79245-103">请按照这些步骤添加**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="79245-103">Follow these steps to add a **Scope**shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="79245-104">若要添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="79245-104">To add a Scope shape</span></span>  
  
1.  <span data-ttu-id="79245-105">右键单击下的箭头**ReceiveFromIn**端口，指向**插入形状**，然后单击**范围**。</span><span class="sxs-lookup"><span data-stu-id="79245-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     <span data-ttu-id="79245-106">在中**作用域**形状，你将可能有错误的操作设置。</span><span class="sxs-lookup"><span data-stu-id="79245-106">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="79245-107">例如，在 SQLExecute 业务流程中添加发送、 接收和发送端口。</span><span class="sxs-lookup"><span data-stu-id="79245-107">For example, add a send, a receive and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="79245-108">在此示例中，向服务器发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="79245-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="79245-109">服务器发出响应。</span><span class="sxs-lookup"><span data-stu-id="79245-109">SERVER gives a response.</span></span> <span data-ttu-id="79245-110">它运行业务流程的其余部分，并返回到 OutFile 端口返回信息。</span><span class="sxs-lookup"><span data-stu-id="79245-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="79245-111">在中**作用域**形状中，设置**事务类型**到**None**。</span><span class="sxs-lookup"><span data-stu-id="79245-111">In the **Scope** shape, set the **Transaction Type** to **None**.</span></span>  
  
3.  <span data-ttu-id="79245-112">内右击**作用域**形状，然后选择**新建异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="79245-112">Right-click inside the **Scope** shape and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="79245-113">这将创建`Catch Exception`块。</span><span class="sxs-lookup"><span data-stu-id="79245-113">This creates the `Catch Exception`block.</span></span> <span data-ttu-id="79245-114">如果从后端出现异常，则在捕获到`Catch Exception`块。</span><span class="sxs-lookup"><span data-stu-id="79245-114">If an exception occurs from the back-end, it is caught inside the `Catch Exception`block.</span></span>  
  
4.  <span data-ttu-id="79245-115">在`Catch Exception`块中，必须添加逻辑。</span><span class="sxs-lookup"><span data-stu-id="79245-115">In the `Catch Exception` block, you must add the logic.</span></span>  
  
     <span data-ttu-id="79245-116">必须设置的最重要逻辑是您希望收到的错误消息的类型。</span><span class="sxs-lookup"><span data-stu-id="79245-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79245-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="79245-117">See Also</span></span>  
 [<span data-ttu-id="79245-118">使用 BizTalk Server 的异常处理</span><span class="sxs-lookup"><span data-stu-id="79245-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)