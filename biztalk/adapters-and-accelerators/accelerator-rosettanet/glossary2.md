---
title: "RosettaNet 快捷键 BizTalk Server 中的术语表 |Microsoft 文档"
description: "常见术语和定义知道并了解用于 BizTalk Accelerator RosettaNet"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d98a5ed4-adc5-4ca9-b9d9-38ab02a0bda6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd89d75b0d36359fcf59f7edae0bb950a7196ca7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="glossary"></a>词汇表
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用以下术语表术语和定义。  

  
## <a name="a"></a>仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，  
 **应用程序适配器**  
 实现的应用程序的应用程序适配器接口。 接受传入的操作消息 （请求或响应） 上的通知机制调用的应用程序适配器。 它实现两种方法：`BeginNotify`和`EndNotify`。 公共响应方时，将调用`BeginNotify`方法，而现成可用的专用响应方时，将调用`EndNotify`方法。 调用`Notify`方法意味着消息已成功保存到 MessagesToLOB 表。  
  
 **操作 URL**  
 到本组织传输操作消息在异步过程中，例如，http://FabrikamServer/BTARNApp/RNIFReceive.aspx 合作伙伴 URL。  
  
## <a name="b"></a>B  
 **BizTalk Accelerator for RosettaNet**  
 给 BizTalk Server，可帮助组织构建 RosettaNet 实现框架 (RNIF) 外接程序产品-合规的解决方案。  
  
 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理**  
 一个 Microsoft [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 应用程序，使用它可以描述流程模板和管理合作伙伴协议。  
  
 **BizTalk 编辑器**  
 一种工具，这可以用于创建、 编辑和管理规范。 使用 BizTalk 编辑器可以创建基于规范模板、 现有架构、 文档实例，某些类型的规范或空白的规范。  
  
 **BizTalk 业务流程设计器**  
 可用于创建绘图可描述长时间运行的设计工具松散耦合，可执行业务流程。 绘制 XLANG 计划是用于运行自动化的业务流程 XLANG 计划在编译的。  
  
 **BizTalk Server**  
 用于业务流程自动化和应用程序集成在和企业之间的 Microsoft 产品。 BizTalk Server 提供了一个功能强大的基于 Web 的开发和执行环境集成松散耦合，长时间运行业务流程，在和企业之间。  
  
 BizTalk Server 功能包括新的和现有 XLANG 计划; 组成现有应用程序; 之间的集成文档规范和规范转换; 的定义监视和运行时活动日志记录。  
  
 服务器发送和接收文档分布在 Internet 提供标准网关，并提供一系列可帮助确保数据完整性、 传递、 安全性和对 BizTalk 框架和其他密钥的文档格式的支持的服务。  
  
 **BtarnClean**  
 关闭计算机的干净 BTARN 项目到实用工具。  
  
 **业务操作**  
 RosettaNet 消息包含业务如采购订单请求或报价请求的内容。 业务的信号，以及这些操作构成了所需的元素以完成指定的特定合作伙伴接口过程 (PIP) 的业务活动。  
  
 **业务活动监视 (BAM)**  
 一个 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 功能，它向业务用户提供各种业务流程的实时视图。 这使他们能够做出重要的业务决策。  
  
 **业务信号**  
 RosettaNet 消息，例如 ReceiptAcknowledgement 或异常，两个 RosettaNet 网络应用程序进行通信的 PIP 实例执行过程中的某些事件之间交换。 业务操作，以及这些信号构成了所需的元素以完成指定特定 PIP 的业务活动。  
 
  
## <a name="c"></a>C  
 **CertWizard**  
 用于签名或加密证书 (.p12).pfx 或.cer (.der) 文件中导入与 BTARN 一起使用的私有或公用存储区的实用工具。 .Pfx 文件，也称为个人信息交换-PKCS #12，通常受密码，因为它包含用于解密或签名的私钥。 .Cer 文件 （证书文件） 包含用于加密和验证签名的公钥。  
  
 **筛选数据交换 (CIDX) Chem eStandards**  
 专门为购买、 销售，和传递化学品开发统一标准的数据交换。 这些标准基于对于电子数据交换的公认标准-XML。 BTARN 支持 CIDX Chem eStandards。  
  
 **群集**  
 高级业务流程，例如订单管理、 库存管理或服务和支持组。 由 RosettaNet 确定分类表示供应链行业的核心业务流程。  
  
## <a name="d"></a>D  
 **数据通用编号系统 (D-U-N-S) 编号**  
 按顺序生成的包含 9 位数字，用于唯一标识业务位置，以及的作用域具有全局性。  
  
 **传递标头**  
 RosettaNet 消息的一部分。 传递标头是一个标识邮件发件人、 收件人和消息实例信息的 XML 文档。  
  
 **目标组织**  
 用作文档的目标已指定在消息传递端口中的组织。  
  
 **数字算法**  
 将作为输入一条消息，并生成哈希或它一组固定长度以某种非常复杂的方式取决于消息内容的位的摘要算法。 设计标准包括这使得任何人伪造摘要或更改一条消息，而不更改其摘要式极其困难。 应用程序通常使用摘要算法是在消息身份验证和数字签名方案。 广泛使用的算法包括 MD5 和 SHA1。 BTARN 支持 MD5 和 SHA1 对于传入消息，并仅 SHA1 为传出消息。  
  
 **文档定义**  
 表示特定文档的属性集。 文档定义属性包括指向文档规范的并且只能包含全局跟踪字段和选择条件。  
  
 **文档实例**  
 发送到 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 的实际数据的表示形式。 文档实例与不同，文档规范的规范定义的数据结构的文档实例时的表示形式包含在结构的特定数据。  
  
 **文档类型定义 (DTD)**  
 指定的元素和属性的标准定义可能会出现在其他元素和属性，用于指定其排序、 频率和内容的任何约束。  
  
 **double 操作事务**   
 其中发起方发送一个请求的操作，一个进程收到信号，其后是从响应方的响应操作。 发起方将通过将信号发送到响应操作完成过程。  
  
## <a name="e"></a>E  
 **可扩展标记语言 (XML)**  
 由万维网联合会 (W3C) 规范，它使设计器来创建超出标准 HTML 功能的自定义的标记。 尽管 HTML 使用仅预定义的标记来描述页中的元素，XML 将使页面的开发人员定义的标记。 对于几乎任何数据项，如产品或金额，由于标记可以用于特定应用程序。 这使网页能够充当数据库记录。  
  
 **可扩展样式表语言 (XSL)**  
 样式表的格式为 XML 文档的。 XSL 用于一样级联样式表 (CSS) 用于定义的 HTML 显示定义的 XML 的显示。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用 XSL 作为两个规范之间的转换语言。  
  
## <a name="g"></a>G  
 **全局业务标识 (GBI)**  
 若要标识贸易方唯一标识符。 RosettaNet GBI 中用作九位数 Dun 和 Bradstreet 编码系统 (DUNS)。  
  
## <a name="h"></a>H  
 **本组织**   
 别名以识别您的组织。  
  
## <a name="i"></a>I  
 **发起程序**  
 启动到贸易合作伙伴过程的事务或通知过程中组织的角色。  
  
## <a name="l"></a>L  
 **(LOB) 业务线应用程序**  
 应用程序作为后端系统 BTARN 与之通信。  
  
 **环回实用程序**  
 用于开发人员能够自动生成实例是镜像副本主页合作伙伴协议的环回协议的实用程序。 这使你能够在单个计算机上执行本组织到合作伙伴以及合作伙伴到本组织的消息交换。  
  
## <a name="m"></a>M  
 **映射**  
 定义一种规范的记录和字段与另一种规范的记录和字段之间对应关系的 XML 文件。 映射中包含一个 XSL 样式表，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 使用该样式表来执行映射中描述的转换。 在 BizTalk 映射程序中创建映射。
  
 **我的组织**  
 在贸易合作伙伴协议表示你的组织。   
  
 **多用途 Internet 邮件扩展 (MIME)**  
 允许你的 Internet 电子邮件协议的扩展使用协议交换不同类型的 Internet 上的数据文件： 音频、 视频、 图像和应用程序。  
  
## <a name="n"></a>否  
 **不可否认性**  
 若要确保消息的发件人无法更高版本无法识别发件人发送消息和接收方无法拒绝无收到了消息，一种方式。 传入消息的不可否认性要求，则接收方，保存该消息和消息应具有数字签名使用发件人的签名证书以确保其可靠性。 不可否认性传出消息，则需要保存确认消息 （从第一条消息的接收方的传入消息），消息应具有与原始的摘要的数字签名消息和使用的签名接收方的证书。   
  
 **通知**  
 其中发起方通知与单个消息响应方 RNIF 1.1 进程类型。 响应方应使用业务信号作为确认答复。  
  
 **失败 (PIP 0A1) 的通知**  
 特殊 PIP，该值指示进程意外的失败。 发起方还是对响应方可以启动故障通知。 它将引用为现有的或以前交换过程。 收到 0A1，接收方可以确保，引用的过程被视为不有效。  
  
## <a name="o"></a>O  
 **组织**  
 贸易合作伙伴或业务单位，可以执行业务事务。  
  
## <a name="p"></a>P  
 **打包**  
 将转换其 XML 表示形式中，反之亦然 RosettaNet 消息的过程。  
  
 **合作伙伴接口过程 (PIP)**  
 PIP 描述一组的业务文档和协议详细信息，包括文档内容的详细信息。  
  
 **PIP 规范文档**  
 包含有关要使用当你在 BTARN 管理控制台中创建过程配置的设置指南的文档。 你从 RosettaNet 组织，RosettaNet.org 下载 PIP 规范文档和 PIP。包含有关要使用当你在 BTARN 管理控制台中创建过程配置的设置指南的文档。 你从 RosettaNet 组织，RosettaNet.org 下载 PIP 规范文档和 PIP。  
  
 **前导码标头**  
 标识的名称和版本的业务消息与之符合标准的 XML 节点。 它与其他标头，以形成完整的 RosettaNet 消息一起打包。 也称为前导码。  
  
 **专用流程**   
 属于组织内部的业务流程。 BTARN 实现私有进程作为长时间运行 BizTalk 业务流程。  
  
 **进程配置设置 (PC) 配置文件**  
 确定合作伙伴协议的运行方式。 使用电脑配置文件输入配置详细信息的 RosettaNet 合作伙伴接口过程 (PIP)。 RosettaNet PIP 规范映射到的电脑配置文件中的一个元素中指定的所有配置值。 一个电脑配置文件可用于多个合作伙伴协议。  
  
 **port**  
 命名的位置使用的特定实现。 在 BizTalk 业务流程设计器中，端口的定义方法的位置向其发送消息或从中接收消息，以及用于实现通信操作的技术。 该位置由端口名称唯一标识。  
  
 **公共过程**   
 包含与贸易合作伙伴作为公共进程的集成的业务流程。 BTARN 实现公共进程作为长时间运行 BizTalk 业务流程。 在发起方和响应方各会运行一个公用业务流程。 BTARN 安装程序将提供发起方和响应方公共进程业务流程 RNIF 1.1 和 RNIF 2.01 的版本。 这些公用业务流程实现了所有的 RNIF 流程。 公用流程使 RNIF 对于其他组件来说变得相对简单了。 除了强制实施 RNIF 符合消息流时，公共过程还确定默认跟踪设置，并提供在运行时的处理状态信息。  
  
## <a name="r"></a>R  
 **响应方**  
 贸易合作伙伴的请求响应的事务或通知过程中组织的角色。  
  
 **RosettaNet 实现框架 (RNIF)**  
 一种标准框架，为想要创建可互操作的软件应用程序组件的运行 Pip 这些公司提供实施准则。  
  
 **RosettaNet 消息**  
 前导码标头、 传递标头 （如果 RNIF 2.0)、 服务标头和服务内容的逻辑分组。  
  
 **RosettaNet 对象**  
 封装对 RosettaNet 实现 Framework 1.1 版中的交付 RosettaNet 消息。  
  
