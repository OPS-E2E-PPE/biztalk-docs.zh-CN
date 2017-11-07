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
# <a name="peoplesoft-enterprise-requirements"></a><span data-ttu-id="a9ab1-101">PeopleSoft Enterprise 要求</span><span class="sxs-lookup"><span data-stu-id="a9ab1-101">PeopleSoft Enterprise Requirements</span></span>

## <a name="send-handler-requirements"></a><span data-ttu-id="a9ab1-102">发送处理程序要求</span><span class="sxs-lookup"><span data-stu-id="a9ab1-102">Send Handler requirements</span></span>  
 <span data-ttu-id="a9ab1-103">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器包含一个自定义组件接口 (CI) 并且可以通过 Java API 对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="a9ab1-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise contains a custom component interface (CI) and provides access to it through a Java API.</span></span> <span data-ttu-id="a9ab1-104">使用 PeopleSoft 工具在 PeopleSoft 系统中部署一个自定义 CI 对象 `GET_CI_INFO`，以提供用于 PeopleSoft Enterprise 的 BizTalk 适配器所需的元数据信息。</span><span class="sxs-lookup"><span data-stu-id="a9ab1-104">A custom CI object, `GET_CI_INFO`, is deployed in the PeopleSoft system using PeopleSoft Tools to provide metadata information that is required by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="a9ab1-105">有关详细信息，请参阅[安装企业应用程序适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="a9ab1-105">For more information, see [Install Enterprise Applications adapters](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md).</span></span>  
  
 <span data-ttu-id="a9ab1-106">上载自定义组件接口是一次性的匹配项。</span><span class="sxs-lookup"><span data-stu-id="a9ab1-106">Uploading the custom component interface is a one-time occurrence.</span></span> <span data-ttu-id="a9ab1-107">该文件 `GET_CI_INFO.pc` 是与产品一起安装的，并且必须安装该文件才能使用该适配器来浏览 CI。</span><span class="sxs-lookup"><span data-stu-id="a9ab1-107">This file, `GET_CI_INFO.pc`, installs with the product and must be installed before you can use the adapter to browse CIs.</span></span> <span data-ttu-id="a9ab1-108">你必须有权 PeopleSoft 应用程序设计器。</span><span class="sxs-lookup"><span data-stu-id="a9ab1-108">You must have access to the PeopleSoft Application Designer.</span></span> <span data-ttu-id="a9ab1-109">应用程序设计器应用程序没有要在 BizTalk Server 计算机上。</span><span class="sxs-lookup"><span data-stu-id="a9ab1-109">The Application Designer application does not have to be on the BizTalk Server computer.</span></span> <span data-ttu-id="a9ab1-110">您可以使用此应用程序设计器将自定义 CI 上载到您浏览的 PeopleSoft 计算机上。</span><span class="sxs-lookup"><span data-stu-id="a9ab1-110">You use the Application Designer to upload the custom CI onto the PeopleSoft computer that you browse.</span></span>  
  
 <span data-ttu-id="a9ab1-111">因为你必须设置此环境变量类路径中，你必须有权 PeopleSoft 计算机 (或设置中的信息**传输属性**屏幕) 以指向 PeopleSoft 的`PSJOA/psjoa.jar`文件。</span><span class="sxs-lookup"><span data-stu-id="a9ab1-111">You must have access to the PeopleSoft computer because you must set the environment variable CLASSPATH (or set the information in the **Transport Properties** screen) to point to PeopleSoft's `PSJOA/psjoa.jar` file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ab1-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9ab1-112">See Also</span></span>  
 [<span data-ttu-id="a9ab1-113">入门</span><span class="sxs-lookup"><span data-stu-id="a9ab1-113">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 