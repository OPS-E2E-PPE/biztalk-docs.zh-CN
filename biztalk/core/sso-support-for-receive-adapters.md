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
# <a name="sso-support-for-receive-adapters"></a>接收适配器的 SSO 支持
使用企业单一登录 (SSO) 提供的服务，可以跨本地、网络和域边界来存储和传输加密的用户凭据。 传输适配器编写人员可以利用 SSO API 来处理传输适配器用于访问后端应用程序的用户凭据。  
  
 通常需要不支持 SSO 的传输适配器来配置用于单组凭据，这些凭据用于访问后端应用程序。 对于许多后端系统而言，单个帐户身份验证可能无法满足所有的安全强制要求。 许多应用程序都根据正访问它们的用户提供不同的访问权限。 SSO 允许适配器基于正尝试访问它的用户动态选择用于终结点的凭据。  
  
## <a name="how-receive-adapters-work-with-sso"></a>接收适配器如何与 SSO 一起工作  
 支持 SSO 的接收适配器在接收消息后、但在将消息发布到 BizTalk Server 前将执行以下步骤：  
  
1. 适配器将模拟发件人，并使用获取 SSO 票证代表发件人**ISSOTicket.IssueTicket** API。  
  
2. 在成功获取某一 SSO 票证后，该适配器会将该票证存储于系统命名空间下的消息上下文属性“SSOTicket”中。  
  
   下面的代码示例演示如何获取票证以及如何将票证存储于消息上下文中。  
  
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
  
## <a name="party-resolution"></a>参与方解析  
 参与方解析管道组件负责将发件人证书或发件人安全标识符 (SID) 映射到相应的已配置 BizTalk Server 参与方。 具有此信息提供给他们的适配器应设置两个系统消息上下文属性**WindowsUser**并**SignatureCertificate**，以供下游的参与方解析如果配置的组件。  
  
 **WindowsUser**发件人，例如 redmond\myBtsUser 的域用户填充属性。 **SignatureCertificate**客户端身份验证证书的指纹填充属性。  
  
## <a name="managing-passwords"></a>管理密码  
 如果您将凭据直接放置于某一终结点的属性中，则在您需要导出绑定文件时密码字段的内容将被清除。 这将要求您的用户以管理员的身份重新输入密码。 可以通过将 SSO 用于凭据来避免此问题。  
  
 如果适配器终结点都有**密码**属性，请注意，以明文形式在 SSO 配置存储数据库中存储的实际值。 这与密码在用户界面中以“*”形式显示的情况不同。 此属性也通过网络传输，并且使用 BizTalk Server 示例 ExplorerOM 的简单脚本就能够读取它。