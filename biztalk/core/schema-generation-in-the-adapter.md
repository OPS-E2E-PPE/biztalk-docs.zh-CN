---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 4e4209c75ca52585c0a11141dbe0d9841fa6a5ba
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="schema-generation-in-the-adapter"></a>适配器中的架构生成
TIBCO Rendezvous 系统中没有消息类型存储库。 所有消息构造和解析都在 Rendezvous 应用程序级别隐藏了。 由于这个限制，用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器无法提供架构生成功能。  
  
## <a name="writing-schemas"></a>编写架构  
 你必须编写架构和使用**添加现有项**在 Visual Studio 中将其导入在业务流程中使用。 架构对于 BizTalk Server 开发工具和 Visual Studio 中的集成都非常重要。 BizTalk Server 开发人员可以选择提供完整架构、最低限要求的架构，或介于二者之间的版本。  
  
## <a name="see-also"></a>另请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)