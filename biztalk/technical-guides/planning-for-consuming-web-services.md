---
title: 规划使用 Web 服务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24863069-929b-4b0b-9643-073965fb5532
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4a13151a5dd76b20b70872b963dc6a688370444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302269"
---
# <a name="planning-for-consuming-web-services"></a>规划使用 Web 服务
规划 Web 服务可以划分为两个类别，规划用于发布 Web 服务和规划使用 Web 服务。 本主题介绍有关使用 Web 服务的注意事项。 有关发布 Web 服务的信息，请参阅[规划发布 Web Services1](../technical-guides/planning-for-publishing-web-services1.md)。  
  
 创建你的计划，请记住以下：  
  
-   **在参数名称中使用两个下划线字符**  
  
     Web 方法的参数名称不能以“__”（两条下划线）开始。 以两条下划线开始的名称可以创建 XLANG/s 不支持（无法使用）的 Web 消息部分。  
  
-   **任何元素和 anyAttribute Web 方法中不支持的特性**  
  
     不能使用**任何**元素或**anyAttribute** Web 方法的架构中的属性。  
  
-   **使用 XLANG/s 关键字**  
  
     Web 服务名称或 Web 方法名称不能为 XLANG/s 中的关键字。 如果在使用中的 Web 服务名称或 Web 方法名称 XLANG/s 关键字，你将收到编译错误，当你将添加 Web 服务。 有关保留字 XLANG/s 语言的列表，请参阅[XLANG/s 保留字](http://go.microsoft.com/fwlink/?LinkId=155765)(http://go.microsoft.com/fwlink/?LinkId=155765)。  
  
-   **参数类型的所需的 XLANG s 支持**  
  
     使用非 XLANG/s 支持的 Web 方法参数类型将导致编译错误。 例如，BizTalk Server 不支持由架构类型的一维数组组成的参数。 此外，BizTalk Server 不支持多维数组。 XLANG/s 语言保留在 BizTalk Server 中的单词列表，请参阅[XLANG/s 保留字](http://go.microsoft.com/fwlink/?LinkId=155765)(http://go.microsoft.com/fwlink/?LinkId=155765)。  
  
-   **避免由添加 Web 引用包含 C# 关键字或标识符导致的编译错误**  
  
     当你使用**添加 Web 引用**若要添加到 BizTalk 项目的 Web 引用，BizTalk Server，将转换所需调用到架构的每个 Web 方法的架构类型。 BizTalk Server 将这些架构添加到 Reference.xsd。 如果你的架构包含都是 C# 关键字的元素名称或元素名称与 C# 标识符无效，则可能获得运行时错误。 要避免运行时错误，请确保您使用的 Web Services 不包含属于 C# 关键字或无效 C# 标识符的元素名称。  
  
-   **不支持多个服务/端口类型定义**  
  
     BizTalk Server 支持添加具有单个服务和端口类型定义的 Web Services 文件。 若要添加具有多个服务或端口类型定义的 WSDL 文件，则可能产生下列错误：  
  
     `Could not generate BizTalk files. Object reference not set to an instance of an object.`  
  
-   **对使用 Web 服务公开的数组的支持**  
  
     BizTalk Server 可以使用一个维度数组和交错数组不是 BizTalk 服务器 Web 服务的 Web 服务公开。 有关如何使用 Web 服务数组的详细信息，请参阅[如何使用 Web 服务数组](http://go.microsoft.com/fwlink/?LinkId=155766)(http://go.microsoft.com/fwlink/?LinkId=155766)。  
  
    > [!NOTE]  
    >  不支持多维数组语法。 例如， *MyArray [1.5]*。  
  
    > [!NOTE]  
    >  BizTalk Server 不支持使用的数组**数据集**由 Web 服务公开的对象。 XLANG/s 子服务以本机方式支持的.NET 数据集类，但如果你创建 BizTalk 项目包含对公开.NET 数据集对象的数组的 Web 服务的 Web 引用时尝试以编译该项目，你会收到错误。  
  
-   **Web 方法参数必须是 Xml 可序列化**  
  
     已使用的 Web Services 中的所有参数都必须执行 Xml 序列化。 若所添加的 Web 方法包含未执行 Xml 序列化的参数，则可能会收到以下错误消息：  
  
     必须对 System.Xml.Element 执行 Xml 序列化，才能使其成为消息部分类型。  
  
    > [!NOTE]  
    >  数据类型， **XmlDocument**和**数据集**，同时不 Xml 可序列化，支持。  
  
-   **使用仅限消息传送的 Web 服务**  
  
     时使用的仅限消息传送的 Web 服务，则所有 BizTalk Server 消息正文部分的名称必须与 Web 方法参数名称都匹配。 例如，如果 Web 服务的签名是`WebMethod(MyType1 type1, MyType2 type2)`，部分组成的名称必须是 type1 和 type2，可能会收到以下运行时错误：  
  
     `Failed to retrieve the message part for parameter %1`  
  
     有关详细信息，请参阅[如何在 Messaging-Only 方案中使用 Web 服务](http://go.microsoft.com/fwlink/?LinkId=155767)(http://go.microsoft.com/fwlink/?LinkId=155767)。  
  
-   **以编程方式配置 SOAP 发送端口**  
  
     可以在消息上下文中以编程方式设置配置属性。 发送端口是静态还是动态，你可以在业务流程或自定义管道组件中设置这些属性。  
  
    > [!NOTE]  
    >  若要配置**MethodName**静态 SOAP 属性以编程方式发送端口，你需要设置**方法名称**到 **[指定更高版本]** 中**Web服务**选项卡**SOAP 传输属性**BizTalk Server 管理控制台中的对话框。  
  
     有关详细信息**MethodName**属性，请参阅[如何动态设置使用的 Web 服务的 URI](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768)。  
  
-   **属性规则**  
  
     如果在业务流程或接收管道的自定义管道组件中设置配置属性，则需遵循下列规则：  
  
    -   如果消息发送到一个静态发送端口，将被覆盖发送端口的值为配置的属性值。  
  
    -   如果一条消息发送到动态发送端口，则属性值不会被覆盖。  
  
     如果在发送管道的自定义管道组件中设置配置属性，则需遵循下列规则：  
  
    -   无论将消息发送到静态发送端口还是动态发送端口，都不会覆盖属性值。 换言之，无论在哪里设置配置属性，发送管道组件都会将其覆盖。  
  
    -   有关自定义管道组件的详细信息，请参阅[开发自定义管道组件](http://go.microsoft.com/fwlink/?LinkId=155769)(http://go.microsoft.com/fwlink/?LinkId=155769)。  
  
    -   有关 SOAP 发送适配器的配置属性的详细信息，请参阅[如何动态设置使用的 Web 服务的 URI](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768)。  
  
-   **添加对使用的 Web 服务包含多取得 root 权限的架构将导致编译错误的 Web 引用**  
  
     如果你添加到你的项目，从已发布的 BizTalk 业务流程派生的 Web 服务的 Web 引用和业务流程包含具有多个根的架构，然后编译项目时也将会出错。 如果给项目添加的 Web 引用派生自已发布的 BizTalk 业务流程，需确保业务流程不包含任何多根架构。  
  
-   **使用 TypedDataSets 作为 Web 方法的参数**  
  
     为支持将 TypedDataSets 用作 Web 方法的参数，需要执行以下操作：  
  
    1.  将 Web 引用添加到 C# 项目，然后生成代理。  
  
    2.  创建 SOAP 发送端口并在发送端口上指定该代理，然后选择方法。  
  
    3.  在业务流程中定义后期绑定端口和消息类型。 有关其中任何属性提升或可分辨的字段访问所需的大多数情况下，类型可以定义为**XMLDocument**。 为该类型选择直通管道。  
  
    4.  在 BizTalk Server 管理控制台中，在**Web 服务**选项卡中**SOAP 传输属性**对话框中的 SOAP 发送端口，指定你想要使用你创建该代理。 您还需要指定程序集、类型和方法。  
  
-   **添加对包含应基于一般的参数将导致编译错误的 Web 方法的使用的 Web 服务的 Web 引用**  
  
     如果你添加到你的项目包含应基于一般的参数，如可以为 null 的参数的 Web 方法的 Web 服务的 Web 引用，编译项目时，将发生错误。 不支持此设置。 您必须使用显式专用化从 XLANG/s 中调用泛型类。  
  
-   **使用添加 Web 引用 BizTalk 架构生成**  
  
     当你使用**添加 Web 引用**若要添加到 BizTalk 项目的 Web 引用，BizTalk Server，将转换所需调用到架构的每个 Web 方法的架构类型。 BizTalk Server 将这些架构添加到 Reference.xsd。 若要确保**添加 Web 引用**生成 BizTalk 架构是否正确，Web 服务必须遵循以下指导原则：  
  
    -   Web 方法应具有**SoapDocumentMethodAttribute**而不是**SoapRpcMethodAttribute**。  
  
    -   Web 服务和方法必须使用**文本**绑定而不**编码**如 **[SoapDocumentMethod(Use=SoapBindingUse.Literal)]**。  
  
    -   Web 方法参数和返回类型必须具有**XmlRootAttribute**使用一个有效**Namespace**属性除非它们是本机的 XSD 类型和 XmlNode 类型。  
  
    -   Web 方法不得使用**RequestNamespace**和**ResponseNamespace**中的属性**SoapDocumentMethodAttribute**。  
  
    -   Web Services 必须符合 Web Services 互操作性 (WSI) 基本配置文件版本 1.1。  
  
-   **添加 Web 引用不支持 Web 服务描述语言 (WSDL) 导入元素**  
  
     在为具有导入元素的 WSDL 文件添加 Web 引用时，“添加 Web 引用”会失败。  
  
## <a name="see-also"></a>另请参阅  
 [规划 BizTalk 服务器层](../technical-guides/planning-the-biztalk-server-tier.md)