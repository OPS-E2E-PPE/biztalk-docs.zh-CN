---
title: 使用 WCF LOB 适配器 SDK 中的 WSDL 代理使用的命名空间 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 781d20fa-83e3-42fa-866e-5650d5eb71a7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1838ad1a9f611061477397c548daf80ba31ccab8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362704"
---
# <a name="use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="e0a73-102">使用 WCF LOB 适配器 SDK 中的 WSDL 代理使用的命名空间</span><span class="sxs-lookup"><span data-stu-id="e0a73-102">Use namespaces with the WSDL-Proxy in the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="e0a73-103">[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]生成 WSDL 和代理服务器使用由开发人员使用提供的值的适配器[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]或通过修改服务命名空间的私有变量的代码中指定和/或`Namespace`适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="e0a73-103">The [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] generates WSDL and proxies for an adapter using values supplied by the developer using the [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)] or specified in code through modification of the SERVICENAMESPACE private variable and/or the `Namespace` property of the adapter.</span></span>  
  
 <span data-ttu-id="e0a73-104">架构类型和定义中的元素\<wsdl:types\>\<架构\>默认情况下使用 {OperationNamespace}。</span><span class="sxs-lookup"><span data-stu-id="e0a73-104">The schema types and elements defined within the \<wsdl:types\>\<schema\> use the {OperationNamespace} by default.</span></span> <span data-ttu-id="e0a73-105">如果特定类型具有中设置重写的 TypeNamespace **TypeMetadata**对象，该命名空间用于复杂类型和 / 或元素定义。</span><span class="sxs-lookup"><span data-stu-id="e0a73-105">If a particular type has an overridden TypeNamespace set in the **TypeMetadata** object, that namespace is used for the complex type and/or or element definition.</span></span>  
  
## <a name="impact-on-wsdl"></a><span data-ttu-id="e0a73-106">对 WSDL 的影响</span><span class="sxs-lookup"><span data-stu-id="e0a73-106">Impact on WSDL</span></span>  
 <span data-ttu-id="e0a73-107">下表显示了不同的命名空间中的自定义适配器如何影响相应的 WSDL。</span><span class="sxs-lookup"><span data-stu-id="e0a73-107">The following table shows how the different namespaces in a custom adapter affect the corresponding WSDL.</span></span> <span data-ttu-id="e0a73-108">在表中，~ {OperationNamespace} 是 URI; 的类命名空间映射例如，如果 {OperationNamespace} 为"myscheme://a.b/c"~ {OperationNamespace} 将 myscheme.a.b.c。</span><span class="sxs-lookup"><span data-stu-id="e0a73-108">In the table, ~{OperationNamespace} is the class namespace mapping of a URI; for example, if {OperationNamespace} is "myscheme://a.b/c", ~{OperationNamespace} will be myscheme.a.b.c.</span></span>  
  
