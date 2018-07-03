---
title: 集成的 BizTalk 适配器的配置属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, security
- adapters, passwords
- IReceiveLocation.CustomData property
- security, passwords
- ISendPort.CustomData property
- binding files, passwords
- adapters, properties
- binding files, security
ms.assetid: 4780a558-4322-428a-aa4a-0c32913faded
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45779131906460040db969bd4ef412b8f9220ab6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005982"
---
# <a name="configuration-properties-for-integrated-biztalk-adapters"></a>集成的 BizTalk 适配器的配置属性
BizTalk 浏览器对象模型公开**IReceiveLocation.CustomData**并**ISendPort.CustomData**包含名称/值形式的适配器配置属性包的属性对 XML 字符串。 此名称/值对 XML 字符串存储在\<CustomProps\>中的元素\<TransportTypeData\>绑定文件中的元素。 中的信息的大多数\<CustomProps\>元素对应于 BizTalk Server 用户界面 （例如 BizTalk 管理控制台或 BizTalk 浏览器中） 中可以为适配器设置的信息。 如果在某一绑定文件中提供这些值，则这些值将在导入该绑定文件时应用于指定的接收位置和发送端口的适配器配置。 所有适配器的配置信息都存储于单一登录数据库中。  
  
 本部分说明可为每个集成的 BizTalk 适配器设置的配置属性。  
  
> [!NOTE]
>  密码信息存储在\<TransportTypeData\>绑定文件的元素，以便不以明文形式保存敏感数据屏蔽。 根据传输，密码信息或者由 NULL 代替，或者由星号代替。 您必须手动在绑定文件中输入此信息，以便在将绑定文件导入到目标 BizTalk Server 配置前更新适配器配置。  
  
 适配器使用适配器框架生成的配置数据存储在\<AdapterConfig\>元素。 由于\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型**\< \>** 必须对此元素中包含的字符进行转义，否则将发生错误时你尝试导入绑定文件。 这会导致配置数据文本在可读性上比对这些字符进行转义前要低。 下面的示例阐释对这些字符（它们来自绑定到 POP3 适配器的发送端口的示例配置数据）进行转义的影响。  
  
 **未转义中使用的 <> 字符的 TransportTypeData 配置数据\<AdapterConfig\>元素**  
  
 此配置数据无效因为\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型和\<\>中包含的字符\<AdapterConfig\>未转义元素：  
  
```  
<TransportTypeData>  
<CustomProps>  
<AdapterConfig vt="8">  
<Config xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<mailServer>test.microsoft.com</mailServer>  
<serverPort>0</serverPort>  
<userName>testuser</userName>  
<password>******</password>  
<authenticationScheme>Basic</authenticationScheme>  
<sslRequired>false</sslRequired>  
<applyMIME>true</applyMIME>  
<bodyPartContentType>text/xml</bodyPartContentType>  
<bodyPartIndex>1</bodyPartIndex>  
<errorThreshold>10</errorThreshold>  
<pollingInterval>5</pollingInterval>  
<pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure>   
<uri>POP3://test.microsoft.com#testuser</uri>  
</Config>  
</AdapterConfig>  
</CustomProps>  
</TransportTypeData>  
```  
  
 **对 <> 中所用字符的 TransportTypeData 配置数据\<AdapterConfig\>元素**  
  
 由于\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型\<\>字符必须转义从\<AdapterConfig\>元素，如下所示：  
  
```  
<TransportTypeData>  
<CustomProps>  
<AdapterConfig vt="8">  
<Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd="http://www.w3.org/2001/XMLSchema"><mailServer>test  
microsoft.com</mailServer><serverPort>0</serverPort>&  
lt;userName>testuser</userName><password>******</pass  
word><authenticationScheme>Basic</authenticationScheme>&  
lt;sslRequired>false</sslRequired><applyMIME>true</ap  
plyMIME><bodyPartContentType>text/xml</bodyPartContentType&  
gt;<bodyPartIndex>1</bodyPartIndex><errorThreshold>10  
</errorThreshold><pollingInterval>5</pollingInterval>  
<pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure><uri  
>POP3://test.microsoft.com#testuser</uri></Config>  
</AdapterConfig>  
</CustomProps>  
</TransportTypeData>  
```  
  
 以下是使用适配器框架已创建的集成的适配器：  
  
- FTP 适配器  
  
- MQSeries 适配器  
  
- MSMQ 适配器  
  
- POP3 适配器  
  
- Windows Sharepoint Services 适配器  
  
  若要查看用作每个集成的适配器的 TransportTypeData 配置数据的示例字符串，请查看本部分中与该适配器关联的配置属性主题。  
  
## <a name="in-this-section"></a>本节内容  
 [配置属性变量类型](../core/configuration-property-variable-types.md)  
  
 [文件适配器配置属性](../core/file-adapter-configuration-properties.md)  
  
 [FTP 适配器配置属性](../core/ftp-adapter-configuration-properties.md)  
  
 [HTTP 适配器配置属性](../core/http-adapter-configuration-properties.md)  
  
 [MQSeries 适配器配置属性](../core/mqseries-adapter-configuration-properties.md)  
  
 [MSMQ 适配器配置属性](../core/msmq-adapter-configuration-properties.md)  
  
 [POP3 适配器配置属性](../core/pop3-adapter-configuration-properties.md)  
  
 [SMTP 适配器配置属性](../core/smtp-adapter-configuration-properties.md)  
  
 [SOAP 适配器配置属性](../core/soap-adapter-configuration-properties.md)  
  
 [Windows SharePoint Services 适配器配置属性](../core/windows-sharepoint-services-adapter-configuration-properties.md)