## <a name="s"></a>S  
 **架构**  
 XML 文件的结构的定义。 架构包含属性信息，因为它涉及到的记录和结构中的字段。  
  
 **服务的内容**  
 RosettaNet 消息主要组件。 它是表示业务内容由特定 PIP 指定的 XML 节点。  
  
 **服务标头**  
 XML 文档可标识与业务消息，包括 PIP、 业务活动和操作，发送和接收服务、 贸易合作伙伴和角色关联的部分。  
  
 **信号 URL**  
 本组织将信号消息传输的 URL。 例如，http://FabrikamServer/BTARNApp/RNIFReceive.aspx。  
  
 **单个操作通知**  
 发起方将单个操作消息和响应方发送的进程使用消息进行回复。  
  
 **规范**  
 特定于 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 的 XML 架构。 创建 BizTalk 编辑器中的规范，并可以基于行业标准，如 EDIFACT、 X12 和 XML，或在平面文件，例如分隔，位置，或分隔和位置。 BizTalk 映射程序使用规范，作为源规范和目标规范，打开创建地图。  
  
 **同步 URL**  
 本组织用于建立与伙伴，例如，http://FabikamServer/BTARNApp/RNIFReceive.aspx 同步事务的 URL。  
  
 **同步事务**  
 过程，其中发起方返回响应 （双操作） 或信号 （单次操作） 的相同的 HTTP 状态而无需关闭连接。  
  
## <a name="t"></a>T  
 **贸易合作伙伴**  
 外部组织你的组织与其交换电子数据。  
  
 **贸易合作伙伴协议**  
 你的组织和贸易合作伙伴之间的协议。 贸易合作伙伴协议引用过程配置设置配置文件、 组织、 合作伙伴，并包含协议特定的配置设置。  
  
 **事务**  
 其中发起方发送 RosettaNet 消息时，一个 RNIF 1.1 过程收到信号，接收 RosettaNet 消息为答案，然后发送确认的信号。  
  
## <a name="v"></a>V  
 **验证适配器**  
 实现的应用程序验证适配器接口。 在接收操作消息 （请求或响应） 时，公共响应方调用验证适配器。 它可以包括任何组的业务可能需要再接受传入消息的验证规则。 BTARN 本机执行验证，接收管道中和在公共业务流程中。  
  
## <a name="x"></a>X  
 **XLANG 计划**  
 一种特定的 XML 语言，描述业务流程和后端的集成。 XLANG 语言来表述 BTARN 中的特定业务流程。 文件名称扩展.skx 保存 XLANG 计划。  
  
