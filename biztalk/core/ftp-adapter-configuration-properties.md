---
title: FTP 适配器配置属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, adapters
- FTP adapters, properties
- FTP adapters, code sample
- FTP adapters, send ports
- FTP adapters, receive locations
- send ports, adapters
ms.assetid: 88a2084e-cb26-4136-9077-8b9463062ccc
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29124c17603abbc9b38a078238d13cdfb1c992e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975267"
---
# <a name="ftp-adapter-configuration-properties"></a>FTP 适配器配置属性
下表列出了可为 FTP 适配器接收位置设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|URI|VT_BSTR|指定接收位置监视的位置的完整路径。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
|serverAddress|VT_BSTR|指定 FTP 服务器的服务器名称或 IP 地址。|无|无|  
|serverPort|VT_BSTR|指定用来与目标 FTP 服务器进行通信的 TCP 端口。|无|无|  
|userName|VT_BSTR|指定用于访问 FTP 服务器的用户名。|无|无|  
|password|VT_BSTR|指定用来访问 FTP 服务器的密码。|在导出绑定文件时此值始终会被屏蔽。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此属性中填充密码。|无|  
|fileMask|VT_BSTR|指定传输文件时使用的文件掩码筛选器。|无|无|  
|targetFolder|VT_BSTR|指定 FTP 服务器上的轮询位置。|无|无|  
|commandLogFilename|VT_BSTR|指定要保存日志文件的副本的位置。|无|此文件用于诊断发送或接收通过 FTP 适配器的文件时的错误条件。|  
|representationType|VT_BSTR|选择 FTP 适配器接收数据的方式。|有效值为<br /><br /> -二进制<br />ASCII|默认值为二进制。|  
|spoolingFolder|VT_BSTR|指定 FTP 服务器上的临时文件夹的位置。 此位置用于保证在传输失败后可以进行恢复。|无|无|  
|receiveDataTimeOut|VT_BSTR|指定接收调用将中止之前的时间（以毫秒为单位）。 这用来防止较慢的服务器导致接收位置挂起。|无|默认值为 90000。|  
|maximumBatchSize|VT_BSTR|指定每个 BizTalk Server 批的最大字节数。|无|无|  
|maximumNumberOfFiles|VT_BSTR|指定每个 BizTalk Server 批的最大文件数。|无|无|  
|passiveMode|VT_BSTR|指定适配器连接到 FTP 服务器的模式。|有效值为<br /><br /> -被动<br />-活动|默认值为“Active”。|  
|useNLST|VT_BSTR|指定此值为“是”，只检索文件名而非默认系统定义的文件列表。|有效值为<br /><br /> -是<br />-无|默认值为：否。|  
|beforeGet|VT_BSTR|指定在文件 GET 之前执行的 FTP 命令。|用分号 （;） 的单独命令**注意：** QUIT 命令文件 GET 之前不受支持。|无|  
|afterGet|VT_BSTR|指定在文件 GET 后执行的 FTP 命令。|用分号 (;) 分隔命令|无|  
|firewallType|VT_BSTR|指定部署的防火墙的类型。|有效值为<br /><br /> -无<br />-Socks 4<br />-Socks 5|默认值为 None。|  
|firewallAddress|VT_BSTR|指定防火墙的地址（DNS 名称或 IP 地址）。|无|无|  
|firewallPort|VT_BSTR|指定防火墙的端口。|有效值为从 1 到 65535 之间。|默认值为 21。|  
|firewallUserName|VT_BSTR|指定防火墙的用户名。|无|无|  
|firewallPassword|VT_BSTR|指定防火墙的密码。|无|无|  
|pollingUnitOfMeasure|VT_BSTR|指定 pollingInterval 属性的单位类型。|有效值为<br /><br /> -秒<br />-分钟<br />-小时数<br />-天数|默认值是“秒”。|  
|pollingInterval|VT_BSTR|指定为轮询此位置的间隔值。|无|若要连续轮询，请将此值设置为 0。<br /><br /> 默认值为 60。|  
|redownloadInterval|VT_BSTR|指定 FTP 适配器将再次下载该文件的时间间隔（以秒为单位）。|该属性仅在 deleteAfterDownload 和 enableTimeComparison 属性都设置为“否”时适用。|值为“-1”表示适配器将不再下载该文件。<br /><br /> 默认值为-1。|  
|ssoAffiliateApplication|VT_BSTR|指定单一登录 (SSO) 关联应用程序。|无|无|  
|errorThreshold|VT_BSTR|指定 BizTalk Server 可能会遇到的错误数禁用该位置之前。|无|默认值为 10。|  
|maxFileSize|VT_BSTR|指定可下载文件的最大大小 (MB)。|无|0 值表示对文件大小没有限制。<br /><br /> 默认值为 100。|  
|useSsl|VT_BSTR|如果 FTP 适配器在与 FTPS 服务器通信时必须使用 SSL，则指定此值为“是”。|有效值为<br /><br /> -是<br />-无|默认值为：否。|  
|useDataProtection|VT_BSTR|如果 FTP 适配器在向 FTPS 服务器发送文件和从其接收文件时必须使用 SSL 加密，则将此值指定为“是”。|如果 useSsl 属性被设置为“是”，则此属性将有效。<br /><br /> 有效值为<br /><br /> -是<br />-无|默认值为是。|  
|ftpsConnMode|VT_BSTR|指定到 FTPS 服务器的 SSL 连接模式。|有效值为<br /><br /> 显式<br />隐式|默认值为“显性”。|  
|clientCertificateHash|VT_BSTR|指定必须使用的客户端证书的 SHA1 哈希在 SSL 协商。|无|基于此哈希，从运行 BizTalk 主机实例的用户帐户的个人存储中提取客户端证书。|  
|deleteAfterDownload|VT_BSTR|如果在下载完成之后适配器必须从 FTP 服务器删除该文件，则指定此值为“是”。|有效值为<br /><br /> -是<br />-无|默认值为是。|  
|enableTimeComparison|VT_BSTR|如果在文件的时间戳中出现更改时适配器必须再次下载该文件，则指定此值为“是”。|此属性仅当 deleteAfterDownload 设置为“否”时才有效。<br /><br /> 目标 FTP 服务器必须为此功能支持 MDTM 命令。<br /><br /> 有效值为<br /><br /> -是<br />-无|默认值为：否。|  
  
 以下代码显示用于设置这些属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>ftp://localhost:21/in/*.xml</uri><serverAddress>localhost</serverAddress><serverPort>21</serverPort><userName>domain\testuser</userName><password>******</password><fileMask>*.xml</fileMask><targetFolder>in</targetFolder><commandLogFilename>c:\temp\realftplog.txt</commandLogFilename><representationType>binary</representationType><maximumBatchSize>0</maximumBatchSize><maximumNumberOfFiles>0</maximumNumberOfFiles><passiveMode>False</passiveMode><firewallType>NoFirewall</firewallType><firewallPort>21</firewallPort><pollingUnitOfMeasure>Seconds</pollingUnitOfMeasure><pollingInterval>5</pollingInterval><errorThreshold>10</errorThreshold><maxFileSize>5000</maxFileSize><useSsl>False</useSsl><useDataProtection>True</useDataProtection><ftpsConnMode>Explicit</ftpsConnMode><clientCertificateHash>‎bc 32 2c a9 22 75 6a 3f e4 f7 a9 b1 b3 3a 24 20 23 53 68 49</clientCertificateHash><deleteAfterDownload>True</deleteAfterDownload><enableTimeComparison>False</enableTimeComparison></Config></AdapterConfig></CustomProps>  
