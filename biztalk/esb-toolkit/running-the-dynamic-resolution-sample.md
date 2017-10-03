---
title: "运行动态解析示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c933839f-13e6-4b49-9838-2773e3f99b64
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e613934c44db03cf29edbf3fff4ef34d6b946577
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-dynamic-resolution-sample"></a><span data-ttu-id="79e09-102">运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="79e09-102">Running the Dynamic Resolution Sample</span></span>
<span data-ttu-id="79e09-103">若要执行使用案例之一，您将相应的 Microsoft BizTalk 绑定文件导入 GlobalBank.ESB BizTalk 应用程序然后放到示例输入文件夹的合适的消息或调用的示例 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="79e09-103">To execute one of the use case examples, you import the appropriate Microsoft BizTalk binding file into the GlobalBank.ESB BizTalk application and then either drop a suitable message into the sample input folder or call the sample Web service.</span></span> <span data-ttu-id="79e09-104">动态解析示例支持两个主要方案：</span><span class="sxs-lookup"><span data-stu-id="79e09-104">The Dynamic Resolution sample supports two main scenarios:</span></span>  
  
-   <span data-ttu-id="79e09-105">[动态解析示例的单向消息传递方案](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="79e09-105">[One-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="79e09-106">使用文件放置文件夹作为发布这种情况下将指向 Microsoft BizTalk 动态解析示例支持。</span><span class="sxs-lookup"><span data-stu-id="79e09-106">The Dynamic Resolution sample supports this scenario using a file drop folder as the publication point into Microsoft BizTalk.</span></span>  
  
-   <span data-ttu-id="79e09-107">[动态解析示例的双向消息传递方案](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="79e09-107">[Two-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="79e09-108">动态解析示例支持这种情况下，使用位于 http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx 在发布的 NorthAmerican Web 服务点到 BizTalk。</span><span class="sxs-lookup"><span data-stu-id="79e09-108">The Dynamic Resolution sample supports this scenario using the NorthAmerican Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx as the publication point into BizTalk.</span></span>  
  
 <span data-ttu-id="79e09-109">若要了解该示例的 ESB 调度程序和 ESB 调度程序反汇编程序管道组件的使用，请参阅[动态解析示例的工作原理](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)。</span><span class="sxs-lookup"><span data-stu-id="79e09-109">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>