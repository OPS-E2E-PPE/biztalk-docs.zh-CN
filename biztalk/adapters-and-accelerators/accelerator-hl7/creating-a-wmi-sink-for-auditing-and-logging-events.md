---
title: 用于审核和日志记录事件创建 WMI 接收器 |Microsoft Docs
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
ms.openlocfilehash: 375a16a338c991f80e6a1ffb079ea15fedc0389c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255676"
---
# <a name="creating-a-wmi-sink-for-auditing-and-logging-events"></a>用于审核和日志记录事件创建 WMI 接收器
可以使用下面的示例代码创建[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]Management Instrumentation (WMI) 接收器以监视审核和日志记录事件：  
  
 `//Create the WMI query and Event watcher and subscribe to events`  
  
 `ManagementEventWatcher watcher = new ManagementEventWatcher ("root/Default", "select * from  PackageEvent");`  
  
 `ManagementBaseObject evtObj = watcher.WaitForNextEvent();`  
  
 `//Do what you want with the event`  
  
## <a name="see-also"></a>请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)