---
title: 创建 WMI 审核和日志记录事件接收器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WMI sink
- auditing, WMI sink
- WMI sink, auditing
- logging, WMI sink
- WMI sink, logging
ms.assetid: 5feb1e98-32ed-4505-878e-274028d50c3c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d9592bb8fc140fc088906d9d7e565c5cbc40bb3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204549"
---
# <a name="creating-a-wmi-sink-for-auditing-and-logging-events"></a><span data-ttu-id="0d6eb-102">为审核和记录的事件创建 WMI 接收器</span><span class="sxs-lookup"><span data-stu-id="0d6eb-102">Creating a WMI Sink for Auditing and Logging Events</span></span>
<span data-ttu-id="0d6eb-103">你可以使用下面的示例代码创建[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]Management Instrumentation (WMI) 接收器监视审核和记录的事件：</span><span class="sxs-lookup"><span data-stu-id="0d6eb-103">You can use the following sample code to create a [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI) sink to monitor auditing and logging events:</span></span>  
  
 `//Create the WMI query and Event watcher and subscribe to events`  
  
 `ManagementEventWatcher watcher = new ManagementEventWatcher ("root/Default", "select * from  PackageEvent");`  
  
 `ManagementBaseObject evtObj = watcher.WaitForNextEvent();`  
  
 `//Do what you want with the event`  
  
## <a name="see-also"></a><span data-ttu-id="0d6eb-104">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d6eb-104">See Also</span></span>  
 [<span data-ttu-id="0d6eb-105">编程指南</span><span class="sxs-lookup"><span data-stu-id="0d6eb-105">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)