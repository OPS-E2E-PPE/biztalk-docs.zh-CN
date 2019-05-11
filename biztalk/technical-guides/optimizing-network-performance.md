---
title: 优化网络性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6c3985a-48b3-489b-8fe3-3b7bfd0515f9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30d58dcac30f2f2395aa9407aaf18fd039c3458f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291380"
---
# <a name="optimizing-network-performance"></a>优化网络性能
在 BizTalk Server 环境中 BizTalk Server 计算机的 SQL 服务器计算机独立开来的位置，由 BizTalk Server 处理的每个消息需要通过网络通信。 此通信包括 BizTalk Server 计算机和 BizTalk MessageBox 数据库、 BizTalk 管理数据库、 BAM 数据库和其他数据库之间的大量流量。 在高负载情况下，此通信可能会导致大量网络流量，可能成为瓶颈，尤其是在没有优化网络设置、 安装没有足够的网络接口卡，或没有足够的网络带宽可用。  
  
 本部分提供了提高网络性能的一些常规建议，并介绍了几个可以修改，以优化网络堆栈，以缓解瓶颈在网络上的匹配项的注册表项。  
  
> [!IMPORTANT]  
>  在本部分中建议的一些要求修改 Windows 注册表。 对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章[256896，"Windows 注册表信息对于高级用户"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [优化网络性能的通用指南](../technical-guides/general-guidelines-for-improving-network-performance.md)  
  
-   [优化网络性能的可修改设置](../technical-guides/settings-that-can-be-modified-to-improve-network-performance.md)  
  
## <a name="see-also"></a>请参阅  
 [优化性能](../technical-guides/optimizing-performance.md)