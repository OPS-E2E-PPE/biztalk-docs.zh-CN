---
title: "使用 WCF LOB 适配器 SDK 中的 WSDL 代理使用的命名空间 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 781d20fa-83e3-42fa-866e-5650d5eb71a7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc21b37ae80299bf5ddd78d1ca48331e1e369e78
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk"></a>使用 WCF LOB 适配器 SDK 中的 WSDL 代理使用的命名空间
[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]生成 WSDL 和适配器使用开发人员使用所提供值的代理[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]或通过修改服务命名空间的私有变量的代码中指定和/或`Namespace`的适配器的属性。  
  
 架构类型和元素中定义\<wsdl:types\>\<架构\>默认情况下使用 {OperationNamespace}。 某个特定类型是否具有设置被重写的全名**在**对象，该命名空间用于复杂类型和 / 或元素定义。  
  
## <a name="impact-on-wsdl"></a>对 WSDL 的影响  
 下表显示不同的命名空间中的自定义适配器如何影响相应的 WSDL。 在表中，~ {OperationNamespace} 是 URI; 类命名空间映射例如，如果 {OperationNamespace} 为"myscheme://a.b/c"~ {OperationNamespace} 将 myscheme.a.b.c。  
  
|WSDL 构造|语法|  
|--------------------|------------|  
|WSDL targetNamespace<br /><br /> Xmlns:ts|{自定义}Adapter.Namespace|  
|\<wsdl:portType\>|{方案}。 ~ {OperationNamespace}|  
|WSDL 输入的消息名称|{方案}。 ~ {OperationNamespace} _ {OperationName} _InputMessage|  
|WSDL 输出消息名称|{方案}。 ~ {OperationNamespace} _ {OperationName} _OutputMessage|  
|\<wsdl:types\>\<架构\>targetNamespace|{方案}:// {OperationNamespace}|  
|\<元素\>\<complexType\>|如果其值不为 null 或为空，则使用 {全名}。|  
  
## <a name="impact-on-proxy"></a>对代理的影响  
 代理中的三个不同属性受命名空间：  
  
-   [**System.ServiceModel.ServiceContractAttribute**(名称 ="{方案}。 ~ {OperationNamespace}"，Namespace="{Custom}Adapter.Namespace"]  
  
-   [**System.ServiceModel.MessageContractAttribute**(WrapperName ="DivideResponse"，WrapperNamespace ="{方案}:// {OperationNamespace}"、 IsWrapped = true)]  
  
-   [**System.ServiceModel.MessageBodyMemberAttribute**(Namespace ="{方案}:// {全名}"，顺序 = 0)]  
  
## <a name="see-also"></a>另请参阅  
 [使用 WCF LOB 适配器 SDK 开发最佳做法](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)