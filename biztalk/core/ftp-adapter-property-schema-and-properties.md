---
title: FTP 适配器属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [FTP adapters], schemas
- FTP adapters, properties
- BeforePut property [FTP adapters]
- PassiveMode property [FTP adapters]
- configuring [FTP adapters], properties
- UserName property, FTP adapters
- SSOAffiliateApplication property [FTP adapters]
- AfterPut property [FTP adapters]
- ReceivedFileName property [FTP adapters]
- RepresentationType property [FTP adapters]
- SpoolingFolder property [FTP adapters]
- FTP adapters, schemas
- CommandLogFileName property [FTP adapters]
- AllocateStorage property [FTP adapters]
- schemas, FTP adapters
- Password property [FTP adapters]
- MaxConnections property [FTP adapters]
ms.assetid: 677fdb61-c2b0-4df2-a826-840113e61e8b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b61a9bf97f3003a83d148b1c800c13216360ef3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387782"
---
# <a name="ftp-adapter-property-schema-and-properties"></a>FTP 适配器属性架构和属性
下表包含 FTP 适配器属性架构中的属性。  
  
 **Namespace**： http://schemas.microsoft.com/BizTalk/2003/ftp-properties  
  
|“属性”|类型|Description|  
|----------|----------|-----------------|  
|**RepresentationType**|xs:string|指定 FTP 适配器发送数据的方式。<br /><br /> **有效值：** 二进制或 ASCII|  
|**SSOAffiliateApplication**|xs:string|指定的企业单一登录关联应用程序使用 FTP 发送端口上。|  
|**UserName**|xs:string|指定要发送消息时登录到 FTP 服务器的用户名。|  
|**密码**|xs:string|指定要发送消息时登录到 FTP 服务器时使用的密码。|  
|**BeforePut**|xs:string|指定要在文件 PUT，例如，若要更改默认值在 FTP 服务器上的命令之前运行的 FTP 命令。 用分号 （;） 分隔命令。 没有打开命令是必需的。|  
|**AfterPut**|xs:string|指定要在文件 PUT 后运行的 FTP 命令。 用分号 （;） 分隔命令。|  
|**ReceivedFileName**|xs:string|指定 FTP 适配器从中读取消息的文件的完整名称。|  
|**MaxConnections**|xs:unsignedInt|指定的最大并发可打开到服务器的 FTP 连接数。 值为 0 表示没有限制。|  
|**CommandLogFileName**|xs:string|指定要保存一份可用于发送或接收通过 FTP 文件时诊断错误情况的日志文件的位置。|  
|**AllocateStorage**|xs:boolean|此选项已弃用 BizTalk Server 中，建议不要使用此属性。|  
|**PassiveMode**|xs:boolean|指定适配器连接到 FTP 服务器的模式。<br /><br /> 在主动模式下，FTP 服务器连接到由 FTP 适配器打开的端口。 在被动模式下，FTP 适配器连接到 FTP 服务器打开的端口。<br /><br /> 如果**PassiveMode**为 false，则适配器将连接到 FTP 服务器使用主动模式。 此属性的默认值为 false。|  
|**SpoolingFolder**|xs:string|指定 FTP 服务器上的临时文件夹的位置。 此位置用于确保在传输失败进行恢复。|  
|**UseSsl**|xs:boolean|指定 FTP 适配器是否必须使用 SSL 与 FTPS 服务器进行通信。|  
|**UseDataProtection**|xs:boolean|指定是否为文件传输使用 SSL 加密。 如果适配器必须使用 SSL 加密，它将发送和接收来自 FTPS 服务器数据文件时，请选择 true。 请选择 false 以发送和接收数据文件以纯文本形式的适配器。|  
|**FtpsConnectionMode**|xs:string|指定与 FTPS 服务器建立 SSL 连接模式。<br /><br /> **有效的值：** 隐式或显式|  
|**ClientCertificateHash**|xs:string|指定在安全套接字层 (SSL) 协商中必须使用的客户端证书的 SHA1 哈希。<br /><br /> 基于此哈希值，客户端证书提取其下运行的 BizTalk 主机实例的用户帐户的个人存储中。|  
  
## <a name="see-also"></a>请参阅  
 [配置 FTP 适配器](../core/configuring-the-ftp-adapter.md)
 
 [有关 FTP 适配器的最佳做法和建议](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)
 
 [FTP 适配器](../core/ftp-adapter.md)