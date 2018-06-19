---
title: 集成的 BizTalk 适配器的配置属性 |Microsoft 文档
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
ms.openlocfilehash: 950f244c3a46af87164c4e276a50cd7a91fee14b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969955"
---
# <a name="configuration-properties-for-integrated-biztalk-adapters"></a><span data-ttu-id="e6fe1-102">集成的 BizTalk 适配器的配置属性</span><span class="sxs-lookup"><span data-stu-id="e6fe1-102">Configuration Properties for Integrated BizTalk Adapters</span></span>
<span data-ttu-id="e6fe1-103">BizTalk 资源管理器对象模型公开了**IReceiveLocation.CustomData**和**ISendPort.CustomData**包含一个名称/值形式的适配器配置属性包的属性对 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-103">The BizTalk Explorer object model exposes the **IReceiveLocation.CustomData** and **ISendPort.CustomData** properties that contain the adapter configuration property bag in the form of a name/value pair XML string.</span></span> <span data-ttu-id="e6fe1-104">此名称/值对 XML 字符串存储在\<CustomProps\>中的元素\<TransportTypeData\>绑定文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-104">This name/value pair XML string is stored in a \<CustomProps\> element within a \<TransportTypeData\> element in a binding file.</span></span> <span data-ttu-id="e6fe1-105">中的信息的大多数\<CustomProps\>元素对应于可以在 BizTalk Server 用户界面 （如 BizTalk 管理控制台或 BizTalk 资源管理器中） 中为适配器设置的信息。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-105">Most of the information in the \<CustomProps\> element corresponds to information that can be set for an adapter in the BizTalk Server user interface (such as the BizTalk Administration Console or BizTalk Explorer).</span></span> <span data-ttu-id="e6fe1-106">如果在某一绑定文件中提供这些值，则这些值将在导入该绑定文件时应用于指定的接收位置和发送端口的适配器配置。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-106">If these values are present in a binding file then they are applied to the adapter configuration for the specified receive locations and send ports when the binding file is imported.</span></span> <span data-ttu-id="e6fe1-107">所有适配器的配置信息都存储于单一登录数据库中。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-107">Configuration information for all adapters is stored in the Single Sign-On database.</span></span>  
  
 <span data-ttu-id="e6fe1-108">本部分说明可为每个集成的 BizTalk 适配器设置的配置属性。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-108">This section describes the configuration properties that can be set for each integrated BizTalk adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6fe1-109">在存储的密码信息\<TransportTypeData\>绑定文件的元素，以便以明文形式不保存敏感数据屏蔽。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-109">Password information that is stored in the \<TransportTypeData\> element of a binding file is masked so that sensitive data is not saved in clear text.</span></span> <span data-ttu-id="e6fe1-110">根据传输，密码信息或者由 NULL 代替，或者由星号代替。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-110">Depending on the transport, password information is either replaced with NULL or is replaced with asterisks.</span></span> <span data-ttu-id="e6fe1-111">您必须手动在绑定文件中输入此信息，以便在将绑定文件导入到目标 BizTalk Server 配置前更新适配器配置。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-111">You must manually enter this information in the binding file to update the adapter configuration before importing the binding file into the target BizTalk Server configuration.</span></span>  
  
 <span data-ttu-id="e6fe1-112">使用适配器框架构建的适配器的配置数据存储在\<AdapterConfig\>元素。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-112">The configuration data for adapters built using the Adapter Framework is stored in an \<AdapterConfig\> element.</span></span> <span data-ttu-id="e6fe1-113">由于\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型，  **\< \>** 此元素中包含的字符必须进行转义，否则将发生错误时你尝试导入的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-113">Since the \<AdapterConfig\> element specifies the VT_BSTR (vt="8") data type, the **\< \>** characters contained in this element must be escaped or an error will occur when you attempt to import the binding file.</span></span> <span data-ttu-id="e6fe1-114">这会导致配置数据文本在可读性上比对这些字符进行转义前要低。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-114">This causes the text for the configuration data to be less human readable than if these characters were not escaped.</span></span> <span data-ttu-id="e6fe1-115">下面的示例阐释对这些字符（它们来自绑定到 POP3 适配器的发送端口的示例配置数据）进行转义的影响。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-115">The following example illustrates the effect of escaping these characters from sample configuration data for a send port bound to the POP3 adapter.</span></span>  
  
 <span data-ttu-id="e6fe1-116">**未转义中使用的 <> 字符的 TransportTypeData 配置数据\<AdapterConfig\>元素**</span><span class="sxs-lookup"><span data-stu-id="e6fe1-116">**TransportTypeData configuration data that does not escape the <> characters used in the \<AdapterConfig\> element**</span></span>  
  
 <span data-ttu-id="e6fe1-117">此配置数据无效因为\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型和\<\>中包含的字符\<AdapterConfig\>未转义元素：</span><span class="sxs-lookup"><span data-stu-id="e6fe1-117">This configuration data is invalid because the \<AdapterConfig\> element specifies the VT_BSTR (vt="8") data type and the \< \> characters contained in the \<AdapterConfig\> element are not escaped:</span></span>  
  
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
  
 <span data-ttu-id="e6fe1-118">**未转义中使用的 <> 字符的 TransportTypeData 配置数据\<AdapterConfig\>元素**</span><span class="sxs-lookup"><span data-stu-id="e6fe1-118">**TransportTypeData configuration data that does escape the <> characters used in the \<AdapterConfig\> element**</span></span>  
  
 <span data-ttu-id="e6fe1-119">由于\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型， \< \>必须从转义字符\<AdapterConfig\>元素，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e6fe1-119">Since the \<AdapterConfig\> element specifies the VT_BSTR (vt="8") data type, the \< \> characters must be escaped from the \<AdapterConfig\> element as seen below:</span></span>  
  
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
  
 <span data-ttu-id="e6fe1-120">以下是使用适配器框架已创建的集成的适配器：</span><span class="sxs-lookup"><span data-stu-id="e6fe1-120">The integrated adapters that were created with the Adapter Framework include the following:</span></span>  
  
