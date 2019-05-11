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
ms.openlocfilehash: 4a747cd27a5629dd551d5e9137c59fcd76fe5509
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306089"
---
# <a name="considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system"></a>在 64 位 Windows 操作系统上使用 BizTalk Server 时的注意事项
当使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上 64 位 Windows 操作系统，请务必考虑本主题中所述的问题。 与 Microsoft BizTalk Server 的 64 位支持相关的问题方面的常见问题，请参阅[BizTalk Server 64 位支持](http://go.microsoft.com/fwlink/?LinkID=155306)(<http://go.microsoft.com/fwlink/?LinkID=155306>)。  
  
## <a name="modify-the-process-memory-usage-throttling-threshold"></a>修改进程内存使用量限制阈值  
 默认情况下**进程的内存利用率**主机阻止阈值设置为 25。 如果超出此值，BizTalk 进程内存使用率超过 300 MB，可能会出现限制情况。 在 64 位服务器上，可以增加此值设置为 100。 这允许更多的内存消耗 BizTalk 进程之前会发生限制。 有关如何修改进程内存使用情况主机阻止阈值的说明，请参阅[如何修改默认主机阻止设置](http://go.microsoft.com/fwlink/?LinkId=157210)(http://go.microsoft.com/fwlink/?LinkId=157210)。  
  
> [!NOTE]  
>  即使系统具有 2 GB 以上物理内存的最大可用进程内存不能进行上述计算，2 GB 的地址空间大小。 2 GB 进程内存上限限制用于进行上述计算 32 位和 64 位系统上。 为了防止内存不足错误，建议您不要指定一个值，会使主机实例内存超过 1.54 GB，而不考虑运行 32 位版本的 BizTalk Server 中，如果在 32 位或 64 位操作系统 sy 安装 BizTalk Server 时stem。 例如，如果指定一个介于 1 和 100 之间的此设置以基于进程内存使用百分比，不输入大于 75 (.75 * 2 GB = 1.54 GB) 的值。 如果您指定的值大于 100 的此设置以基于指定的数量，以 mb 为单位，不要输入大于 1536.If 运行 64 位版本的 BizTalk Server 中，指定一个值或任一 100 （100%)或者，使用 2048 (2GB) 启动时可用的最大进程 2 GB 的内存限制。  
  
## <a name="adapters-that-do-not-support-64-bit-hosts"></a>不支持 64 位主机的适配器  
 以下适配器不支持 64 位主机实例上运行：  
  
- FTP 适配器  
  
- POP3 适配器  
  
  请确保在 32 位主机实例中运行这些适配器。  
  
## <a name="configure-the-mimesmime-encoder-to-run-in-32-bit-mode"></a>配置 MIME/SMIME 编码器，以便在 32 位模式下运行  
 在 BizTalk Server 中，MIME/SMIME 编码器管道组件就完了没有支持本机 64 位模式。 这意味着，此组件必须在 32 位仿真模式进程 (WOW64) 中运行。 这意味着，必须在 32 位仿真模式下运行此编码器组件 （或它的一部分的发送管道） 运行的主机实例。 要注意的性能 （和其他） 的此限制对此相同的主机实例中运行的 BizTalk 的其他元素的含义。