---
title: 在 64 位 Windows 操作系统上使用 BizTalk Server 时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac630f55-7ebe-4b93-bf98-70b00788520f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 486df5450c01b51426383e7ab7a3d100013c23dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990574"
---
# <a name="considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system"></a><span data-ttu-id="52399-102">在 64 位 Windows 操作系统上使用 BizTalk Server 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="52399-102">Considerations While Using BizTalk Server on a 64-bit Windows Operating System</span></span>
<span data-ttu-id="52399-103">当使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上 64 位 Windows 操作系统，请务必考虑本主题中所述的问题。</span><span class="sxs-lookup"><span data-stu-id="52399-103">When using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a 64-bit Windows operating system, make sure you consider the issues described in this topic.</span></span> <span data-ttu-id="52399-104">与 Microsoft BizTalk Server 的 64 位支持相关的问题方面的常见问题，请参阅[BizTalk Server 64 位支持](http://go.microsoft.com/fwlink/?LinkID=155306)(<http://go.microsoft.com/fwlink/?LinkID=155306>)。</span><span class="sxs-lookup"><span data-stu-id="52399-104">For frequently asked questions related to 64-bit support for Microsoft BizTalk Server, see [BizTalk Server 64-bit Support](http://go.microsoft.com/fwlink/?LinkID=155306) (<http://go.microsoft.com/fwlink/?LinkID=155306>).</span></span>  
  
## <a name="modify-the-process-memory-usage-throttling-threshold"></a><span data-ttu-id="52399-105">修改进程内存使用量限制阈值</span><span class="sxs-lookup"><span data-stu-id="52399-105">Modify the Process Memory Usage Throttling Threshold</span></span>  
 <span data-ttu-id="52399-106">默认情况下**进程的内存利用率**主机阻止阈值设置为 25。</span><span class="sxs-lookup"><span data-stu-id="52399-106">By default, the **Process memory usage** host throttling threshold is set to 25.</span></span> <span data-ttu-id="52399-107">如果超出此值，BizTalk 进程内存使用率超过 300 MB，可能会出现限制情况。</span><span class="sxs-lookup"><span data-stu-id="52399-107">If this value is exceeded and the BizTalk process memory usage is more than 300 MB, a throttling condition may occur.</span></span> <span data-ttu-id="52399-108">在 64 位服务器上，可以增加此值设置为 100。</span><span class="sxs-lookup"><span data-stu-id="52399-108">On a 64-bit server, you can increase this value to 100.</span></span> <span data-ttu-id="52399-109">这允许更多的内存消耗 BizTalk 进程之前会发生限制。</span><span class="sxs-lookup"><span data-stu-id="52399-109">This allows for more memory consumption by the BizTalk process before throttling occurs.</span></span> <span data-ttu-id="52399-110">有关如何修改进程内存使用情况主机阻止阈值的说明，请参阅[如何修改默认主机阻止设置](http://go.microsoft.com/fwlink/?LinkId=157210)(http://go.microsoft.com/fwlink/?LinkId=157210)。</span><span class="sxs-lookup"><span data-stu-id="52399-110">For instructions on how to modify the process memory usage host throttling threshold, see [How to Modify the Default Host Throttling Settings](http://go.microsoft.com/fwlink/?LinkId=157210) (http://go.microsoft.com/fwlink/?LinkId=157210).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52399-111">为进行上述计算，最大可用进程内存不能超过 2 GB 的地址空间大小，即使系统具有 2 GB 以上的物理内存。</span><span class="sxs-lookup"><span data-stu-id="52399-111">The maximum available process memory is capped at an address space size of 2 GB for purposes of this calculation, even if the system has more than 2 GB of physical memory.</span></span> <span data-ttu-id="52399-112">不论是 32 位系统还是 64 位系统，进行上述计算均需使用 2 GB 的进程内存上限。</span><span class="sxs-lookup"><span data-stu-id="52399-112">A 2 GB process memory upper limit is used for purposes of this calculation on both 32 bit and 64 bit systems.</span></span> <span data-ttu-id="52399-113">为了防止内存不足错误，建议您不要指定一个值，会使主机实例内存超过 1.54 GB，而不考虑运行 32 位版本的 BizTalk Server 中，如果在 32 位或 64 位操作系统 sy 安装 BizTalk Server 时stem。</span><span class="sxs-lookup"><span data-stu-id="52399-113">In order to prevent out of memory errors, it is recommended that you do not specify a value that will allow host instance memory to exceed 1.54 GB when running a 32 bit version of BizTalk Server, regardless of if BizTalk Server is installed on a 32 bit or 64 bit operating system.</span></span> <span data-ttu-id="52399-114">例如，如果您为该设置指定从 1 到 100 之间的值，以基于进程内存使用百分比进行阻止，请不要输入大于 75 的值 (.75 \* 2GB = 1.54 GB)。</span><span class="sxs-lookup"><span data-stu-id="52399-114">For example, if you specify a value from 1 through 100 for this setting to initiate throttling based upon the percentage of process memory used, do not enter a value greater than 75 (.75 \* 2GB = 1.54 GB).</span></span> <span data-ttu-id="52399-115">如果您指定大于 100 的此设置以基于指定的数量，以 mb 为单位，不要输入大于 1536.If 的值的值在运行 64 位版本的 BizTalk Server，指定一个值或 100 （100%) 或 2048 (2GB) 启动 使用 2 GB 的最大可用进程内存时进行阻止。</span><span class="sxs-lookup"><span data-stu-id="52399-115">If you specify a value greater than 100 for this setting to initiate throttling based upon the specified number in MB, do not enter a value greater than 1536.If you are running a 64 bit version of BizTalk Server, specify a value or either 100 (100%) or 2048 (2GB) to initiate throttling when the maximum available process memory of 2 GB is used.</span></span>  
  
## <a name="adapters-that-do-not-support-64-bit-hosts"></a><span data-ttu-id="52399-116">不支持 64 位主机的适配器</span><span class="sxs-lookup"><span data-stu-id="52399-116">Adapters That Do Not Support 64-bit Hosts</span></span>  
 <span data-ttu-id="52399-117">以下适配器不支持 64 位主机实例上运行：</span><span class="sxs-lookup"><span data-stu-id="52399-117">The following adapters are not supported to run on 64-bit host instances:</span></span>  
  
- <span data-ttu-id="52399-118">FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="52399-118">FTP adapter</span></span>  
  
- <span data-ttu-id="52399-119">POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="52399-119">POP3 adapter</span></span>  
  
  <span data-ttu-id="52399-120">请确保在 32 位主机实例中运行这些适配器。</span><span class="sxs-lookup"><span data-stu-id="52399-120">Make sure you run these adapters in a 32-bit host instance.</span></span>  
  
## <a name="configure-the-mimesmime-encoder-to-run-in-32-bit-mode"></a><span data-ttu-id="52399-121">配置 MIME/SMIME 编码器，以便在 32 位模式下运行</span><span class="sxs-lookup"><span data-stu-id="52399-121">Configure the MIME/SMIME Encoder to run in 32-bit mode</span></span>  
 <span data-ttu-id="52399-122">在 BizTalk Server 中，MIME/SMIME 编码器管道组件就完了没有支持本机 64 位模式。</span><span class="sxs-lookup"><span data-stu-id="52399-122">In BizTalk Server, the MIME/SMIME encoder pipeline component dies not have native 64-bit support.</span></span> <span data-ttu-id="52399-123">这意味着此组件必须运行在 32 位仿真模式进程 (WOW64) 中。</span><span class="sxs-lookup"><span data-stu-id="52399-123">This means that this component must be run in a 32-bit emulation mode process (WOW64).</span></span> <span data-ttu-id="52399-124">这表示运行此编码器组件（或其所属发送管道）的主机实例必须以 32 位仿真模式运行。</span><span class="sxs-lookup"><span data-stu-id="52399-124">This implies that the host instance in which this encoder component (or the send pipeline of which it is a part) runs must be running in 32-bit emulation mode.</span></span> <span data-ttu-id="52399-125">请注意此限制对运行在此主机实例中的其他 BizTalk 元素性能（和其他方面）的影响。</span><span class="sxs-lookup"><span data-stu-id="52399-125">Be aware of the performance (and other) implications of this restriction for other elements of BizTalk running in this same host instance.</span></span>