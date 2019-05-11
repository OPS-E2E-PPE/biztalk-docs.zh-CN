---
title: FTP 适配器配置属性 |Microsoft Docs
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
ms.openlocfilehash: aae34d48585db6025a6270388a724faf2a45f511
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387875"
---
# <a name="ftp-adapter-configuration-properties"></a>FTP 适配器配置属性
下表列出了可以设置为 FTP 适配器的配置属性接收位置：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|指定接收位置所监视的位置的完整路径。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
|serverAddress|VT_BSTR|指定服务器名称或 FTP 服务器的 IP 地址。|None|None|  
|serverPort|VT_BSTR|指定要对其与目标 FTP 服务器进行通信的 TCP 端口。|None|None|  
|userName|VT_BSTR|指定用于访问 FTP 服务器的用户名。|None|None|  
|password|VT_BSTR|指定用于访问 FTP 服务器的密码。|导出绑定文件时，此值始终会被屏蔽。 此属性前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。|None|  
|fileMask|VT_BSTR|指定文件掩码筛选器以传输文件时使用。|None|None|  
|targetFolder|VT_BSTR|指定 FTP 服务器上的轮询位置。|None|None|  
|commandLogFilename|VT_BSTR|指定要保存日志文件的副本的位置。|None|此文件用于发送或接收通过 FTP 适配器的文件时诊断错误情况。|  
|representationType|VT_BSTR|选择 FTP 适配器接收数据的方式。|有效值为<br /><br /> -二进制<br />-   ASCII|默认值为二进制文件。|  
|spoolingFolder|VT_BSTR|指定 FTP 服务器上的临时文件夹的位置。 此位置用于保证从传输失败中的恢复。|None|None|  
|receiveDataTimeOut|VT_BSTR|接收调用将中止之前，以毫秒为单位指定的时间。 这用于防止缓慢服务器造成接收位置挂起。|None|默认值为 90000。|  
|maximumBatchSize|VT_BSTR|指定最大的每个 BizTalk Server 批的字节数。|None|None|  
|maximumNumberOfFiles|VT_BSTR|指定每个 BizTalk Server 批的文件的最大数目。|None|None|  
|passiveMode|VT_BSTR|指定适配器连接到 FTP 服务器的模式。|有效值为<br /><br /> -被动<br />-   Active|默认值为处于活动状态。|  
|useNLST|VT_BSTR|指定此值为是将只检索文件名而不是默认系统定义的文件列表。|有效值为<br /><br /> -是<br />-无|默认值是不可以。|  
|beforeGet|VT_BSTR|指定要在文件 GET 之前执行的 FTP 命令。|用分号 （;） 分隔命令**注意：** 在文件 GET 之前不支持 QUIT 的命令。|None|  
|afterGet|VT_BSTR|指定要在文件 GET 后执行的 FTP 命令。|用分号 （;） 分隔命令|None|  
|firewallType|VT_BSTR|指定部署的防火墙的类型。|有效值为<br /><br /> -None<br />-Socks 4<br />-Socks 5|默认值为 None。|  
|firewallAddress|VT_BSTR|指定的地址的防火墙 （DNS 名称或 IP 地址）。|None|None|  
|firewallPort|VT_BSTR|指定防火墙的端口。|有效值为从 1 到 65535 之间。|默认值为 21。|  
|firewallUserName|VT_BSTR|指定防火墙的用户名。|None|None|  
|firewallPassword|VT_BSTR|指定防火墙的密码。|None|None|  
|pollingUnitOfMeasure|VT_BSTR|指定 pollingInterval 属性的单位类型。|有效值为<br /><br /> / 字节秒<br />-分钟<br />小时数<br />-天|默认值为秒。|  
|pollingInterval|VT_BSTR|指定轮询此位置的时间间隔值。|None|若要连续轮询，请将此值设置为 0。<br /><br /> 默认值为 60。|  
|redownloadInterval|VT_BSTR|以秒为单位在其后 FTP 适配器将再次下载文件中指定的间隔。|此属性才适用，仅当 deleteAfterDownload 和 enableTimeComparison 属性设置为 no。|值为-1 指示该适配器将再次下载该文件。<br /><br /> 默认值为-1。|  
|ssoAffiliateApplication|VT_BSTR|指定单一登录 (SSO) 关联应用程序。|None|None|  
|errorThreshold|VT_BSTR|指定 BizTalk Server 可能会遇到的错误数之前禁用该位置。|None|默认值为 10。|  
|maxFileSize|VT_BSTR|指定可下载的最大文件大小，以兆字节表示。|None|值为 0 指示文件大小没有限制。<br /><br /> 默认值为 100。|  
|useSsl|VT_BSTR|指定此值为是，如果 FTP 适配器必须使用 SSL 与 FTPS 服务器通信时。|有效值为<br /><br /> -是<br />-无|默认值是不可以。|  
|useDataProtection|VT_BSTR|指定此值为是，如果 FTP 适配器必须使用 SSL 加密时发送和接收文件到和从 FTPS 服务器。|如果 useSsl 属性被设置为是，此属性才有效。<br /><br /> 有效值为<br /><br /> -是<br />-无|默认值为是。|  
|ftpsConnMode|VT_BSTR|指定与 FTPS 服务器建立 SSL 连接模式。|有效值为<br /><br /> -   Explicit<br />隐式|默认值为显性。|  
|clientCertificateHash|VT_BSTR|指定在 SSL 协商中必须使用的客户端证书的 SHA1 哈希。|None|基于此哈希值，客户端证书提取其下运行的 BizTalk 主机实例的用户帐户的个人存储中。|  
|deleteAfterDownload|VT_BSTR|指定此值为是如果适配器必须后删除该文件从 FTP 服务器下载已完成。|有效值为<br /><br /> -是<br />-无|默认值为是。|  
|enableTimeComparison|VT_BSTR|指定此值为是如果适配器必须在文件的时间戳中的更改时再次下载该文件。|此属性才有效，仅当 deleteAfterDownload 设置为 no。<br /><br /> 目标 FTP 服务器必须为此功能支持 MDTM 命令。<br /><br /> 有效值为<br /><br /> -是<br />-无|默认值是不可以。|  
  
 下面的代码显示了使用设置的属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>ftp://localhost:21/in/*.xml</uri><serverAddress>localhost</serverAddress><serverPort>21</serverPort><userName>domain\testuser</userName><password>******</password><fileMask>*.xml</fileMask><targetFolder>in</targetFolder><commandLogFilename>c:\temp\realftplog.txt</commandLogFilename><representationType>binary</representationType><maximumBatchSize>0</maximumBatchSize><maximumNumberOfFiles>0</maximumNumberOfFiles><passiveMode>False</passiveMode><firewallType>NoFirewall</firewallType><firewallPort>21</firewallPort><pollingUnitOfMeasure>Seconds</pollingUnitOfMeasure><pollingInterval>5</pollingInterval><errorThreshold>10</errorThreshold><maxFileSize>5000</maxFileSize><useSsl>False</useSsl><useDataProtection>True</useDataProtection><ftpsConnMode>Explicit</ftpsConnMode><clientCertificateHash>‎bc 32 2c a9 22 75 6a 3f e4 f7 a9 b1 b3 3a 24 20 23 53 68 49</clientCertificateHash><deleteAfterDownload>True</deleteAfterDownload><enableTimeComparison>False</enableTimeComparison></Config></AdapterConfig></CustomProps>  
