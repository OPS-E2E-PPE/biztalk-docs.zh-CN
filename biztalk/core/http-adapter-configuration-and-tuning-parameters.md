---
title: HTTP 适配器配置和优化参数 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, parameters
- configuring [HTTP adapters], parameters
- HTTP adapters, tuning
- RequestQueueSize key [HTTP adapters]
- HttpReceiveThreadsPerCpu key [HTTP adapters]
- HttpOutTimeoutInterval key [HTTP adapters]
- HttpOutInflightSize key [HTTP adapters]
- configuring [HTTP adapters], tuning
- DisableChunkEncoding key [HTTP adapters]
- HttpOutCompleteSize key [HTTP adapters]
ms.assetid: c8989a88-722a-40b5-94cf-4b6840add02e
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db4f4dc4403ddfbf677ac2729c00e2b1976db61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257781"
---
# <a name="http-adapter-configuration-and-tuning-parameters"></a>HTTP 适配器配置和优化参数
通过注册表项和修改 BizTalk Server 安装根目录中的 BTSNTSvc.exe.config 文件，可以访问 HTTP 适配器的一些配置和优化参数。  
  
 **对 HTTP 适配器性能影响的注册表设置**  
  
 下表介绍了影响 HTTP 适配器性能的注册表设置。 注意，默认情况下，注册表中没有 HTTP 适配器项，因此，HTTP 适配器将使用默认设置。 如果需要更改默认设置，则需要在注册表的以下位置下创建下列注册表项：  
  
-   **DisableChunkEncoding**， **RequestQueueSize**，和**HttpReceiveThreadsPerCpu**中必须定义**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**。  
  
-   **HttpOutTimeoutInterval**， **HttpOutInflightSize**，和**HttpOutCompleteSize**中必须定义**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {GUID}** 其中**GUID**是 HTTP 发送处理程序的主机的 ID。  
  
|项名|类型|默认|解释|  
|--------------|----------|-------------|-----------------|  
|**DisableChunkEncoding**|DWORD|0|规定 HTTP 接收适配器在将响应发送回客户端时是否使用 Chunked 编码。<br /><br /> 设置为非零值可为 HTTP 接收适配器响应关闭 Chunked 编码。<br /><br /> **最小值：** 0<br /><br /> **最大值：** 任何非零值|  
|**RequestQueueSize**|DWORD|256|指定 HTTP 接收适配器一次可处理的并行请求数。<br /><br /> **最小值：** 10<br /><br /> **最大值：** 2048年|  
|**HttpReceiveThreadsPerCpu**|DWORD|2|定义每个 CPU 为 HTTP 接收适配器分配的线程数。<br /><br /> **最小值：** 1<br /><br /> **最大值：** 10|  
|**HttpOutTimeoutInterval**|DWORD|2000|定义 HTTP 发送适配器在超时之前等待的时间间隔（秒）。<br /><br /> **最小值：** 500<br /><br /> **最大值：** 10000000|  
|**HttpOutInflightSize**|DWORD|100|此为 BizTalk Server HTTP 发送适配器实例将并行处理的最大 HTTP 请求数。<br /><br /> 延迟的建议的值是之间的 3 到 5 倍， **maxconnection**如下所述的配置文件条目。<br /><br /> **最小值：** 1<br /><br /> **最大值：** 1024年|  
|**HttpOutCompleteSize**|DWORD|5|控制从 HTTP 发送适配器返回的消息批的大小。 如果缓冲区未满且有未完成的响应适配器将等待 1 秒，直到它会将提交批处理。  低延迟方案这应设置为 1，这将允许立即将发送响应消息到的消息框处理的适配器。<br /><br /> **最小值：** 1<br /><br /> **最大值：** 1024年|  
  
 **配置文件条目以控制对特定的目标服务器通过 HTTP 发送适配器进行的并发连接数**  
  
 通过在位于 BizTalk Server 安装根目录的 BTSNTSvc.exe.config 文件中创建一项，可以配置 HTTP 适配器为特定的目标服务器并行打开的连接数。  
  
> [!NOTE]
>  如果 HTTP 和 SOAP 适配器将消息发送到同一目标 HTTP 服务器，则此属性将同时应用于这两个适配器。 “最大连接”属性的默认值为 2，可以为所有 URI 设置的“最大连接”属性的最大值为 20。  
  
 以下为最大连接数属性的配置示例：  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "20" />  
      <add address = "http://www.northwind.com" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅  
 [配置 HTTP 适配器](../core/configuring-the-http-adapter.md)