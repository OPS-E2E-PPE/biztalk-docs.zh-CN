---
title: WCF 适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, WCF adapters
- performance, performance counters
- WCF adapters, performance
ms.assetid: 9feb052f-5674-419f-84ab-9b5d312a04a5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04a9aa02d0206f4edb5b50943718b6c62d647966
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395939"
---
# <a name="wcf-adapters-performance-counters"></a>WCF 适配器性能计数器
性能计数器可用于监视的系统的站点上的服务执行的工作的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。 WCF 适配器不提供自身的性能计数器。 但是，可以监视性能计数器的 Windows Communication Foundation (WCF) 以衡量性能的 WCF 接收位置。 若要为 WCF 接收位置使用 WCF 性能计数器，您必须启用运行接收位置的主机实例的性能计数器。  
  
> [!NOTE]
>  WCF 性能计数器不可用于 WCF 发送端口。  
  
 对于进程内 WCF 适配器，可以通过 BTSNTSvc.exe.config 文件启用性能计数器。 对于独立 WCF 适配器，可以修改 Web.config 文件以启用性能计数器。 有关 WCF 性能计数器的详细信息，请参阅"WCF 性能计数器"处[ http://go.microsoft.com/fwlink/?LinkID=87245 ](http://go.microsoft.com/fwlink/?LinkID=87245)。  
  
## <a name="enabling-the-wcf-performance-counters-for-the-wcf-receive-locations"></a>为 WCF 接收位置启用 WCF 性能计数器  
 对于进程内 WCF 适配器，可以通过 BTSNTSvc.exe.config 文件启用性能计数器。  
  
 对于独立 WCF 适配器，您可以通过修改 BizTalk WCF 服务发布向导创建 Web 应用程序文件夹中的 Web.config 文件中启用 WCF 跟踪  
  
 若要修改 BTSNtSvc.exe.config 或 Web.config，请打开配置文件，然后配置 WCF 跟踪，如下面的配置示例中所示：  
  
> [!NOTE]
>  BTSNTSvc.exe.config 文件始终与 BTSNTSvc.exe 文件，这通常是相同的目录中位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。  
  
```  
<configuration>  
 <system.serviceModel>  
 <diagnostics performanceCounters="All" />  
 </system.serviceModel>  
 </configuration>  
```  
  
 **PerformanceCounters**属性可设置为启用特定类型的性能计数器。 有效值为  
  
- **全部**：所有类别计数器 (**ServiceModelService**， **ServiceModelEndpoint**，并**ServiceModelOperation**) 启用。  
  
- **ServiceOnly**:仅**ServiceModelService**启用类别计数器。  
  
- **OFF**：禁用 ServiceModel * 性能计数器。 这是默认值。  
  
  修改后的 BTSNTSvc.exe.config 文件，您必须重新启动主机实例运行的进程内 WCF 接收位置。  
  
## <a name="types-of-performance-counters"></a>性能计数器的类型  
 WCF 性能计数器可分为三个不同级别： 服务、 终结点和操作。  
  
 **服务性能计数器**  
  
 服务性能计数器测量作为一个整体的服务行为，并可用于诊断服务整体性能。 下可找到这些**ServiceModelService 3.0.0.0**性能对象时使用性能监视器查看。 使用以下模式命名实例：  
  
```  
biztalkserviceinstance@<URI of a receive location>  
```  
  
 每个接收位置，则 WCF 适配器会创建单独的服务主机，因为每个接收位置创建性能计数器实例。 有关实现 WCF 的服务类的详细信息的服务协定，请参阅**BizTalkServiceInstance 类** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
  
 **终结点性能计数器**  
  
 终结点性能计数器，可查看数据专用于反映将终结点如何接受消息。 下可找到这些**ServiceModelEndpoint 3.0.0.0**性能对象时使用性能监视器查看。 使用以下模式命名实例：  
  
```  
biztalkserviceinstance.<WCF service contract>@<URI of a receive location>  
```  
  
 每个接收位置创建一个性能计数器实例。 在上面的模式的 WCF 服务约定名称表示 WCF 适配器选择用于通过接收位置接收消息的服务约定。 有关 WCF 适配器如何选择服务协定从可用 WCF 服务协定，请参阅**WCF 适配器服务协定引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
 **操作性能计数器**  
  
 下找到操作性能计数器**ServiceModelOperation 3.0.0.0**性能对象时使用性能监视器查看。 每个接收位置，会创建两个性能计数器实例。 一个对象实例的名为使用以下模式：  
  
```  
biztalkserviceinstance.<WCF service contract>biztalksubmit@<URI of a receive location>  
```  
  
 在上面的模式的 WCF 服务约定名称表示 WCF 适配器选择用于通过接收位置接收消息的服务约定。 **biztalksubmit**是服务协定中声明的操作名称，将导致运行时元数据中创建 WSDL 操作。  
  
> [!NOTE]
>  有关 WCF 适配器如何选择服务协定从可用 WCF 服务协定，请参阅**WCF 适配器服务协定引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 另一个对象实例使用以下模式进行命名：  
  
```  
biztalkserviceinstance.<WCF service contract><twowaymethod|onewaymethod>@<URI of a receive location>  
```  
  
 此性能计数器实例表示异步处理通过接收位置传入的消息的操作。 此实例的操作名称部分可以是**twowaymethod**或**onewaymethod**根据 WCF 适配器的接收位置中使用的类型。 如果使用 Wcf-netmsmq 适配器，实例拥有**onewaymethod**创建操作名称。 对于其他适配器， **twowaymethod**用于操作名称部分。