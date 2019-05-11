---
title: 用于 Siebel eBusiness 应用程序的 BizTalk 适配器的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- limitations of, Siebel adapter
- Siebel adapter, limitations of
ms.assetid: fda63dd6-bad5-4f6d-8cc1-5855efb6f063
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 482d48a4d67ea6c232c892045548e2ac180289db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371475"
---
# <a name="limitations-of-biztalk-adapter-for-siebel-ebusiness-applications"></a>用于 Siebel eBusiness 应用程序的 BizTalk 适配器的限制
以下已知的限制[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]:  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不兼容的 Microsoft BizTalk 适配器用于 Siebel eBusiness 应用程序，以前版本的适配器。 该适配器的当前版本不支持发送和接收消息具有通过使用适配器的早期版本生成的架构的。  
  
  > [!NOTE]
  >  您可以修改为使用新的 Siebel 适配器的以前版本的 BizTalk 项目的基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 有关详细信息，请参阅[迁移 BizTalk 项目创建使用 Siebel 适配器的上一步版本](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持工作流对象。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不会验证该客户端到 Siebel 系统传递的时间值的格式。 适配器客户端必须确保指定的日期和时间字段的值遵循 Siebel 系统需要在其中的格式。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不执行架构验证。 例如，如果 Siebel 系统允许长度为 30 的字段可能需要使用长度为 100，值。 它还会导致在某些方案中的数据丢失，因为客户端将通过业务对象插入的数据可能不一定是实际写入到数据库的数据。 适配器客户端必须显式验证输入针对显示适配器的架构。 但是，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]未能验证所有必需的字段 （适用于业务组件） 或指定参数 （适用于业务服务）。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]预期要在 Siebel 的标准格式中指定的时间值 — 即 hh: mm:。 时间值中指定了任何其他格式将产生错误，并[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]引发`TargetSystemException`。  
  
- 在某些情况下，Siebel 应用程序可能会或可能不会引发一条错误消息。 例如，使用表达式的搜索操作可能会引发异常或返回零个 accords。 相应地，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可能会引发`TargetSystemException`或获取空的 XML 作为输出。  
  
- 从 Siebel 系统使用 WCF 服务模型，检索数据时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不超过 65536 节点的 Xml 反序列化。 请确保输出 XML 具有节点小于或等于为 65536。 可以通过修改你的应用程序的 app.config 文件来解决此限制。 有关说明，请参阅[Siebel 适配器的故障排除操作问题](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md)。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]从业务组件层，而不是数据库层中检索字段的最大长度。 因此，如果尝试插入符合数据库列的最大长度，但这是在业务组件的相应字段的最大长度大于一个值，写入到数据库的值可能不同于你想要的值若要输入。  
  
- 执行批处理操作 （Insert、 Update 和 Delete） 时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将引发错误，如果第一个操作会导致错误。 但是，如果第一个操作成功，任何后续操作失败，适配器将不会引发错误，但是返回到输出中的成功操作相对应的记录的 Id。 适配器客户端必须显式验证是否已成功的操作。  
  
- 由于超时由基础 Siebel 客户端 API，处理的问题[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持命令，并连接超时。  
  
- 考虑用户"A"Siebel 中生成的元数据的操作的其中一个方案。 "B"，具有较低特权用户"A"以外的另一个用户将能够访问的元数据。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不执行任何检查来验证是否用户"B"必须有权访问元数据。 但是，因特权不足而用户"B"可能不能通过使用元数据执行对 Siebel 系统的任何操作。  
  
- [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持指定连接 URI，其中含有特殊字符的任何参数值。 对于每个参数值，该值包含特殊字符，请确保指定的 URI 编码标准的相应值替换特殊字符。  
  
- 使用与适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，如果在 WCF 自定义的凭据将发送端口不正确，不会处理请求消息。 指定正确的凭据后，将消息发送到 Siebel 系统中，并收到的响应。 但是，响应消息不是输出连接到可用的。 在这种情况下，可能需要重新启动主机实例。  
  
## <a name="see-also"></a>请参阅  
 [了解用于 Siebel eBusiness 应用程序的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)