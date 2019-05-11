---
title: 在 BizTalk Server 中的 RosettaNet 加速器的术语表 |Microsoft Docs
description: 通用术语和定义，以了解并了解如何使用 BizTalk Accelerator for RosettaNet
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d98a5ed4-adc5-4ca9-b9d9-38ab02a0bda6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c332c70137f391e2a0d026fa9fe56442ed3fa75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283693"
---
# <a name="glossary"></a>词汇表
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 使用以下术语表术语和定义。  

  
## <a name="a"></a>A  
 **application adapter**  
 实现应用程序适配器接口的应用程序。 接受传入操作消息 （请求或响应） 上的通知机制调用应用程序适配器。 它实现了两种方法：`BeginNotify`和`EndNotify`。 公用响应方调用`BeginNotify`方法，而开箱专用响应方调用`EndNotify`方法。 对调用`Notify`方法意味着该消息已成功保存到 MessagesToLOB 表。  
  
 **操作 URL**  
 到本组织操作消息传送在异步过程，例如，合作伙伴 URL http://FabrikamServer/BTARNApp/RNIFReceive.aspx。  
  
## <a name="b"></a>B  
 **BizTalk Accelerator for RosettaNet**  
 BizTalk Server 可帮助组织构建 RosettaNet 实现框架 (RNIF) 的一个附加产品-符合解决方案。  
  
 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 管理**  
 Microsoft [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] ，可以描述流程模板和管理合作伙伴协议的应用程序。  
  
 **BizTalk Editor**  
 这可以用于创建、 编辑和管理规范工具。 使用 BizTalk 编辑器可以创建基于规范模板、 现有架构、 文档实例的某些类型的规范或空白的规范。  
  
 **BizTalk 业务流程设计器**  
 可用于创建描述长时间运行的图形设计工具松散耦合的可执行业务流程。 绘制的 XLANG 计划用于运行的自动化的业务程序 XLANG 计划中编译。  
  
 **BizTalk Server**  
 获取该 Microsoft 产品的业务流程自动化和应用程序集成中和企业间。 BizTalk Server 提供了功能强大的基于 Web 的开发和执行环境，它集成松散耦合，长时间运行业务流程，在和企业间。  
  
 BizTalk Server 功能包括新的和现有 XLANG 调度; 的组合在现有应用程序; 之间的集成文档规范和规范转换的定义监视和运行时活动的日志记录。  
  
 服务器用于发送和接收文档在 Internet 上提供一个标准网关，并提供一系列可帮助确保数据完整性、 传送、 安全性和支持 BizTalk Framework 和其他密钥文档格式的服务。  
  
 **BtarnClean**  
 关闭计算机的干净 BTARN 项目到实用工具。  
  
 **业务操作**  
 包含业务内容，如采购订单请求或引号的请求的 RosettaNet 消息。 业务信号，以及这些操作构成了所需的元素以完成业务活动指定的特定合作伙伴接口流程 (PIP)。  
  
 **业务活动监视 (BAM)**  
 一个[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为业务用户提供其异构业务流程的实时视图的功能。 这使他们能够做出重要业务决策。  
  
 **业务信号**  
 RosettaNet 消息，如 ReceiptAcknowledgement 或两个 RosettaNet 网络应用程序进行通信的 PIP 实例执行过程中的某些事件之间交换的异常。 业务操作，以及这些信号构成了所需的元素以完成指定特定 PIP 的业务活动。  
 
  
## <a name="c"></a>C  
 **CertWizard**  
 用于签名或加密证书 (.p12).pfx 或.cer (.der) 文件中导入用于 BTARN 专用或公用存储区的实用工具。 .Pfx 文件，也称为个人信息交换-PKCS #12，通常受密码，它包含用于解密或签名的私钥。 .Cer 文件 （证书文件） 包含用于加密和验证签名的公钥。  
  
 **化工数据交换 (CIDX) Chem eStandards**  
 专门为购买、 销售和交付的化学物开发统一的数据交换标准。 这些标准基于电子数据交换的公认标准 — XML。 BTARN 支持 CIDX Chem eStandards。  
  
 **cluster**  
 高级业务流程，例如订单管理、 库存管理或服务和支持的组。 所处理的 RosettaNet 群集表示供应链行业的核心业务流程。  
  
## <a name="d"></a>D  
 **数据统一编码系统 (D-U-N-S) 数量**  
 按顺序生成的九位数字，用于唯一标识业务位置，并为全局作用域中。  
  
 **传递头**  
 RosettaNet 消息的一部分。 传递头是一个标识邮件发件人、 收件人和消息实例信息的 XML 文档。  
  
 **目标组织**  
 已被指定为消息传送端口中为文档的目标组织。  
  
 **数字算法**  
 将消息作为输入，并生成哈希或它的一些非常复杂的方式取决于消息内容的位数一固定长度组的摘要算法。 设计条件包括非常难以伪造摘要或更改一条消息，而无需更改其摘要的任何人。 通常情况下使用摘要算法的应用程序是在消息身份验证和数字签名方案。 广泛使用的算法包括 MD5 和 SHA1。 BTARN 支持 MD5 和 SHA1 为传入消息，并仅 SHA1 为传出消息。  
  
 **文档定义**  
 表示特定文档的属性集。 文档定义属性包含一个指向文档规范和可以包括全局跟踪字段和选择条件。  
  
 **文档实例**  
 发送到的实际数据的表示形式[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 文档实例与从文档规范的规范定义的数据结构，而文档实例是一种结构中包含的特定数据的表示形式。  
  
 **文档类型定义 (DTD)**  
 指定的元素和属性的标准定义可能会出现在其他元素和属性并指定其排序、 频率和内容的任何约束。  
  
 **双操作事务**   
 其中发起方发送的请求操作，一个进程收到信号，同时从响应方跟响应操作。 发起方通过将信号发送到响应操作完成过程。  
  
## <a name="e"></a>E  
 **可扩展标记语言 (XML)**  
 由 World Wide Web 联合会 (W3C) 开发的规范，使设计人员可以创建超出标准 HTML 功能的自定义的标记。 HTML 使用预定义的标签来描述页面中的元素，而利用 XML 标记来定义由页面开发人员。 几乎任何数据项，例如产品或金额，由于标记可以用于特定应用程序。 这使网页能够作为数据库记录。  
  
 **可扩展样式表语言 (XSL)**  
 样式表的格式为 XML 文档的。 XSL 用于定义 XML 的显示，就像级联样式表 (CSS) 用于定义显示的 HTML。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 使用 XSL 作为两个规范之间的转换语言。  
  
## <a name="g"></a>G  
 **全球业务标识 (GBI)**  
 若要标识贸易参与方的唯一标识符。 RosettaNet 使用 9 位数字 Dun 和 Bradstreet 编码系统 (DUNS) 作为 GBI。  
  
## <a name="h"></a>H  
 **本组织**   
 若要确定你的组织别名。  
  
## <a name="i"></a>I  
 **initiator**  
 启动一个过程，向贸易合作伙伴的通知或事务过程中组织的角色。  
  
## <a name="l"></a>L  
 **业务线 (LOB) 应用程序的行**  
 应用程序与 BTARN 作为后端系统进行通信。  
  
 **Loopback 实用工具**  
 用于开发人员能够自动生成环回协议，它是本组织到合作伙伴协议的镜像副本的实用程序。 这允许您在单台计算机上执行本组织合作伙伴和合作伙伴主页消息交换。  
  
## <a name="m"></a>M  
 **map**  
 XML 文件的另一个规范中定义的记录和一个规范中的字段和记录和字段之间的对应关系。 映射中包含一个 XSL 样式表[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于执行在映射中所描述的转换。 在 BizTalk 映射器创建映射。
  
 **我的组织**  
 贸易合作伙伴协议中表示你的组织。   
  
 **多用途 Internet 邮件扩展 (MIME)**  
 可让你的 Internet 电子邮件协议的扩展使用的协议来交换不同类型的数据文件在 Internet 上： 音频、 视频、 图像和应用程序的程序。  
  
## <a name="n"></a>N  
 **non-repudiation**  
 若要确保消息的发件人不能更高版本无法识别发件人发送消息和接收方收到消息，不能拒绝一种方法。 传入消息的不可否认性要求消息由接收方，保存，并且该消息应执行数字签名使用发件人的签名证书以确保它的真实性。 传出的消息的不可否认，则需要保存确认消息 （从第一条消息的接收方的传入消息），并且该消息应包含原始摘要的数字签名消息使用签名收件人的证书。   
  
 **notification**  
 发起方通知响应方使用一条消息的其中一个 RNIF 1.1 进程类型。 响应方应使用业务信号，表示确认答复。  
  
 **失败 (的 PIP 0A1) 的通知**  
 特殊的 PIP，该值指示进程意外的失败。 发起方或响应方可以启动失败通知。 它引用一个现有的或以前交换的过程。 收到的 0A1，接收方可以确保，所引用的进程被视为不有效。  
  
## <a name="o"></a>O  
 **organization**  
 贸易合作伙伴或可执行业务交易某个业务部门。  
  
## <a name="p"></a>P  
 **packaging**  
 转换其 XML 表示形式中，反之亦然 RosettaNet 消息的过程。  
  
 **合作伙伴接口流程 (PIP)**  
 PIP 描述一组业务文档和协议详细信息，包括文档内容的详细信息。  
  
 **PIP 规范文档**  
 包含有关要在 BTARN 管理控制台创建流程配置时使用的设置指南的文档。 从 RosettaNet 组织，从 RosettaNet.org 下载 PIP 规范文档和 PIP。包含有关要在 BTARN 管理控制台创建流程配置时使用的设置指南的文档。 从 RosettaNet 组织，从 RosettaNet.org 下载 PIP 规范文档和 PIP。  
  
 **前导头**  
 标识的名称和版本的业务消息与符合标准的 XML 节点。 它与其他标头，以形成完整的 RosettaNet 消息一起打包。 也名为前导码。  
  
 **专用流程**   
 将组织内部的业务流程。 BTARN 专用流程作为长期 BizTalk 业务流程来实现。  
  
 **进程配置设置 (PC) 配置文件**  
 确定合作伙伴协议的运行方式。 PC 配置文件用于输入的配置详细信息的 RosettaNet 合作伙伴接口流程 (PIP)。 RosettaNet PIP 规范映射到 PC 配置文件中的一个元素中指定的所有配置值。 一个 PC 配置文件可用于多个合作伙伴协议。  
  
 **port**  
 使用的特定实现的命名的位置。 在 BizTalk 业务流程设计器中的位置向其发送消息或从其接收消息，以及用于实现通信操作的技术通过定义端口。 由该端口的名称唯一标识该位置。  
  
 **公用流程**   
 涉及与贸易合作伙伴作为公用过程集成的业务流程。 BTARN 公用流程作为长期 BizTalk 业务流程来实现。 一个公用业务流程在发起方和响应方各上运行。 BTARN 安装程序提供了在发起方和响应方公用流程，用于 RNIF 1.1 和 RNIF 2.01 的版本。 这些公用业务流程实现所有的 RNIF 流程。 公用流程使 RNIF 从其他组件的复杂性。 除了强制实施符合 RNIF 消息流，则公用流程还确定默认跟踪设置，并提供在运行时进程状态信息。  
  
## <a name="r"></a>R  
 **responder**  
 对贸易合作伙伴请求做出响应的通知或事务过程中组织的角色。  
  
 **RosettaNet Implementation Framework (RNIF)**  
 一种标准框架，为想要创建可互操作的软件应用程序组件运行 Pip 的这些公司提供实现指导原则。  
  
 **RosettaNet 消息**  
 前导头、 传递头 （对于 RNIF 2.0)、 服务头和服务内容的逻辑分组。  
  
 **RosettaNet 对象**  
 RosettaNet 消息封装为 RosettaNet 实现框架版本 1.1 中的传递。  
  
## <a name="s"></a>S  
 **schema**  
 XML 文件的结构的定义。 架构包含属性的信息，因为它涉及到的记录和字段结构中。  
  
 **服务内容**  
 RosettaNet 消息的主要组件。 它是一个 XML 节点，表示指定的特定 PIP 的业务内容。  
  
 **service header**  
 标识与业务消息，其中包括 PIP、 业务活动和操作，发送和接收服务、 贸易合作伙伴和角色关联的部分 XML 文档。  
  
 **信号 URL**  
 本组织将信号消息传输到的 URL。 例如， http://FabrikamServer/BTARNApp/RNIFReceive.aspx。  
  
 **单个操作通知**  
 使用一条消息回复发起方将单一操作消息和响应方发送的进程。  
  
 **specification**  
 一个[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]-特定 XML 架构。 创建在 BizTalk 编辑器中的规范，并可以基于行业标准，例如 EDIFACT，x12 和 XML，或在平面文件，例如带分隔符、 位置，或分隔和位置。 BizTalk 映射器使用规范作为源规范和目标规范，打开创建映射。  
  
 **sync URL**  
 本组织用于建立与合作伙伴，例如，同步事务的 URL http://FabikamServer/BTARNApp/RNIFReceive.aspx。  
  
 **同步事务**  
 一个过程，其中发起方返回响应 （双操作） 或信号 （单操作） 的相同的 HTTP 状态而不关闭连接。  
  
## <a name="t"></a>T  
 **贸易合作伙伴**  
 外部组织与你的组织交换电子数据。  
  
 **贸易合作伙伴协议**  
 你的组织和贸易合作伙伴之间的协议。 贸易合作伙伴协议引用流程配置设置配置文件、 本组织、 合作伙伴，并包含协议特定的配置设置。  
  
 **transaction**  
 其中发起方发送 RosettaNet 消息，RNIF 1.1 流程收到信号，接收 RosettaNet 消息作为答案，并发送确认的信号。  
  
## <a name="v"></a>V  
 **验证适配器**  
 实现验证适配器接口的应用程序。 公用响应方接收操作消息 （请求或响应） 时调用验证适配器。 它可以包含任何组的企业可能需要再接受传入消息的验证规则。 在接收管道中，以及公用业务流程中，BTARN 本机执行验证。  
  
## <a name="x"></a>X  
 **XLANG 计划**  
 特定的 XML 语言来描述业务流程和后端集成。 BTARN 中的特定业务流程表示在 XLANG 语言。 XLANG 计划与文件名称扩展.skx 一起保存。  
  
