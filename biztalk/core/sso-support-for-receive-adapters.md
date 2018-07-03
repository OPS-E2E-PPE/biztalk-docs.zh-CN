---
title: 接收适配器的 SSO 支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4767387c-f24b-4986-aaed-6724c5d6b347
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00948d53ada9dd5eb428b0d1975e16b21b19064d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008430"
---
# <a name="sso-support-for-receive-adapters"></a><span data-ttu-id="659f0-102">接收适配器的 SSO 支持</span><span class="sxs-lookup"><span data-stu-id="659f0-102">SSO Support for Receive Adapters</span></span>
<span data-ttu-id="659f0-103">使用企业单一登录 (SSO) 提供的服务，可以跨本地、网络和域边界来存储和传输加密的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="659f0-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local, network, and domain boundaries.</span></span> <span data-ttu-id="659f0-104">传输适配器编写人员可以利用 SSO API 来处理传输适配器用于访问后端应用程序的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="659f0-104">Transport adapter writers can leverage SSO APIs to handle the user credentials that a transport adapter uses to access back-end applications.</span></span>  
  
 <span data-ttu-id="659f0-105">通常需要不支持 SSO 的传输适配器来配置用于单组凭据，这些凭据用于访问后端应用程序。</span><span class="sxs-lookup"><span data-stu-id="659f0-105">Transport adapters that do not support SSO are usually required to be configured with a single set of credentials that they use for accessing back-end applications.</span></span> <span data-ttu-id="659f0-106">对于许多后端系统而言，单个帐户身份验证可能无法满足所有的安全强制要求。</span><span class="sxs-lookup"><span data-stu-id="659f0-106">For many back-end systems, single account authentication may not satisfy all security enforcements.</span></span> <span data-ttu-id="659f0-107">许多应用程序都根据正访问它们的用户提供不同的访问权限。</span><span class="sxs-lookup"><span data-stu-id="659f0-107">Many applications provide different access rights depending on the user who is accessing them.</span></span> <span data-ttu-id="659f0-108">SSO 允许适配器基于正尝试访问它的用户动态选择用于终结点的凭据。</span><span class="sxs-lookup"><span data-stu-id="659f0-108">SSO allows adapters to dynamically choose the credentials to use for the endpoint based on the user who is trying to access it.</span></span>  
  
## <a name="how-receive-adapters-work-with-sso"></a><span data-ttu-id="659f0-109">接收适配器如何与 SSO 一起工作</span><span class="sxs-lookup"><span data-stu-id="659f0-109">How Receive Adapters Work with SSO</span></span>  
 <span data-ttu-id="659f0-110">支持 SSO 的接收适配器在接收消息后、但在将消息发布到 BizTalk Server 前将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="659f0-110">Receive adapters that support SSO perform the following steps after receiving a message and before publishing it to BizTalk Server:</span></span>  
  
1. <span data-ttu-id="659f0-111">适配器将模拟发件人，并使用获取 SSO 票证代表发件人**ISSOTicket.IssueTicket** API。</span><span class="sxs-lookup"><span data-stu-id="659f0-111">The adapter impersonates the sender and obtains the SSO ticket on behalf of the sender by using the **ISSOTicket.IssueTicket** API.</span></span>  
  
2. <span data-ttu-id="659f0-112">在成功获取某一 SSO 票证后，该适配器会将该票证存储于系统命名空间下的消息上下文属性“SSOTicket”中。</span><span class="sxs-lookup"><span data-stu-id="659f0-112">After successfully obtaining an SSO ticket the adapter stores it on the message context property “SSOTicket” under the system namespace.</span></span>  
  
   <span data-ttu-id="659f0-113">下面的代码示例演示如何获取票证以及如何将票证存储于消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="659f0-113">The following code fragment demonstrates how the ticket is obtained and how it is stored on the message context.</span></span>  
  