-   <span data-ttu-id="e6fe1-121">FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="e6fe1-121">FTP Adapter</span></span>  
  
-   <span data-ttu-id="e6fe1-122">MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="e6fe1-122">MQSeries Adapter</span></span>  
  
-   <span data-ttu-id="e6fe1-123">MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="e6fe1-123">MSMQ Adapter</span></span>  
  
-   <span data-ttu-id="e6fe1-124">POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="e6fe1-124">POP3 Adapter</span></span>  
  
-   <span data-ttu-id="e6fe1-125">Windows Sharepoint Services Adapter</span><span class="sxs-lookup"><span data-stu-id="e6fe1-125">Windows Sharepoint Services Adapter</span></span>  
  
 <span data-ttu-id="e6fe1-126">若要查看用作每个集成的适配器的 TransportTypeData 配置数据的示例字符串，请查看本部分中与该适配器关联的配置属性主题。</span><span class="sxs-lookup"><span data-stu-id="e6fe1-126">To view a sample string used as the TransportTypeData configuration data for each integrated adapter, please see the configuration properties topic that is associated with the adapter in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6fe1-127">本节内容</span><span class="sxs-lookup"><span data-stu-id="e6fe1-127">In This Section</span></span>  
 [<span data-ttu-id="e6fe1-128">配置属性变量类型</span><span class="sxs-lookup"><span data-stu-id="e6fe1-128">Configuration Property Variable Types</span></span>](../core/configuration-property-variable-types.md)  
  
 [<span data-ttu-id="e6fe1-129">文件适配器配置属性</span><span class="sxs-lookup"><span data-stu-id="e6fe1-129">File Adapter Configuration Properties</span></span>](../core/file-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="e6fe1-130">FTP 适配器配置属性</span><span class="sxs-lookup"><span data-stu-id="e6fe1-130">FTP Adapter Configuration Properties</span></span>](../core/ftp-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="e6fe1-131">HTTP 适配器配置属性</span><span class="sxs-lookup"><span data-stu-id="e6fe1-131">HTTP Adapter Configuration Properties</span></span>](../core/http-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="e6fe1-132">MQSeries 适配器配置属性</span><span class="sxs-lookup"><span data-stu-id="e6fe1-132">MQSeries Adapter Configuration Properties</span></span>](../core/mqseries-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="e6fe1-133">MSMQ 适配器配置属性</span><span class="sxs-lookup"><span data-stu-id="e6fe1-133">MSMQ Adapter Configuration Properties</span></span>](../core/msmq-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="e6fe1-134">POP3 适配器配置属性</span><span class="sxs-lookup"><span data-stu-id="e6fe1-134">POP3 Adapter Configuration Properties</span></span>](../core/pop3-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="e6fe1-135">SMTP 适配器配置属性</span><span class="sxs-lookup"><span data-stu-id="e6fe1-135">SMTP Adapter Configuration Properties</span></span>](../core/smtp-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="e6fe1-136">SOAP 适配器配置属性</span><span class="sxs-lookup"><span data-stu-id="e6fe1-136">SOAP Adapter Configuration Properties</span></span>](../core/soap-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="e6fe1-137">Windows SharePoint Services 适配器配置属性</span><span class="sxs-lookup"><span data-stu-id="e6fe1-137">Windows Sharepoint Services Adapter Configuration Properties</span></span>](../core/windows-sharepoint-services-adapter-configuration-properties.md)