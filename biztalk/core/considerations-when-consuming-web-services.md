---
title: Web 服务使用时的注意事项 |Microsoft Docs
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
ms.openlocfilehash: e7747e04357f041451e8aa6651704f815cba562a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354703"
---
# <a name="considerations-when-consuming-web-services"></a>使用 Web 服务时的注意事项
本部分提供使用 Web 服务时应考虑的信息。  
  
## <a name="using-two-underscore-characters-in-a-parameter-name"></a>参数名称中使用两个下划线字符  
 Web 方法的参数名称不能以"__"（两条下划线） 开头。 以两个下划线字符开头的名称可能会创建不受支持的 Web 消息部分 （不可用） 的 XLANG/s。  
  
## <a name="the-any-element-and-the-anyattribute-attributes-are-not-supported-in-web-methods"></a>在 Web 方法中不支持 any 元素和 anyAttribute 属性。  
 不能使用**任何**元素或**anyAttribute** Web 方法的架构中的属性。  
  
## <a name="using-xlangs-keywords"></a>使用 XLANG/s 关键字  
 Web 服务名称或 Web 方法名称不能是 XLANG/s 中的关键字。 如果使用 Web 服务名称或 Web 方法名称中的 XLANG/s 关键字，则会编译错误，当您将添加 Web 服务。 XLANG/s 语言保留字的列表，请参阅[xlang-s 保留字](../core/xlang-s-reserved-words.md)。  
  
## <a name="required-xlangs-support-for-parameter-types"></a>参数类型所需的 XLANG/s 支持  
 使用非 XLANG/s 支持的 Web 方法参数类型将导致编译错误。 例如，BizTalk Server 不支持包含的一维数组的架构类型的参数。 此外，BizTalk Server 不支持多维数组。 XLANG/s 语言保留在 BizTalk Server 中的单词列表，请参阅[xlang-s 保留字](../core/xlang-s-reserved-words.md)。  
  
## <a name="avoiding-compilation-errors-caused-by-adding-web-references-containing-c-keywords-or-identifiers"></a>避免由添加包含 C# 关键字或标识符的 Web 引用导致的编译错误  
 当你使用**添加服务引用**服务将引用添加到 BizTalk 项目，BizTalk Server 将调用架构到每个 Web 方法所需的架构类型。 BizTalk Server 将这些架构添加到 Reference.xsd。 如果您的架构包含元素名称的 C# 关键字或元素名称不是有效的 C# 标识符，您可能会出现运行时错误。 若要避免运行时错误，请确保你使用的 Web 服务不包含 C# 关键字或无效 C# 标识符的元素名称。  
  
## <a name="multiple-serviceport-type-definitions-are-unsupported"></a>不支持多个服务/端口类型定义  
 BizTalk Server 支持添加单个服务和端口类型定义的 Web 服务文件。 如果添加具有多个服务的 WSDL 文件或端口类型定义，可能会收到以下错误：  
  
 无法生成 BizTalk 文件。 对象引用未设置为某个对象的实例。  
  
## <a name="support-for-consuming-arrays-exposed-by-web-services"></a>使用 Web 服务所公开的数组的支持  
 BizTalk Server 可以使用不是 BizTalk Web 服务的 Web 服务公开的一维和交错数组。 有关如何使用 Web 服务数组的详细信息，请参阅[如何使用 Web 服务数组](../core/how-to-consume-web-service-arrays.md)。  
  
> [!NOTE]
>  不支持多维数组语法。 例如，`MyArray[1,5]`。  
  
> [!NOTE]
>  BizTalk Server 不支持使用一个数组**数据集**由 Web 服务公开的对象。 XLANG/s 子服务以本机方式支持的.NET 数据集类，但如果您创建一个包含对公开.NET 数据集对象的数组的 Web 服务的 Web 引用的 BizTalk 项目尝试编译项目时，您会收到错误。  
  
## <a name="web-method-parameters-must-be-xml-serializable"></a>Web 方法的参数必须是 Xml 可序列化  
 已使用的 Web 服务中的所有参数必须都是 Xml 可序列化。 如果添加的 Web 方法包含不是 Xml 可序列化的参数时，可能会收到以下错误消息：  
  
 才能使其必须是 Xml Seralizeable 为消息部分类型。  
  
> [!NOTE]
>  数据类型， **XmlDocument**并**数据集**，支持时不执行 Xml 序列化。  
  
## <a name="consuming-messaging-only-web-services"></a>使用消息传送的唯一 Web 服务  
 当使用消息传送仅 Web 服务时，所有 BizTalk 消息正文部分组成的名称必须与 Web 方法参数名称都匹配。 例如，如果 Web 服务的签名为`WebMethod(MyType1 type1, MyType2 type2)`、 部分名必须为 type1 和 type2，可能会收到以下运行时错误：  
  
 无法检索参数 %1 的消息部分  
  
 有关详细信息，请参阅[如何在仅消息传递方案中使用 Web 服务](../core/how-to-consume-web-services-in-a-messaging-only-scenario.md)。  
  
## <a name="configuring-a-soap-send-port-programmatically"></a>以编程方式配置 SOAP 发送端口  
 就可以以编程方式设置配置属性在消息上下文。 可以在业务流程或自定义管道组件中设置这些属性，指示发送端口为静态或动态。  
  
