---
title: 已知问题的 EDI 接收处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbb3fd6a-381b-479e-a9f2-7b6371fac39e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 734a093a554f01b8625d8cd1ba8f154153d33979
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330238"
---
# <a name="known-issues-with-edi-receive-processing"></a>接收处理的 EDI 的已知的问题
本主题介绍了处理的已知的问题在 EDI 接收管道。  
  
## <a name="receive-side-processing-of-trailing-separators-fails"></a>尾部分隔符的接收方处理失败  
 **症状**  
  
 设置带有尾部分隔符的事务失败，错误代码为 AK403 = 6 的 X12 编码的消息或错误代码 UCM3 = 4/UCD1 = 45 对于 EDIFACT 编码的消息。  
  
 **可能的原因**  
  
 未启用尾部分隔符的处理。  
  
 **解决方法**  
  
 打开发送消息的参与方 EDI 属性。 在 EDI 属性对话框中 （对于 X12 或 EDIFACT） 的验证和确认生成页中，选择"允许尾部分隔符"。 单击此复选框之后, 可以指定为尾部分隔符的中间 XML 中通过单击"创建为尾部分隔符的空 XML 标记"已创建空 XML 标记。  
  
## <a name="contrl-ack-is-enabled-but-not-generated"></a>已启用，但不是会生成 CONTRL 确认  
 **症状**  
  
 验证和确认生成中的生成功能确认复选框处于选中状态发送参与方，但 EDI 接收管道尚未生成 CONTRL 确认。  
  
 **可能的原因**  
  
 CONTRL 消息包含几个必需的数据元素，必须从交换复制。 如果交换中的数据元素缺失或在语法上无效，则接收管道无法生成语法上有效的 CONTRL 消息。  
  
 **解决方法**  
  
 CONTRL 确认以外的其他某种方法报告错误条件。  
  
## <a name="there-was-a-failure-executing-the-receive-pipeline-error-message"></a>"出现执行接收管道..."错误消息  
 **症状**  
  
 尝试运行 AS2 接收管道结果导致出现 80040154 错误。  
  
 **可能的原因**  
  
 管道不支持在 64 位主机实例上。  
  
 **解决方法**  
  
 将管道与 32 位主机相关联。  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a>如果启用了基于端口的身份验证，并且 BizTalk Server 不具有访问授权和安全信息的 X12 编码消息被挂起  
 **症状**  
  
 通过用于已启用的身份验证，并发送不能确定该消息的参与方的接收端口收到一条消息时，BizTalk Server 将挂起该消息。  
  
 **可能的原因**  
  
 BizTalk Server 的接收端口 （接收端口的"无身份验证"属性被清除） 启用身份验证，如果需要设置为"ISA1-2 （授权限定符和信息）"和"ISA3-4 （安全限定符和信息）"若要处理的交换的属性。 这些属性设置为 X12 中的参与方作为交换发送方的参与方的交换处理属性页。 如果 BizTalk Server 无法确定这些属性的值，它将挂起该消息。  
  
 这可能通过两种方式。 在第一种情况下，如果 BizTalk Server 无法确定参与方发送消息，它将使用 EDI 全局属性并不会访问授权和安全设置。 因此，它将挂起该消息。 在第二种情况下，如果 BizTalk Server 确定参与方，但未配置的参与方 ISA1-2 和 ISA3-4 属性，BizTalk Server 也无权访问授权和安全信息并将挂起该消息。  
  
 **解决方法**  
  
 请确保可以识别的消息发送方和 ISA1-2 和 ISA3-4 属性参与方协议中定义。  
  
## <a name="incorrect-se01-in-a-split-hipaa-subdocument"></a>拆分 HIPAA 子文档中的 SE01 不正确  
 **症状**  
  
 事务集尾部 （SE01 字段） 提供的数据段，其中包括 X12/HIPAA 文档的标头和尾部段的计数。 但是，对于拆分的 HIPAA 子文档，EDI 接收管道会应用相同的 SE01 值与原始文档，而不是重新对其进行计算。  
  
 **原因**  
  
 EDI 接收管道将 SE01 的值从原始 HIPAA 文档到拆分的子文档。  
  
## <a name="error-message-for-duplicate-unb5-or-unh1-is-not-descriptive"></a>有关 UNB5 或 UNH1 重复的错误消息不是描述性  
 如果 BizTalk Server 接收一条消息，具有重复的 UNB5 （交换控制编号） 或 UNH1 （事务集参考编号）、 错误代码和描述，它将发布将不清楚地指明问题的性质。  
  
## <a name="biztalk-server-will-suspend-a-very-large-interchange-if-it-runs-out-of-memory"></a>如果内存不足，BizTalk Server 将挂起非常大的交换  
 分析非常大的交换时，BizTalk Server 可能会耗尽内存。 如果是这样，它将发布错误并挂起该交换。 在组中心页中，您将无法再以查看所有已挂起的特大交换的内容。 你将能够看到初始消息的一部分，但 BizTalk Server 是已挂起的交换，它可以显示的数据量的限制。  
  
## <a name="korean-characters-added-to-an-enumeration-in-a-kedifact-schema-must-be-in-unicode"></a>KEDIFACT 架构中的枚举添加的韩语字符必须为 unicode 格式  
 当 BizTalk Server 收到包含韩语字符 KEDIFACT 编码的交换时，它将使用 UNB2 字段中的代码页/字符集值来处理交换。 但是，如果您通过枚举具有 ID 数据类型添加的韩语字符来修改 KEDIFACT 架构，您必须添加值 utf-16 UNICODE，为指定的架构的顶部。  
  
## <a name="executing-an-edi-receive-pipeline-from-within-an-orchestration-is-not-supported"></a>执行 EDI 接收管道在业务流程不支持  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您通常可以执行接收管道的表达式形状中业务流程。 尚未针对 EDIReceive 管道或 AS2EdiReceive 管道，因此不支持测试此功能。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>不得修改 BizTalk EDI 应用程序  
 不得修改或删除 BizTalk EDI 应用程序中的项目。 如果修改此应用程序，则没有办法可以恢复到原始应用程序通过取消配置和重新配置 EDI 和 AS2 功能。  
  
## <a name="see-also"></a>请参阅  
 [EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md)   
 [BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)   
 [演练 (X12):接收 EDI 交换并发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)