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
ms.openlocfilehash: edfd57afb1eba520c6ae0211cbb6bc0e90922d59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398978"
---
# <a name="sso-support-for-receive-adapters"></a>接收适配器的 SSO 支持
企业单一登录 (SSO) 提供的服务来存储和传输加密用户凭据跨本地、 网络和域边界。 传输适配器编写人员可以利用 SSO Api 来处理传输适配器用于访问后端应用程序的用户凭据。  
  
 通常需要使用一组凭据用于访问后端应用程序所使用的配置不支持 SSO 的传输适配器。 对于许多后端系统，单个帐户身份验证可能无法满足所有的安全强制要求。 许多应用程序提供不同的访问权限，具体取决于正访问它们的用户。 SSO 允许适配器能够动态选择要使用的用户尝试访问它所基于的终结点的凭据。  
  
## <a name="how-receive-adapters-work-with-sso"></a>接收适配器与 SSO 一起工作的方式  
 接收适配器接收消息之后、 之前将其发布到 BizTalk Server SSO 支持，执行以下步骤：  
  
1. 适配器将模拟发件人，并使用获取 SSO 票证代表发件人**ISSOTicket.IssueTicket** API。  
  
2. 已成功获取 SSO 票证后，适配器将其存储在系统命名空间下的消息上下文属性"SSOTicket"。  
  
   下面的代码片段演示如何获取票证以及消息上下文上的存储方式。  
  
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
 如果凭据直接置于终结点的属性，密码字段将被留空时您需要导出绑定文件。 这将要求你重新输入密码以管理员身份的用户。 可以通过将 SSO 用于凭据来避免此问题。  
  
 如果适配器终结点都有**密码**属性，请注意，以明文形式在 SSO 配置存储数据库中存储的实际值。 这是尽管它作为用户界面中显示"*"。 此属性还会通过网络传输和使用 BizTalk Server 示例 ExplorerOM 的简单脚本将能够读取它。