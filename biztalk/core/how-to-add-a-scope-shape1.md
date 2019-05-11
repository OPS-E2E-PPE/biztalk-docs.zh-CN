---
title: 如何添加作用域形状 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- Scope shapes, Catch Exception blocks
- Catch Exception blocks, Scope shapes
- adding, Scope shapes
ms.assetid: dfe039d1-4c4a-4e21-ae03-7ca534aafec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faabba82196f7e595427f36c0d07d66769bafd18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387318"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="84088-102">如何添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="84088-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="84088-103">请按照这些步骤添加作用域形状。</span><span class="sxs-lookup"><span data-stu-id="84088-103">Follow these steps to add a Scope shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="84088-104">若要添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="84088-104">To add a Scope Shape</span></span>  
  
1.  <span data-ttu-id="84088-105">右键单击下的箭头**ReceiveFromIn**端口，指向**插入形状**，然后单击**范围**。</span><span class="sxs-lookup"><span data-stu-id="84088-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     <span data-ttu-id="84088-106">![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")</span><span class="sxs-lookup"><span data-stu-id="84088-106">![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")</span></span>  
  
     <span data-ttu-id="84088-107">在作用域形状中，您将可能有错误的操作。</span><span class="sxs-lookup"><span data-stu-id="84088-107">In the Scope shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="84088-108">例如，在 SQLExecute 业务流程中添加发送、 接收和发送端口。</span><span class="sxs-lookup"><span data-stu-id="84088-108">For example, add a send, a receive, and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="84088-109">在此示例中，我们正在向 DB2 发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="84088-109">In this example, we are sending a message to DB2.</span></span> <span data-ttu-id="84088-110">DB2 提供响应。</span><span class="sxs-lookup"><span data-stu-id="84088-110">DB2 gives a response.</span></span> <span data-ttu-id="84088-111">它运行业务流程的其余部分，并返回到 OutFile 端口返回信息。</span><span class="sxs-lookup"><span data-stu-id="84088-111">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="84088-112">在作用域形状中，设置**事务**到**None**。</span><span class="sxs-lookup"><span data-stu-id="84088-112">In the Scope shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="84088-113">作用域形状内右键单击并选择**新建异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="84088-113">Right-click inside the Scope shape, and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="84088-114">![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")</span><span class="sxs-lookup"><span data-stu-id="84088-114">![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")</span></span>  
  
     <span data-ttu-id="84088-115">这会创建捕获异常块。</span><span class="sxs-lookup"><span data-stu-id="84088-115">This creates the Catch Exception block.</span></span> <span data-ttu-id="84088-116">如果从后端出现异常，它会捕获到捕获异常块内。</span><span class="sxs-lookup"><span data-stu-id="84088-116">If an exception occurs from the back-end, it is caught inside the Catch Exception block.</span></span>  
  
4.  <span data-ttu-id="84088-117">在捕获异常块中，必须添加逻辑。</span><span class="sxs-lookup"><span data-stu-id="84088-117">In the Catch Exception block, you must add the logic.</span></span>  
  
     <span data-ttu-id="84088-118">必须设置的最重要逻辑是您需要错误消息的类型。</span><span class="sxs-lookup"><span data-stu-id="84088-118">The most important logic you must set is the type of error message you are expecting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84088-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="84088-119">See Also</span></span>  
 [<span data-ttu-id="84088-120">使用 BizTalk Server 的异常处理</span><span class="sxs-lookup"><span data-stu-id="84088-120">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)