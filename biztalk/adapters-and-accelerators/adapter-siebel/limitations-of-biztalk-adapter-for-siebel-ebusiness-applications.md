---
title: 为 Siebel eBusiness 应用程序的 BizTalk Adapter 限制 |Microsoft 文档
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
ms.openlocfilehash: f9018c79e910c2bfac05f07466cbeeb79ea045ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222645"
---
# <a name="limitations-of-biztalk-adapter-for-siebel-ebusiness-applications"></a>为 Siebel eBusiness 应用程序的 BizTalk Adapter 限制
以下已知的限制[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]:  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不兼容与 Microsoft BizTalk 适配器为 Siebel eBusiness 应用程序，以前的版本中的适配器。 当前版本的适配器不支持发送和接收具有通过使用该适配器的早期版本生成的架构的消息。  
  
    > [!NOTE]
    >  你可以修改 BizTalk 项目对于早期版本 Siebel 适配器，以使用新的基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 有关详细信息，请参阅[迁移 BizTalk 项目创建使用 Siebel 适配器的上一步版本](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持工作流对象。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不会验证该客户端到 Siebel 系统传递一个时间值的格式。 适配器客户端必须确保为日期和时间字段指定的值符合 Siebel 系统需要在其中的格式。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不执行架构验证。 例如，如果 Siebel 系统允许的长度为 30 的字段，就可能需要 100，长度的值。 它还可能导致在某些方案中的数据丢失，因为客户端插入通过业务对象的数据不一定是实际写入到数据库的数据。 适配器客户端必须显式验证针对该适配器显示架构的输入。 但是，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]未能验证所有必需的字段 （适用于业务组件），或指定自变量 （对于业务服务）。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]需要标准 Siebel 格式中指定的时间值-即 hh: mm:。 时间值中任何其他格式将产生错误，指定与[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]引发`TargetSystemException`。  
  
-   在某些情况下，Siebel 应用程序可能或可能不会引发一条错误消息。 例如，使用表达式的搜索操作可能会引发异常或返回零 accords。 相应地，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可能引发`TargetSystemException`或获取空的 XML 作为输出。  
  
-   从使用 WCF 服务模型时，Siebel 系统检索数据时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不具有多个 65536 节点的 Xml 反序列化。 请确保输出 XML 具有节点小于或等于为 65536。 可以通过修改你的应用程序的 app.config 文件来解决此限制。 有关说明，请参阅[Siebel 适配器的故障排除操作问题](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md)。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]从业务组件层，而不是数据库层中检索字段的最大长度。 因此，如果你尝试插入的值符合的数据库列的最大长度，但超过了在业务组件的相应字段的最大长度，写入到数据库的值可能不同于你想要的值若要输入。  
  
-   执行批处理操作 （Insert、 Update 和 Delete） 时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]的第一个操作会导致出现错误时引发错误。 但是，如果第一个操作成功，并且任何后续的操作失败，适配器将不会引发错误，而是返回到成功的操作在输出中的相对应的记录的 Id。 适配器客户端必须显式验证是否所有的操作已成功。  
  
-   由于出现超时处理由基础 Siebel 客户端 API，问题[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持命令和连接超时。  
  
-   假设用户"A"在 Siebel 生成操作的元数据的其中一个方案。 另一个用户"B"，具有较小特权比"A，"用户将能够访问的元数据。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不执行任何检查来验证是否用户"B"必须有权访问元数据。 但是，由于没有足够的特权用户"B"可能不能使用元数据执行 Siebel 系统上的任何操作。  
  
-   [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持指定的连接具有任何参数值的特殊字符的 URI。 对于每个参数值包含特殊字符，请确保的特殊字符替换为相应的值，指定的 URI 编码标准。  
  
-   使用具有适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，如果在 WCF 自定义的凭据将发送端口不正确，不会处理请求消息。 指定正确的凭据后，将消息发送到 Siebel 系统中，并收到的响应。 但是，响应消息不可用到的输出端口。 在这种情况下，你可能需要重新启动主机实例。  
  
## <a name="see-also"></a>另请参阅  
 [为 Siebel eBusiness 应用程序了解的 BizTalk Adapter](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)