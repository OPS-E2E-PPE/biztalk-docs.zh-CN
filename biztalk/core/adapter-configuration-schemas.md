---
title: 适配器配置架构 |Microsoft 文档
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
ms.openlocfilehash: 89ca7d02c756fdbdf819e1a15069a95d0784d764
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966499"
---
# <a name="adapter-configuration-schemas"></a><span data-ttu-id="abe23-102">适配器配置架构</span><span class="sxs-lookup"><span data-stu-id="abe23-102">Adapter Configuration Schemas</span></span>
<span data-ttu-id="abe23-103">在适配器的设计时配置中使用不同类型的架构。</span><span class="sxs-lookup"><span data-stu-id="abe23-103">Different types of schemas are used in design-time configuration of an adapter.</span></span> <span data-ttu-id="abe23-104">根据属性值的可见性和作用域，可修改和使用不同的架构。</span><span class="sxs-lookup"><span data-stu-id="abe23-104">Depending upon the visibility and scope of property values, different schemas are modified and used.</span></span>  
  
## <a name="handler-schemas"></a><span data-ttu-id="abe23-105">处理程序架构</span><span class="sxs-lookup"><span data-stu-id="abe23-105">Handler Schemas</span></span>  
 <span data-ttu-id="abe23-106">来自处理程序的适配器配置适用于适配器及其在全局作用域的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="abe23-106">Adapter configuration that comes from a handler applies to the adapter and all its consumers on a global scope.</span></span> <span data-ttu-id="abe23-107">管理员可以通过使用静态更改在设计时的处理程序配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，可展开的适配器接收或发送处理程序并打开指定的主机的属性。</span><span class="sxs-lookup"><span data-stu-id="abe23-107">An administrator can statically alter handler configuration at design time by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to expand the adapter's receive or send handler and bring up the properties of the specified host.</span></span>  
  
 <span data-ttu-id="abe23-108">SDK 中包括的示例文件适配器有一组 XSD 文件，用于配置其接收位置、发送端口、接收处理程序和发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="abe23-108">The sample file adapter included in the SDK has a set of XSD files used to configure its receive location, send port, receive handler, and send handler.</span></span> <span data-ttu-id="abe23-109">可以修改这些 XSD 文件，从而使您的自定义适配器接收所需要的配置属性。</span><span class="sxs-lookup"><span data-stu-id="abe23-109">Modify these XSD files so that your custom adapter receives the configuration properties it requires.</span></span> <span data-ttu-id="abe23-110">随示例文件适配器提供的需要修改的文件为 TransmitHandler.xsd and ReceiveHandler.xsd 架构文件。</span><span class="sxs-lookup"><span data-stu-id="abe23-110">The files included with the sample file adapter that you need to modify are the TransmitHandler.xsd and ReceiveHandler.xsd schema files.</span></span> <span data-ttu-id="abe23-111">这些文件配置发送处理程序，并接收处理程序中，分别通过控制用于配置中的处理程序的属性页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="abe23-111">These files configure the send handler and receive handler, respectively, by controlling the property pages used to configure the handlers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="abe23-112">使用适配器要求，创建每个终结点所需的配置属性列表。</span><span class="sxs-lookup"><span data-stu-id="abe23-112">Using your adapter requirements, create a list of configuration properties required for each of the endpoints.</span></span> <span data-ttu-id="abe23-113">如果所有配置属性为全局的，您可能只需要修改发送和接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="abe23-113">If all of your configuration properties are global, you may only need to modify the send and receive port configurations.</span></span> <span data-ttu-id="abe23-114">如果需要为每个发送端口或接收位置设置适配器属性，您还必须修改接收位置和发送端口配置文件。</span><span class="sxs-lookup"><span data-stu-id="abe23-114">If the adapter properties need to be set for each send port or receive location, you have to modify the receive location and send port configuration files as well.</span></span>  
  
 <span data-ttu-id="abe23-115">适配器框架提供架构扩展和高级配置选项，以支持常见的适配器配置要求。</span><span class="sxs-lookup"><span data-stu-id="abe23-115">The Adapter Framework provides schema extensions and advanced configuration options to support common adapter configuration requirements.</span></span> <span data-ttu-id="abe23-116">它还提供与示例文件适配器包括在一起的架构中没有的扩展。</span><span class="sxs-lookup"><span data-stu-id="abe23-116">It also provides extensions that are not in the schema included with the sample file adapter.</span></span> <span data-ttu-id="abe23-117">有关这些适配器 Framework 架构扩展的详细信息，请参阅[适配器 Framework 配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。</span><span class="sxs-lookup"><span data-stu-id="abe23-117">For more information about the Adapter Framework schema extensions, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span> <span data-ttu-id="abe23-118">有关高级的配置选项，例如自定义下拉列表编辑器和自定义类型转换器的详细信息，请参阅[适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="abe23-118">For more information about advanced configuration options such as custom drop-down editors and custom type converters, see [Advanced Configuration Components for Adapters](../core/advanced-configuration-components-for-adapters.md).</span></span>  
  
 <span data-ttu-id="abe23-119">本主题末尾部分的代码来自 TransmitHandler.xsd 文件，它生成以下属性页。</span><span class="sxs-lookup"><span data-stu-id="abe23-119">The code at the end of this topic is from the TransmitHandler.xsd file, and produces the following property page.</span></span>  
  
 <span data-ttu-id="abe23-120">![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")</span><span class="sxs-lookup"><span data-stu-id="abe23-120">![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")</span></span>  
<span data-ttu-id="abe23-121">TransmitHandler.xsd 文件创建的发送处理程序属性页</span><span class="sxs-lookup"><span data-stu-id="abe23-121">Send handler property page created by the TransmitHandler.xsd file</span></span>  
  
 <span data-ttu-id="abe23-122">请注意，使用\<baf:designer\>， \<baf:displayname\>，和\<baf:description\>如下所示的 TransmitHandler.xsd 代码中的标记。</span><span class="sxs-lookup"><span data-stu-id="abe23-122">Note the use of the \<baf:designer\>, \<baf:displayname\>, and \<baf:description\> tags in the TransmitHandler.xsd code that is shown below.</span></span> <span data-ttu-id="abe23-123">这些标记是适配器框架提供的自定义修饰，以便更快地生成这些属性页。</span><span class="sxs-lookup"><span data-stu-id="abe23-123">These are custom decorations provided by the Adapter Framework to make the generation of these property pages faster.</span></span>  
  
 <span data-ttu-id="abe23-124">有关所有可供使用的适配器框架中的修饰的列表，请参阅[适配器 Framework 配置架构修饰标记](../core/adapter-framework-configuration-schema-decoration-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="abe23-124">For a list of all of the decorations available for use within the Adapter Framework, see [Adapter Framework Configuration Schema Decoration Tags](../core/adapter-framework-configuration-schema-decoration-tags.md).</span></span>  
  
 <span data-ttu-id="abe23-125">注意，架构只有一个元素，不包含 URI 元素。</span><span class="sxs-lookup"><span data-stu-id="abe23-125">Note that the schema has only one element and does not contain a URI element.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="abe23-126">不要将敏感的客户数据存储在默认适配器架构中。</span><span class="sxs-lookup"><span data-stu-id="abe23-126">Do not store sensitive customer data in the default adapter schema.</span></span> <span data-ttu-id="abe23-127">为安全起见，应当只在部署适配器之后才配置用户名和密码信息。</span><span class="sxs-lookup"><span data-stu-id="abe23-127">For security reasons, configure user name and password information only after you deploy an adapter.</span></span> <span data-ttu-id="abe23-128">这样可以确保信息存储在企业单一登录 (SSO) 数据库中。</span><span class="sxs-lookup"><span data-stu-id="abe23-128">This ensures that the information gets stored in the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="abe23-129">SSO 数据库有关的详细信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="abe23-129">For more information about the SSO database, see [Using SSO](../core/using-sso.md).</span></span>  
  
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
  
## <a name="send-port-and-receive-location-schemas"></a><span data-ttu-id="abe23-130">发送端口和接收位置架构</span><span class="sxs-lookup"><span data-stu-id="abe23-130">Send Port and Receive Location Schemas</span></span>  
 <span data-ttu-id="abe23-131">若要为适配器设置特定于端口的属性，请修改接收位置和发送端口配置架构。</span><span class="sxs-lookup"><span data-stu-id="abe23-131">To set port-specific properties for your adapter, modify the receive location and send port configuration schemas.</span></span> <span data-ttu-id="abe23-132">TransmitLocation.xsd 和 ReceiveLocation.xsd 架构文件分别配置发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="abe23-132">The TransmitLocation.xsd and ReceiveLocation.xsd schema files configure the send port and receive location, respectively.</span></span>  
  
 <span data-ttu-id="abe23-133">适配器框架提供架构扩展和高级配置选项，以支持常见的适配器配置要求。</span><span class="sxs-lookup"><span data-stu-id="abe23-133">The Adapter Framework provides schema extensions and advanced configuration options to support common adapter configuration requirements.</span></span> <span data-ttu-id="abe23-134">有关这些适配器 Framework 架构扩展的详细信息，请参阅[适配器 Framework 配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。</span><span class="sxs-lookup"><span data-stu-id="abe23-134">For more information about the Adapter Framework schema extensions, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span> <span data-ttu-id="abe23-135">有关高级的配置选项，例如自定义下拉列表编辑器和自定义类型转换器的详细信息，请参阅[适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="abe23-135">For more information about advanced configuration options such as custom drop-down editors and custom type converters, see [Advanced Configuration Components for Adapters](../core/advanced-configuration-components-for-adapters.md).</span></span>  
  
 <span data-ttu-id="abe23-136">下面的代码来自 TransmitLocation.xsd 文件，它生成以下属性页。</span><span class="sxs-lookup"><span data-stu-id="abe23-136">The code that follows is from the TransmitLocation.xsd file, and produces the following property page.</span></span>  
  
 <span data-ttu-id="abe23-137">![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")</span><span class="sxs-lookup"><span data-stu-id="abe23-137">![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")</span></span>  
<span data-ttu-id="abe23-138">解释示例文件适配器的发送端口属性页</span><span class="sxs-lookup"><span data-stu-id="abe23-138">Illustrates the send port property page for the sample file adapter</span></span>  
  
 <span data-ttu-id="abe23-139">请注意下面 TransmitLocation.xsd 文件中，发送端口配置包含\<baf:designer\>， \<baf:displayname\>，和\<baf:description\>标记，就像发送处理程序，而且它还使用\<baf:category\>标记。</span><span class="sxs-lookup"><span data-stu-id="abe23-139">Note in the TransmitLocation.xsd file below that the send port configuration contains the \<baf:designer\>, \<baf:displayname\>, and \<baf:description\> tags, just like the send handler, and it also uses the \<baf:category\> tag.</span></span> <span data-ttu-id="abe23-140">类别标记允许您将属性一起分组。</span><span class="sxs-lookup"><span data-stu-id="abe23-140">The category tag enables you to group properties together.</span></span> <span data-ttu-id="abe23-141">如果有一个以上的类别，则类别是可展开的、可折叠的，并且作为标题以灰色显示在该类别中属性上方。</span><span class="sxs-lookup"><span data-stu-id="abe23-141">If you have more than one category, the category is expandable and collapsible and appears in gray as a header above the properties in that category.</span></span> <span data-ttu-id="abe23-142">有关详细信息，请参阅[适配器 Framework 配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。</span><span class="sxs-lookup"><span data-stu-id="abe23-142">For more information, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span>  
  
 <span data-ttu-id="abe23-143">此架构还包含 URI 字段。</span><span class="sxs-lookup"><span data-stu-id="abe23-143">This schema also contains a URI field.</span></span> <span data-ttu-id="abe23-144">此字段填充在当您在适配器执行的验证处理期间在发送端口属性页上输入所有字段信息后显示的页面上。</span><span class="sxs-lookup"><span data-stu-id="abe23-144">This is populated on the page that appears after you enter all of the field information on the send port property page during the validation processing by the adapter.</span></span>  
  
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