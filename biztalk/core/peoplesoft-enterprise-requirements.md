---
redirect_url: /biztalk/core/architecture-of-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 3db930f26e9c8a1d460f29c502d841ac27fd6c8e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314509"
---
# <a name="peoplesoft-enterprise-requirements"></a>PeopleSoft Enterprise 要求

## <a name="send-handler-requirements"></a>发送处理程序要求  
 用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器包含自定义组件接口 (CI)，并提供对它通过 Java API 的访问。 自定义 CI 对象`GET_CI_INFO`，使用 PeopleSoft 工具提供用于 PeopleSoft Enterprise 的 BizTalk 适配器所需的元数据信息在 PeopleSoft 系统中部署。 有关详细信息，请参阅[安装企业应用程序适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)。  
  
 上传自定义组件接口是执行一次。 此文件中， `GET_CI_INFO.pc`、 随产品安装和使用适配器来浏览 Ci 之前必须安装。 必须有权访问 PeopleSoft 应用程序设计器。 应用程序设计器应用程序不必位于 BizTalk Server 计算机上。 应用程序设计器用于上传到您浏览的 PeopleSoft 计算机上将自定义 CI。  
  
 必须有权访问的 PeopleSoft 计算机，因为您必须设置环境变量 CLASSPATH (或中设置该信息**传输属性**屏幕) 以指向 PeopleSoft 的`PSJOA/psjoa.jar`文件。  
  
## <a name="see-also"></a>请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 