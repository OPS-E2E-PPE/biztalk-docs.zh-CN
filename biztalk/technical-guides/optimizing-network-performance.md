---
title: 优化网络性能 |Microsoft 文档
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
ms.openlocfilehash: 8225bd082140ac1347bc99a91ea209f9d79a8bab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299045"
---
# <a name="optimizing-network-performance"></a>优化网络性能
在 BizTalk Server 环境中的 BizTalk Server 计算机是 SQL 服务器计算机独立开来，BizTalk 服务器处理的每个消息在网络上需要的通信。 这种通信包括 BizTalk Server 计算机和 BizTalk MessageBox 数据库、 BizTalk 管理数据库、 BAM 数据库和其他数据库之间的大量流量。 在高负载情况下，此通信可能会导致大量网络流量，尤其是在网络设置未经过优化，没有足够的网络接口卡已安装，或足够的网络带宽可能成为瓶颈，可用。  
  
 本部分提供了提高网络性能的一些常规建议，并说明可以修改，以优化网络堆栈，以减轻网络上的瓶颈的匹配项的若干注册表条目。  
  
> [!IMPORTANT]  
>  此部分中建议的一些要求修改 Windows 注册表。 对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。 请慎用注册表编辑器，风险自负。 有关如何备份、 还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章[256896，"Windows 注册表信息对于高级用户"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [一般性的指导原则，用于提高网络性能](../technical-guides/general-guidelines-for-improving-network-performance.md)  
  
-   [可以修改为提高网络性能的设置](../technical-guides/settings-that-can-be-modified-to-improve-network-performance.md)  
  
## <a name="see-also"></a>另请参阅  
 [优化性能](../technical-guides/optimizing-performance.md)