---
title: 企业单一登录概述 |Microsoft Docs
description: 阅读有关在 BizTalk Server 中使用 SSO 票证处理消息和 adminster SSO 的 affilicate 应用程序
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
ms.openlocfilehash: 4635e63f96aa075340e8e53380432e0efdfbdb59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389057"
---
# <a name="enterprise-single-sign-on-overview"></a>企业单一登录概述
依赖于多个不同的应用程序的业务流程可能需要跨多个不同的安全域。 访问 Microsoft Windows 系统上的应用程序可能需要一组安全凭据，而访问 IBM 大型机上的应用程序可能需要不同的凭据，例如 RACF 用户名和密码。 处理此而言并非易事的凭据是对于用户而言，它可以是自动化的过程更加困难。 若要解决此问题，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含企业单一登录。  
  
 不会混淆，这不是一种机制，允许用户一次登录的所有应用程序。 相反，企业单一登录提供了一种方法将映射到非 Windows 用户凭据的 Windows 用户 ID。 不能解决所有组织的企业单一登录问题，但此服务可进一步简化为不同系统使用应用程序的业务流程的操作。  
  
## <a name="create-affiliate-application-for-non-windows-systems"></a>创建关联应用程序的非 Windows 系统  
 若要使用企业单一登录，管理员需要定义关联应用程序，其中每个表示非 Windows 系统或应用程序。 例如，关联应用程序可能是软件的在 IBM 大型机，Unix 或任何其他类型上运行的 SAP ERP 系统上运行的 CICS 应用程序。 每个这些应用程序都有其自身的机制进行身份验证，并因此每个都需要其自己唯一的凭据。  
  
 企业单一登录将用户的 Windows 用户 ID 和他的凭据之间的加密的映射存储一个或多个关联应用程序在 SSO 数据库。 当此用户需要访问关联应用程序时，可以通过单一登录 (SSO) 服务器查找在 SSO 数据库中为该应用程序的凭据。 下图显示了这的工作原理。  
  
 ![](../core/media/understandingbts-11-esso.gif "UnderstandingBTS_11_ESSO")  
  
 在此示例中，某些应用程序对 BizTalk Server 发送的消息处理由业务流程，然后发送到关联应用程序在 IBM 大型机上运行。 企业单一登录工作是确保传递到关联应用程序时，将正确的凭据 （即，正确的用户名和密码） 发送消息。  
  
## <a name="message-processing-with-an-sso-ticket"></a>使用 SSO 票证消息处理  
 如图所示，当接收适配器收到消息时，适配器可以请求一个 SSO 票证从 SSO 服务器 A （步骤 1）。 此加密的票证包含发出请求和超时期限的用户的 Windows 标识。 (不要将此 Kerberos 票证相混淆，它不是相同的操作。)获取该票证后，它是作为属性添加到传入的消息。 然后，该消息进行常规处理通过 BizTalk Server 引擎，在此示例中这意味着它由业务流程处理。 当此业务流程生成传出消息时，该消息还包含前面获取的 SSO 票证。  
  
 此新消息发送到在 IBM 大型机上运行的应用程序，因此它必须包含此用户访问该应用程序的相应凭据。 若要获取这些凭据，发送适配器联系人 SSO 服务器 B （步骤 2）、 提供的消息 （其中包含 SSO 票证） 刚刚收到和关联应用程序的名称正在尝试进行检索的凭据。 此操作称为兑现，会导致 SSO 服务器 B 将验证 SSO 票证，然后查找该应用程序 （步骤 3） 的此用户的凭据。 SSO 服务器 B 将这些凭据返回到发送适配器发送适配器 （步骤 4），使用它们来将相应地进行身份验证的消息发送到关联应用程序 （步骤 5）。  
  
## <a name="administering-sso"></a>管理 SSO  
 企业单一登录还包括管理工具执行各种操作。 SSO 数据库执行的所有操作进行都审核，例如，以便提供工具，可让管理员可以监视这些操作并设置不同的审核级别。 其他工具允许管理员禁用特定的关联应用程序、 打开和关闭单独的映射是用户，以及执行其他功能。 此外，还有一个客户端实用程序，允许最终用户配置其自己的凭据和映射。 和 BizTalk Server 的其他部分，如企业单一登录公开其服务通过可编程 API。 第三方 BizTalk Server 适配器的创建者使用此 API 访问单一登录服务，并且管理员可以使用它来创建自动执行常见任务的脚本。  
  
 上面所述的示例显示了典型用法的企业单一登录，但可以用其他方式配置 SSO。 例如，较小的 BizTalk Server 安装可能会产生只有一台 SSO 服务器，并可以为企业单一登录独立使用从 BizTalk Server 引擎。 （该技术也会随 Microsoft Host Integration Server。）  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 消息引擎](../core/the-biztalk-server-messaging-engine.md)   
 [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)
