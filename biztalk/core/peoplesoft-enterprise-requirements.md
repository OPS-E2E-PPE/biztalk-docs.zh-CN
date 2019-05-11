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
# <a name="peoplesoft-enterprise-requirements"></a><span data-ttu-id="3e0dc-101">PeopleSoft Enterprise 要求</span><span class="sxs-lookup"><span data-stu-id="3e0dc-101">PeopleSoft Enterprise Requirements</span></span>

## <a name="send-handler-requirements"></a><span data-ttu-id="3e0dc-102">发送处理程序要求</span><span class="sxs-lookup"><span data-stu-id="3e0dc-102">Send Handler requirements</span></span>  
 <span data-ttu-id="3e0dc-103">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器包含自定义组件接口 (CI)，并提供对它通过 Java API 的访问。</span><span class="sxs-lookup"><span data-stu-id="3e0dc-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise contains a custom component interface (CI) and provides access to it through a Java API.</span></span> <span data-ttu-id="3e0dc-104">自定义 CI 对象`GET_CI_INFO`，使用 PeopleSoft 工具提供用于 PeopleSoft Enterprise 的 BizTalk 适配器所需的元数据信息在 PeopleSoft 系统中部署。</span><span class="sxs-lookup"><span data-stu-id="3e0dc-104">A custom CI object, `GET_CI_INFO`, is deployed in the PeopleSoft system using PeopleSoft Tools to provide metadata information that is required by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="3e0dc-105">有关详细信息，请参阅[安装企业应用程序适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="3e0dc-105">For more information, see [Install Enterprise Applications adapters](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md).</span></span>  
  
 <span data-ttu-id="3e0dc-106">上传自定义组件接口是执行一次。</span><span class="sxs-lookup"><span data-stu-id="3e0dc-106">Uploading the custom component interface is a one-time occurrence.</span></span> <span data-ttu-id="3e0dc-107">此文件中， `GET_CI_INFO.pc`、 随产品安装和使用适配器来浏览 Ci 之前必须安装。</span><span class="sxs-lookup"><span data-stu-id="3e0dc-107">This file, `GET_CI_INFO.pc`, installs with the product and must be installed before you can use the adapter to browse CIs.</span></span> <span data-ttu-id="3e0dc-108">必须有权访问 PeopleSoft 应用程序设计器。</span><span class="sxs-lookup"><span data-stu-id="3e0dc-108">You must have access to the PeopleSoft Application Designer.</span></span> <span data-ttu-id="3e0dc-109">应用程序设计器应用程序不必位于 BizTalk Server 计算机上。</span><span class="sxs-lookup"><span data-stu-id="3e0dc-109">The Application Designer application does not have to be on the BizTalk Server computer.</span></span> <span data-ttu-id="3e0dc-110">应用程序设计器用于上传到您浏览的 PeopleSoft 计算机上将自定义 CI。</span><span class="sxs-lookup"><span data-stu-id="3e0dc-110">You use the Application Designer to upload the custom CI onto the PeopleSoft computer that you browse.</span></span>  
  
 <span data-ttu-id="3e0dc-111">必须有权访问的 PeopleSoft 计算机，因为您必须设置环境变量 CLASSPATH (或中设置该信息**传输属性**屏幕) 以指向 PeopleSoft 的`PSJOA/psjoa.jar`文件。</span><span class="sxs-lookup"><span data-stu-id="3e0dc-111">You must have access to the PeopleSoft computer because you must set the environment variable CLASSPATH (or set the information in the **Transport Properties** screen) to point to PeopleSoft's `PSJOA/psjoa.jar` file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e0dc-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e0dc-112">See Also</span></span>  
 [<span data-ttu-id="3e0dc-113">入门</span><span class="sxs-lookup"><span data-stu-id="3e0dc-113">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 