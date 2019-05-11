---
title: 用于在 BizTalk 中的 Oracle 数据库的 BizTalk 适配器的术语表 |Microsoft Docs
description: 常见术语和定义使用的 BizTalk 适配器包 (BAP) 中的 Oracle 数据库适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d386cd36-d8e4-4e5e-806e-0d02e042344f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2a89bfcfcf387ed6451f795a9e5f83c174eca74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376523"
---
# <a name="glossary"></a>词汇表
中使用以下术语和定义[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。    
  
## <a name="a"></a>A  
  
**adapter**  
基于 WCF 的组件，可帮助 exchange 应用程序 （例如，业务线系统） 之间的消息和 BizTalk Server。 适配器由设计时组件和接收和发送操作的运行时组件组成。

**适配器客户端**  
应用程序与通过适配器的业务线 (LOB) 系统进行交互。  
  
## <a name="b"></a>B  
  
**BFILE**  
Oracle 数据类型，可以访问二进制文件存储在文件系统外部的 Oracle 数据库中的 Lob。 一个 BFILE 列存储 BFILE 定位符，它表示的目录名称和包含服务器文件系统上的数据的文件名称。

**二进制大型对象**  
1.  一个大型的数据，如位图，特征是大型字段值、 不可预测的表的大小，并为不从应用程序的角度来看定型数据的数据。
2.  指定包含有关的数据块的信息的 BLOB 结构关键字。

**binding**  
通过哪种软件组件和层链接在一起的过程。 安装网络组件时，建立绑定关系和依赖项的组件。 绑定允许组件彼此通信。 在 BizTalk Server 中，业务流程适配器无关的终结点 （端口或角色链接） 和物理特定于适配器的终结点 （发送/接收端口或参与方） 之间已建立的映射。

**BizTalk Server**  
连接不同的软件。 BizTalk Server，可创建和修改使用该软件的流程逻辑。 BizTalk Server 还可以监视正在运行的进程、 与贸易合作伙伴进行交互以及执行其他面向企业的任务的信息工作者。
  
## <a name="c"></a>C  
  
**channel**  
绑定元素的具体实现。 绑定表示配置，而通道为与该配置关联的实现。 因此，没有与每个绑定元素关联的通道。 通道堆叠在一起以形成绑定的具体实现： 通道堆栈。

**连接 URI**  
标识分布式环境中的资源的字符串。 适配器使用统一资源标识符 (URI)，其中包含与 LOB 系统建立连接所需的信息的连接。

**contract**  
指定的集合和访问服务提供的操作所需的消息的结构。  
  
## <a name="d"></a>D  
  
**数据操作语言 (DML)**  
用于检索和操作数据的 SQL 语句的子集。 DML 语句通常开始于 SELECT、 INSERT、 UPDATE 或 DELETE。

**设计时体验**  
过程和开发人员在设计时期间执行的操作例如，使用使用适配器服务的 BizTalk 项目添加中检索消息架构。  
  
## <a name="e"></a>E  
  
**终结点地址**  
网络地址标识 Windows Communication Foundation (WCF) 服务终结点的位置。 为适配器，终结点地址表示为统一资源标识符 (URI)，其中包含位置和连接参数的连接。 适配器可以使用这些来建立与基础业务 (LOB) 系统的连接。

**企业单一登录系统 (SSO)**  
SSO 数据库、 主密钥服务器和一个或多个企业单一登录 (SSO) 服务器。 这些服务器的 Windows 和非 Windows 凭据之间进行映射，查找在 SSO 数据库中，凭据用于管理 SSO 系统。 SSO 数据库还用作为配置存储来保存适配器的自定义配置数据。

**可扩展标记语言 (XML)**  
标记语言，专门用于描述数据。 未预定义的 XML 标记。  
  
## <a name="g"></a>G  
  
**全局程序集缓存 (GAC)**  
计算机范围内的代码缓存，用于存储专为由计算机上的许多应用程序共享而安装的程序集。 应用程序部署到全局程序集缓存中必须具有强名称。
  
## <a name="i"></a>I  
  
**入站的操作**  
调用的业务 (LOB) 系统的适配器上的操作。  
  
## <a name="l"></a>L  
  
**本地命名方法**  
Oracle 命名 Oracle 数据库适配器所支持的方法。 在此命名方法中，对 Oracle 客户端将网络服务名称解析为本地 tnsnames.ora 文件中的条目。  
  
## <a name="m"></a>M  
  
**metadata**  
在 WCF 中，是指由服务公开的协定说明。 这称为服务说明和表示 WSDL 文档中。 由适配器公开的元数据描述的 （接口） 它可以对基础 LOB 系统执行的操作。

**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
生成 BizTalk 适配器使用基于 Web 服务的开放标准规范。  
  
## <a name="n"></a>N  
  
**命名方法**  
Oracle 命名方法确定如何对 Oracle 客户端获取 Oracle 数据库服务 （实例） 的连接信息。 可以配置 Oracle 客户端通过使用 Oracle 网络配置助手使用特定的命名方法。 Oracle 数据库适配器支持本地命名方法。

**网络服务名称**  
Oracle 客户端用于获取连接信息的 Oracle 数据库别名。 作为一个连接 URI 中的连接属性提供网络服务名称。  
  
## <a name="o"></a>O  
  
**one-way**  
接收方会返回在其中发送方发送一条消息，但无响应的消息交换模式 (MEP)。 在 BizTalk Server 中，Mep 统称为通信模式。

**出站操作**  
由业务线系统 (LOB) 适配器调用操作。

**output.cs**  
ServiceModel 元数据实用工具 (svcutil.exe) 工具创建的默认输出文件。  
  
## <a name="p"></a>P  
  
**polling**  
设备驱动程序用于找出从多个设备它们是否包含要传输的数据的一种方法。 设备是轮询一次一个。

**proxy**  
在 WCF 中，是指用于实现服务协定由服务公开的托管代码对象。 WCF 服务模型基于此类代理使用。 在 WCF 服务模型中，服务协定表示为.NET 接口。
  
## <a name="r"></a>R  
  
**REF CURSOR**  
Oracle PL/SQL 数据类型，对结果集的 Oracle 数据库中表示的指针。 REF CURSOR 类型支持输入和输出数据的流式处理，适合用于传输大量数据传入和传出 PL/SQL 代码块。

**request-response**  
消息交换模式 (MEP) 发件人发送请求消息，并期望来自接收方的响应消息。 在 BizTalk Server 中，Mep 统称为通信模式。 具体取决于消息传送技术和方向 （入站或出站） 的请求消息，此模式也称为请求-答复或要求响应。

**运行时体验**  
过程和在运行时期间或部署解决方案; 由开发人员执行的操作例如，从 BizTalk Server 管理控制台中创建物理端口绑定。  
  
## <a name="s"></a>S  
  
**schema**  
一条消息的结构。 架构可以包含多个子架构。

**ServiceModel Metadata Utility Tool (svcutil.exe)**  
WCF 附带一个命令行实用工具。 它用于从由适配器之类的 WCF 服务公开的服务说明 （元数据） 创建服务模型代理代码。 对于出站操作，该工具将创建一个 WCF 客户端类和帮助器代码;对于入站操作，该工具创建 WCF 服务协定和帮助程序代码。

**SOAP （简单对象访问协议）**  
用于交换结构化和分散、 分布式环境中的类型信息的简单、 基于 XML 的协议。 WCF 基于客户端与服务调用操作并返回结果的 SOAP 消息的交换。

**SOAP 消息**  
格式正确的 XML 文档。 它应使用的 SOAP 信封和 SOAP 编码命名空间并包含可选的 XML 声明后, 跟 SOAP 信封 （根元素），其中一个可选的 SOAP 标头和 SOAP 消息正文组成。

**SQL Server Integration Services (SSIS)**  
使用导入、 导出和转换来自不同数据源的数据的组件。 以前调用过数据转换服务 (DTS)。

**强类型化数据**  
数据集或绑定到基础对象类型的结果集。 强类型化的 XML 数据集中的每一行被组成类型化的名为对应于基础对象类型的字段的元素。  
 
## <a name="w"></a>W  
**WCF 通道模型**  
依赖于多个接口和其他类型的编程模型。 通道提供用于发送和接收消息的低级编程模型。

**WCF 客户端**  
一种服务操作作为方法公开的客户端应用程序构造。 可以使用添加适配器服务参考 Visual Studio 插件或 ServiceModel Metadata Utility Tool 从由适配器公开的元数据生成 WCF 客户端类。

**WCF 服务约定**  
服务协定的托管代码表示形式。 它将表示为一个接口的类和方法中经过属性化来定义服务、 操作、 消息和数据协定，用来与服务通信。 可以使用 ServiceModel 元数据实用工具工具或添加适配器服务参考 Visual Studio 插件以从由适配器公开的元数据生成 WCF 服务约定。 实现 WCF 服务约定以接收从 LOB 系统的操作。

**WCF 服务模型**  
WCF 编程模型在其中一项服务表示为托管的代码对象。 由服务公开的操作表示为具有强类型化数据的方法。

**弱类型数据**  
数据集或未绑定到基础对象类型的结果集。 在弱类型 XML 数据集中每个行组成的一般列中的属性描述的名称和类型的每个元素的集合。

**Web 服务**  
提供数据和服务添加到其他应用程序的应用程序逻辑的单位。 应用程序访问 XML Web services 使用标准 Web 协议和数据格式如 HTTP、 XML 和 SOAP，独立于每个 XML Web 服务的实现方式。 XML Web services 结合了基于组件的开发的最佳方面和 Web，和是 Microsoft.NET 编程模型的基石。

**Web 服务描述语言 (WSDL)**  
一种基于 XML 的语言，它描述为一组操作的终结点对消息的服务。 WSDL 文档描述服务协定、 操作约定、 消息协定和客户端必须使用的数据协定与服务进行交互。

**Windows Communication Foundation (WCF)**  
Microsoft 面向服务的通信基础结构。 该框架本质上是提供客户端与服务编程模型和编程模型，用于消息交换的更精细的控制通道。

**WS-元数据交换 (MEX) 终结点**  
实现 WCF 服务，如适配器公开的终结点**IMetadataExchange**接口。 WS-元数据交换终结点可以用于检索服务说明 (WSDL) 公开目标系统上的适配器的操作。
  
## <a name="x"></a>X  
  
**XML 架构定义语言 (XSD)**  
一种架构语言。 XML 架构定义元素、 属性和数据类型符合 World Wide Web 联合会 (W3C) XML 架构第 1 部分：XML 架构定义语言的结构建议。 W3C XML 架构第 2 部分：Datatypes Recommendation 是用于在 XML 架构中定义所使用的数据类型的建议。 XML 架构定义语言，可定义 XML 消息的结构和数据类型。