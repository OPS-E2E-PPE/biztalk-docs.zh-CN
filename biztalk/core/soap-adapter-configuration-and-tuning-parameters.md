---
title: SOAP 适配器配置和优化参数 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], tuning
- SOAP adapters, tuning
ms.assetid: 73c175aa-16b9-4620-b303-9092ae29af21
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be6a71938876ad932a58d369abe40d7c8b073f72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277341"
---
# <a name="soap-adapter-configuration-and-tuning-parameters"></a><span data-ttu-id="a6420-102">SOAP 适配器配置和优化参数</span><span class="sxs-lookup"><span data-stu-id="a6420-102">SOAP Adapter Configuration and Tuning Parameters</span></span>
<span data-ttu-id="a6420-103">通过在位于 BizTalk Server 根安装目录的 BTSNTSvc.exe.config 文件中创建一项，可以配置 SOAP 适配器为特定的目标服务器打开的并发连接数。</span><span class="sxs-lookup"><span data-stu-id="a6420-103">You can configure the number of concurrent connections that the SOAP adapter opens for a particular destination server by making an entry in the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6420-104">如果 HTTP 和 SOAP 适配器将消息发送到同一目标 HTTP 服务器，则此属性将同时应用于这两个适配器。</span><span class="sxs-lookup"><span data-stu-id="a6420-104">This property will be applied to both HTTP and SOAP adapters if they send messages to the same destination HTTP server.</span></span> <span data-ttu-id="a6420-105">“最大连接”属性的默认值为 2，可以为所有 URI 设置的“最大连接”属性的最大值为 20。</span><span class="sxs-lookup"><span data-stu-id="a6420-105">The default value for the “maxconnnection” property is 2, the maximum value that can be set for the “maxconnection” property for all URIs is 20.</span></span>  
  
 <span data-ttu-id="a6420-106">以下为最大连接数属性的配置示例：</span><span class="sxs-lookup"><span data-stu-id="a6420-106">The following is an example of the configuration for the maximum connections property:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a6420-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6420-107">See Also</span></span>  
 <span data-ttu-id="a6420-108">[配置 SOAP 适配器](../core/configuring-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a6420-108">[Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="a6420-109">HTTP 适配器配置和优化参数</span><span class="sxs-lookup"><span data-stu-id="a6420-109">HTTP Adapter Configuration and Tuning Parameters</span></span>](../core/http-adapter-configuration-and-tuning-parameters.md)