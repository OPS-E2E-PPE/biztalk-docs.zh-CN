---
redirect_url: /biztalk/core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: a277c5f5588a9455119b96f7c600dbadccffb8ac
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="peoplesoft-enterprise-requirements"></a>PeopleSoft Enterprise 要求

## <a name="send-handler-requirements"></a>发送处理程序要求  
 用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器包含一个自定义组件接口 (CI) 并且可以通过 Java API 对其进行访问。 使用 PeopleSoft 工具在 PeopleSoft 系统中部署一个自定义 CI 对象 `GET_CI_INFO`，以提供用于 PeopleSoft Enterprise 的 BizTalk 适配器所需的元数据信息。 有关详细信息，请参阅[安装企业应用程序适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)。  
  
 上载自定义组件接口是一次性的匹配项。 该文件 `GET_CI_INFO.pc` 是与产品一起安装的，并且必须安装该文件才能使用该适配器来浏览 CI。 你必须有权 PeopleSoft 应用程序设计器。 应用程序设计器应用程序没有要在 BizTalk Server 计算机上。 您可以使用此应用程序设计器将自定义 CI 上载到您浏览的 PeopleSoft 计算机上。  
  
 因为你必须设置此环境变量类路径中，你必须有权 PeopleSoft 计算机 (或设置中的信息**传输属性**屏幕) 以指向 PeopleSoft 的`PSJOA/psjoa.jar`文件。  
  
## <a name="see-also"></a>另请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 