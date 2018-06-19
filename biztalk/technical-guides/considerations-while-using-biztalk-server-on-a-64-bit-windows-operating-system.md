---
title: 在 64 位 Windows 操作系统上使用 BizTalk Server 时的注意事项 |Microsoft 文档
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
ms.openlocfilehash: f4c6ac3b8a3104e1c96b2dc9ebd880489d3c9833
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008382"
---
# <a name="considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system"></a>在 64 位 Windows 操作系统上使用 BizTalk Server 时的注意事项
使用时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 64 位 Windows 操作系统中，确保考虑本主题中所述的问题。 有关 Microsoft BizTalk Server 的 64 位支持的常见问题及问题，请参阅[BizTalk Server 64 位支持](http://go.microsoft.com/fwlink/?LinkID=155306)(http://go.microsoft.com/fwlink/?LinkID=155306)。  
  
## <a name="modify-the-process-memory-usage-throttling-threshold"></a>修改限制阈值的进程内存使用量  
 默认情况下，**处理内存使用量**主机限制阈值设置为 25。 如果超出此值时，BizTalk 进程内存使用率为 300 MB 以上，可能会发生限制条件。 在 64 位服务器上，您可以增大此值为 100。 这使得更多的内存消耗由 BizTalk 进程限制发生之前。 有关如何修改限制阈值进程内存使用情况宿主的说明，请参阅[如何修改默认的主机限制设置](http://go.microsoft.com/fwlink/?LinkId=157210)(http://go.microsoft.com/fwlink/?LinkId=157210)。  
  
> [!NOTE]  
>  为进行上述计算，最大可用进程内存不能超过 2 GB 的地址空间大小，即使系统具有 2 GB 以上的物理内存。 不论是 32 位系统还是 64 位系统，进行上述计算均需使用 2 GB 的进程内存上限。 为了防止内存不足错误，建议你不指定一个值，将允许主机实例内存超过 1.54 GB，而不考虑运行 32 位版本的 BizTalk Server 中，如果在 32 位或 64 位操作系统 sy 安装 BizTalk Server 时主干。 例如，如果您为该设置指定从 1 到 100 之间的值，以基于进程内存使用百分比进行阻止，请不要输入大于 75 的值 (.75 * 2GB = 1.54 GB)。 如果你指定的值大于此设置以启动限制基于在以 mb 为单位的指定数目的 100 未输入值大于 1536.If 运行 64 位版本的 BizTalk Server，指定一个值或 100 （100%) 或 2048 (2GB) 来启动 限制使用 2 GB 的可用的最大处理内存时。  
  
## <a name="adapters-that-do-not-support-64-bit-hosts"></a>不支持 64 位主机适配器  
 以下的适配器不支持在 64 位主机实例上运行：  
  
-   FTP 适配器  
  
-   POP3 适配器  
  
 请确保在一个 32 位主机实例中运行这些适配器。  
  
## <a name="configure-the-mimesmime-encoder-to-run-in-32-bit-mode"></a>配置 MIME/SMIME 编码器，以便在 32 位模式下运行  
 在 BizTalk Server 中，MIME/SMIME 编码器管道组件发生故障不具有本机 64 位支持。 这意味着此组件必须运行在 32 位仿真模式进程 (WOW64) 中。 这表示运行此编码器组件（或其所属发送管道）的主机实例必须以 32 位仿真模式运行。 请注意此限制对运行在此主机实例中的其他 BizTalk 元素性能（和其他方面）的影响。