|<span data-ttu-id="e0a73-109">WSDL 构造</span><span class="sxs-lookup"><span data-stu-id="e0a73-109">WSDL Construct</span></span>|<span data-ttu-id="e0a73-110">语法</span><span class="sxs-lookup"><span data-stu-id="e0a73-110">Syntax</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="e0a73-111">WSDL targetNamespace</span><span class="sxs-lookup"><span data-stu-id="e0a73-111">WSDL targetNamespace,</span></span><br /><br /> <span data-ttu-id="e0a73-112">Xmlns:ts</span><span class="sxs-lookup"><span data-stu-id="e0a73-112">Xmlns:ts</span></span>|<span data-ttu-id="e0a73-113">{Custom}Adapter.Namespace</span><span class="sxs-lookup"><span data-stu-id="e0a73-113">{Custom}Adapter.Namespace</span></span>|  
|<span data-ttu-id="e0a73-114">\<wsdl:portType\></span><span class="sxs-lookup"><span data-stu-id="e0a73-114">\<wsdl:portType\></span></span>|<span data-ttu-id="e0a73-115">{scheme}。 ~ {OperationNamespace}</span><span class="sxs-lookup"><span data-stu-id="e0a73-115">{scheme}.~{OperationNamespace}</span></span>|  
|<span data-ttu-id="e0a73-116">WSDL 输入的消息名称</span><span class="sxs-lookup"><span data-stu-id="e0a73-116">WSDL Input Message Name</span></span>|<span data-ttu-id="e0a73-117">{scheme}。 ~ {OperationNamespace} _ {操作名称} _InputMessage</span><span class="sxs-lookup"><span data-stu-id="e0a73-117">{scheme}.~{OperationNamespace}_{OperationName}_InputMessage</span></span>|  
|<span data-ttu-id="e0a73-118">WSDL 输出消息名称</span><span class="sxs-lookup"><span data-stu-id="e0a73-118">WSDL Output Message Name</span></span>|<span data-ttu-id="e0a73-119">{scheme}。 ~ {OperationNamespace} _ {操作名称} _OutputMessage</span><span class="sxs-lookup"><span data-stu-id="e0a73-119">{scheme}.~{OperationNamespace}_{OperationName}_OutputMessage</span></span>|  
|<span data-ttu-id="e0a73-120">\<wsdl:types\>\<架构\>targetNamespace</span><span class="sxs-lookup"><span data-stu-id="e0a73-120">\<wsdl:types\>\<schema\> targetNamespace</span></span>|<span data-ttu-id="e0a73-121">{scheme}://{OperationNamespace}</span><span class="sxs-lookup"><span data-stu-id="e0a73-121">{scheme}://{OperationNamespace}</span></span>|  
|<span data-ttu-id="e0a73-122">\<element\>\<complexType\></span><span class="sxs-lookup"><span data-stu-id="e0a73-122">\<element\>\<complexType\></span></span>|<span data-ttu-id="e0a73-123">如果其值不为 null 或为空，则使用 {TypeNamespace}。</span><span class="sxs-lookup"><span data-stu-id="e0a73-123">Use {TypeNamespace} if its value is not null or empty.</span></span>|  
  
## <a name="impact-on-proxy"></a><span data-ttu-id="e0a73-124">对代理的影响</span><span class="sxs-lookup"><span data-stu-id="e0a73-124">Impact on Proxy</span></span>  
 <span data-ttu-id="e0a73-125">在代理中的三个不同属性受到命名空间：</span><span class="sxs-lookup"><span data-stu-id="e0a73-125">Three different attributes in the proxy are affected by namespaces:</span></span>  
  
-   <span data-ttu-id="e0a73-126">[**System.ServiceModel.ServiceContractAttribute**(Name="{scheme}.~{OperationNamespace}", Namespace="{Custom}Adapter.Namespace”]</span><span class="sxs-lookup"><span data-stu-id="e0a73-126">[**System.ServiceModel.ServiceContractAttribute**(Name="{scheme}.~{OperationNamespace}", Namespace="{Custom}Adapter.Namespace”]</span></span>  
  
-   <span data-ttu-id="e0a73-127">[**System.ServiceModel.MessageContractAttribute**(WrapperName="DivideResponse", WrapperNamespace="{scheme}://{OperationNamespace}", IsWrapped=true)]</span><span class="sxs-lookup"><span data-stu-id="e0a73-127">[**System.ServiceModel.MessageContractAttribute**(WrapperName="DivideResponse", WrapperNamespace="{scheme}://{OperationNamespace}", IsWrapped=true)]</span></span>  
  
-   <span data-ttu-id="e0a73-128">[**System.ServiceModel.MessageBodyMemberAttribute**(Namespace="{scheme}://{TypeNamespace}", Order=0)]</span><span class="sxs-lookup"><span data-stu-id="e0a73-128">[**System.ServiceModel.MessageBodyMemberAttribute**(Namespace="{scheme}://{TypeNamespace}", Order=0)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0a73-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0a73-129">See Also</span></span>  
 [<span data-ttu-id="e0a73-130">使用 WCF LOB 适配器 SDK 开发最佳做法</span><span class="sxs-lookup"><span data-stu-id="e0a73-130">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)