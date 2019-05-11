---
title: 适配器配置架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc08fa71-c5f7-4365-9506-e02351b17567
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 837e4ff704b086f5511c42f8184c1edc03928ef8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361564"
---
# <a name="adapter-configuration-schemas"></a>适配器配置架构
在设计时适配器配置中使用不同类型的架构。 根据的可见性和作用域的属性值，不同的架构修改，使用。  
  
## <a name="handler-schemas"></a>处理程序架构  
 来自处理程序的适配器配置适用于适配器，并在全局作用域所有使用者。 管理员可以通过使用以静态方式更改在设计时的处理程序配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，可展开的适配器接收或发送处理程序，此时指定主机的属性。  
  
 SDK 中包含的示例文件适配器具有一组 XSD 文件用来配置其接收位置、 发送端口、 接收处理程序和发送处理程序。 修改这些 XSD 文件，使您的自定义适配器接收它需要的配置属性。 您需要修改示例文件适配器附带的文件是 TransmitHandler.xsd and ReceiveHandler.xsd 架构文件。 这些文件配置发送处理程序和接收处理程序，分别通过控制用于配置中的处理程序的属性页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 使用适配器要求，创建所需的每个终结点的配置属性的列表。 如果所有配置属性都是全局的可能只需要修改发送和接收端口配置。 如果需要为每个发送端口或接收位置设置适配器属性，您必须修改接收位置和发送端口配置文件。  
  
 适配器框架提供架构扩展和高级的配置选项，以支持常见的适配器配置要求。 它还提供了不在随附的示例文件适配器的架构中的扩展。 有关适配器框架架构扩展的详细信息，请参阅[适配器框架配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。 有关高级的配置选项，例如自定义下拉编辑器和自定义类型转换器的详细信息，请参阅[适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)。  
  
 在本主题末尾的代码来自 TransmitHandler.xsd 文件中，它生成以下属性页。  
  
 ![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")  
发送处理程序属性页创建的 TransmitHandler.xsd 文件  
  
 请注意，使用\<baf: designer\>， \<baf:displayname\>，并\<baf: description\>如下所示的 TransmitHandler.xsd 代码中的标记。 这些是自定义提供的适配器框架，以更快地做出这些属性页生成的修饰。  
  
 有关所有可供使用适配器框架中的修饰的列表，请参阅[适配器框架配置架构修饰标记](../core/adapter-framework-configuration-schema-decoration-tags.md)。  
  
 请注意，架构只有一个元素不包含 URI 元素。  
  
> [!IMPORTANT]
>  在默认适配器架构中存储敏感的客户数据。 出于安全原因，只在部署适配器之后才配置用户名和密码信息。 这可确保信息获取存储在企业单一登录 (SSO) 数据库。 有关 SSO 数据库的详细信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:baf="BiztalkAdapterFramework.xsd"   
xmlns:b="http://schemas.microsoft.com/BizTalk/2003"   
xmlns="http://tempuri.org/XMLSchema1.xsd"   
elementFormDefault="qualified" targetNamespace="http://tempuri.org/XMLSchema1.xsd"   
id="TransmitHandler" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="Config">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element default="50" name="sendBatchSize" type="xs:int" >  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="sendBatchSizeName">Batch Size</baf:displayname>  
               <baf:description _locID="sendBatchSizeDesc">Enter the   
maximum number of files to be transmitted per batch</baf:description>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
  
        <xs:element default="4096" name="bufferSize" type="xs:int" >  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="bufferSizeName">Write Buffer Size</baf:displayname>  
               <baf:description _locID="bufferSizeDesc">Enter the size of   
the buffer used to write the file</baf:description>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
  
        <xs:element default="1" name="threadsPerCPU" type="xs:int" >  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="threadsPerCPUName">Threads Per CPU</baf:displayname>  
               <baf:description _locID="threadsPerCPUDesc">Enter the   
number of threads per CPU to execute in the thread pool</baf:description>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="send-port-and-receive-location-schemas"></a>发送端口和接收位置架构  
 若要为适配器设置特定于端口的属性，修改接收位置和发送端口配置架构。 TransmitLocation.xsd 和 ReceiveLocation.xsd 架构文件配置发送端口和接收位置，分别。  
  
 适配器框架提供架构扩展和高级的配置选项，以支持常见的适配器配置要求。 有关适配器框架架构扩展的详细信息，请参阅[适配器框架配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。 有关高级的配置选项，例如自定义下拉编辑器和自定义类型转换器的详细信息，请参阅[适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)。  
  
 下面的代码来自 TransmitLocation.xsd 文件中，并生成以下属性页。  
  
 ![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")  
说明了示例文件适配器的发送端口属性页  
  
 请注意在下面的 TransmitLocation.xsd 文件中的发送端口配置包含\<baf: designer\>， \<baf:displayname\>，并\<baf: description\>标记，就像发送处理程序，它也使用\<baf:category\>标记。 类别标记允许您将组属性在一起。 如果有多个类别，类别是可展开和折叠和作为该类别中属性上方的标头显示为灰色。 有关详细信息，请参阅[适配器框架配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。  
  
 此架构还包含 URI 字段。 这被填充上显示的验证处理期间发送端口属性页上输入的所有字段信息后的页适配器。  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:baf="BiztalkAdapterFramework.xsd" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://tempuri.org/XMLSchema1.xsd" elementFormDefault="qualified" targetNamespace="http://tempuri.org/XMLSchema1.xsd" id="TransmitLocation" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="Config">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="directory" type="xs:string">  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
               <baf:displayname _locID="sendDirectoryName">Directory</baf:displayname>  
               <baf:description _locID="sendDirectoryDesc">Directory to write the file to</baf:description>  
                         <baf:category _locID="transmitLocationCategory">Transmit Location</baf:category>  
                    </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
        </xs:element>  
  
        <xs:element default="%MessageID%.xml" name="fileName" type="xs:string">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
                <baf:displayname _locID="fileNameName">File Name</baf:displayname>  
      <baf:description _locID="fileNameDesc">The name of the file that will be written</baf:description>  
                <baf:category _locID="transmitLocationCategory">Transmit Location</baf:category>  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
  
        <xs:element default="2" name="fileCopyMode" type="CopyMode">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
                <baf:displayname _locID="fileCopyModeName">File Mode</baf:displayname>  
                <baf:category _locID="transmitLocationCategory">Transmit Location</baf:category>  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
  
        <xs:element name="uri" type="xs:string">  
          <xs:annotation>  
            <xs:appinfo>  
              <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
                <baf:browsable show="false" />  
              </baf:designer>  
            </xs:appinfo>  
          </xs:annotation>  
        </xs:element>  
  
   <!-- An example of how an SSO affiliate application would be configured for this endpoint: -->  
   <!--  
   <xs:element name="ssoAffiliateApplication" type="baf:SSOList">  
      <xs:annotation>  
         <xs:appinfo>  
            <baf:designer>  
               <baf:displayname _locID="ssoAffiliateApplicationName">SSO Affiliate</baf:displayname>  
               <baf:description _locID="ssoAffiliateApplicationDesc">The Single Sign On (SSO) Affiliate Application</baf:description>  
               <baf:category _locID="ftpCategory">FTP</baf:category>  
            </baf:designer>  
         </xs:appinfo>  
      </xs:annotation>  
   </xs:element>  
   -->  
  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  
  <xs:simpleType name="CopyMode">  
    <xs:restriction base="xs:int">  
      <xs:enumeration value="0">  
        <xs:annotation>  
          <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
              <baf:displayname _locID="appendName">Append</baf:displayname>  
            </baf:designer>  
          </xs:appinfo>  
        </xs:annotation>  
      </xs:enumeration>  
      <xs:enumeration value="1">  
        <xs:annotation>  
          <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
              <baf:displayname _locID="createName">Create</baf:displayname>  
            </baf:designer>  
          </xs:appinfo>  
        </xs:annotation>  
      </xs:enumeration>  
      <xs:enumeration value="2">  
        <xs:annotation>  
          <xs:appinfo>  
            <baf:designer xmlns:baf="BiztalkAdapterFramework.xsd">  
              <baf:displayname _locID="createNewName">CreateNew</baf:displayname>  
            </baf:designer>  
          </xs:appinfo>  
        </xs:annotation>  
      </xs:enumeration>  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```