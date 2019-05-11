---
title: 运行动态解析示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c933839f-13e6-4b49-9838-2773e3f99b64
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d6d6aaf524af19672c86c5fe4a2a6d052bbfe2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292549"
---
# <a name="running-the-dynamic-resolution-sample"></a><span data-ttu-id="6f97b-102">运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="6f97b-102">Running the Dynamic Resolution Sample</span></span>
<span data-ttu-id="6f97b-103">若要执行用例之一，您将相应的 Microsoft BizTalk 绑定文件导入 GlobalBank.ESB BizTalk 应用程序并放入的示例输入文件夹的适当消息或调用示例 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="6f97b-103">To execute one of the use case examples, you import the appropriate Microsoft BizTalk binding file into the GlobalBank.ESB BizTalk application and then either drop a suitable message into the sample input folder or call the sample Web service.</span></span> <span data-ttu-id="6f97b-104">动态解析示例支持两个主要方案：</span><span class="sxs-lookup"><span data-stu-id="6f97b-104">The Dynamic Resolution sample supports two main scenarios:</span></span>  
  
- <span data-ttu-id="6f97b-105">[动态解析示例的单向消息传送方案](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="6f97b-105">[One-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="6f97b-106">动态解析示例支持此方案中使用的文件放置文件夹，在发布到 Microsoft BizTalk 点。</span><span class="sxs-lookup"><span data-stu-id="6f97b-106">The Dynamic Resolution sample supports this scenario using a file drop folder as the publication point into Microsoft BizTalk.</span></span>  
  
- <span data-ttu-id="6f97b-107">[动态解析示例的双向消息传送方案](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md) 。</span><span class="sxs-lookup"><span data-stu-id="6f97b-107">[Two-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="6f97b-108">动态解析示例支持这种情况下，使用 NorthAmerican Web 服务位于 http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx 作为发布点到 BizTalk。</span><span class="sxs-lookup"><span data-stu-id="6f97b-108">The Dynamic Resolution sample supports this scenario using the NorthAmerican Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx as the publication point into BizTalk.</span></span>  
  
  <span data-ttu-id="6f97b-109">若要了解此示例如何使用 ESB 调度程序和 ESB 调度程序反汇编程序管道组件，请参阅[动态解析示例的工作原理](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)。</span><span class="sxs-lookup"><span data-stu-id="6f97b-109">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>