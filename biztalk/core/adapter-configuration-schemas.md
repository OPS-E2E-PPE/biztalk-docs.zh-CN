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
# <a name="adapter-configuration-schemas"></a><span data-ttu-id="778f5-102">适配器配置架构</span><span class="sxs-lookup"><span data-stu-id="778f5-102">Adapter Configuration Schemas</span></span>
<span data-ttu-id="778f5-103">在设计时适配器配置中使用不同类型的架构。</span><span class="sxs-lookup"><span data-stu-id="778f5-103">Different types of schemas are used in design-time configuration of an adapter.</span></span> <span data-ttu-id="778f5-104">根据的可见性和作用域的属性值，不同的架构修改，使用。</span><span class="sxs-lookup"><span data-stu-id="778f5-104">Depending upon the visibility and scope of property values, different schemas are modified and used.</span></span>  
  
## <a name="handler-schemas"></a><span data-ttu-id="778f5-105">处理程序架构</span><span class="sxs-lookup"><span data-stu-id="778f5-105">Handler Schemas</span></span>  
 <span data-ttu-id="778f5-106">来自处理程序的适配器配置适用于适配器，并在全局作用域所有使用者。</span><span class="sxs-lookup"><span data-stu-id="778f5-106">Adapter configuration that comes from a handler applies to the adapter and all its consumers on a global scope.</span></span> <span data-ttu-id="778f5-107">管理员可以通过使用以静态方式更改在设计时的处理程序配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，可展开的适配器接收或发送处理程序，此时指定主机的属性。</span><span class="sxs-lookup"><span data-stu-id="778f5-107">An administrator can statically alter handler configuration at design time by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to expand the adapter's receive or send handler and bring up the properties of the specified host.</span></span>  
  
 <span data-ttu-id="778f5-108">SDK 中包含的示例文件适配器具有一组 XSD 文件用来配置其接收位置、 发送端口、 接收处理程序和发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="778f5-108">The sample file adapter included in the SDK has a set of XSD files used to configure its receive location, send port, receive handler, and send handler.</span></span> <span data-ttu-id="778f5-109">修改这些 XSD 文件，使您的自定义适配器接收它需要的配置属性。</span><span class="sxs-lookup"><span data-stu-id="778f5-109">Modify these XSD files so that your custom adapter receives the configuration properties it requires.</span></span> <span data-ttu-id="778f5-110">您需要修改示例文件适配器附带的文件是 TransmitHandler.xsd and ReceiveHandler.xsd 架构文件。</span><span class="sxs-lookup"><span data-stu-id="778f5-110">The files included with the sample file adapter that you need to modify are the TransmitHandler.xsd and ReceiveHandler.xsd schema files.</span></span> <span data-ttu-id="778f5-111">这些文件配置发送处理程序和接收处理程序，分别通过控制用于配置中的处理程序的属性页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="778f5-111">These files configure the send handler and receive handler, respectively, by controlling the property pages used to configure the handlers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="778f5-112">使用适配器要求，创建所需的每个终结点的配置属性的列表。</span><span class="sxs-lookup"><span data-stu-id="778f5-112">Using your adapter requirements, create a list of configuration properties required for each of the endpoints.</span></span> <span data-ttu-id="778f5-113">如果所有配置属性都是全局的可能只需要修改发送和接收端口配置。</span><span class="sxs-lookup"><span data-stu-id="778f5-113">If all of your configuration properties are global, you may only need to modify the send and receive port configurations.</span></span> <span data-ttu-id="778f5-114">如果需要为每个发送端口或接收位置设置适配器属性，您必须修改接收位置和发送端口配置文件。</span><span class="sxs-lookup"><span data-stu-id="778f5-114">If the adapter properties need to be set for each send port or receive location, you have to modify the receive location and send port configuration files as well.</span></span>  
  
 <span data-ttu-id="778f5-115">适配器框架提供架构扩展和高级的配置选项，以支持常见的适配器配置要求。</span><span class="sxs-lookup"><span data-stu-id="778f5-115">The Adapter Framework provides schema extensions and advanced configuration options to support common adapter configuration requirements.</span></span> <span data-ttu-id="778f5-116">它还提供了不在随附的示例文件适配器的架构中的扩展。</span><span class="sxs-lookup"><span data-stu-id="778f5-116">It also provides extensions that are not in the schema included with the sample file adapter.</span></span> <span data-ttu-id="778f5-117">有关适配器框架架构扩展的详细信息，请参阅[适配器框架配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。</span><span class="sxs-lookup"><span data-stu-id="778f5-117">For more information about the Adapter Framework schema extensions, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span> <span data-ttu-id="778f5-118">有关高级的配置选项，例如自定义下拉编辑器和自定义类型转换器的详细信息，请参阅[适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="778f5-118">For more information about advanced configuration options such as custom drop-down editors and custom type converters, see [Advanced Configuration Components for Adapters](../core/advanced-configuration-components-for-adapters.md).</span></span>  
  
 <span data-ttu-id="778f5-119">在本主题末尾的代码来自 TransmitHandler.xsd 文件中，它生成以下属性页。</span><span class="sxs-lookup"><span data-stu-id="778f5-119">The code at the end of this topic is from the TransmitHandler.xsd file, and produces the following property page.</span></span>  
  
 <span data-ttu-id="778f5-120">![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")</span><span class="sxs-lookup"><span data-stu-id="778f5-120">![](../core/media/ebiz-prog-custad-sh.gif "ebiz_prog_custad_sh")</span></span>  
<span data-ttu-id="778f5-121">发送处理程序属性页创建的 TransmitHandler.xsd 文件</span><span class="sxs-lookup"><span data-stu-id="778f5-121">Send handler property page created by the TransmitHandler.xsd file</span></span>  
  
 <span data-ttu-id="778f5-122">请注意，使用\<baf: designer\>， \<baf:displayname\>，并\<baf: description\>如下所示的 TransmitHandler.xsd 代码中的标记。</span><span class="sxs-lookup"><span data-stu-id="778f5-122">Note the use of the \<baf:designer\>, \<baf:displayname\>, and \<baf:description\> tags in the TransmitHandler.xsd code that is shown below.</span></span> <span data-ttu-id="778f5-123">这些是自定义提供的适配器框架，以更快地做出这些属性页生成的修饰。</span><span class="sxs-lookup"><span data-stu-id="778f5-123">These are custom decorations provided by the Adapter Framework to make the generation of these property pages faster.</span></span>  
  
 <span data-ttu-id="778f5-124">有关所有可供使用适配器框架中的修饰的列表，请参阅[适配器框架配置架构修饰标记](../core/adapter-framework-configuration-schema-decoration-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="778f5-124">For a list of all of the decorations available for use within the Adapter Framework, see [Adapter Framework Configuration Schema Decoration Tags](../core/adapter-framework-configuration-schema-decoration-tags.md).</span></span>  
  
 <span data-ttu-id="778f5-125">请注意，架构只有一个元素不包含 URI 元素。</span><span class="sxs-lookup"><span data-stu-id="778f5-125">Note that the schema has only one element and does not contain a URI element.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="778f5-126">在默认适配器架构中存储敏感的客户数据。</span><span class="sxs-lookup"><span data-stu-id="778f5-126">Do not store sensitive customer data in the default adapter schema.</span></span> <span data-ttu-id="778f5-127">出于安全原因，只在部署适配器之后才配置用户名和密码信息。</span><span class="sxs-lookup"><span data-stu-id="778f5-127">For security reasons, configure user name and password information only after you deploy an adapter.</span></span> <span data-ttu-id="778f5-128">这可确保信息获取存储在企业单一登录 (SSO) 数据库。</span><span class="sxs-lookup"><span data-stu-id="778f5-128">This ensures that the information gets stored in the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="778f5-129">有关 SSO 数据库的详细信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="778f5-129">For more information about the SSO database, see [Using SSO](../core/using-sso.md).</span></span>  
  
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
  
## <a name="send-port-and-receive-location-schemas"></a><span data-ttu-id="778f5-130">发送端口和接收位置架构</span><span class="sxs-lookup"><span data-stu-id="778f5-130">Send Port and Receive Location Schemas</span></span>  
 <span data-ttu-id="778f5-131">若要为适配器设置特定于端口的属性，修改接收位置和发送端口配置架构。</span><span class="sxs-lookup"><span data-stu-id="778f5-131">To set port-specific properties for your adapter, modify the receive location and send port configuration schemas.</span></span> <span data-ttu-id="778f5-132">TransmitLocation.xsd 和 ReceiveLocation.xsd 架构文件配置发送端口和接收位置，分别。</span><span class="sxs-lookup"><span data-stu-id="778f5-132">The TransmitLocation.xsd and ReceiveLocation.xsd schema files configure the send port and receive location, respectively.</span></span>  
  
 <span data-ttu-id="778f5-133">适配器框架提供架构扩展和高级的配置选项，以支持常见的适配器配置要求。</span><span class="sxs-lookup"><span data-stu-id="778f5-133">The Adapter Framework provides schema extensions and advanced configuration options to support common adapter configuration requirements.</span></span> <span data-ttu-id="778f5-134">有关适配器框架架构扩展的详细信息，请参阅[适配器框架配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。</span><span class="sxs-lookup"><span data-stu-id="778f5-134">For more information about the Adapter Framework schema extensions, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span> <span data-ttu-id="778f5-135">有关高级的配置选项，例如自定义下拉编辑器和自定义类型转换器的详细信息，请参阅[适配器的高级配置组件](../core/advanced-configuration-components-for-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="778f5-135">For more information about advanced configuration options such as custom drop-down editors and custom type converters, see [Advanced Configuration Components for Adapters](../core/advanced-configuration-components-for-adapters.md).</span></span>  
  
 <span data-ttu-id="778f5-136">下面的代码来自 TransmitLocation.xsd 文件中，并生成以下属性页。</span><span class="sxs-lookup"><span data-stu-id="778f5-136">The code that follows is from the TransmitLocation.xsd file, and produces the following property page.</span></span>  
  
 <span data-ttu-id="778f5-137">![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")</span><span class="sxs-lookup"><span data-stu-id="778f5-137">![](../core/media/ebiz-prog-custad-sp.gif "ebiz_prog_custad_sp")</span></span>  
<span data-ttu-id="778f5-138">说明了示例文件适配器的发送端口属性页</span><span class="sxs-lookup"><span data-stu-id="778f5-138">Illustrates the send port property page for the sample file adapter</span></span>  
  
 <span data-ttu-id="778f5-139">请注意在下面的 TransmitLocation.xsd 文件中的发送端口配置包含\<baf: designer\>， \<baf:displayname\>，并\<baf: description\>标记，就像发送处理程序，它也使用\<baf:category\>标记。</span><span class="sxs-lookup"><span data-stu-id="778f5-139">Note in the TransmitLocation.xsd file below that the send port configuration contains the \<baf:designer\>, \<baf:displayname\>, and \<baf:description\> tags, just like the send handler, and it also uses the \<baf:category\> tag.</span></span> <span data-ttu-id="778f5-140">类别标记允许您将组属性在一起。</span><span class="sxs-lookup"><span data-stu-id="778f5-140">The category tag enables you to group properties together.</span></span> <span data-ttu-id="778f5-141">如果有多个类别，类别是可展开和折叠和作为该类别中属性上方的标头显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="778f5-141">If you have more than one category, the category is expandable and collapsible and appears in gray as a header above the properties in that category.</span></span> <span data-ttu-id="778f5-142">有关详细信息，请参阅[适配器框架配置架构扩展](../core/adapter-framework-configuration-schema-extensions.md)。</span><span class="sxs-lookup"><span data-stu-id="778f5-142">For more information, see [Adapter Framework Configuration Schema Extensions](../core/adapter-framework-configuration-schema-extensions.md).</span></span>  
  
 <span data-ttu-id="778f5-143">此架构还包含 URI 字段。</span><span class="sxs-lookup"><span data-stu-id="778f5-143">This schema also contains a URI field.</span></span> <span data-ttu-id="778f5-144">这被填充上显示的验证处理期间发送端口属性页上输入的所有字段信息后的页适配器。</span><span class="sxs-lookup"><span data-stu-id="778f5-144">This is populated on the page that appears after you enter all of the field information on the send port property page during the validation processing by the adapter.</span></span>  
  
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