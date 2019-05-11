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
# <a name="use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk"></a>使用 WCF LOB 适配器 SDK 中的 WSDL 代理使用的命名空间
[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]生成 WSDL 和代理服务器使用由开发人员使用提供的值的适配器[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]或通过修改服务命名空间的私有变量的代码中指定和/或`Namespace`适配器的属性。  
  
 架构类型和定义中的元素\<wsdl:types\>\<架构\>默认情况下使用 {OperationNamespace}。 如果特定类型具有中设置重写的 TypeNamespace **TypeMetadata**对象，该命名空间用于复杂类型和 / 或元素定义。  
  
## <a name="impact-on-wsdl"></a>对 WSDL 的影响  
 下表显示了不同的命名空间中的自定义适配器如何影响相应的 WSDL。 在表中，~ {OperationNamespace} 是 URI; 的类命名空间映射例如，如果 {OperationNamespace} 为"myscheme://a.b/c"~ {OperationNamespace} 将 myscheme.a.b.c。  
  
|WSDL 构造|语法|  
|--------------------|------------|  
|WSDL targetNamespace<br /><br /> Xmlns:ts|{Custom}Adapter.Namespace|  
|\<wsdl:portType\>|{scheme}。 ~ {OperationNamespace}|  
|WSDL 输入的消息名称|{scheme}。 ~ {OperationNamespace} _ {操作名称} _InputMessage|  
|WSDL 输出消息名称|{scheme}。 ~ {OperationNamespace} _ {操作名称} _OutputMessage|  
|\<wsdl:types\>\<架构\>targetNamespace|{scheme}://{OperationNamespace}|  
|\<element\>\<complexType\>|如果其值不为 null 或为空，则使用 {TypeNamespace}。|  
  
## <a name="impact-on-proxy"></a>对代理的影响  
 在代理中的三个不同属性受到命名空间：  
  
-   [**System.ServiceModel.ServiceContractAttribute**(Name="{scheme}.~{OperationNamespace}", Namespace="{Custom}Adapter.Namespace”]  
  
-   [**System.ServiceModel.MessageContractAttribute**(WrapperName="DivideResponse", WrapperNamespace="{scheme}://{OperationNamespace}", IsWrapped=true)]  
  
-   [**System.ServiceModel.MessageBodyMemberAttribute**(Namespace="{scheme}://{TypeNamespace}", Order=0)]  
  
## <a name="see-also"></a>请参阅  
 [使用 WCF LOB 适配器 SDK 开发最佳做法](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)