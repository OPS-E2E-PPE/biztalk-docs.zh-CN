---
title: 使用时的注意事项 Web 服务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea7038dc-4740-4c0a-b6a1-08bc22f42bc2
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c5cbef60d968119950b6c426a45c94d2e9ab60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241997"
---
# <a name="considerations-when-consuming-web-services"></a>使用 Web Services 时的注意事项
本部分说明在使用 Web Services 时应注意的事项。  
  
## <a name="using-two-underscore-characters-in-a-parameter-name"></a>在参数名称中使用两条下划线  
 Web 方法的参数名称不能以“__”（两条下划线）开始。 以两条下划线开始的名称可以创建 XLANG/s 不支持（无法使用）的 Web 消息部分。  
  
## <a name="the-any-element-and-the-anyattribute-attributes-are-not-supported-in-web-methods"></a>在 Web 方法中不支持 any 元素和 anyAttribute 属性。  
 不能使用**任何**元素或**anyAttribute** Web 方法的架构中的属性。  
  
## <a name="using-xlangs-keywords"></a>使用 XLANG/s 关键字  
 Web 服务名称或 Web 方法名称不能为 XLANG/s 中的关键字。 如果在使用中的 Web 服务名称或 Web 方法名称 XLANG/s 关键字，你将收到编译错误，当你将添加 Web 服务。 有关保留字 XLANG/s 语言的列表，请参阅[XLANG-s 保留字](../core/xlang-s-reserved-words.md)。  
  
## <a name="required-xlangs-support-for-parameter-types"></a>参数类型所需的 XLANG/s 支持  
 使用非 XLANG/s 支持的 Web 方法参数类型会导致编译错误。 例如，BizTalk Server 不支持由架构类型的一维数组组成的参数。 另外，BizTalk Server 不支持多维数组。 XLANG/s 语言保留在 BizTalk Server 中的单词列表，请参阅[XLANG-s 保留字](../core/xlang-s-reserved-words.md)。  
  
## <a name="avoiding-compilation-errors-caused-by-adding-web-references-containing-c-keywords-or-identifiers"></a>避免由添加包含 C# 关键字或标识符的 Web 引用导致的编译错误  
 当你使用**添加服务引用**服务将引用添加到 BizTalk 项目，BizTalk Server，将转换所需调用到架构的每个 Web 方法的架构类型。 BizTalk Server 将这些架构添加到 Reference.xsd。 如果你的架构包含都是 C# 关键字的元素名称或元素名称与 C# 标识符无效，则可能获得运行时错误。 要避免运行时错误，请确保您使用的 Web Services 不包含属于 C# 关键字或无效 C# 标识符的元素名称。  
  
## <a name="multiple-serviceport-type-definitions-are-unsupported"></a>不支持多个服务/端口类型定义  
 BizTalk Server 支持添加具有单个服务和端口类型定义的 Web Services 文件。 若要添加具有多个服务或端口类型定义的 WSDL 文件，则可能产生下列错误：  
  
 无法生成 BizTalk 文件。 对象引用未设置为某个对象的实例。  
  
## <a name="support-for-consuming-arrays-exposed-by-web-services"></a>对使用 Web Services 提供的数组的支持  
 BizTalk Server 可以使用由 Web Services 提供的不是 BizTalk 的一维和交错数组。 有关如何使用 Web 服务数组的详细信息，请参阅[如何使用 Web 服务数组](../core/how-to-consume-web-service-arrays.md)。  
  
> [!NOTE]
>  不支持多维数组语法。 例如， `MyArray[1,5]`。  
  
> [!NOTE]
>  BizTalk Server 不支持使用的数组**数据集**由 Web 服务公开的对象。 XLANG/s 子服务本身支持 .NET 数据集类，但是如果您创建的 BizTalk 项目包含对 Web Services 的 Web 引用，而该 Web Services 提供 .NET 数据集对象的数组，那么在您尝试编译该项目时将出错。  
  
## <a name="web-method-parameters-must-be-xml-serializable"></a>Web 方法参数必须执行 Xml 序列化  
 已使用的 Web Services 中的所有参数都必须执行 Xml 序列化。 若所添加的 Web 方法包含未执行 Xml 序列化的参数，则可能会收到以下错误消息：  
  
 必须对 System.Xml.Element 执行 Xml 序列化，才能使其成为消息部分类型。  
  
> [!NOTE]
>  数据类型， **XmlDocument**和**数据集**，同时不 Xml 可序列化，支持。  
  
## <a name="consuming-messaging-only-web-services"></a>使用仅进行消息传送的 Web Services  
 在使用仅进行消息传送的 Web Services 时，所有 BizTalk 消息正文的部分名都必须与 Web 方法的参数名称相匹配。 例如，如果 Web 服务的签名是`WebMethod(MyType1 type1, MyType2 type2)`，部分组成的名称必须是 type1 和 type2，可能会收到以下运行时错误：  
  
 未能检索参数 %1 的消息部分  
  
 有关详细信息，请参阅[如何在仅消息传递方案中使用 Web 服务](../core/how-to-consume-web-services-in-a-messaging-only-scenario.md)。  
  
## <a name="configuring-a-soap-send-port-programmatically"></a>以编程方式配置 SOAP 发送端口  
 可以在消息上下文中以编程方式设置配置属性。 无论发送端口为静态还是动态，您都可以在业务流程或自定义管道组件中设置这些属性。  
  
