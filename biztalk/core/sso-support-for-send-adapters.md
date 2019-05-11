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
# <a name="sso-support-for-send-adapters"></a>发送适配器的 SSO 支持
企业单一登录 (SSO) 提供的服务来存储和传输加密用户凭据跨本地、 网络和域边界。 创建传输适配器时，您可以利用 SSO Api 来处理传输适配器用于访问后端应用程序的用户凭据。  
  
 通常需要使用一组凭据用于访问后端应用程序所使用的配置不支持 SSO 的传输适配器。 对于许多后端系统，单个帐户身份验证可能无法满足所有的安全强制要求。 许多应用程序提供不同的访问权限，具体取决于正访问它们的用户。 SSO 允许适配器能够动态选择要使用的用户尝试访问它所基于的终结点的凭据。  
  
## <a name="how-send-adapters-work-with-sso"></a>如何发送适配器与 SSO 一起工作  
 发送适配器支持 SSO 的验证和兑换票证并使用从 SSO 系统获取用户凭据**ISSOTicket.ValidateAndRedeemTicket** API。 适配器使用获取的凭据进行身份验证的目标终结点。  
  
 下面的代码段演示了如何发送适配器将从 SSO 系统获取用户凭据：  
  
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
 参与方解析管道组件负责将发件人证书或发件人安全标识符 (SID) 映射到相应的已配置 BizTalk Server 参与方。 具有此信息提供给他们的适配器应设置两个系统消息上下文属性**WindowsUser**并**SignatureCertificate**，以供下游的参与方解析如果配置的组件。  
  
 **WindowsUser**发件人，例如 redmond\myBtsUser 的域用户填充属性。 **SignatureCertificate**客户端身份验证证书的指纹填充属性。  
  
## <a name="managing-passwords"></a>管理密码  
 如果凭据直接置于终结点的属性，密码字段将被留空时您需要导出绑定文件。 这将要求你重新输入密码以管理员身份的用户。 可以通过将 SSO 用于凭据来避免此问题。