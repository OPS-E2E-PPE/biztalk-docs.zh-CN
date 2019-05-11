---
title: 教程：使用用于 JD Edwards EnterpriseOne 的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cafbe72-2b90-4d8e-9a1d-5735cefeb3d4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d34080e00ef05113a7d67787bcde2896b6b6e2aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393856"
---
# <a name="tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="384f0-102">教程：使用用于 JD Edwards EnterpriseOne 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="384f0-102">Tutorial: Using the BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="384f0-103">以下代码演示了使用 BizTalk 上下文属性来控制 j.d.</span><span class="sxs-lookup"><span data-stu-id="384f0-103">The following demonstrates using BizTalk Context Properties to control the J.D.</span></span>  <span data-ttu-id="384f0-104">在业务流程中 Edwards OneWorld 会话。</span><span class="sxs-lookup"><span data-stu-id="384f0-104">Edwards OneWorld session in your orchestration.</span></span> <span data-ttu-id="384f0-105">本教程假定你已将发送到发送端口与用于 J.D.Microsoft BizTalk 适配器绑定 BeginDoc、 EditLine 和 EndDoc 调用的业务流程</span><span class="sxs-lookup"><span data-stu-id="384f0-105">The tutorial assumes you have an orchestration that sends BeginDoc, EditLine and EndDoc calls to a send port bound to the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="384f0-106">Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="384f0-106">Edwards OneWorld.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="384f0-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="384f0-107">In This Section</span></span>  
  
-   [<span data-ttu-id="384f0-108">步骤 1：引用架构 DLL</span><span class="sxs-lookup"><span data-stu-id="384f0-108">Step 1: Reference the Schema DLL</span></span>](../core/step-1-reference-the-schema-dll1.md)  
  
-   [<span data-ttu-id="384f0-109">步骤 2：创建业务流程</span><span class="sxs-lookup"><span data-stu-id="384f0-109">Step 2: Create the Orchestration</span></span>](../core/step-2-create-the-orchestration2.md)  
  
-   [<span data-ttu-id="384f0-110">步骤 3：完成并运行项目</span><span class="sxs-lookup"><span data-stu-id="384f0-110">Step 3: Complete and Run the Project</span></span>](../core/step-3-complete-and-run-the-project1.md)  
  
-   [<span data-ttu-id="384f0-111">步骤 4：创建示例 XML BeginDoc</span><span class="sxs-lookup"><span data-stu-id="384f0-111">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc2.md)