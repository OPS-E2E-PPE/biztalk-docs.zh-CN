---
title: 使用 Microsoft BizTalk LoadGen 2007 工具 |Microsoft Docs
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
ms.openlocfilehash: ba37985ad0841f0bc6b39bb9a5958b625033f168
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395996"
---
# <a name="using-the-microsoft-biztalk-loadgen-2007-tool"></a><span data-ttu-id="170ec-102">使用 Microsoft BizTalk LoadGen 2007 工具</span><span class="sxs-lookup"><span data-stu-id="170ec-102">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>
<span data-ttu-id="170ec-103">Microsoft BizTalk LoadGen 2007 工具适用于开发人员和 IT 专家模拟 BizTalk Server 上的负载。</span><span class="sxs-lookup"><span data-stu-id="170ec-103">The Microsoft BizTalk LoadGen 2007 Tool is intended for developers and IT professionals to simulate load on a BizTalk Server.</span></span> <span data-ttu-id="170ec-104">使用此工具，可以模拟检测性能和压力根据 BizTalk 部署到的负载。</span><span class="sxs-lookup"><span data-stu-id="170ec-104">Using this tool, you can simulate load to instrument performance and stress against a BizTalk deployment.</span></span> <span data-ttu-id="170ec-105">此外，此工具还可以扩展由开发人员来模拟自定义传输的负载。</span><span class="sxs-lookup"><span data-stu-id="170ec-105">In addition, this tool may also be extended by developers to simulate load for custom transports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="170ec-106">下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。</span><span class="sxs-lookup"><span data-stu-id="170ec-106">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span> 
  
 <span data-ttu-id="170ec-107">此工具应仅在测试环境中使用并不应在生产环境中使用。</span><span class="sxs-lookup"><span data-stu-id="170ec-107">This tool should be used in a test environment only, and should not be used in a production environment.</span></span> <span data-ttu-id="170ec-108">此工具提供"作为-是"不受支持。</span><span class="sxs-lookup"><span data-stu-id="170ec-108">This tool is provided "as-is" and is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="170ec-109">可以使用 MSMQ 适配器使用 BizTalk Server 负载生成工具，但必须执行一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="170ec-109">You can use BizTalk Server Load Generation Tool with the MSMQ adapter, but you must do some additional steps.</span></span> <span data-ttu-id="170ec-110">有关说明，请参阅[与 MSMQ 将 LoadGen 2007](../core/using-loadgen-2007-with-msmq.md)。</span><span class="sxs-lookup"><span data-stu-id="170ec-110">For instructions, see [Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="170ec-111">LoadGen 可能不支持在 64 位计算机上。</span><span class="sxs-lookup"><span data-stu-id="170ec-111">LoadGen may not be supported on 64-bit computers.</span></span> <span data-ttu-id="170ec-112">您可以使用 LoadGen 远程运行在 32 位计算机上生成对 64 位服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="170ec-112">You can use LoadGen remotely running on a 32-bit computer to generate load against a 64-bit server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="170ec-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="170ec-113">See Also</span></span>  
 [<span data-ttu-id="170ec-114">过载测试</span><span class="sxs-lookup"><span data-stu-id="170ec-114">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)