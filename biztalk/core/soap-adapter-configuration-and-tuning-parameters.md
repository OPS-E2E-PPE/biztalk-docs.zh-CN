---
title: SOAP 适配器配置和优化参数 |Microsoft Docs
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
ms.openlocfilehash: 170743f3bd352856fa5c26acabb71f9c9261f2ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314563"
---
# <a name="soap-adapter-configuration-and-tuning-parameters"></a>SOAP 适配器配置和优化参数
可以配置 SOAP 适配器为特定目标服务器打开位于 BizTalk Server 安装目录的根目录的 BTSNTSvc.exe.config 文件中创建一项的并发连接数。  
  
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
 [配置 SOAP 适配器](../core/configuring-the-soap-adapter.md)   
 [HTTP 适配器配置和优化参数](../core/http-adapter-configuration-and-tuning-parameters.md)