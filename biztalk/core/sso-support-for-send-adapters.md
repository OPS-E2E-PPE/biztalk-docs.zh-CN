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
# <a name="sso-support-for-send-adapters"></a>SSO 支持个发送适配器
使用企业单一登录 (SSO) 提供的服务，可以跨本地、网络和域边界来存储和传输加密的用户凭据。 在您创建某一传输适配器时，可以充分利用 SSO API 来处理该传输适配器用于访问后端应用程序的用户凭据。  
  
 通常需要不支持 SSO 的传输适配器来配置用于单组凭据，这些凭据用于访问后端应用程序。 对于许多后端系统而言，单个帐户身份验证可能无法满足所有的安全强制要求。 许多应用程序都根据正访问它们的用户提供不同的访问权限。 SSO 允许适配器基于正尝试访问它的用户动态选择用于终结点的凭据。  
  
## <a name="how-send-adapters-work-with-sso"></a>发送适配器如何与 SSO 一起工作  
 支持 SSO 的适配器验证和兑换该票证并使用从 SSO 系统中获取用户凭据发送**ISSOTicket.ValidateAndRedeemTicket** API。 该适配器使用获取的凭据对目标终结点进行身份验证。  
  
 下面的代码段演示了发送适配器如何从 SSO 系统获取用户凭据：  
  
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
  
## <a name="party-resolution"></a>参与方解析  
 参与方解析管道组件负责将发件人证书或发件人安全标识符 (SID) 映射到相应的已配置 BizTalk Server 参与方。 具有此信息提供给他们的适配器应设置两个系统消息上下文属性**WindowsUser**和**SignatureCertificate**，可供下游方解析如果配置的组件。  
  
 **WindowsUser**以域用户的发件人，例如 redmond\myBtsUser 填充属性。 **SignatureCertificate**以客户端身份验证证书的指纹填充属性。  
  
## <a name="managing-passwords"></a>管理密码  
 如果您将凭据直接放置于某一终结点的属性中，则在您需要导出绑定文件时密码字段的内容将被清除。 这将要求您的用户以管理员的身份重新输入密码。 可以通过将 SSO 用于凭据来避免此问题。