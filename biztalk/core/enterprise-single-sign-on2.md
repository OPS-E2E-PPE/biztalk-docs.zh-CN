---
title: 企业单一登录概述 |Microsoft 文档
description: 了解在 BizTalk Server 中使用 SSO 票证与处理消息和 adminster SSO 的 affilicate 应用程序
ms.custom: ''
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2aaab59-8cf7-4848-b71a-e7c8682dd3bd
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f242e11e31de957fee0c6cbf228094f7e40010d
ms.sourcegitcommit: 5e6ef63416e8885a5ee91bd65618a842b3a0cc54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2017
ms.locfileid: "23129694"
---
# <a name="enterprise-single-sign-on-overview"></a>企业单一登录概述
依赖于多个不同应用程序的业务流程可能要涉及多个不同的安全域。 访问 Microsoft Windows 系统中的应用程序可能需要一组安全凭据，而访问 IBM 大型机中的应用程序则可能需要不同的凭据，例如 RACF 用户名和密码。 处理如此多的凭据对于用户而言并非易事，而对于自动化流程来说，这会更加困难。 为解决此问题，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括了企业单一登录。  
  
 请不要混淆，企业单一登录不是指供用户一次登录所有应用程序的机制。 实际上，使用企业单一登录可将 Windows 用户 ID 映射到非 Windows 用户凭据。 这不能解决组织中所有的企业登录问题，但对于使用不同系统的应用程序的业务流程，此服务可简化这些问题。  
  
## <a name="create-affiliate-application-for-non-windows-systems"></a>创建非 Windows 系统的关联应用程序  
 若要使用企业单一登录，管理员需要定义关联应用程序，每个关联应用程序均代表一个非 Windows 系统或应用程序。 例如，关联应用程序可能是在 IBM 大型机上运行的 CICS 应用程序、在 Unix 上运行的 SAP ERP 系统或任何其他类型的软件。 以上每种应用程序都拥有自己的验证机制，因此它们也都需要自己的唯一凭据。  
  
 企业单一登录将用户的 Windows 用户 ID 与该用户的一个或多个关联应用程序的凭据之间的加密映射存储在 SSO 数据库中。 当该用户需要访问某关联应用程序时，单一登录 (SSO) 服务器将在 SSO 数据库中查找此应用程序的凭证。 下图显示了具体过程：  
  
 ![](../core/media/understandingbts-11-esso.gif "UnderstandingBTS_11_ESSO")  
  
 在此示例中，某些应用程序发送到 BizTalk Server 的消息由业务流程进行处理，然后发送给在 IBM 大型机上运行的关联应用程序。 企业单一登录的作用是确保在消息传递到关联应用程序时该消息中包含正确凭据（即正确的用户名和密码）。  
  
## <a name="message-processing-with-an-sso-ticket"></a>使用 SSO 票证处理消息  
 如图所示，在接收适配器收到消息时，该适配器可以从 SSO 服务器 A 请求 SSO 票证（步骤 1）。 此加密的票证包含发出请求的用户的 Windows 标识和超时期。 （请不要将此票证与 Kerberos 票证相混淆，这两种票证是不同的。）在获取该票证后，会将其作为属性添加到传入消息中。 然后，通过 BizTalk Server 引擎对该消息进行常规处理，在本示例中是指由业务流程进行处理。 在此业务流程生成传出消息后，该消息中还包含先前获得的 SSO 票证。  
  
 由于此新建消息的目标应用程序在 IBM 大型机上运行，因此其中必须包含此用户访问该应用程序所需的相应凭据。 为获得这些凭据，发送适配器将与 SSO 服务器 B 进行联系（步骤 2），提供刚刚收到的消息（其中包含 SSO 票证）以及尝试检索其凭据的关联应用程序的名称。 此操作称为兑现，在执行后，SSO 服务器 B 将验证 SSO 票证，然后查找此用户对该关联应用程序的凭据（步骤 3）。 SSO 服务器 B 将这些凭据返回到发送适配器（步骤 4），发送适配器再使用这些凭据将正确验证的消息发送到关联应用程序（步骤 5）。  
  
## <a name="administering-sso"></a>管理 SSO  
 企业单一登录还包括可执行各种操作的管理工具。 例如，对 SSO 数据库执行的所有操作都需要进行审核，因此管理员可以通过提供的工具来监视这些操作并设置不同的审核级别。 管理员还可以利用其他工具来禁用特定的关联应用程序，为用户打开和关闭单独的映射以及实现其他功能。 此外，最终用户也可使用客户端实用工具配置自己的凭据和映射。 与 BizTalk Server 的其他组件一样，企业单一登录可以通过可编程 API 公开其服务。 第三方 BizTalk Server 适配器的创建者可使用此 API 访问单一登录服务，管理员则可使用它来创建自动执行常规任务的脚本。  
  
 以上示例显示了企业单一登录的典型用法，但 SSO 还可以通过其他方式进行配置。 例如，如果 BizTalk Server 安装较小，则可能只需要一台 SSO 服务器，与 BizTalk Server 引擎分开使用企业单一登录。 （Microsoft Host Integration Server 也提供了这种技术。）  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server Messaging Engine](../core/the-biztalk-server-messaging-engine.md)   
 [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)
