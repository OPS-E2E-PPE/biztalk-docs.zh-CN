---
title: 已知问题的 POP3 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6d621a2-4801-44fe-a266-d4c05ac82633
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bc86b2ae14b04b160f7387f870615116e659b3f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261941"
---
# <a name="known-issues-with-the-pop3-adapter"></a><span data-ttu-id="527bb-102">POP3 适配器已知问题</span><span class="sxs-lookup"><span data-stu-id="527bb-102">Known Issues with the POP3 Adapter</span></span>
<span data-ttu-id="527bb-103">本部分包含可帮助你避免出现错误的信息。</span><span class="sxs-lookup"><span data-stu-id="527bb-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="527bb-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="527bb-104">Known Issues</span></span>  
  
#### <a name="the-pop3-adapter-fails-to-process-documents-when-running-on-a-64-bit-operating-system"></a><span data-ttu-id="527bb-105">POP3 适配器在运行在 64 位操作系统上时无法处理文档</span><span class="sxs-lookup"><span data-stu-id="527bb-105">The POP3 Adapter fails to process documents when running on a 64 bit operating system</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="527bb-106">问题</span><span class="sxs-lookup"><span data-stu-id="527bb-106">Problem</span></span>  
 <span data-ttu-id="527bb-107">POP3 适配器在运行在 64 位操作系统上时将无法处理文档。</span><span class="sxs-lookup"><span data-stu-id="527bb-107">The POP3 Adapter will not process documents when running on a 64 bit operating system.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="527bb-108">原因</span><span class="sxs-lookup"><span data-stu-id="527bb-108">Cause</span></span>  
 <span data-ttu-id="527bb-109">POP3 适配器的适配器处理程序无法运行在 64 位主机实例上。</span><span class="sxs-lookup"><span data-stu-id="527bb-109">The POP3 Adapter adapter handler is unable to run in a 64 bit host instance.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="527bb-110">解决方法</span><span class="sxs-lookup"><span data-stu-id="527bb-110">Resolution</span></span>  
 <span data-ttu-id="527bb-111">如果要在 64 位计算机上运行 POP3 适配器，需要将 POP3 适配器处理程序配置为在 32 位主机中运行。</span><span class="sxs-lookup"><span data-stu-id="527bb-111">If you are running the POP3 Adapter on a 64 bit machine, configure the POP3 Adapter handlers to run in a 32 bit host.</span></span> <span data-ttu-id="527bb-112">在可通过 BizTalk 管理控制台访问的“主机属性”页上提供了此选项。</span><span class="sxs-lookup"><span data-stu-id="527bb-112">This option is available on the Host Properties page accessible from the BizTalk Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="527bb-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="527bb-113">See Also</span></span>  
 [<span data-ttu-id="527bb-114">故障排除 POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="527bb-114">Troubleshooting the POP3 Adapter</span></span>](../core/troubleshooting-the-pop3-adapter.md)