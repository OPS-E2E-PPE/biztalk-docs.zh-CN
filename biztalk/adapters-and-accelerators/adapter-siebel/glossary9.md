---
title: 在 BizTalk Siebel 电子商务应用程序的 BizTalk Adapter 术语表 |Microsoft 文档
description: 常见术语和定义使用 BizTalk 适配器包 (BAP) 中的 Siebel 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75c74760-53b6-45c3-bacc-bb7ab4fb5b4b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54cb0b66bc7cb4b7477160ab2673ec06165ee6c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224677"
---
# <a name="terms-and-definitions-for-the-siebel-adapter"></a>术语和定义为 Siebel 适配器
中使用以下术语和定义[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
 
## <a name="a"></a>仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，  

**适配器**  
应用程序 （例如，业务线系统） 之间的基于 WCF 的组件，可帮助 exchange 消息和 BizTalk Server。 适配器由执行接收操作和发送操作的设计时组件和运行时组件组成。

**适配器客户端**  
应用程序与通过适配器的业务线 (LOB) 系统进行交互。  

  
## <a name="b"></a>B
  
**绑定**  
链接软件组件和层的过程。 安装网络组件时，会建立组件间的绑定关系和依存关系。 绑定可使组件之间互相通信。 在 BizTalk Server 中，指的是与业务流程适配器无关的终结点（端口或角色链接）和特定于物理适配器的终结点（发送/接收端口或参与方）之间已建立的映射。

**BizTalk Server**  
连接不同的软件。 BizTalk Server，可创建和修改过程逻辑，它使用该软件。 使用 BizTalk Server，信息工作者还可以监视正在运行的进程、与贸易合作伙伴进行交互，以及执行其他面向企业的任务。

 
## <a name="c"></a>C
  
**通道**  
绑定元素的具体实现。 绑定表示配置，而通道是与该配置相关联的实现。 因此，没有与每个绑定元素关联的通道。 通道堆叠在一起以形成绑定的具体实现： 通道堆栈。

**连接 URI**  
一个字符串，标识分布式环境中的资源。 适配器使用的连接统一资源标识符 (URI)，包含与 LOB 系统建立连接所需的信息。

**协定**  
指定的集合和访问服务提供的操作所必需的消息的结构。  
  
## <a name="d"></a>D
  
**设计时体验**  
过程和开发人员在设计时; 期间执行的操作例如，使用使用适配器服务 BizTalk 项目外接程序检索消息架构。 

 
## <a name="e"></a>E 
  
**终结点地址**  
标识 Windows Communication Foundation (WCF) 服务终结点的位置的网络地址。 对于适配器，终结点地址表示为统一资源标识符 (URI)，包含位置及连接参数的连接。 适配器可以使用这些建立与基础的业务线 (LOB) 系统的连接。

**企业单一登录系统 (SSO)**  
由 SSO 数据库、主密钥服务器以及一个或多个企业单一登录 (SSO) 服务器组成。 这些服务器在 Windows 凭据和非 Windows 凭据之间建立映射，在 SSO 数据库中查找凭据并管理 SSO 系统。 SSO 数据库还用作配置存储，以保存适配器的自定义配置数据。

**可扩展标记语言 (XML)**  
标记语言，专门用于描述数据。 XML 标记不是预定义。  
 
 
## <a name="g"></a>G
  
**全局程序集缓存 (GAC)**  
计算机范围内的代码缓存，用于存储专为由计算机上的许多应用程序共享而安装的程序集。 在全局程序集缓存中部署的应用程序必须具有强名称。
  
 
## <a name="i"></a>I
  
**入站的操作**  
是由在适配器上的业务线 (LOB) 系统调用的操作。  
  
## <a name="m"></a>M
  
**元数据**  
在 WCF 中，是指由服务公开的协定的说明。 这被称为服务说明和表示 WSDL 文档中。 适配器公开的元数据描述的 （接口） 它可以对基础的 LOB 系统执行的操作。 诸如位置、时间、消息大小等信息和/或异常信息。


**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
用于构建 BizTalk 适配器使用开放标准，基于 Web 服务规范。  
  
## <a name="o"></a>O
  
**单向**  
发件人发送一条消息，但没有响应的消息交换模式 (MEP) 返回的接收方。 在 BizTalk Server 中 Mep 统称为通信模式。

**出站操作**  
由业务线系统 (LOB) 上的适配器调用操作。

**output.cs**  
ServiceModel 元数据实用工具 (svcutil.exe) 创建的默认输出文件。  
 
## <a name="p"></a>P
  
**选择列表**  
其值通常限制为一组值 （像是枚举） 之一的业务组件中的字段。

**代理**  
在 WCF 中，引用托管代码实现的对象，由服务公开的服务协定。 WCF 服务模型取决于此类代理使用。 在 WCF 服务模型中，服务协定表示为.NET 接口。
  
## <a name="r"></a>R
  
**请求-响应**  
消息交换模式 (MEP) 发件人发送请求消息，并需要从接收方的响应消息。 在 BizTalk Server 中 Mep 统称为通信模式。 具体取决于消息传送技术和请求消息 （入站或出站） 的方向，此模式也称为请求-答复或请求作出响应。

**运行时体验**  
过程和在运行时期间或部署解决方案; 由开发人员执行的操作例如，从 BizTalk Server 管理控制台中创建物理端口绑定。  


## <a name="s"></a>S
  
**架构**  
消息的结构。 架构可以包含多个子。

**ServiceModel 元数据实用工具 (svcutil.exe)**  
WCF 包含一个命令行实用工具。 它用于从适配器之类的 WCF 服务公开的服务说明 （元数据） 创建服务模型代理代码。 对于出站操作，该工具可创建 WCF 客户端类和帮助程序代码;对于入站操作，该工具创建 WCF 服务协定和帮助程序代码。

**Siebel 在业务组件**  
关联逻辑上相关列从一个或多个表到单个结构。

**Siebel 业务对象**  
表示业务组件的逻辑分组。
  
**Siebel 业务服务**  
业务服务方法或可以在 Siebel 系统中直接调用的函数的集合。
  
**Siebel COM 数据控件库**  
包含启用外部客户端，如在 Siebel 适配器连接并与 Siebel 应用程序对象管理器通信 Siebel 服务器上的接口。

**SOAP （简单对象访问协议）**  
用于交换结构化和分散和分布式环境中的类型信息的简单、 基于 XML 的协议。 WCF 基于的客户端和服务调用操作并返回结果之间的 SOAP 消息交换。

**SOAP 消息**  
格式正确的 XML 文档。 此消息应使用 SOAP 信封和 SOAP 编码命名空间，并且应包含可选的 XML 声明，声明后跟 SOAP 信封（根元素）。此消息由可选的 SOAP 标头和 SOAP 消息正文组成。

**SQL Server Integration Services (SSIS)**  
用于导入、 导出，并将来自不同数据源的数据转换组件。 以前称为数据转换服务 (DTS)。

**强类型化数据**  
数据集或绑定到的基础对象类型的结果集。 强类型 XML 数据集中的每一行被组成类型化，名为基础的对象类型的字段对应的元素。  
  
## <a name="w"></a>W
  
**WCF 通道模型**  
一个依赖于多个接口和其他类型的编程模型。 通道提供用于发送和接收消息的低级编程模型。
  
**WCF 客户端**  
一个客户端应用程序构造，用于将服务操作作为方法公开。 可用于添加适配器服务引用 Visual Studio 插件或 ServiceModel 元数据实用工具从适配器公开的元数据生成 WCF 客户端类。

**WCF 服务协定**  
托管代码表示形式的服务协定。 它之所以表示为接口中的类和方法属性来定义服务、 操作、 消息和用于与服务通信的数据协定。 你可以使用 ServiceModel 元数据实用工具工具或添加适配器服务引用 Visual Studio 插件从适配器公开的元数据生成 WCF 服务协定。 实现 WCF 服务约定以接收从 LOB 系统的操作。

**WCF 服务模型**  
在其中一项服务会表示为托管的代码对象的一种 WCF 编程模型。 由服务公开的操作表示为具有强类型数据的方法。

**弱类型化数据**  
数据集或未绑定到的基础对象类型的结果集。 弱类型 XML 数据集中的每个行组成的一般顺序特性描述的名称和每个元素的类型的列集合。

**web 服务**  
提供数据和向其他应用程序的服务的应用程序逻辑的单位。 应用程序使用标准 Web 协议和数据格式（如 HTTP、XML 和 SOAP）访问 XML Web Services，并与每个 XML Web Services 如何实现无关。 XML Web Services 结合了基于组件的开发和 Web 两者的优点，同时还是 Microsoft .NET 编程模型的基础。

**Web 服务描述语言**  
一种基于 XML 的语言，它描述作为一组操作的终结点的服务，在消息上。 WSDL 文档描述服务协定、 操作协定、 消息协定和数据协定，客户端必须使用以便与该服务。

**Windows Communication Foundation (WCF)**  
Microsoft 面向服务的通信基础结构。 该框架本质上是提供客户端与服务编程模型和编程模型的消息交换更精细的控制通道。

**WS 元数据交换 (MEX) 终结点**  
实现 WCF 服务，例如适配器，公开的终结点**IMetadataExchange**接口。 WS 元数据交换终结点可以用于检索服务说明 (WSDL) 公开的目标系统上的适配器操作。 |  
  
## <a name="x"></a>X
**XML 架构定义语言 (XSD)**  
一种架构语言。 XML 架构定义元素、 属性和数据类型符合万维网联合会 (W3C) XML 架构第 1 部分： 结构建议的 XML 架构定义语言。 “W3C XML 架构第 2 部分：数据类型建议”是针对定义 XML 架构中使用的数据类型的建议。 使用 XML 架构定义语言可以定义 XML 消息的结构和数据类型。
