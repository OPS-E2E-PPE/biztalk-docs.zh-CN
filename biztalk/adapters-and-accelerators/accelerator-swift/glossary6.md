---
title: BizTalk Server 中的 SWIFT 快捷键的术语表 |Microsoft 文档
description: 常见术语和定义知道并了解如何使用 BizTalk Accelerator for SWIFT
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7331beb-f6a7-4eea-8b31-28f5d15666d0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1230b6b1578a4a3aa7c719df4dffb718b0c748e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210333"
---
# <a name="glossary"></a>词汇表
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for SWIFT 使用以下术语表术语和定义。  
  
## <a name="a"></a>仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，  
 **汇编程序**  
 A [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]发送管道组件的出站管道处理的组装阶段期间将调用。 汇编程序通常执行序列化到某些平面文件格式从 XML 出站消息的作业。  
  
 **程序集**  
 主要构建基块[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]应用程序。 它是重复使用、 版本控制、 安全性和部署的基本单位。 它是向程序员来说，单个动态链接库 (DLL) 或可执行文件 (EXE) 显示的文件的集合。  
  
 **程序集缓存**  
 一种计算机范围的代码缓存，用于并排显示的程序集的存储。 有两个部分缓存。 全局程序集缓存包含显式安装为在计算机上的许多应用程序之间共享的程序集。 页不会影响其他应用程序或下载缓存存储从 Internet 下载的代码或 intranet 站点，隔离到的应用程序触发下载，以便代表一个应用程序下载的代码。  
  
## <a name="b"></a>B  
 **Bank 标识符代码 (BIC)**  
 用于标识金融机构中，由 SWIFT 代码。  
  
 **业务规则编辑器工具**  
 用于编写策略的图形用户界面工具。  
  
 **业务规则引擎 (BRE)**  
 根据事实评估规则并根据评估结果启动操作的运行时推理引擎。  
  
## <a name="c"></a>C  
 **条件规则**  
 一个规则，指定 SWIFT 消息类型的字段之间的关系。 SWIFT 标准版本指南中定义条件的规则。  
  
## <a name="d"></a>D  
 **反汇编程序**  
 A[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收管道组件的入站的管道处理的拆装阶段期间将调用。 Dissembler 通常执行到 XML 分析来自某些平面文件格式的入站的消息的作业。  
  
## <a name="e"></a>E  
 **错误代码**  
 一个代码，包含字母后跟两个数字，指示特定与给定的消息类型的规则的冲突。  
  
 **可扩展标记语言 (XML)**  
 由万维网联合会 (W3C) 规范，它使设计器来创建超出标准 HTML 功能的自定义的标记。 尽管 HTML 使用仅预定义的标记来描述页中的元素，XML 将使页面的开发人员定义的标记。 对于几乎任何数据项，如产品或金额，由于标记可以用于特定应用程序。 这使网页能够充当数据库记录。  
  
 **可扩展样式表语言 (XSL)**  
 样式表的格式为可扩展标记语言 (XML) 文档的。 XSL 用于定义中相同的方式使用该级联样式表 (CSS) 来定义显示的超文本标记语言 (HTML) 的 XML 显示。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用 XSL 作为两个规范之间的转换语言。  
  
## <a name="f"></a>F  
 **FIN**  
 为其 SWIFT 具有定义架构和验证标准 SWIFT 标准版本指南 2003年中的财务消息。  
  
## <a name="g"></a>G  
 **全局程序集缓存 (GAC)**  
 计算机范围内的代码缓存，用于存储专为由计算机上的许多应用程序共享而安装的程序集。 在全局程序集缓存中部署的应用程序必须具有强名称。  
  
## <a name="h"></a>H  
 **超文本传输协议安全 (HTTPS)**  
 超文本传输协议 (HTTP) 使用安全套接字层 (SSL) 加密协议。  
  
## <a name="i"></a>I  
 **交换**  
 完整的消息由较小的消息部分或块构成。 例如，SWIFT 交换中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]定义 SWIFT 标头一部分的串联 （SWIFT 阻塞 1，2，3） 后, 跟 SWIFT 正文部分 （SWIFT 阻止 4），请跟 SWIFT 尾部部分 （SWIFT 阻止 5）。  
  
