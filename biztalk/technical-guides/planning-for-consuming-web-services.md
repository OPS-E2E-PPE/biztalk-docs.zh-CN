---
title: 规划使用 Web 服务 |Microsoft Docs
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
ms.openlocfilehash: 3d5998fbdefeb36af8f6a437613523b95b3d9aba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393480"
---
# <a name="planning-for-consuming-web-services"></a>规划使用 Web 服务
Web 服务的规划可以分为两类，用于发布 Web 服务和规划使用 Web 服务计划。 本主题介绍有关使用 Web services 的注意事项。 有关发布 Web 服务的信息，请参阅[规划发布 Web Services1](../technical-guides/planning-for-publishing-web-services1.md)。  
  
 创建你的计划，请记住以下：  
  
- **在参数名称中使用两个下划线字符**  
  
   Web 方法的参数名称不能以"__"（两条下划线） 开头。 以两个下划线字符开头的名称可能会创建不受支持的 Web 消息部分 （不可用） 的 XLANG/s。  
  
- **任何元素和 anyAttribute Web 方法中不支持特性**  
  
   不能使用**任何**元素或**anyAttribute** Web 方法的架构中的属性。  
  
- **使用 XLANG/s 关键字**  
  
   Web 服务名称或 Web 方法名称不能是 XLANG/s 中的关键字。 如果使用 Web 服务名称或 Web 方法名称中的 XLANG/s 关键字，则会编译错误，当您将添加 Web 服务。 XLANG/s 语言保留字的列表，请参阅[XLANG/s 保留字](http://go.microsoft.com/fwlink/?LinkId=155765)(http://go.microsoft.com/fwlink/?LinkId=155765)。  
  
- **对参数类型的所需的 XLANG/s 支持**  
  
   使用非 XLANG/s 支持的 Web 方法参数类型将导致编译错误。 例如，BizTalk Server 不支持包含的一维数组的架构类型的参数。 此外，BizTalk Server 不支持多维数组。 XLANG/s 语言保留在 BizTalk Server 中的单词列表，请参阅[XLANG/s 保留字](http://go.microsoft.com/fwlink/?LinkId=155765)(http://go.microsoft.com/fwlink/?LinkId=155765)。  
  
- **避免由添加 Web 引用包含 C# 关键字或标识符导致编译错误**  
  
   当你使用**添加 Web 引用**若要添加到 BizTalk 项目的 Web 引用，BizTalk Server 将调用架构到每个 Web 方法所需的架构类型。 BizTalk Server 将这些架构添加到 Reference.xsd。 如果您的架构包含元素名称的 C# 关键字或元素名称不是有效的 C# 标识符，您可能会出现运行时错误。 若要避免运行时错误，请确保你使用的 Web 服务不包含 C# 关键字或无效 C# 标识符的元素名称。  
  
- **不支持多个服务/端口类型定义**  
  
   BizTalk Server 支持添加单个服务和端口类型定义的 Web 服务文件。 如果添加具有多个服务的 WSDL 文件或端口类型定义，可能会收到以下错误：  
  
   `Could not generate BizTalk files. Object reference not set to an instance of an object.`  
  
- **使用 Web 服务所公开的数组的支持**  
  
   BizTalk Server 可以使用不是 BizTalk Server Web 服务的 Web 服务公开的一维和交错数组。 有关如何使用 Web 服务数组的详细信息，请参阅[如何使用 Web 服务数组](http://go.microsoft.com/fwlink/?LinkId=155766)(http://go.microsoft.com/fwlink/?LinkId=155766)。  
  
  > [!NOTE]  
  >  不支持多维数组语法。 例如， *Myarray[1,5]*。  
  
  > [!NOTE]  
  >  BizTalk Server 不支持使用一个数组**数据集**由 Web 服务公开的对象。 XLANG/s 子服务以本机方式支持的.NET 数据集类，但如果您创建一个包含对公开.NET 数据集对象的数组的 Web 服务的 Web 引用的 BizTalk 项目尝试编译项目时，会出现错误。  
  
- **Web 方法参数必须是 Xml 可序列化**  
  
   已使用的 Web 服务中的所有参数必须都是 Xml 可序列化。 如果添加的 Web 方法包含不是 Xml 可序列化的参数时，可能会收到以下错误消息：  
  
   才能使其必须是 Xml Seralizeable 为消息部分类型。  
  
  > [!NOTE]  
  >  数据类型， **XmlDocument**并**数据集**，支持时不执行 Xml 序列化。  
  
- **使用仅消息传递 Web 服务**  
  
   当使用仅消息传递 Web 服务，所有 BizTalk Server 消息正文部分组成的名称必须与 Web 方法参数名称都匹配。 例如，如果 Web 服务的签名为`WebMethod(MyType1 type1, MyType2 type2)`、 部分名必须为 type1 和 type2，可能会收到以下运行时错误：  
  
   `Failed to retrieve the message part for parameter %1`  
  
   有关详细信息，请参阅[如何在 Messaging-Only 方案中使用 Web 服务](http://go.microsoft.com/fwlink/?LinkId=155767)(http://go.microsoft.com/fwlink/?LinkId=155767)。  
  
- **以编程方式配置 SOAP 发送端口**  
  
   就可以以编程方式设置配置属性在消息上下文。 发送端口是静态还是动态，可以在业务流程或自定义管道组件中设置这些属性。  
  
  > [!NOTE]  
  >  若要配置**MethodName**属性为静态 SOAP 发送端口以编程方式，您需要设置**方法名称**到 **[以后指定]** 中**Web服务**选项卡**SOAP 传输属性**BizTalk Server 管理控制台中的对话框。  
  
   有关详细信息**MethodName**属性，请参阅[如何动态设置使用 Web 服务的 URI](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768)。  
  
- **属性规则**  
  
   如果在业务流程中或在接收管道的自定义管道组件中设置配置属性，然后应用以下规则：  
  
  - 如果一条消息发送到静态发送端口，属性值将覆盖与该发送端口配置的值。  
  
  - 如果一条消息发送到动态发送端口，则不会覆盖属性值。  
  
    如果在发送管道的自定义管道组件中设置配置属性，则应用以下规则：  
  
  - 值不会被覆盖而不考虑是否将消息发送到静态或动态发送端口。 换而言之，发送管道组件覆盖无论后者已设置的配置属性。  
  
  - 有关自定义管道组件的详细信息，请参阅[开发自定义管道组件](http://go.microsoft.com/fwlink/?LinkId=155769)(http://go.microsoft.com/fwlink/?LinkId=155769)。  
  
  - 有关 SOAP 发送适配器的配置属性的详细信息，请参阅[如何动态设置使用 Web 服务的 URI](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768)。  
  
- **添加对包含多个根的架构将导致编译错误的已使用的 Web 服务的 Web 引用**  
  
   如果添加对已发布的 BizTalk 业务流程中派生的 Web 服务的项目的 Web 引用，并且该业务流程包含具有多个根的架构，然后编译项目时也将会出错。 如果您添加到你的项目已发布的 BizTalk 业务流程中派生的 Web 引用，请确保该业务流程不包含任何多根的架构。  
  
- **将 TypedDataSets 用作 Web 方法的参数**  
  
   下面是需要执行的操作支持将 TypedDataSets 用作 Web 方法的参数：  
  
  1.  添加一个 C# 项目的 Web 引用，然后生成代理。  
  
  2.  创建 SOAP 发送端口和发送端口上指定该代理，并选择的方法。  
  
  3.  在业务流程，定义后期绑定的端口并定义消息类型。 在大多数情况下需要没有属性升级或可分辨的字段访问的位置，该类型可以定义为**XMLDocument**。 与此类型选择直通管道。  
  
  4.  在 BizTalk Server 管理控制台中，在**Web 服务**选项卡**SOAP 传输属性**对话框中的 soap 发送端口中，指定你想要使用创建该代理。 此外需要指定程序集、 类型和方法。  
  
- **添加对包含的 Web 方法需要基于泛型的参数将导致编译错误的已使用的 Web 服务的 Web 引用**  
  
   如果添加对包含的 Web 方法需要基于泛型的参数，如可以为 null 的参数的 Web 服务的项目的 Web 引用时，编译项目时，将会出错。 不支持此设置。 您必须使用显式专用化从 XLANG/s 调用泛型类。  
  
- **使用添加 Web 引用生成 BizTalk 架构**  
  
   当你使用**添加 Web 引用**若要添加到 BizTalk 项目的 Web 引用，BizTalk Server 将调用架构到每个 Web 方法所需的架构类型。 BizTalk Server 将这些架构添加到 Reference.xsd。 若要确保**添加 Web 引用**生成 BizTalk 架构正确，Web 服务必须符合以下要求：  
  
  -   Web 方法应有**SoapDocumentMethodAttribute**而不是**SoapRpcMethodAttribute**。  
  
  -   Web 服务和方法必须使用**文字**而不绑定**Encoded**如 **[SoapDocumentMethod(Use=SoapBindingUse.Literal)]**。  
  
  -   Web 方法参数和返回类型必须具有**XmlRootAttribute**使用一个有效**Namespace**属性除非它们是本机 XSD 类型和 XmlNode 类型。  
  
  -   不能使用 web 方法**RequestNamespace**并**ResponseNamespace**中的属性**SoapDocumentMethodAttribute**。  
  
  -   Web 服务必须符合 Web 服务互操作性 (WSI) 基本概要 1.1 版。  
  
- **添加 Web 引用不支持 Web 服务描述语言 (WSDL) 导入元素**  
  
   添加 Web 引用的 WSDL 文件的导入元素时，添加 Web 引用将失败。  
  
## <a name="see-also"></a>请参阅  
 [规划 BizTalk Server 层](../technical-guides/planning-the-biztalk-server-tier.md)