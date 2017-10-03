---
title: "0 C 4 请求设置为 0 C 4 响应映射示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21084807-3d96-45e8-b949-032006a13cab
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07e480781d0bea3767d6010b46df82c34b27db1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="0c4-request-to-0c4-response-map-sample"></a><span data-ttu-id="9a7fc-102">0 C 4 请求设置为 0 C 4 响应映射示例</span><span class="sxs-lookup"><span data-stu-id="9a7fc-102">0C4 Request to 0C4 Response Map Sample</span></span>
<span data-ttu-id="9a7fc-103">_0C4RequestMessageTo0C4ResponseMessage.btm 示例演示如何将 0C4 请求消息映射到 0C4 响应消息。</span><span class="sxs-lookup"><span data-stu-id="9a7fc-103">The _0C4RequestMessageTo0C4ResponseMessage.btm sample demonstrates how you can map a 0C4 request message to a 0C4 response message.</span></span>  
  
 <span data-ttu-id="9a7fc-104">默认情况下， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]安装程序将安装中的示例\<*驱动器*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > 快捷键RosettaNet\SDK\PIPAutomation\DoubleAction。</span><span class="sxs-lookup"><span data-stu-id="9a7fc-104">By default, the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Setup program installs the sample in \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="9a7fc-105">示例内容</span><span class="sxs-lookup"><span data-stu-id="9a7fc-105">Sample Contents</span></span>  
 <span data-ttu-id="9a7fc-106">此示例演示如何将 0C4 请求消息的字段映射到 0C4 响应消息。</span><span class="sxs-lookup"><span data-stu-id="9a7fc-106">This sample demonstrates how to map the fields of a 0C4 request message to a 0C4 response message.</span></span> <span data-ttu-id="9a7fc-107">可以将此示例与双操作 PIPAutomation 业务流程示例一起使用。</span><span class="sxs-lookup"><span data-stu-id="9a7fc-107">You can use this sample with the Double Action PIPAutomation Orchestration sample.</span></span> <span data-ttu-id="9a7fc-108">该双操作 PIPAutomation 业务流程示例演示如何实现为双操作 0C2、0C4、3A2 和 3A4 PIP 自动生成响应的业务流程。</span><span class="sxs-lookup"><span data-stu-id="9a7fc-108">The Double Action PIPAutomation Orchestration sample demonstrates how to implement an orchestration to automatically generate responses for double action 0C2, 0C4, 3A2, and 3A4 PIPs.</span></span>