```  
  
 下表列出了发送端口可以设置为 FTP 适配器的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|指定要将数据发送到的位置的完整路径。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
|serverAddress|VT_BSTR|指定的 DNS 名称或 IP 地址的防火墙的地址。|None|None|  
|serverPort|VT_BSTR|指定 FTP 服务器的端口地址。|None|默认值为 21。|  
|userName|VT_BSTR|指定要登录到 FTP 服务器上的用户名称。|None|None|  
|password|VT_BSTR|指定要登录到 FTP 服务器上的密码。|导出绑定文件时，此值始终会被屏蔽。 此属性前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。|None|  
|accountName|VT_BSTR|指定 FTP 服务器的帐户名。|可选|None|  
|targetFolder|VT_BSTR|指定要移动到 FTP 服务器上的文件的位置。|None|None|  
|targetFileName|VT_BSTR|指定文件的替代名称。 保留默认名称将保证发送每条消息的唯一消息名称。|None|默认值为 %messageid%.xml。|  
|commandLogFilename|VT_BSTR|指定要保存日志文件的副本的位置。 使用日志文件以发送或接收通过 FTP 服务器的文件时诊断错误情况。|None|None|  
|representationType|VT_BSTR|选择作为二进制或 ASCII FTP 发送数据的方式。|有效值为<br /><br /> -二进制<br />-   ASCII|默认值为二进制。|  
|beforePut|VT_BSTR|指定要在文件 PUT，例如，若要更改默认值在 FTP 服务器上的命令之前运行的 FTP 命令。|用分号 （;） 分隔命令。 **注意：** 在 PUT 文件之前不支持 QUIT 的命令。|没有打开命令是必需的。|  
|afterPut|VT_BSTR|指定要在文件 PUT 后运行的 FTP 命令。|用分号 （;） 分隔命令。|None|  
|allocateStorage|VT_BSTR|指定是否为旧式主机系统分配的存储空间。|有效值为<br /><br /> -是<br />-无|默认值是不可以。|  
|spoolingFolder|VT_BSTR|指定 FTP 服务器上的临时文件夹的位置。 此位置用于保证从传输失败中的恢复，如果传输模式为二进制。 如果传输模式是 ASCII，适配器将重新开始上传。|None|None|  
|connectionLimit|VT_BSTR|指定的最大并发可打开到服务器的 FTP 连接数。|None|值为 0 表示没有限制。|  
|passiveMode|VT_BSTR|指定是否使用被动模式还是主动模式。|有效值为<br /><br /> -True （被动模式）<br />-False （主动模式）|默认值为 False （主动模式）。|  
|firewallType|VT_BSTR|选择部署的防火墙的类型。|有效值为<br /><br /> -Socks 4<br />-Socks 5<br />-None|默认值为 None。|  
|firewallAddress|VT_BSTR|指定的 DNS 名称或 IP 地址的防火墙的地址。|None|None|  
|firewallPort|VT_BSTR|指定防火墙的端口。|有效值为从 1 到 65535 之间。|默认值为 21。|  
|firewallUserName|VT_BSTR|指定防火墙的用户名。|None|None|  
|firewallPassword|VT_BSTR|指定防火墙的密码。|导出绑定文件时，此值始终会被屏蔽。 此属性前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。|None|  
|ssoAffiliateApplication|VT_BSTR|指定单一登录 (SSO) 关联应用程序。|None|None|  
|useSsl|VT_BSTR|指定此值为是，如果 FTP 适配器必须使用 SSL 与 FTPS 服务器通信时。|有效值为<br /><br /> -是<br />-无|默认值是不可以。|  
|useDataProtection|VT_BSTR|指定此值为是，如果 FTP 适配器必须使用 SSL 加密时发送和接收文件到和从 FTPS 服务器。|此属性是在 useSsL 设置为是才有效。<br /><br /> 有效值为<br /><br /> -是<br />-无|默认值为是。|  
|ftpsConnMode|VT_BSTR|指定与 FTPS 服务器建立 SSL 连接模式。|有效值为<br /><br /> -   Explicit<br />隐式|默认值为显性。|  
|clientCertificateHash|VT_BSTR|指定在 SSL 协商中必须使用的客户端证书的 SHA1 哈希。|None|基于此哈希值，客户端证书提取其下运行的 BizTalk 主机实例的用户帐户的个人存储中。|  
  
 下面的代码显示了使用设置的属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><serverAddress>TestServer</serverAddress><serverPort>21</serverPort><userName>testuser</userName><password>******</password><accountName>testuser</accountName><targetFolder>output</targetFolder><targetFileName>%MessageID%.xml</targetFileName><commandLogFilename>c:\logfile\ftpsendlog.txt</commandLogFilename><representationType>binary</representationType><beforePut>CDW dir</beforePut><afterPut>CDUP </afterPut><allocateStorage>False</allocateStorage><spoolingFolder>tempfolder</spoolingFolder><connectionLimit>0</connectionLimit><passiveMode>False</passiveMode><firewallType>Socks4</firewallType><firewallAddress>TestServer</firewallAddress><firewallPort>21</firewallPort><firewallUserName>domain\testuser</firewallUserName><firewallPassword>******</firewallPassword><useSsl>False</useSsl><useDataProtection>True</useDataProtection><ftpsConnMode>Explicit</ftpsConnMode><clientCertificateHash>‎bc 32 2c a9 22 75 6a 3f e4 f7 a9 b1 b3 3a 24 20 23 53 68 49</clientCertificateHash><uri>ftp://TestServer:21/output/%MessageID%.xml</uri></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  指定使用适配器框架生成的适配器的 TransportTypeData 配置数据，使用的所有名称/值对必须都存储到\<AdapterConfig\>元素。 由于\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型则\<\>必须对数据中的字符进行转义。