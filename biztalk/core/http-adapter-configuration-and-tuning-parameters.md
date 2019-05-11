---
title: HTTP 适配器配置和优化参数 |Microsoft Docs
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
ms.openlocfilehash: aaae6d5cf3a5f810a8c8340a07d1a94fab974afe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383024"
---
# <a name="http-adapter-configuration-and-tuning-parameters"></a>HTTP 适配器配置和优化参数
多个配置和优化参数都可以访问 HTTP 适配器通过注册表项和修改位于 BizTalk Server 安装目录的根目录的 BTSNTSvc.exe.config 文件。  
  
 **影响 HTTP 适配器性能的注册表设置**  
  
 下表介绍了影响 HTTP 适配器性能的注册表设置。 请注意，默认情况下有没有 HTTP 适配器项在注册表中，因此，HTTP 适配器使用默认设置。 如果需要更改默认设置，需要在注册表中创建以下注册表项下的以下位置：  
  
-   **DisableChunkEncoding**， **RequestQueueSize**，和**HttpReceiveThreadsPerCpu**必须在定义**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\HttpReceive**。  
  
-   **HttpOutTimeoutInterval**， **HttpOutInflightSize**，和**HttpOutCompleteSize**必须在定义**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {GUID}** 其中**GUID**是 HTTP 发送处理程序主机的 ID。  
  
|密钥名称|类型|默认|解释|  
|--------------|----------|-------------|-----------------|  
|**DisableChunkEncoding**|DWORD|0|来控制是否 HTTP 接收适配器将使用 chunked 编码时将响应发送回客户端。<br /><br /> 设置为非零值以关闭 chunked 编码为 HTTP 接收适配器的响应。<br /><br /> **最小值：** 0<br /><br /> **最大值：** 任何非零值|  
|**RequestQueueSize**|DWORD|256|定义 HTTP 一次接收适配器处理的并发请求数。<br /><br /> **最小值：** 10<br /><br /> **最大值：** 2048|  
|**HttpReceiveThreadsPerCpu**|DWORD|2|定义接收适配器分配给 HTTP 每个 CPU 线程数。<br /><br /> **最小值：** 1<br /><br /> **最大值：** 10|  
|**HttpOutTimeoutInterval**|DWORD|2000|定义 HTTP 发送适配器将超时之前等待的秒的间隔。<br /><br /> **最小值：** 500<br /><br /> **最大值：** 10000000|  
|**HttpOutInflightSize**|DWORD|100|这是 BizTalk Server HTTP 发送适配器实例将处理的并发 HTTP 请求的最大数目。<br /><br /> 建议的延迟值是 3 到 5 倍的之间**maxconnection**如下所述的配置文件条目。<br /><br /> **最小值：** 1<br /><br /> **最大值：** 1024|  
|**HttpOutCompleteSize**|DWORD|5|控件发送适配器从 HTTP 返回消息批的大小。 如果缓冲区未满且存在未完成的响应，适配器将等待 1 秒，直到提交批处理。  对于低延迟方案这应设置为 1，以允许适配器立即将发送响应消息到 messagebox，以进行处理。<br /><br /> **最小值：** 1<br /><br /> **最大值：** 1024|  
  
 **配置文件条目来控制对通过 HTTP 发送适配器的特定目标服务器的并发连接数**  
  
 可以在位于 BizTalk Server 安装目录的根目录的 BTSNTSvc.exe.config 文件中创建一项配置 HTTP 适配器打开为特定目标服务器的并发连接数。  
  
> [!NOTE]
>  如果将消息发送到同一目标 HTTP 服务器时，才能将此属性应用于 HTTP 和 SOAP 适配器。 "连接"属性的默认值为 2，可以为所有 Uri 设置为"maxconnection"属性的最大值为 20。  
  
 下面是最大连接数属性配置的一个示例：  
  
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
  
## <a name="see-also"></a>请参阅  
 [配置 HTTP 适配器](../core/configuring-the-http-adapter.md)