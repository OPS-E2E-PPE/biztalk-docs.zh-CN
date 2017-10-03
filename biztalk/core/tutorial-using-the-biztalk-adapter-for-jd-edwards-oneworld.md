---
title: "教程： 使用 BizTalk Adapter for 博士 Edwards OneWorld |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e13a648-7eaf-40c4-a71b-b66999087a69
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab54a0fe0f4a036e0045938951cf44337087853b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="f6b33-102">教程： 使用适用于博士 Edwards OneWorld BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="f6b33-102">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>
<span data-ttu-id="f6b33-103">下面演示了如何使用 BizTalk 上下文属性控制 J.D.</span><span class="sxs-lookup"><span data-stu-id="f6b33-103">The following demonstrates using BizTalk Context Properties to control the J.D.</span></span> <span data-ttu-id="f6b33-104">Edwards OneWorld 业务流程中的会话。</span><span class="sxs-lookup"><span data-stu-id="f6b33-104">Edwards OneWorld session in your orchestration.</span></span> <span data-ttu-id="f6b33-105">本教程假定你具有将发送到发送端口绑定到 Microsoft BizTalk 适配器 J.D.BeginDoc、 EditLine 和 EndDoc 调用一个业务流程</span><span class="sxs-lookup"><span data-stu-id="f6b33-105">The tutorial assumes you have an orchestration that sends BeginDoc, EditLine and EndDoc calls to a send port bound to the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="f6b33-106">Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="f6b33-106">Edwards OneWorld.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6b33-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="f6b33-107">In This Section</span></span>  
  
-   [<span data-ttu-id="f6b33-108">步骤 1： 引用 DLL 的架构</span><span class="sxs-lookup"><span data-stu-id="f6b33-108">Step 1: Reference the Schema DLL</span></span>](../core/step-1-reference-the-schema-dll2.md)  
  
-   [<span data-ttu-id="f6b33-109">步骤 2： 创建业务流程</span><span class="sxs-lookup"><span data-stu-id="f6b33-109">Step 2: Create the Orchestration</span></span>](../core/step-2-create-the-orchestration1.md)  
  
-   [<span data-ttu-id="f6b33-110">步骤 3： 完成并运行项目</span><span class="sxs-lookup"><span data-stu-id="f6b33-110">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project2.md)  
  
-   [<span data-ttu-id="f6b33-111">步骤 4： 创建示例 XML BeginDoc</span><span class="sxs-lookup"><span data-stu-id="f6b33-111">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc1.md)