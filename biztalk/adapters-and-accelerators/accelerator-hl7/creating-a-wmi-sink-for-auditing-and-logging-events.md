---
title: "创建 WMI 审核和日志记录事件接收器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WMI sink
- auditing, WMI sink
- WMI sink, auditing
- logging, WMI sink
- WMI sink, logging
ms.assetid: 5feb1e98-32ed-4505-878e-274028d50c3c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d9592bb8fc140fc088906d9d7e565c5cbc40bb3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-wmi-sink-for-auditing-and-logging-events"></a>为审核和记录的事件创建 WMI 接收器
你可以使用下面的示例代码创建[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]Management Instrumentation (WMI) 接收器监视审核和记录的事件：  
  
 `//Create the WMI query and Event watcher and subscribe to events`  
  
 `ManagementEventWatcher watcher = new ManagementEventWatcher ("root/Default", "select * from  PackageEvent");`  
  
 `ManagementBaseObject evtObj = watcher.WaitForNextEvent();`  
  
 `//Do what you want with the event`  
  
## <a name="see-also"></a>另请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)