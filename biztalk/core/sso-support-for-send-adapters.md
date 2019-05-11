---
title: 发送适配器的 SSO 支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45dc2597-0036-4444-8b35-d18621b003d8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efe1b6eac59478dea5e7ba56351c543c04f8c223
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398955"
---
# <a name="sso-support-for-send-adapters"></a><span data-ttu-id="92007-102">发送适配器的 SSO 支持</span><span class="sxs-lookup"><span data-stu-id="92007-102">SSO Support for Send Adapters</span></span>
<span data-ttu-id="92007-103">企业单一登录 (SSO) 提供的服务来存储和传输加密用户凭据跨本地、 网络和域边界。</span><span class="sxs-lookup"><span data-stu-id="92007-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local, network, and domain boundaries.</span></span> <span data-ttu-id="92007-104">创建传输适配器时，您可以利用 SSO Api 来处理传输适配器用于访问后端应用程序的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="92007-104">When you create a transport adapter, you can leverage SSO APIs to handle the user credentials that a transport adapter uses to access back-end applications.</span></span>  
  
 <span data-ttu-id="92007-105">通常需要使用一组凭据用于访问后端应用程序所使用的配置不支持 SSO 的传输适配器。</span><span class="sxs-lookup"><span data-stu-id="92007-105">Transport adapters that do not support SSO are usually required to be configured with a single set of credentials that they use for accessing back-end applications.</span></span> <span data-ttu-id="92007-106">对于许多后端系统，单个帐户身份验证可能无法满足所有的安全强制要求。</span><span class="sxs-lookup"><span data-stu-id="92007-106">For many back-end systems, single account authentication may not satisfy all security enforcements.</span></span> <span data-ttu-id="92007-107">许多应用程序提供不同的访问权限，具体取决于正访问它们的用户。</span><span class="sxs-lookup"><span data-stu-id="92007-107">Many applications provide different access rights depending on the user who is accessing them.</span></span> <span data-ttu-id="92007-108">SSO 允许适配器能够动态选择要使用的用户尝试访问它所基于的终结点的凭据。</span><span class="sxs-lookup"><span data-stu-id="92007-108">SSO allows adapters to dynamically choose the credentials to use for the endpoint based on the user who is trying to access it.</span></span>  
  
## <a name="how-send-adapters-work-with-sso"></a><span data-ttu-id="92007-109">如何发送适配器与 SSO 一起工作</span><span class="sxs-lookup"><span data-stu-id="92007-109">How Send Adapters Work with SSO</span></span>  
 <span data-ttu-id="92007-110">发送适配器支持 SSO 的验证和兑换票证并使用从 SSO 系统获取用户凭据**ISSOTicket.ValidateAndRedeemTicket** API。</span><span class="sxs-lookup"><span data-stu-id="92007-110">Send adapters that support SSO validate and redeem the ticket and obtain the user credentials from the SSO system by using the **ISSOTicket.ValidateAndRedeemTicket** API.</span></span> <span data-ttu-id="92007-111">适配器使用获取的凭据进行身份验证的目标终结点。</span><span class="sxs-lookup"><span data-stu-id="92007-111">The adapter uses the obtained credentials to authenticate with the destination endpoint.</span></span>  
  
 <span data-ttu-id="92007-112">下面的代码段演示了如何发送适配器将从 SSO 系统获取用户凭据：</span><span class="sxs-lookup"><span data-stu-id="92007-112">The following code fragment demonstrates how a send adapter obtains the user credentials from the SSO system:</span></span>  
  
```  
public class MyAdapter : IBTTransport,   
                         IBTTransportConfig,   
                         IBTTransportControl,  
                        IPersistPropertyBag,   
                         IBaseComponent  
{  
...  
     private string m_UserName = null;  
     private string m_UserPassword = null;  
  
 // Get user credentials from SSO  
 // AffiliateAppVal is the name of SSO affiliate   
 // application for the specific destination endpoint  
     private void GetUserCredentials(  
 IBaseMessage message,   
 string AffiliateAppVal )  
     {  
 string creds[] = null;  
 string externalUserName = null;  
  
 ISSOTicket ssoTicket = new ISSOTicket();  
 creds = ssoTicket.ValidateAndRedeemTicket(  
 message,   
 AffiliateAppVal,   
 0,   
 out externalUserName);  
  
 m_UserName = externalUserName;  
 m_UserPassword = creds[0];  
     }  
...  
}  
```  
  
## <a name="party-resolution"></a><span data-ttu-id="92007-113">参与方解析</span><span class="sxs-lookup"><span data-stu-id="92007-113">Party Resolution</span></span>  
 <span data-ttu-id="92007-114">参与方解析管道组件负责将发件人证书或发件人安全标识符 (SID) 映射到相应的已配置 BizTalk Server 参与方。</span><span class="sxs-lookup"><span data-stu-id="92007-114">The Party Resolution pipeline component is responsible for mapping the sender certificate or the sender security identifier (SID) to the corresponding configured BizTalk Server party.</span></span> <span data-ttu-id="92007-115">具有此信息提供给他们的适配器应设置两个系统消息上下文属性**WindowsUser**并**SignatureCertificate**，以供下游的参与方解析如果配置的组件。</span><span class="sxs-lookup"><span data-stu-id="92007-115">Adapters that have this information available to them should set the two system message context properties, **WindowsUser** and **SignatureCertificate**, to be consumed by the downstream party resolution component if configured.</span></span>  
  
 <span data-ttu-id="92007-116">**WindowsUser**发件人，例如 redmond\myBtsUser 的域用户填充属性。</span><span class="sxs-lookup"><span data-stu-id="92007-116">The **WindowsUser** property is populated with the domain user of the sender, for example redmond\myBtsUser.</span></span> <span data-ttu-id="92007-117">**SignatureCertificate**客户端身份验证证书的指纹填充属性。</span><span class="sxs-lookup"><span data-stu-id="92007-117">The **SignatureCertificate** property is populated with the thumbprint of the client authentication certificate.</span></span>  
  
## <a name="managing-passwords"></a><span data-ttu-id="92007-118">管理密码</span><span class="sxs-lookup"><span data-stu-id="92007-118">Managing passwords</span></span>  
 <span data-ttu-id="92007-119">如果凭据直接置于终结点的属性，密码字段将被留空时您需要导出绑定文件。</span><span class="sxs-lookup"><span data-stu-id="92007-119">If you put credentials directly in the properties of an endpoint, the password field will be blanked out when you need to export a binding file.</span></span> <span data-ttu-id="92007-120">这将要求你重新输入密码以管理员身份的用户。</span><span class="sxs-lookup"><span data-stu-id="92007-120">This will require your user to re-enter the password as an administrator.</span></span> <span data-ttu-id="92007-121">可以通过将 SSO 用于凭据来避免此问题。</span><span class="sxs-lookup"><span data-stu-id="92007-121">You can avoid this difficulty by using SSO for credentials.</span></span>