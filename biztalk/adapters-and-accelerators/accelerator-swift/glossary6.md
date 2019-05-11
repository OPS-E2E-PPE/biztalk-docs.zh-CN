---
title: SWIFT 加速器在 BizTalk Server 中的术语表 |Microsoft Docs
description: 通用术语和定义，以了解并了解如何使用 BizTalk Accelerator for SWIFT
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
ms.openlocfilehash: 05a6593d13e2b7afb249f7349b3c702ad70691d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377557"
---
# <a name="glossary"></a>词汇表
Microsoft BizTalk Accelerator for SWIFT 使用以下术语表术语和定义。  
  
## <a name="a"></a>A  
 **assembler**  
 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]出站管道处理的组装阶段调用的发送管道组件。 组装器通常执行序列化到某些平面文件格式从 XML 出站消息的作业。  
  
 **assembly**  
 Microsoft 的主要构建基块[!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]应用程序。 它是重复使用、 版本控制、 安全性和部署的基本单位。 它是显示给程序员来说，单个动态链接库 (DLL) 或可执行文件 (EXE) 文件的集合。  
  
 **程序集缓存**  
 计算机范围的代码缓存，用于通过并行存储的程序集。 有两个部分缓存。 在全局程序集缓存包含显式安装以在计算机上的许多应用程序之间共享的程序集。 下载缓存存储从 Internet 下载的代码或 intranet 站点，以便代表一个应用程序的代码下载触发下载的应用程序隔离或页不会影响其他应用程序。  
  
## <a name="b"></a>B  
 **银行标识代码 (BIC)**  
 用于标识的金融机构定义的 SWIFT 代码。  
  
 **业务规则编辑器工具**  
 用来编写策略的图形用户界面工具。  
  
 **业务规则引擎 (BRE)**  
 根据评估结果所基于的事实和启动操作评估规则运行时推理引擎。  
  
## <a name="c"></a>C  
 **条件规则**  
 一个规则，指定在 SWIFT 消息类型的字段之间的关系。 SWIFT 标准版本指南中定义条件规则。  
  
## <a name="d"></a>D  
 **disassembler**  
 一个[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收管道组件中处理入站的管道的拆装阶段调用。 拆装器通常会为 XML 分析来自某些平面文件格式的入站的消息的作业。  
  
## <a name="e"></a>E  
 **错误代码**  
 代码，包含的字母后跟两位数字，指示与特定的给定的消息类型的规则冲突。  
  
 **可扩展标记语言 (XML)**  
 由 World Wide Web 联合会 (W3C) 开发的规范，使设计人员可以创建超出标准 HTML 功能的自定义的标记。 HTML 使用预定义的标签来描述页中的元素，而利用 XML 标记来定义由页面开发人员。 几乎任何数据项，例如产品或金额，由于标记可以用于特定应用程序。 这使网页能够作为数据库记录。  
  
 **可扩展样式表语言 (XSL)**  
 可扩展标记语言 (XML) 文档的样式表格式。 XSL 用于定义 XML 的显示中相同的方式的级联样式表 (CSS) 用于定义显示的超文本标记语言 (HTML)。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 使用 XSL 作为两个规范之间的转换语言。  
  
## <a name="f"></a>F  
 **FIN**  
 财务为其 SWIFT 具有中定义的消息架构和验证标准指南 2003 版本的 SWIFT 标准。  
  
## <a name="g"></a>G  
 **全局程序集缓存 (GAC)**  
 计算机范围内的代码缓存，用于存储专为由计算机上的许多应用程序共享而安装的程序集。 应用程序部署到全局程序集缓存中必须具有强名称。  
  
## <a name="h"></a>H  
 **超文本传输协议安全 (HTTPS)**  
 超文本传输协议 (HTTP) 使用安全套接字层 (SSL) 加密协议。  
  
## <a name="i"></a>I  
 **interchange**  
 完整消息的较小的消息部分或块组成。 例如，SWIFT 交换中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]指的是 SWIFT 标头部分串联 （SWIFT 的块 1、 2、 3） 后, 跟 SWIFT 正文部分 （SWIFT 阻止 4），跟 SWIFT 尾部部分 （SWIFT 阻止 5）。  
  