```  
  
 下表列出了可为 FTP 适配器发送端口设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|URI|VT_BSTR|指定到数据发送目标位置的完整路径。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
|serverAddress|VT_BSTR|指定的防火墙，DNS 名称或 IP 地址的地址。|无|无|  
|serverPort|VT_BSTR|指定 FTP 服务器的端口地址。|无|默认值为 21。|  
|userName|VT_BSTR|指定登录 FTP 服务器所用的用户名。|无|无|  
|password|VT_BSTR|指定登录 FTP 服务器所用的密码。|在导出绑定文件时此值始终会被屏蔽。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此属性中填充密码。|无|  
|accountName|VT_BSTR|指定 FTP 服务器的帐户名。|可选|无|  
|targetFolder|VT_BSTR|指定将文件移至 FTP 服务器上的位置。|无|无|  
|targetFileName|VT_BSTR|指定文件的替换名称。 保留默认名称将确保每个发送消息的消息名称是唯一的。|无|默认值为 %messageid%.xml。|  
|commandLogFilename|VT_BSTR|指定要保存日志文件的副本的位置。 使用该日志文件在通过 FTP 服务器发送或接收文件时诊断错误情况。|无|无|  
|representationType|VT_BSTR|选择 FTP 发送数据的方式，可以是二进制或 ASCII 形式。|有效值为<br /><br /> -二进制<br />ASCII|默认值为二进制。|  
|beforePut|VT_BSTR|指定在 PUT 文件之前要运行的 FTP 命令，例如，用于在 FTP 服务器上更改默认值的命令。|用分号 (;) 分隔命令。 **注意：** QUIT 命令文件 PUT 之前不受支持。|不需要 open 命令。|  
|afterPut|VT_BSTR|指定在 PUT 文件后要运行的 FTP 命令。|用分号 (;) 分隔命令。|无|  
|allocateStorage|VT_BSTR|指定是否为旧式主机系统分配存储空间。|有效值为<br /><br /> -是<br />-无|默认值为：否。|  
|spoolingFolder|VT_BSTR|指定 FTP 服务器上的临时文件夹的位置。 如果传输模式是二进制，则使用此选项可保证从传输失败中恢复。 如果传输模式是 ASCII，适配器将重新启动上载。|无|无|  
|connectionLimit|VT_BSTR|指定服务器允许的并行打开的最大 FTP 连接数。|无|0 表示无限制。|  
|passiveMode|VT_BSTR|指定是使用被动模式还是主动模式。|有效值为<br /><br /> -True （被动模式）<br />为 false （主动模式）|默认值为 False（主动模式）。|  
|firewallType|VT_BSTR|选择部署的防火墙的类型。|有效值为<br /><br /> -Socks 4<br />-Socks 5<br />-无|默认值为 None。|  
|firewallAddress|VT_BSTR|指定的防火墙，DNS 名称或 IP 地址的地址。|无|无|  
|firewallPort|VT_BSTR|指定防火墙的端口。|有效值为从 1 到 65535 之间。|默认值为 21。|  
|firewallUserName|VT_BSTR|指定防火墙的用户名。|无|无|  
|firewallPassword|VT_BSTR|指定防火墙的密码。|在导出绑定文件时此值始终会被屏蔽。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此属性中填充密码。|无|  
|ssoAffiliateApplication|VT_BSTR|指定单一登录 (SSO) 关联应用程序。|无|无|  
|useSsl|VT_BSTR|如果 FTP 适配器在与 FTPS 服务器通信时必须使用 SSL，则指定此值为“是”。|有效值为<br /><br /> -是<br />-无|默认值为：否。|  
|useDataProtection|VT_BSTR|如果 FTP 适配器在向 FTPS 服务器发送文件和从其接收文件时必须使用 SSL 加密，则将此值指定为“是”。|此属性在 useSsL 设置为“是”时有效。<br /><br /> 有效值为<br /><br /> -是<br />-无|默认值为是。|  
|ftpsConnMode|VT_BSTR|指定到 FTPS 服务器的 SSL 连接模式。|有效值为<br /><br /> 显式<br />隐式|默认值为“显性”。|  
|clientCertificateHash|VT_BSTR|指定必须在 SSL 协商中使用的客户端证书的 SHA1 哈希。|无|基于此哈希，从运行 BizTalk 主机实例的用户帐户的个人存储中提取客户端证书。|  
  
 以下代码显示用于设置这些属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><serverAddress>TestServer</serverAddress><serverPort>21</serverPort><userName>testuser</userName><password>******</password><accountName>testuser</accountName><targetFolder>output</targetFolder><targetFileName>%MessageID%.xml</targetFileName><commandLogFilename>c:\logfile\ftpsendlog.txt</commandLogFilename><representationType>binary</representationType><beforePut>CDW dir</beforePut><afterPut>CDUP </afterPut><allocateStorage>False</allocateStorage><spoolingFolder>tempfolder</spoolingFolder><connectionLimit>0</connectionLimit><passiveMode>False</passiveMode><firewallType>Socks4</firewallType><firewallAddress>TestServer</firewallAddress><firewallPort>21</firewallPort><firewallUserName>domain\testuser</firewallUserName><firewallPassword>******</firewallPassword><useSsl>False</useSsl><useDataProtection>True</useDataProtection><ftpsConnMode>Explicit</ftpsConnMode><clientCertificateHash>‎bc 32 2c a9 22 75 6a 3f e4 f7 a9 b1 b3 3a 24 20 23 53 68 49</clientCertificateHash><uri>ftp://TestServer:21/output/%MessageID%.xml</uri></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  在指定适配器使用适配器框架构建的 TransportTypeData 配置数据时，必须要使用的所有名称/值对都存储在\<AdapterConfig\>元素。 由于\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型则\<\>数据中的字符必须进行转义。