> [!NOTE]
>  若要配置**MethodName**属性为静态 SOAP 发送端口以编程方式，您需要设置**方法名称**到 **[以后指定]** 中**Web服务**选项卡**SOAP 传输属性**BizTalk Server 管理控制台中的对话框。  
> 
>  有关详细信息**MethodName**属性，请参阅[如何动态设置使用 Web 服务的 URI](../core/how-to-dynamically-set-the-uri-of-a-consumed-web-service.md)。  
> 
>  有关详细信息**SOAP 传输属性**对话框中，请参阅**SOAP 传输属性对话框，Web 服务**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="property-rules"></a>属性规则  
 如果在业务流程中或在接收管道的自定义管道组件中设置配置属性，然后应用以下规则：  
  
- 如果一条消息发送到静态发送端口，属性值将覆盖与该发送端口配置的值。  
  
- 如果一条消息发送到动态发送端口，则不会覆盖属性值。  
  
  如果在发送管道的自定义管道组件中设置配置属性，则应用以下规则：  
  
- 值不会被覆盖而不考虑是否将消息发送到静态或动态发送端口。 换而言之，发送管道组件覆盖无论后者已设置的配置属性。  
  
- 有关自定义管道组件的详细信息，请参阅[开发自定义管道组件](../core/developing-custom-pipeline-components.md)。  
  
- 有关 SOAP 发送适配器的配置属性的详细信息，请参阅[如何动态设置使用 Web 服务的 URI](../core/how-to-dynamically-set-the-uri-of-a-consumed-web-service.md)。  
  
## <a name="adding-a-web-reference-to-a-consumed-web-service-that-contains-a-multi-rooted-schema-will-cause-a-compilation-error"></a>添加对包含多个根的架构的已使用 Web 服务的 Web 引用将导致编译错误  
 如果添加对已发布的 BizTalk 业务流程中派生的 Web 服务的项目的 Web 引用，并且该业务流程包含具有多个根的架构然后编译项目时也将会出错。 如果您添加到你的项目已发布的 BizTalk 业务流程中派生的 Web 引用，请确保该业务流程不包含任何多根的架构。  
  
## <a name="using-typeddatasets-as-parameters-to-web-methods"></a>将 TypedDataSets 用作 Web 方法的参数  
 下面是需要执行的操作支持将 TypedDataSets 用作 Web 方法的参数：  
  
1. 添加一个 C# 项目的 Web 引用，然后生成代理。  
  
2. 创建 SOAP 发送端口和发送端口上指定该代理，并选择的方法。  
  
3. 在业务流程，定义后期绑定的端口并定义消息类型。 在大多数情况下需要没有属性升级或可分辨的字段访问的位置，该类型可以定义为**XMLDocument**。 与此类型选择直通管道。  
  
4. 在 BizTalk Server 管理控制台中，在**Web 服务**选项卡**SOAP 传输属性**对话框中的 soap 发送端口中，指定你想要使用创建该代理。 此外需要指定程序集、 类型和方法。 有关详细信息，请参阅**SOAP 传输属性对话框，Web 服务**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="adding-a-web-reference-to-a-consumed-web-service-that-contains-a-web-method-expecting-generic-based-parameters-will-cause-a-compilation-error"></a>添加对包含的 Web 方法需要基于泛型的参数的已使用 Web 服务的 Web 引用将导致编译错误  
 如果添加对包含的 Web 方法需要基于泛型的参数可以为 null 的参数等的 Web 服务的项目的 Web 引用时，编译项目时，将会出错。 不支持此设置。 您必须使用显式专用化从 XLANG/s 调用泛型类。  
  
## <a name="biztalk-schema-generation-using-the-add-service-reference"></a>使用添加服务引用生成 BizTalk 架构  
 当你使用**添加服务引用**服务将引用添加到 BizTalk 项目，BizTalk Server 将调用架构到每个 Web 方法所需的架构类型。 BizTalk Server 将这些架构添加到 Reference.xsd。 若要确保**添加服务引用**生成 BizTalk 架构正确，Web 服务必须符合以下要求：  
  
-   Web 方法应有**SoapDocumentMethodAttribute**而不是**SoapRpcMethodAttribute**。  
  
-   Web 服务和方法必须使用**文字**而不绑定**Encoded**如 **[SoapDocumentMethod(Use=SoapBindingUse.Literal)]**。  
  
-   Web 方法参数和返回类型必须具有**XmlRootAttribute**使用一个有效**Namespace**属性除非它们是本机 XSD 类型和 XmlNode 类型。  
  
-   不能使用 web 方法**RequestNamespace**并**ResponseNamespace**中的属性**SoapDocumentMethodAttribute**。  
  
-   Web 服务必须符合 Web 服务互操作性 (WSI) 基本概要 1.1 版。  
  
## <a name="xsd-will-not-contain-nodes-for-simple-parameter-types"></a>XSD 将不包含简单参数类型的节点  
 如果添加 Web 引用和 Web 方法包含是简单类型的参数，所生成的 XSD 将不包含该参数的节点。 相反，会生成多部分消息将包含属于简单类型的部件。 业务流程应适当地处理此消息部分。 如果它是对 Web 服务的请求的一部分，手动将该值赋给具有消息赋值形状该部件。 如果它属于来自 Web 服务的响应，手动访问以查看值的表达式形状中该部分。  
  
## <a name="the-add-service-reference-do-not-support-the-web-services-description-language-wsdl-import-element"></a>添加服务引用不支持 Web 服务描述语言 (WSDL) 导入元素  
 添加服务引用的 WSDL 文件的导入元素时，添加服务引用将失败。  
  
## <a name="see-also"></a>请参阅  
 [构造 Web 消息](../core/constructing-web-messages.md)