```  
public class MyAdapter : IBTTransport,   
                         IBTTransportConfig,   
                         IBTTransportControl,  
                         IPersistPropertyBag,   
                         IBaseComponent  
{  
...  
     private string m_SSOToken = null;  
  
 // Get a ticket for the sender  
     private void GetSSOTicket(IntPtr token)  
     {  
       bool impersonated = false;  
      WindowsImpersonationContext wic = null;  
  
 if (token != (IntPtr)0)   
 {  
     try   
 {  
         // Impersonate the user using his security  
 // token  
            WindowsIdentity wi =   
 new WindowsIdentity(token);  
            wic = wi.Impersonate();  
            impersonated = true;  
  
         // Get an SSO ticket for the impersonated  
 // user  
            ISSOTicket ssoTicket = new ISSOTicket();  
            m_SSOToken = ssoTicket.IssueTicket(0);  
         }  
         finally   
 {  
           if (impersonated)  
            // Revert the impersonation  
            wic.Undo();  
          }  
}  
}  
...  
  
     private void WriteSSOTicketToContext(  
 IBaseMessage message )  
     {  
         if (m_SSOTicket != null)   
 {  
 // Write the SSO ticket to the message context  
          message.Context.Write(  
 “SSOTicket”,  
 http://schemas.microsoft.com/BizTalk/2003/system-properties,   
 m_SSOToken);  
        }  
      }  
}  
```  
  
## <a name="party-resolution"></a><span data-ttu-id="659f0-114">参与方解析</span><span class="sxs-lookup"><span data-stu-id="659f0-114">Party Resolution</span></span>  
 <span data-ttu-id="659f0-115">参与方解析管道组件负责将发件人证书或发件人安全标识符 (SID) 映射到相应的已配置 BizTalk Server 参与方。</span><span class="sxs-lookup"><span data-stu-id="659f0-115">The Party Resolution pipeline component is responsible for mapping the sender certificate or the sender security identifier (SID) to the corresponding configured BizTalk Server party.</span></span> <span data-ttu-id="659f0-116">具有此信息提供给他们的适配器应设置两个系统消息上下文属性**WindowsUser**并**SignatureCertificate**，以供下游的参与方解析如果配置的组件。</span><span class="sxs-lookup"><span data-stu-id="659f0-116">Adapters that have this information available to them should set the two system message context properties, **WindowsUser** and **SignatureCertificate**, to be consumed by the downstream party resolution component if configured.</span></span>  
  
 <span data-ttu-id="659f0-117">**WindowsUser**发件人，例如 redmond\myBtsUser 的域用户填充属性。</span><span class="sxs-lookup"><span data-stu-id="659f0-117">The **WindowsUser** property is populated with the domain user of the sender, for example redmond\myBtsUser.</span></span> <span data-ttu-id="659f0-118">**SignatureCertificate**客户端身份验证证书的指纹填充属性。</span><span class="sxs-lookup"><span data-stu-id="659f0-118">The **SignatureCertificate** property is populated with the thumbprint of the client authentication certificate.</span></span>  
  
## <a name="managing-passwords"></a><span data-ttu-id="659f0-119">管理密码</span><span class="sxs-lookup"><span data-stu-id="659f0-119">Managing Passwords</span></span>  
 <span data-ttu-id="659f0-120">如果您将凭据直接放置于某一终结点的属性中，则在您需要导出绑定文件时密码字段的内容将被清除。</span><span class="sxs-lookup"><span data-stu-id="659f0-120">If you put credentials directly in the properties of an endpoint, the password field will be blanked out when you need to export a binding file.</span></span> <span data-ttu-id="659f0-121">这将要求您的用户以管理员的身份重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="659f0-121">This will require your user to re-enter the password as an administrator.</span></span> <span data-ttu-id="659f0-122">可以通过将 SSO 用于凭据来避免此问题。</span><span class="sxs-lookup"><span data-stu-id="659f0-122">You can avoid this difficulty by using SSO for credentials.</span></span>  
  
 <span data-ttu-id="659f0-123">如果适配器终结点都有**密码**属性，请注意，以明文形式在 SSO 配置存储数据库中存储的实际值。</span><span class="sxs-lookup"><span data-stu-id="659f0-123">If the adapter endpoint has a **Password** property, be aware that the actual value is stored in clear text in the SSO Configure Store database.</span></span> <span data-ttu-id="659f0-124">这与密码在用户界面中以“\*”形式显示的情况不同。</span><span class="sxs-lookup"><span data-stu-id="659f0-124">This is despite the fact that it is displayed in the user interface as "\*".</span></span> <span data-ttu-id="659f0-125">此属性也通过网络传输，并且使用 BizTalk Server 示例 ExplorerOM 的简单脚本就能够读取它。</span><span class="sxs-lookup"><span data-stu-id="659f0-125">This property is also transferred through the network and a simple script using the BizTalk Server sample ExplorerOM will be able to read it.</span></span>