## <a name="m"></a>M  
 **map**  
 XML 文件的另一个规范中定义的记录和一个规范中的字段和记录和字段之间的对应关系。 映射包含可扩展样式表语言 (XSL) 样式表[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于执行在映射中所描述的转换。 在 BizTalk 映射器创建映射。  
  
 **消息类型**  
 在 SWIFT 标准的版本指南，例如"接收针对付款"中定义的消息格式之一。 由"MT"后跟三位代码通常表示消息类型。  
  
## <a name="p"></a>P  
 **付款事务标识符 (PTI)**  
 附加到付款相关银行消息源自银行，例如付款启动消息和信用额度通知启动客户提供一个唯一事务标识符。  
  
 **policy**  
 版本控制的业务规则的集合。  
  
 **PTI**  
 付款事务标识符。  
  
## <a name="r"></a>R  
 **rule**  
 条件和操作对。  
  
 **规则集**  
 类似的规则的逻辑分组。 此可查看作为规则引擎的一种分组/分区机制。  
  
## <a name="s"></a>S  
 **schema**  
 XML 文件的结构的定义。 架构包含属性信息，因为它涉及到的记录和结构中的字段。  
  
 **全球范围内 Interbank 金融电信 (SWIFT) 协会**  
 全球范围内 Interbank 金融电信协会。 提供消息传递到银行、 经纪商、 投资经理和市场中付款、 财务、 证券和贸易的基础结构服务组织。 SWIFT 创建共享的全球数据处理和通信链接和国际金融交易的通用语言。  
  
 **specification**  
 一个[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]-特定 XML 架构。 规范创建在 BizTalk 编辑器中，并且可以根据行业标准 （如 SWIFT，EDIFACT，x12 和 XML) 或平面文件 （带分隔符、 位置，或分隔和位置）。 BizTalk 映射器使用规范作为源规范和目标规范，打开创建映射。  
  
 **强名称**  
 包含的程序集的标识的名称 — 其简单文本名称、 版本号和区域性信息 （如果提供） — 通过公钥和针对该程序集生成的数字签名加强。 由于程序集清单包含构成程序集实现的所有文件的文件哈希值，就足以通过只包含程序集清单的程序集的一个文件生成数字签名。 具有相同强名称程序集都将是完全相同。  
  
 **直接通过处理 (STP)**  
 通过多个步骤，需任何手动干预消息自动处理。 通常应用于处理路径从于金融机构; 的内部系统中生成的事务发布的金融机构在从 SWIFT 消息接收的或者，从外部指令或操作在通过 SWIFT 或其他财务的基础结构; 结果消息传输的金融机构的接收或者，从内部的金融机构系统传输到一个或多个相关的消息通过 SWIFT 或其他财务基础结构。  
  
 **SWIFT 标准发布指南 (SRG)**  
 SWIFT 发布提供了更新和建议标准了一系列 FIN 消息。 这是一组多卷定义的布局和每个消息类型、 有效的值和用于每个字段，应用到每条消息的网络规则和任何使用规则或常见做法格式字段的文档。 可通过订阅服务从 SWIFT 此 CD 发布。  
  
 **系统发起消息尾部 (SYS)**  
 尾部追加到消息的 SWIFT 网络传送，该值指示 FIN 服务生成消息的金融机构。 示例是广播，响应用户请求和报表。  
  
## <a name="u"></a>U  
 **唯一汇款标识符 (URI)**  
 与业务交换的交换生成的 RosettaNet 付款里程碑计划同步银行的参与者的标识符。  
  
## <a name="x"></a>X  
  
 **XML 数据缩减 (XDR)**  
 一种早期语言，用于创建一个标识的结构和特定的 XML 文档约束的架构。 XML 数据缩减是指的为了可在 Microsoft XML Parser (MSXML) 3.0 以及更高版本的 XML 数据架构规范的子集。 它会执行相同的基本任务与 DTD，但具有更多的功能和灵活性。 与 DTD，需要其自己的语言和语法，不同 XDR 语言使用 XML 语法。 与 XSD，最近才作为一种标准推荐，不同，XDR 已实现并可由 Microsoft 的 XSD 存在作为由 W3C XML 架构工作组建议标准之前很长。  
  
 **XML 架构定义 (XSD)**  
 一种 W3C XML 架构工作组建议在定义架构中使用的语言。 架构可用于强制执行结构和/或约束可以有效使用其他 XML 文档中的数据类型。 XML 架构定义是指在编写 XML 架构中使用的完全指定并且目前建议标准。 因为 XSD 规范是唯一的最近已完成，支持它只由发布 Microsoft XML Core Services (MSXML) 4.0 时可用。 它会执行相同的基本任务与 DTD，但具有更多的功能和灵活性。 与 DTD，需要其自己的语言和语法，不同 XSD 语言使用 XML 语法。 XSD 密切类似于并扩展了 XDR 的功能。 W3C 现在才建议使用 XSD 作为一种标准，用于定义 XML 架构。