---
title: 教程：使用用于 JD Edwards OneWorld 的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e13a648-7eaf-40c4-a71b-b66999087a69
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87bd059311e8414ed4dcded49d6ec5d1d7cb0155
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393842"
---
# <a name="tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="8e782-102">教程：使用用于 JD Edwards OneWorld 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="8e782-102">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>
<span data-ttu-id="8e782-103">以下代码演示了使用 BizTalk 上下文属性来控制 j.d.</span><span class="sxs-lookup"><span data-stu-id="8e782-103">The following demonstrates using BizTalk Context Properties to control the J.D.</span></span> <span data-ttu-id="8e782-104">在业务流程中 Edwards OneWorld 会话。</span><span class="sxs-lookup"><span data-stu-id="8e782-104">Edwards OneWorld session in your orchestration.</span></span> <span data-ttu-id="8e782-105">本教程假定你已将发送到发送端口与用于 J.D.Microsoft BizTalk 适配器绑定 BeginDoc、 EditLine 和 EndDoc 调用的业务流程</span><span class="sxs-lookup"><span data-stu-id="8e782-105">The tutorial assumes you have an orchestration that sends BeginDoc, EditLine and EndDoc calls to a send port bound to the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="8e782-106">Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="8e782-106">Edwards OneWorld.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e782-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="8e782-107">In This Section</span></span>  
  
-   [<span data-ttu-id="8e782-108">步骤 1：引用架构 DLL</span><span class="sxs-lookup"><span data-stu-id="8e782-108">Step 1: Reference the Schema DLL</span></span>](../core/step-1-reference-the-schema-dll2.md)  
  
-   [<span data-ttu-id="8e782-109">步骤 2：创建业务流程</span><span class="sxs-lookup"><span data-stu-id="8e782-109">Step 2: Create the Orchestration</span></span>](../core/step-2-create-the-orchestration1.md)  
  
-   [<span data-ttu-id="8e782-110">步骤 3：完成并运行项目</span><span class="sxs-lookup"><span data-stu-id="8e782-110">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project2.md)  
  
-   [<span data-ttu-id="8e782-111">步骤 4：创建示例 XML BeginDoc</span><span class="sxs-lookup"><span data-stu-id="8e782-111">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc1.md)