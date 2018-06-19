---
title: 使用 Microsoft BizTalk LoadGen 2007 工具 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1973a26-1c98-4261-bd9a-6357cdb19ccf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dcf55b2371387ffd52139724d74a118d52ce999
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007198"
---
# <a name="using-the-microsoft-biztalk-loadgen-2007-tool"></a><span data-ttu-id="2e037-102">使用 Microsoft BizTalk LoadGen 2007 工具</span><span class="sxs-lookup"><span data-stu-id="2e037-102">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>
<span data-ttu-id="2e037-103">Microsoft BizTalk LoadGen 2007 工具可供开发人员和 IT 专家模拟 BizTalk Server 上的负载。</span><span class="sxs-lookup"><span data-stu-id="2e037-103">The Microsoft BizTalk LoadGen 2007 Tool is intended for developers and IT professionals to simulate load on a BizTalk Server.</span></span> <span data-ttu-id="2e037-104">使用此工具，可以模拟负载，以便根据 BizTalk 部署检测性能和压力。</span><span class="sxs-lookup"><span data-stu-id="2e037-104">Using this tool, you can simulate load to instrument performance and stress against a BizTalk deployment.</span></span> <span data-ttu-id="2e037-105">此外，开发人员还可以扩展此工具，以便模拟自定义传输的负载。</span><span class="sxs-lookup"><span data-stu-id="2e037-105">In addition, this tool may also be extended by developers to simulate load for custom transports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e037-106">下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。</span><span class="sxs-lookup"><span data-stu-id="2e037-106">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span> 
  
 <span data-ttu-id="2e037-107">此工具应仅用于测试环境中，不应用于生产环境中。</span><span class="sxs-lookup"><span data-stu-id="2e037-107">This tool should be used in a test environment only, and should not be used in a production environment.</span></span> <span data-ttu-id="2e037-108">此工具以“保持原样”提供，不支持用于生产环境中。</span><span class="sxs-lookup"><span data-stu-id="2e037-108">This tool is provided "as-is" and is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e037-109">你可以使用 MSMQ 适配器中，BizTalk 服务器负载生成工具，但必须执行一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="2e037-109">You can use BizTalk Server Load Generation Tool with the MSMQ adapter, but you must do some additional steps.</span></span> <span data-ttu-id="2e037-110">有关说明，请参阅[使用 MSMQ LoadGen 2007](../core/using-loadgen-2007-with-msmq.md)。</span><span class="sxs-lookup"><span data-stu-id="2e037-110">For instructions, see [Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e037-111">LoadGen 可能不支持在 64 位计算机上。</span><span class="sxs-lookup"><span data-stu-id="2e037-111">LoadGen may not be supported on 64-bit computers.</span></span> <span data-ttu-id="2e037-112">您可以远程使用运行在 32 位计算机上的 LoadGen 以生成对 64 位服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="2e037-112">You can use LoadGen remotely running on a 32-bit computer to generate load against a 64-bit server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e037-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e037-113">See Also</span></span>  
 [<span data-ttu-id="2e037-114">过载测试</span><span class="sxs-lookup"><span data-stu-id="2e037-114">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)