## <a name="m"></a>M  
 **映射**  
 定义一种规范的记录和字段与另一种规范的记录和字段之间对应关系的 XML 文件。 地图包含可扩展样式表语言 (XSL) 样式表[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于执行在映射中所述的转换。 在 BizTalk 映射程序中创建映射。  
  
 **消息类型**  
 SWIFT 标准的发行版指南，例如"接收针对付款"中定义的消息格式之一。 由"MT"跟三个数字代码通常表示消息类型。  
  
## <a name="p"></a>P  
 **付款事务标识符 (PTI)**  
 由启动附加到来自银行，例如付款启动消息和信用额度通知的支付相关银行消息的客户提供一个唯一的事务标识符。  
  
 **策略**  
 版本化的业务规则集合。  
  
 **PTI**  
 付款事务标识符。  
  
## <a name="r"></a>R  
 **规则**  
 条件和操作对。  
  
 **规则集**  
 相似规则的逻辑分组。 可将规则集看作规则引擎的一种分组/分区机制。  
  
## <a name="s"></a>S  
 **架构**  
 XML 文件的结构的定义。 架构包含属性信息，因为它涉及到的记录和结构中的字段。  
  
 **全球 Interbank 财务电信 (SWIFT) 的互联网协会**  
 全球 Interbank 财务电信的互联网协会。 提供到银行、 经纪人、 投资管理器和市场中付款、 财政部、 证券和贸易的基础结构的消息传递服务的组织。 SWIFT 创建共享的全球数据处理和通信链接和国际金融交易的常见语言。  
  
 **规范**  
 特定于 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 的 XML 架构。 规范创建 BizTalk 编辑器中，可以基于行业标准 （如 SWIFT，EDIFACT、 X12 和 XML) 或平面文件 （带分隔符、 位置，或带分隔符和位置）。 BizTalk 映射程序使用规范，作为源规范和目标规范，打开创建地图。  
  
 **强名称**  
 包含的程序集的标识的名称-其简单文本名称、 版本号和区域性信息 （如果有的话） — 通过一个公钥和针对该程序集生成的数字签名的强化。 由于程序集清单包含构成程序集实现的所有文件的文件哈希值，它只需通过只需使用一个文件中包含程序集清单的程序集生成数字签名。 具有相同的强名称的程序集应相同。  
  
 **直连处理方式 (STP)**  
 自动处理多个步骤，需任何手动干预通过消息中。 通常用于处理路径，从结果中的事务的金融机构; 内部系统发布到在金融机构 SWIFT 从消息接收的或从接收外部指令或在与通过 SWIFT 或其他财务的基础结构; 结果的消息传输的金融机构的操作或者，从内部金融机构系统传输到一个或多个相关通过 SWIFT 或其他财务基础结构的消息。  
  
 **SWIFT 标准版本指南 (SRG)**  
 SWIFT 发布了更新和建议标准进行的一组 FIN 消息。 这是多卷组定义的布局和字段的每个消息类型、 有效的值和每个字段、 网络规则应用到每条消息，任何使用规则或常见的做法的格式的文档。 此 CD 发布可从 SWIFT 订阅服务。  
  
 **系统发起消息预告片 (SYS)**  
 尾部追加 SWIFT 网络与消息传递到金融机构，，该值指示 FIN 服务生成消息。 示例包括广播，对用户请求和报告的响应。  
  
## <a name="u"></a>U  
 **唯一汇款标识符 (URI)**  
 生成参与者 RosettaNet 付款里程碑程序与业务的交换同步银行的交换中的标识符。  
  
## <a name="x"></a>X  
  
 **XML 数据缩减 (XDR)**  
 一种早期语言，用于创建架构，该标识的结构和约束将特定的 XML 文档的架构。 XML 数据缩减指中提供的 XML 数据架构规范子集[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]XML 分析器 (MSXML) 3.0 版及更高版本。 它会执行相同的基本任务 DTD，但更加强大和灵活。 与 DTD，需要其自己的语言和语法，不同 XDR 其语言使用 XML 语法。 与不同的是 XSD，只是最近已建议作为一种标准，XDR 已实现，并可通过[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]大大超出作为由 W3C XML 架构工作组建议标准存在的 XSD。  
  
 **XML 架构定义 (XSD)**  
 一种语言，在定义架构中使用建议的 W3C XML 架构使用组。 架构可用于强制执行结构和/或约束的可有效地在其他 XML 文档中的数据类型。 XML 架构定义是指创作 XML 架构中使用的完全指定的和当前建议使用标准。 由于最近才终止 XSD 规范，支持仅未进行的版本提供的[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]XML Core Services (MSXML) 4.0。 它会执行相同的基本任务 DTD，但更加强大和灵活。 与 DTD，需要其自己的语言和语法，不同 XSD 其语言使用 XML 语法。 XSD 密切类似于和扩展 XDR 的功能。 现在，W3C 建议使用 XSD 作为一种标准，用于定义 XML 架构。