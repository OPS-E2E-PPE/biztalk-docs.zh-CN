---
title: "在 64 位 Windows 操作系统上使用 BizTalk Server 时的注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac630f55-7ebe-4b93-bf98-70b00788520f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4c6ac3b8a3104e1c96b2dc9ebd880489d3c9833
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system"></a><span data-ttu-id="24436-102">在 64 位 Windows 操作系统上使用 BizTalk Server 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="24436-102">Considerations While Using BizTalk Server on a 64-bit Windows Operating System</span></span>
<span data-ttu-id="24436-103">使用时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 64 位 Windows 操作系统中，确保考虑本主题中所述的问题。</span><span class="sxs-lookup"><span data-stu-id="24436-103">When using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a 64-bit Windows operating system, make sure you consider the issues described in this topic.</span></span> <span data-ttu-id="24436-104">有关 Microsoft BizTalk Server 的 64 位支持的常见问题及问题，请参阅[BizTalk Server 64 位支持](http://go.microsoft.com/fwlink/?LinkID=155306)(http://go.microsoft.com/fwlink/?LinkID=155306)。</span><span class="sxs-lookup"><span data-stu-id="24436-104">For frequently asked questions related to 64-bit support for Microsoft BizTalk Server, see [BizTalk Server 64-bit Support](http://go.microsoft.com/fwlink/?LinkID=155306) (http://go.microsoft.com/fwlink/?LinkID=155306).</span></span>  
  
## <a name="modify-the-process-memory-usage-throttling-threshold"></a><span data-ttu-id="24436-105">修改限制阈值的进程内存使用量</span><span class="sxs-lookup"><span data-stu-id="24436-105">Modify the Process Memory Usage Throttling Threshold</span></span>  
 <span data-ttu-id="24436-106">默认情况下，**处理内存使用量**主机限制阈值设置为 25。</span><span class="sxs-lookup"><span data-stu-id="24436-106">By default, the **Process memory usage** host throttling threshold is set to 25.</span></span> <span data-ttu-id="24436-107">如果超出此值时，BizTalk 进程内存使用率为 300 MB 以上，可能会发生限制条件。</span><span class="sxs-lookup"><span data-stu-id="24436-107">If this value is exceeded and the BizTalk process memory usage is more than 300 MB, a throttling condition may occur.</span></span> <span data-ttu-id="24436-108">在 64 位服务器上，您可以增大此值为 100。</span><span class="sxs-lookup"><span data-stu-id="24436-108">On a 64-bit server, you can increase this value to 100.</span></span> <span data-ttu-id="24436-109">这使得更多的内存消耗由 BizTalk 进程限制发生之前。</span><span class="sxs-lookup"><span data-stu-id="24436-109">This allows for more memory consumption by the BizTalk process before throttling occurs.</span></span> <span data-ttu-id="24436-110">有关如何修改限制阈值进程内存使用情况宿主的说明，请参阅[如何修改默认的主机限制设置](http://go.microsoft.com/fwlink/?LinkId=157210)(http://go.microsoft.com/fwlink/?LinkId=157210)。</span><span class="sxs-lookup"><span data-stu-id="24436-110">For instructions on how to modify the process memory usage host throttling threshold, see [How to Modify the Default Host Throttling Settings](http://go.microsoft.com/fwlink/?LinkId=157210) (http://go.microsoft.com/fwlink/?LinkId=157210).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24436-111">为进行上述计算，最大可用进程内存不能超过 2 GB 的地址空间大小，即使系统具有 2 GB 以上的物理内存。</span><span class="sxs-lookup"><span data-stu-id="24436-111">The maximum available process memory is capped at an address space size of 2 GB for purposes of this calculation, even if the system has more than 2 GB of physical memory.</span></span> <span data-ttu-id="24436-112">不论是 32 位系统还是 64 位系统，进行上述计算均需使用 2 GB 的进程内存上限。</span><span class="sxs-lookup"><span data-stu-id="24436-112">A 2 GB process memory upper limit is used for purposes of this calculation on both 32 bit and 64 bit systems.</span></span> <span data-ttu-id="24436-113">为了防止内存不足错误，建议你不指定一个值，将允许主机实例内存超过 1.54 GB，而不考虑运行 32 位版本的 BizTalk Server 中，如果在 32 位或 64 位操作系统 sy 安装 BizTalk Server 时主干。</span><span class="sxs-lookup"><span data-stu-id="24436-113">In order to prevent out of memory errors, it is recommended that you do not specify a value that will allow host instance memory to exceed 1.54 GB when running a 32 bit version of BizTalk Server, regardless of if BizTalk Server is installed on a 32 bit or 64 bit operating system.</span></span> <span data-ttu-id="24436-114">例如，如果您为该设置指定从 1 到 100 之间的值，以基于进程内存使用百分比进行阻止，请不要输入大于 75 的值 (.75 * 2GB = 1.54 GB)。</span><span class="sxs-lookup"><span data-stu-id="24436-114">For example, if you specify a value from 1 through 100 for this setting to initiate throttling based upon the percentage of process memory used, do not enter a value greater than 75 (.75 * 2GB = 1.54 GB).</span></span> <span data-ttu-id="24436-115">如果你指定的值大于此设置以启动限制基于在以 mb 为单位的指定数目的 100 未输入值大于 1536.If 运行 64 位版本的 BizTalk Server，指定一个值或 100 （100%) 或 2048 (2GB) 来启动 限制使用 2 GB 的可用的最大处理内存时。</span><span class="sxs-lookup"><span data-stu-id="24436-115">If you specify a value greater than 100 for this setting to initiate throttling based upon the specified number in MB, do not enter a value greater than 1536.If you are running a 64 bit version of BizTalk Server, specify a value or either 100 (100%) or 2048 (2GB) to initiate throttling when the maximum available process memory of 2 GB is used.</span></span>  
  
## <a name="adapters-that-do-not-support-64-bit-hosts"></a><span data-ttu-id="24436-116">不支持 64 位主机适配器</span><span class="sxs-lookup"><span data-stu-id="24436-116">Adapters That Do Not Support 64-bit Hosts</span></span>  
 <span data-ttu-id="24436-117">以下的适配器不支持在 64 位主机实例上运行：</span><span class="sxs-lookup"><span data-stu-id="24436-117">The following adapters are not supported to run on 64-bit host instances:</span></span>  
  
-   <span data-ttu-id="24436-118">FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="24436-118">FTP adapter</span></span>  
  
-   <span data-ttu-id="24436-119">POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="24436-119">POP3 adapter</span></span>  
  
 <span data-ttu-id="24436-120">请确保在一个 32 位主机实例中运行这些适配器。</span><span class="sxs-lookup"><span data-stu-id="24436-120">Make sure you run these adapters in a 32-bit host instance.</span></span>  
  
## <a name="configure-the-mimesmime-encoder-to-run-in-32-bit-mode"></a><span data-ttu-id="24436-121">配置 MIME/SMIME 编码器，以便在 32 位模式下运行</span><span class="sxs-lookup"><span data-stu-id="24436-121">Configure the MIME/SMIME Encoder to run in 32-bit mode</span></span>  
 <span data-ttu-id="24436-122">在 BizTalk Server 中，MIME/SMIME 编码器管道组件发生故障不具有本机 64 位支持。</span><span class="sxs-lookup"><span data-stu-id="24436-122">In BizTalk Server, the MIME/SMIME encoder pipeline component dies not have native 64-bit support.</span></span> <span data-ttu-id="24436-123">这意味着此组件必须运行在 32 位仿真模式进程 (WOW64) 中。</span><span class="sxs-lookup"><span data-stu-id="24436-123">This means that this component must be run in a 32-bit emulation mode process (WOW64).</span></span> <span data-ttu-id="24436-124">这表示运行此编码器组件（或其所属发送管道）的主机实例必须以 32 位仿真模式运行。</span><span class="sxs-lookup"><span data-stu-id="24436-124">This implies that the host instance in which this encoder component (or the send pipeline of which it is a part) runs must be running in 32-bit emulation mode.</span></span> <span data-ttu-id="24436-125">请注意此限制对运行在此主机实例中的其他 BizTalk 元素性能（和其他方面）的影响。</span><span class="sxs-lookup"><span data-stu-id="24436-125">Be aware of the performance (and other) implications of this restriction for other elements of BizTalk running in this same host instance.</span></span>