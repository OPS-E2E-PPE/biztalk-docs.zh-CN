---
title: 在业务流程中使用 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, creating
- SOAP headers, properties
- Web services, SOAP headers
- orchestrations, SOAP headers
- creating, SOAP headers
ms.assetid: 4754dd23-386b-4093-8ea4-4da6b4d9279c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faae7013c824926adea67feab296e1993f93e326
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288533"
---
# <a name="using-soap-headers-in-orchestrations"></a>在业务流程中使用 SOAP 标头
业务流程使用属性架构来定义 SOAP 标头上下文属性。 使用 BizTalk 编辑器可以设置 SOAP 标头上下文属性。  
  
## <a name="defining-soap-header-context-properties-with-property-schemas"></a>使用属性架构定义 SOAP 标头上下文属性  
 若要在业务流程中使用已定义的 SOAP 标头上下文属性，您需要一个属性架构。 属性架构必须具有的目标命名空间**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**，和**属性架构基**属性设置为**MessageContextPropertyBase**。 属性架构中的每个根元素名称必须与已定义的 SOAP 标头的根元素名称匹配。 然后，可以使用属性架构的命名空间和属性名称设置上下文属性的值。  
  
> [!NOTE]
>  属性架构的命名空间是不同的目标架构的命名空间 (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**)。 命名空间可以是任何字符串；但是，它通常默认为项目的名称。  
  
 下面的代码演示分配属性架构命名空间的 SOAP 标头上下文属性**SOAPHeader**属性名称为**OrigDest**:  
  
```  
requestMessageInstance(SOAPHeader.OrigDest) = stringVar;  
```  
  
 有关属性架构和上下文属性的详细信息，请参阅[属性架构](../core/property-schemas.md)。  
  
## <a name="using-biztalk-editor-to-set-soap-header-context-properties"></a>使用 BizTalk 编辑器设置 SOAP 标头上下文属性  
 对于业务流程，SOAP 标头上下文属性均设置为包含 XML 数据的字符串。 设置使用中的 BizTalk 表达式编辑器这些字符串**消息分配**或**表达式**形状。  
  
 下面的示例演示设置该上下文属性的字符串：  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = "<?xml version=\"1.0\"?>  
<OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
<Origination>Home</Origination>  
<Destination>Work</Destination>  
</OrigDest>"  
```  
  
## <a name="using-biztalk-editor-to-create-an-instance-of-a-soap-header-root-element"></a>使用 BizTalk 编辑器创建 SOAP 标头根元素的实例  
 将 SOAP 标头设置为正确的字符串可能并不容易。 添加对 BizTalk 项目的 Web 引用时，所有复杂的 Web 消息部分都将作为根元素添加到 Reference.xsd。 Reference.xsd 还包含每个已定义的 SOAP 标头的根元素。 为确保使用正确的字符串设置 SOAP 标头，应使用 BizTalk 编辑器为 Reference.xsd 创建 SOAP 标头根元素的实例。 您可以直接使用生成的实例数据，或使用包含实际数据的实例数据。  
  
 有关使用 BizTalk 编辑器生成实例数据的详细信息，请参阅[如何生成实例消息](../core/how-to-generate-instance-messages.md)。  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a>创建用于设置上下文属性的 XmlDocument  
 你可以通过创建设置上下文属性**XmlDocument**和写入的字符串值**XmlDocument**到上下文属性。 声明类型的变量的**XMLDocument**并将 XML 数据分配。  
  
 下面的示例演示设置声明类型的变量的**XMLDocument**并将 XML 数据分配：  
  
```  
xmlDoc.LoadXml("<?xml version=\"1.0\"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination>Home</Origination><Destination>Work</Destination></OrigDest>");  
```  
  
 下面的示例显示了如何设置上下文属性：  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = xmlDoc.OuterXml;  
```  
  
 有关使用 BizTalk 表达式编辑器的详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。 有关调用.NET 类的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
## <a name="creating-soap-headers-for-a-soap-request"></a>为 SOAP 请求创建 SOAP 标头  
 为 SOAP 请求创建 SOAP 标头时，必须确保您已正确创建 SOAP 标头。 SOAP 适配器不验证 SOAP 标头上下文属性的内容。  
  
> [!NOTE]
>  如果 SOAP 标头不正确，则 BizTalk 就不能将 SOAP 请求发送到 Web Services。  
  
 BizTalk 返回给 Web Services 的 SOAP 响应也可能包含 SOAP 标头。 只有 SOAP 标头为已定义的 SOAP 标头时才可以访问这些 SOAP 标头。  
  
> [!NOTE]
>  已使用的 Web Services 仅支持已定义的 SOAP 标头。  
  
 有关定义的 SOAP 标头的详细信息，请参阅[使用 SOAP 标头](../core/using-soap-headers.md)。 响应 SOAP 标头使用与请求 SOAP 标头相同的语法设置为上下文属性。  
  
 下面的代码显示了如何访问响应 SOAP 标头：  
  
```  
stringVar = ResponseMessageInstance(SOAPHeader.OrigDest);  
```  
  
 上下文属性中包含的值是包含 XML 数据的字符串。 设置使用 BizTalk 表达式编辑器，在这些字符串**消息分配**或**表达式**形状。 加载中的字符串**XmlDocument**并使用 XPath 查询来访问特定字段。  
  
 有关创建 BizTalk 表达式编辑器中的 XML 文档的详细信息，请参阅[XLANG-s 语言](../core/xlang-s-language.md)。  
  
## <a name="see-also"></a>另请参阅  
 [XLANG-s 语言](../core/xlang-s-language.md)   
 [与使用的 Web 服务的 SOAP 标头](../core/soap-headers-with-consumed-web-services.md)