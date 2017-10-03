---
title: "适配器配置架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc08fa71-c5f7-4365-9506-e02351b17567
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2afa0e2f06471d90326b0dd8e2b83b8d4c38a82b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-configuration-schemas"></a>适配器配置架构
在适配器的设计时配置中使用不同类型的架构。 根据属性值的可见性和作用域，可修改和使用不同的架构。  
  
## <a name="handler-schemas"></a>处理程序架构  
 来自处理程序的适配器配置适用于适配器及其在全局作用域的所有使用者。 管理员可以通过使用静态更改在设计时的处理程序配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，可展开的适配器接收或发送处理程序并打开指定的主机的属性。  
  
 SDK 中包括的示例文件适配器有一组 XSD 文件，用于配置其接收位置、发送端口、接收处理程序和发送处理程序。 可以修改这些 XSD 文件，从而使您的自定义适配器接收所需要的配置属性。 随示例文件适配器提供的需要修改的文件为 TransmitHandler.xsd and ReceiveHandler.xsd 架构文件。 这些文件配置发送处理程序，并接收处理程序中，分别通过控制用于配置中的处理程序的属性页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 使用适配器要求，创建每个终结点所需的配置属性列表。 如果所有配置属性为全局的，您可能只需要修改发送和接收端口配置。 如果需要为每个发送端口或接收位置设置适配器属性，您还必须修改接收位置和发送端口配置文件。  
  
 适配器框架提供架构扩展和高级配置选项，以支持常见的适配器配置要求。 它还提供与示例文件适配器包括在一起的架构中没有的扩展。 有关这些适配器 Framework 架构扩展的详细信息，请参阅[适配器 Framework 配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。 有关高级的配置选项，例如自定义下拉列表编辑器和自定义类型转换器的详细信息，请参阅[适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)。  
  
 本主题末尾部分的代码来自 TransmitHandler.xsd 文件，它生成以下属性页。  
  
 ![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")  
TransmitHandler.xsd 文件创建的发送处理程序属性页  
  
 请注意，使用\<baf:designer >， \<baf:displayname >，和\<baf:description > 如下所示的 TransmitHandler.xsd 代码中的标记。 这些标记是适配器框架提供的自定义修饰，以便更快地生成这些属性页。  
  
 有关所有可供使用的适配器框架中的修饰的列表，请参阅[适配器 Framework 配置架构修饰标记](../core/adapter-framework-configuration-schema-decoration-tags.md)。  
  
 注意，架构只有一个元素，不包含 URI 元素。  
  
> [!IMPORTANT]
>  不要将敏感的客户数据存储在默认适配器架构中。 为安全起见，应当只在部署适配器之后才配置用户名和密码信息。 这样可以确保信息存储在企业单一登录 (SSO) 数据库中。 SSO 数据库有关的详细信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
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
 若要为适配器设置特定于端口的属性，请修改接收位置和发送端口配置架构。 TransmitLocation.xsd 和 ReceiveLocation.xsd 架构文件分别配置发送端口和接收位置。  
  
 适配器框架提供架构扩展和高级配置选项，以支持常见的适配器配置要求。 有关这些适配器 Framework 架构扩展的详细信息，请参阅[适配器 Framework 配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。 有关高级的配置选项，例如自定义下拉列表编辑器和自定义类型转换器的详细信息，请参阅[适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)。  
  
 下面的代码来自 TransmitLocation.xsd 文件，它生成以下属性页。  
  
 ![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")  
解释示例文件适配器的发送端口属性页  
  
 请注意下面 TransmitLocation.xsd 文件中，发送端口配置包含\<baf:designer >， \<baf:displayname >，和\<baf:description > 标记，就像发送处理程序，而且它还使用\<baf:category > 标记。 类别标记允许您将属性一起分组。 如果有一个以上的类别，则类别是可展开的、可折叠的，并且作为标题以灰色显示在该类别中属性上方。 有关详细信息，请参阅[适配器 Framework 配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。  
  
 此架构还包含 URI 字段。 此字段填充在当您在适配器执行的验证处理期间在发送端口属性页上输入所有字段信息后显示的页面上。  
  
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