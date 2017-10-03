---
title: "发送适配器的 SSO 支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45dc2597-0036-4444-8b35-d18621b003d8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d590ada6b8ee80c942714a698d0001c207ac6751
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sso-support-for-send-adapters"></a><span data-ttu-id="36eef-102">SSO 支持个发送适配器</span><span class="sxs-lookup"><span data-stu-id="36eef-102">SSO Support for Send Adapters</span></span>
<span data-ttu-id="36eef-103">使用企业单一登录 (SSO) 提供的服务，可以跨本地、网络和域边界来存储和传输加密的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="36eef-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local, network, and domain boundaries.</span></span> <span data-ttu-id="36eef-104">在您创建某一传输适配器时，可以充分利用 SSO API 来处理该传输适配器用于访问后端应用程序的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="36eef-104">When you create a transport adapter, you can leverage SSO APIs to handle the user credentials that a transport adapter uses to access back-end applications.</span></span>  
  
 <span data-ttu-id="36eef-105">通常需要不支持 SSO 的传输适配器来配置用于单组凭据，这些凭据用于访问后端应用程序。</span><span class="sxs-lookup"><span data-stu-id="36eef-105">Transport adapters that do not support SSO are usually required to be configured with a single set of credentials that they use for accessing back-end applications.</span></span> <span data-ttu-id="36eef-106">对于许多后端系统而言，单个帐户身份验证可能无法满足所有的安全强制要求。</span><span class="sxs-lookup"><span data-stu-id="36eef-106">For many back-end systems, single account authentication may not satisfy all security enforcements.</span></span> <span data-ttu-id="36eef-107">许多应用程序都根据正访问它们的用户提供不同的访问权限。</span><span class="sxs-lookup"><span data-stu-id="36eef-107">Many applications provide different access rights depending on the user who is accessing them.</span></span> <span data-ttu-id="36eef-108">SSO 允许适配器基于正尝试访问它的用户动态选择用于终结点的凭据。</span><span class="sxs-lookup"><span data-stu-id="36eef-108">SSO allows adapters to dynamically choose the credentials to use for the endpoint based on the user who is trying to access it.</span></span>  
  
## <a name="how-send-adapters-work-with-sso"></a><span data-ttu-id="36eef-109">发送适配器如何与 SSO 一起工作</span><span class="sxs-lookup"><span data-stu-id="36eef-109">How Send Adapters Work with SSO</span></span>  
 <span data-ttu-id="36eef-110">支持 SSO 的适配器验证和兑换该票证并使用从 SSO 系统中获取用户凭据发送**ISSOTicket.ValidateAndRedeemTicket** API。</span><span class="sxs-lookup"><span data-stu-id="36eef-110">Send adapters that support SSO validate and redeem the ticket and obtain the user credentials from the SSO system by using the **ISSOTicket.ValidateAndRedeemTicket** API.</span></span> <span data-ttu-id="36eef-111">该适配器使用获取的凭据对目标终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="36eef-111">The adapter uses the obtained credentials to authenticate with the destination endpoint.</span></span>  
  
 <span data-ttu-id="36eef-112">下面的代码段演示了发送适配器如何从 SSO 系统获取用户凭据：</span><span class="sxs-lookup"><span data-stu-id="36eef-112">The following code fragment demonstrates how a send adapter obtains the user credentials from the SSO system:</span></span>  
  
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
  
## <a name="party-resolution"></a><span data-ttu-id="36eef-113">参与方解析</span><span class="sxs-lookup"><span data-stu-id="36eef-113">Party Resolution</span></span>  
 <span data-ttu-id="36eef-114">参与方解析管道组件负责将发件人证书或发件人安全标识符 (SID) 映射到相应的已配置 BizTalk Server 参与方。</span><span class="sxs-lookup"><span data-stu-id="36eef-114">The Party Resolution pipeline component is responsible for mapping the sender certificate or the sender security identifier (SID) to the corresponding configured BizTalk Server party.</span></span> <span data-ttu-id="36eef-115">具有此信息提供给他们的适配器应设置两个系统消息上下文属性**WindowsUser**和**SignatureCertificate**，可供下游方解析如果配置的组件。</span><span class="sxs-lookup"><span data-stu-id="36eef-115">Adapters that have this information available to them should set the two system message context properties, **WindowsUser** and **SignatureCertificate**, to be consumed by the downstream party resolution component if configured.</span></span>  
  
 <span data-ttu-id="36eef-116">**WindowsUser**以域用户的发件人，例如 redmond\myBtsUser 填充属性。</span><span class="sxs-lookup"><span data-stu-id="36eef-116">The **WindowsUser** property is populated with the domain user of the sender, for example redmond\myBtsUser.</span></span> <span data-ttu-id="36eef-117">**SignatureCertificate**以客户端身份验证证书的指纹填充属性。</span><span class="sxs-lookup"><span data-stu-id="36eef-117">The **SignatureCertificate** property is populated with the thumbprint of the client authentication certificate.</span></span>  
  
## <a name="managing-passwords"></a><span data-ttu-id="36eef-118">管理密码</span><span class="sxs-lookup"><span data-stu-id="36eef-118">Managing passwords</span></span>  
 <span data-ttu-id="36eef-119">如果您将凭据直接放置于某一终结点的属性中，则在您需要导出绑定文件时密码字段的内容将被清除。</span><span class="sxs-lookup"><span data-stu-id="36eef-119">If you put credentials directly in the properties of an endpoint, the password field will be blanked out when you need to export a binding file.</span></span> <span data-ttu-id="36eef-120">这将要求您的用户以管理员的身份重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="36eef-120">This will require your user to re-enter the password as an administrator.</span></span> <span data-ttu-id="36eef-121">可以通过将 SSO 用于凭据来避免此问题。</span><span class="sxs-lookup"><span data-stu-id="36eef-121">You can avoid this difficulty by using SSO for credentials.</span></span>