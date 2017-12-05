---
title: "使用 WCF LOB 适配器 SDK 的性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b928eaf-2ab6-40a6-a1dd-804d4e89541e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bfff208920b25ee1a22aa2c3c74feeba42f4b43
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="use-performance-counters-with-the-wcf-lob-adapter-sdk"></a>使用具有 WCF LOB 适配器 SDK 的性能计数器
你可以使用性能工具自动从正在运行的本地或远程计算机中收集性能数据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 你可以定义开始和停止自动日志生成时间、 从单个控制台窗口中，管理多个日志记录会话和上启用要发送的消息的计算机或要满足你的条件时启动的日志设置警报。 本主题讨论的性能计数器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  
  
## <a name="performance-objects-and-counters"></a>性能对象和计数器  
 当你安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，安装名为"ServiceModel 适配器"的单个性能对象。 性能对象包含多个不同的性能计数器。 性能对象测量给定的资源，应用程序或服务的活动。 性能对象和计数器从其获取性能数据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、 功能，和服务计算机上的使用。 此性能数据通常名为组件生成数据。 性能计数器用于收集特定信息或指定的性能对象的数据。  
  
 当从 ServiceModel 适配器性能对象中选择计数器，你可以选择仅通过从选择实例列表中选择的实例监视信息特定的适配器实例。 中的格式将列出每个适配器实例\<ProcessId\>@\<ConnectionString\>。 例如， 115@echo:&#124; &#124; 主机 &#124; temp？ echoprefix = pre 指示 echo 适配器实例 115 的进程中运行。  
  
 有关在 WCF 中的性能计数器的信息，请参阅[WCF 性能计数器](https://msdn.microsoft.com/library/ms735098.aspx)。
  
### <a name="servicemodel-adapters-metadata-cache-performance-counters"></a>ServiceModel 适配器元数据缓存性能计数器  
 下表总结了可以用于监视缓存性能计数器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  
  
|计数器|Description|  
|-------------|-----------------|  
|%缓存读取命中数|读取适配器缓存中的命中的元数据的百分比。|  
|解析的元数据|适配器已解决的元数据项目数。|  
|%缓存已满|中使用的缓存大小限制的百分比。|  
  
### <a name="servicemodel-adapters-connection-performance-counters"></a>ServiceModel 适配器连接性能计数器  
 下表总结了可以用于监视的连接性能计数器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  
  
|计数器|Description|  
|-------------|-----------------|  
|中止的连接|中止的目标系统连接数。|  
|使用连接|当前正在使用目标系统连接数。|  
|打开的连接|当前打开的目标系统连接数。|  
|准备连接|可用目标系统连接数。|  
|挂起的连接请求|大挂起目标系统连接请求。|  
  
### <a name="servicemodel-adapters-message-exchange-performance-counters"></a>ServiceModel 适配器消息交换性能计数器  
 下表总结了可以用于监视的消息交换性能计数器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  
  
|计数器|Description|  
|-------------|-----------------|  
|出站调用|从适配器到目标系统的出站调用次数。|  
|出站 Calls/sec|出站调用数每秒从适配器到目标系统。|  
  
## <a name="see-also"></a>另请参阅  
 [解决使用 WCF LOB 适配器 SDK 创建的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)