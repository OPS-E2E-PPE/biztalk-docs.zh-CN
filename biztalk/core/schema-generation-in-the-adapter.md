---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 04db79d76850bf657dbd45e6c60e6fb7edbf1ffb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396951"
---
# <a name="schema-generation-in-the-adapter"></a>在适配器中的架构生成
TIBCO Rendezvous 系统不包括消息类型存储库。 所有消息构造和分析隐藏在 Rendezvous 应用程序级别的信息。 鉴于此限制，用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器不能提供架构生成功能。  
  
## <a name="writing-schemas"></a>编写架构  
 必须编写一个架构，并使用**添加现有项**在 Visual Studio 中将其导入在业务流程中使用。 架构是 BizTalk Server 开发工具和 Visual Studio 中的集成非常重要。 BizTalk Server 开发人员可以选择提供完整的架构、 最低要求的架构或二者之间的版本之间。  
  
## <a name="see-also"></a>请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)