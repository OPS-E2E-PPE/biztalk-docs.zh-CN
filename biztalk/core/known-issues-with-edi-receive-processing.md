---
title: "已知问题的 EDI 接收处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbb3fd6a-381b-479e-a9f2-7b6371fac39e
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ab2769ab4a6eacf885dbf675a6bd3fda371007
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-receive-processing"></a>EDI 接收处理的已知问题
本主题介绍在 EDI 接收管道中进行处理时的已知问题。  
  
## <a name="receive-side-processing-of-trailing-separators-fails"></a>尾部分隔符的接收端处理失败  
 **症状**  
  
 带有尾部分隔符的事务集出错，对于 X12 编码的消息，产生的错误代码为 AK403= 6，对于 EDIFACT 编码的消息，产生的错误代码为 UCM3=4/UCD1=45。  
  
 **可能的原因**  
  
 未启用对尾部分隔符的处理。  
  
 **解决方法**  
  
 打开发送消息的参与方的“EDI 属性”。 在“EDI 属性”对话框（对于 X12 或 EDIFACT）的“验证和确认生成”页中，选中“允许尾部分隔符”。 单击此复选框后，可以通过单击“为尾部分隔符创建空 XML 标记”来指定在中间 XML 中为尾部分隔符创建空的 XML 标记。  
  
## <a name="contrl-ack-is-enabled-but-not-generated"></a>CONTRL 确认已启用，但未生成  
 **症状**  
  
 在发送方的“验证和确认生成”中已选中“生成功能确认”复选框，但 EDI 接收管道尚未生成 CONTRL 确认。  
  
 **可能的原因**  
  
 CONTRL 消息包含几个必须从交换复制的必需数据元素。 如果交换中的数据元素丢失或在语法上无效，则接收管道无法生成在语法上有效的 CONTRL 消息。  
  
 **解决方法**  
  
 通过 CONTRL 确认以外的其他某种方式来报告错误情况。  
  
## <a name="there-was-a-failure-executing-the-receive-pipeline-error-message"></a>"出现故障执行接收管道..." 错误消息  
 **症状**  
  
 尝试运行 AS2 接收管道时导致出现 80040154 错误。  
  
 **可能的原因**  
  
 在 64 位主机实例上不支持使用管道。  
  
 **解决方法**  
  
 将相应管道与 32 位主机关联。  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a>如果已启用基于端口的身份验证而 BizTalk Server 却无权访问授权和安全信息，X12 编码的消息将挂起  
 **症状**  
  
 如果某消息是通过已启用身份验证的接收端口接收的，而又无法确定发送该消息的参与方，BizTalk Server 将挂起该消息。  
  
 **可能的原因**  
  
 如果已为某接收端口启用了身份验证（清除了该接收端口的“无验证”属性），则 BizTalk Server 需要获得“ISA1-2 (授权限定符和信息)”和“ISA3-4 (安全限定符和信息)”属性的设置才能处理相应的交换。 这些属性是在作为交换发送方的参与方的“X12 交换处理属性”页为相应参与方设置的。 如果 BizTalk Server 不能确定这些属性的值，它将挂起相应消息。  
  
 这一问题分为两种情况： 第一种情况，如果 BizTalk Server 无法确定发送相应消息的参与方，它将使用 EDI 全局属性，并且将无权访问授权和安全设置。 因此，它将挂起该消息。 第二种情况，如果 BizTalk Server 已确定了相应的参与方，但是该参与方的 ISA1-2 和 ISA3-4 属性并没有进行配置，则 BizTalk Server 也无权访问授权和安全信息，因而将挂起相应消息。  
  
 **解决方法**  
  
 确保可以识别发送消息的参与方，且已在参与方协议中定义 ISA1-2 和 ISA3-4 属性。  
  
## <a name="incorrect-se01-in-a-split-hipaa-subdocument"></a>拆分 HIPAA 子文档中的 SE01 不正确  
 **症状**  
  
 事务集尾部（SE01 字段）提供数据段的计数，包括 X12/HIPAA 文档的标头和尾部段。 但对于拆分的 HIPAA 子文档，EDI 接收管道与原始文档应用相同的 SE01 值，而不是重新计算该值。  
  
 **可能的原因**  
  
 EDI 接收管道将 SE01 的值从原始 HIPAA 文档复制到拆分的子文档。  
  
## <a name="error-message-for-duplicate-unb5-or-unh1-is-not-descriptive"></a>有关 UNB5 或 UNH1 重复的错误消息描述不清  
 如果 BizTalk Server 收到有关 UNB5（交换控制编号）或 UNH1（事务集参考编号）重复的消息，则它布的错误代码和说明将不能清楚地说明问题的性质。  
  
## <a name="biztalk-server-will-suspend-a-very-large-interchange-if-it-runs-out-of-memory"></a>如果内存不足，BizTalk Server 将挂起非常大的交换  
 BizTalk Server 在分析非常大的交换时可能会导致内存不足。 如果出现这种情况，它将发布出错信息并挂起相应交换。 在“组中心”页中，您将无法看到已挂起的特大交换的所有内容。 你将能够看到的消息，初始一部分但 BizTalk Server 是从它可以显示挂起交换的数据量的限制。  
  
## <a name="korean-characters-added-to-an-enumeration-in-a-kedifact-schema-must-be-in-unicode"></a>向 KEDIFACT 架构中的枚举添加的韩语字符必须为 UNICODE 格式  
 当 BizTalk Server 收到包含韩语字符的 KEDIFACT 编码的交换时，它将使用 UNB2 字段中的代码页/字符集值来处理相应交换。 但是，如果您通过向枚举添加具有 ID 数据类型的韩语字符来修改 KEDIFACT 架构，则必须按照架构顶部指定的那样以 UTF-16 UNICODE 格式添加相应值。  
  
## <a name="executing-an-edi-receive-pipeline-from-within-an-orchestration-is-not-supported"></a>不支持从业务流程内部执行 EDI 接收管道  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，您通常可以执行业务流程的表达式形状中的接收管道。 尚未针对 EDIReceive 管道或 AS2EdiReceive 管道测试此功能，因此不支持此功能。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>不得修改 BizTalk EDI 应用程序  
 不得修改或删除 BizTalk EDI 应用程序中的项目。 如果修改了此应用程序，则您将无法通过取消配置和重新配置 EDI 及 AS2 功能来恢复原始应用程序。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md)   
 [BizTalk Server 接收 EDI 消息的方式](../core/how-biztalk-server-receives-edi-messages.md)   
 [演练 (X12)： 接收 EDI 交换和发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)