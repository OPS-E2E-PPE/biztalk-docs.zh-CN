---
title: 使用 MSMQ LoadGen 2007 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8f23a86-0e6d-478a-87a3-5b02338c9afb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55d67628b7863df3f2396cd9b45b55f42a488b8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287125"
---
# <a name="using-loadgen-2007-with-msmq"></a><span data-ttu-id="3f28d-102">将 LoadGen 2007 与 MSMQ 一起使用</span><span class="sxs-lookup"><span data-stu-id="3f28d-102">Using LoadGen 2007 with MSMQ</span></span>
<span data-ttu-id="3f28d-103">使用负载生成工具 Loadgen，您可以模拟 BizTalk Server 系统过载时的情况。</span><span class="sxs-lookup"><span data-stu-id="3f28d-103">The Load Generation tool, Loadgen, enables you to simulate heavy loads on a BizTalk Server system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f28d-104">LoadGen 2007 工具是可在下载[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841)。</span><span class="sxs-lookup"><span data-stu-id="3f28d-104">The LoadGen 2007 tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span></span>  
  
 <span data-ttu-id="3f28d-105">支持将 LoadGen 与 MSMQ 一起使用，但在安装期间不自动注册 MSMQ COM 组件，因为计算机上可能未安装 MSMQ 运行时服务。</span><span class="sxs-lookup"><span data-stu-id="3f28d-105">Using LoadGen with MSMQ is supported, but we do not auto-register the MSMQ COM components during installation since the MSMQ runtime service may not be installed on your computer.</span></span>  
  
 <span data-ttu-id="3f28d-106">若要使用 MSMQ 和 LoadGen，请手动注册位于 bins 目录中的 MSMQTransmitter.dll 和 ComMsmqMonitor.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="3f28d-106">To use MSMQ and LoadGen, manually register the MSMQTransmitter.dll and ComMsmqMonitor.dll files located in the bins directory:</span></span>  
  
```  
regsvr32 MSMQTransmitter.dll  
```  
  
 <span data-ttu-id="3f28d-107">如果不注册 MSMQ COM 组件，则将收到以下运行时错误：</span><span class="sxs-lookup"><span data-stu-id="3f28d-107">If you do not register the MSMQ COM components, you will receive the following runtime errors:</span></span>  
  
```  
Cannot Load Transport DLL C:\Program Files\LoadGen\Bins\MSMQTransport.dll for Section MSMQRxQTxn   
Exception has been thrown by the target of an invocation.  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f28d-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f28d-108">See Also</span></span>  
 [<span data-ttu-id="3f28d-109">用于测量引擎 MST 测试方案</span><span class="sxs-lookup"><span data-stu-id="3f28d-109">Test Scenarios for Measuring MST of the Engine</span></span>](../core/test-scenarios-for-measuring-mst-of-the-engine.md)