> [!NOTE]
>  若要配置**MethodName**静态 SOAP 属性以编程方式发送端口，你需要设置**方法名称**到 **[指定更高版本]** 中**Web服务**选项卡**SOAP 传输属性**BizTalk Server 管理控制台中的对话框。  
>   
>  有关详细信息**MethodName**属性，请参阅[如何动态设置使用的 Web 服务的 URI](../core/how-to-dynamically-set-the-uri-of-a-consumed-web-service.md)。  
>   
>  有关详细信息**SOAP 传输属性**对话框中，请参阅**SOAP 传输属性对话框中，Web 服务**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="property-rules"></a>属性规则  
 如果在业务流程或接收管道的自定义管道组件中设置配置属性，则需遵循下列规则：  
  
-   如果消息发送到一个静态发送端口，将被覆盖发送端口的值为配置的属性值。  
  
-   如果一条消息发送到动态发送端口，则属性值不会被覆盖。  
  
 如果在发送管道的自定义管道组件中设置配置属性，则需遵循下列规则：  
  
-   无论将消息发送到静态发送端口还是动态发送端口，都不会覆盖属性值。 换言之，无论在哪里设置配置属性，发送管道组件都会将其覆盖。  
  
-   有关自定义管道组件的详细信息，请参阅[开发自定义管道组件](../core/developing-custom-pipeline-components.md)。  
  
-   有关 SOAP 发送适配器的配置属性的详细信息，请参阅[如何动态设置使用的 Web 服务的 URI](../core/how-to-dynamically-set-the-uri-of-a-consumed-web-service.md)。  
  
## <a name="adding-a-web-reference-to-a-consumed-web-service-that-contains-a-multi-rooted-schema-will-cause-a-compilation-error"></a>向已使用的包含多个根架构的 Web Services 添加 Web 引用将导致编译错误  
 如果给 Web Services 项目添加的 Web 引用派生自已发布的 BizTalk 业务流程，并且该业务流程包含具有多个根的架构，则在编译该项目时会出错。 如果给项目添加的 Web 引用派生自已发布的 BizTalk 业务流程，需确保业务流程不包含任何多根架构。  
  
## <a name="using-typeddatasets-as-parameters-to-web-methods"></a>将 TypedDataSets 用作 Web 方法的参数  
 为支持将 TypedDataSets 用作 Web 方法的参数，需要执行以下操作：  
  
1.  将 Web 引用添加到 C# 项目，然后生成代理。  
  
2.  创建 SOAP 发送端口并在发送端口上指定该代理，然后选择方法。  
  
3.  在业务流程中定义后期绑定端口和消息类型。 有关其中任何属性提升或可分辨的字段访问所需的大多数情况下，类型可以定义为**XMLDocument**。 为该类型选择直通管道。  
  
4.  在 BizTalk Server 管理控制台中，在**Web 服务**选项卡中**SOAP 传输属性**对话框中的 SOAP 发送端口，指定你想要使用你创建该代理。 您还需要指定程序集、类型和方法。 有关详细信息，请参阅**SOAP 传输属性对话框中，Web 服务**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="adding-a-web-reference-to-a-consumed-web-service-that-contains-a-web-method-expecting-generic-based-parameters-will-cause-a-compilation-error"></a>如果已使用的 Web Services 所包含的 Web 方法需要基于泛型的参数，那么在将 Web 引用添加到这样的 Web Services 时，将导致编译错误  
 如果给 Web Services 项目添加的 Web 引用所包含的 Web 方法需要基于泛型的参数，例如空参数，则在编译此项目时会出错。 不支持此设置。 您必须使用显式专用化从 XLANG/s 中调用泛型类。  
  
## <a name="biztalk-schema-generation-using-the-add-service-reference"></a>使用“添加服务引用”生成 BizTalk 架构  
 当你使用**添加服务引用**服务将引用添加到 BizTalk 项目，BizTalk Server，将转换所需调用到架构的每个 Web 方法的架构类型。 BizTalk Server 将这些架构添加到 Reference.xsd。 若要确保**添加服务引用**生成 BizTalk 架构是否正确，Web 服务必须遵循以下指导原则：  
  
-   Web 方法应具有**SoapDocumentMethodAttribute**而不是**SoapRpcMethodAttribute**。  
  
-   Web 服务和方法必须使用**文本**绑定而不**编码**如 **[SoapDocumentMethod(Use=SoapBindingUse.Literal)]**。  
  
-   Web 方法参数和返回类型必须具有**XmlRootAttribute**使用一个有效**Namespace**属性除非它们是本机的 XSD 类型和 XmlNode 类型。  
  
-   Web 方法不得使用**RequestNamespace**和**ResponseNamespace**中的属性**SoapDocumentMethodAttribute**。  
  
-   Web Services 必须符合 Web Services 互操作性 (WSI) 基本配置文件版本 1.1。  
  
## <a name="xsd-will-not-contain-nodes-for-simple-parameter-types"></a>XSD 将不包含简单参数类型的节点  
 当您添加 Web 应用且 Web 方法具有一个简单类型的参数时，生成的 XSD 将不包含该参数的节点。 而生成的多部分消息将包含属于简单类型的参数。 业务流程应适当地处理此消息部分。 如果它属于到 Web 服务的请求，则将值手动分配到具有消息赋值形状的消息部分。 如果它属于来自 Web 服务的响应，则对表达式形状的消息部分进行手动访问来查看值。  
  
## <a name="the-add-service-reference-do-not-support-the-web-services-description-language-wsdl-import-element"></a>“添加服务引用”不支持 Web Services 描述语言 (WSDL) 导入元素  
 为具有导入元素的 WSDL 文件添加服务引用时，“添加服务引用”会失败。  
  
## <a name="see-also"></a>另请参阅  
 [构造 Web 消息](../core/constructing-web-messages.md)