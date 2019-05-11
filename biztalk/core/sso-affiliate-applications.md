---
title: SSO 关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, designing applications
- applications [SSO], application types
- SSO, application types
- SSO, application properties
- applications [SSO], properties
- applications [SSO]
- SSO, applications
- applications [SSO], designing
ms.assetid: 002ecf7e-4d52-425a-9498-0e7bd6545047
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fad1ec2dd92364934481d47e34d720422ade099
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401776"
---
# <a name="sso-affiliate-applications"></a>SSO 关联应用程序
企业单一登录 (SSO) 关联应用程序是代表系统或如主机、 后端系统或业务线应用程序的子系统的逻辑实体连接到使用 SSO。 关联应用程序可以表示诸如大型机或 UNIX 计算机之类的后端系统。 它还可以表示 （如 SAP) 的应用程序或系统，如"福利"的一个分支，或"付款存根"子系统。  
  
 当 SSO 管理员或 SSO 关联管理员定义关联应用程序时，它们还必须确定谁将管理关联应用程序 （应用程序管理员）、 关联应用程序的用户的身份 (应用程序的用户） 和 SSO 系统将使用此用户进行身份验证的参数关联应用程序 （用户 ID、 密码、 PIN 号码等）。 有关应用程序管理员和应用程序用户的详细信息，请参阅[SSO 用户组](../core/sso-user-groups.md)。  
  
## <a name="affiliate-application-types"></a>关联应用程序类型  
 企业 SSO 定义了多种不同的应用程序类型。 不同的应用程序类型支持非 Windows 系统上的不同类型的 Windows 帐户和帐户之间的映射。  
  
 应用程序类型包括：  
  
 **单个**单个应用程序支持的 Windows 帐户和非 Windows 帐户之间的一对一映射。 在各个类型的应用程序，一个 Windows 帐户被映射到其中一个，且仅有一个非 Windows 帐户。 可以在任一方向，从 Windows 到非 Windows，或从非 Windows Windows，或两者，具体取决于已设置为此应用程序的标志中使用的映射。 因此，单个应用程序不能用于 Windows 启动的 SSO，主机启动的 SSO，或两者。  
  
 **组**组应用程序支持一个 Windows 组到单个非 Windows 帐户之间的映射。 应用程序用户帐户用于定义将用于此组应用程序的 Windows 组。 只有一个映射可以定义组应用程序，并且该映射必须是 Windows 组与此 Windows 组的所有成员将都用于访问非 Windows 系统的单个非 Windows 帐户之间。 组应用程序可能仅用于 Windows 启动的 SSO。  
  
 **主机组**主机组应用程序在概念上正好相反的组应用程序。 它们支持一组定义的非 Windows 帐户添加到单个 Windows 帐户之间的映射。 由应用程序的应用程序用户帐户定义将由非 Windows 帐户的单个 Windows 帐户。 通过创建每个非 Windows 帐户的映射定义允许访问此应用程序的非 Windows 帐户的组。 主机组应用程序只能用于主机启动的 SSO。  
  
## <a name="designing-an-affiliate-application"></a>设计关联应用程序  
 在创建关联应用程序之前, SSO 关联管理员或 SSO 管理员必须做出以下决策：  
  
1. **此关联应用程序将代表什么？** 您需要知道关联应用程序将表示在 SSO 系统中的非 Windows 应用程序。 例如，  
  
    应用程序名称：APP1  
  
    说明:付款存根 （stub） 部门的应用程序  
  
    请联系： administrator@companyname.com  
  
2. **谁将管理此关联应用程序？** 您需要确定此关联应用程序的管理员。 这些构成此关联应用程序的 Windows 管理员组。 例如，Domain\APP1AdminGroup  
  
3. **谁将使用此关联应用程序？** 您需要确定的最终用户此关联应用程序。 这些用户表示此关联应用程序的 Windows 用户组例如，Domain\DomainUsers。 如果付款存根是应用程序，您可能希望所有用户访问其付款存根信息，以便为此应用程序的用户组指定的域用户组。  
  
4. **将哪些凭据会关联应用程序使用其用户进行身份验证？** 不同的应用程序使用不同的凭据进行身份验证的用户。 例如，某些应用程序可能使用用户 Id、 密码、 Pin 或这些项的组合。 您还必须确定系统是否需要为用户提供屏蔽这些凭据。  
  
5. **将使用单项映射还是组映射此关联应用程序？** 每个 Windows 用户帐户在具有后端系统，或后端系统是否具有一个为所有 Windows 用户帐户？ 对于付款存根系统中，每个用户具有其自己的帐户来访问其付款存根信息，并需要使用单项映射。  
  
   创建关联应用程序后，无法修改以下属性：  
  
-   关联应用程序的名称  
  
-   与关联应用程序关联的字段  
  
-   关联应用程序类型 （主机组、 单项或配置存储区）  
  
-   相同与 affiliate administrators 组的管理帐户。 （如果选择此属性，然后 affiliate administrators 组使用应用程序管理员帐户作为此关联应用程序。）  
  
## <a name="affiliate-application-properties"></a>关联应用程序属性  
 下表列出了需要为你创建每个关联应用程序定义的属性。  
  
|属性|Description|  
|--------------|-----------------|  
|应用程序名称|关联应用程序的名称。 在创建关联应用程序后，您不能更改此属性|  
|Description|关联应用程序的简短说明|  
|请联系|用户可以使用此关联应用程序主要联系人。 （可以是电子邮件地址。）|  
|appUserAccount|包含将使用此关联应用程序的最终用户的用户帐户的 Windows 组|  
|appAdminAccount|包含将管理此关联应用程序的管理员帐户的 Windows 组。 **注意：** 不需要定义此属性，如果将 adminAccountSame 设置为是。|  
  
|应用程序标志|Description|  
|----------------------|-----------------|  
|enableApp|此关联应用程序的状态。|  
|groupApp|确定此应用程序使用组映射 （是） 还是单项映射 （否）。<br /><br /> 创建应用程序后，不能更改此属性。|  
|configStoreApp|确定此关联应用程序是否配置存储区类型的应用程序 （是）。<br /><br /> 创建应用程序后，不能更改此属性。|  
|hostInitiatedSSO|如果主机启动的 SSO 类型应用程序，请启用此选项。 默认值是不可以。|  
|windowsInitiatedSSO|如果它是 Windows 启动的 SSO 类型应用程序，请启用此选项。 默认值为是。|  
|validatePassword|这仅适用于主机启动的 SSO 应用程序。 当应用程序尝试检索凭据时，它必须提供用于验证由 SSO 服务的 SSO 数据库中的密码。 默认值为是。|  
|disableCredCache|SSO 服务器将凭据存储在缓存中以加快访问速度。 默认值是不可以。|  
|allowTickets|确定 SSO 系统是否对此关联应用程序使用票证。<br /><br /> **安全**必须是 SSO 管理员才能设置此标志。|  
|validateTickets|确定是否在 SSO 系统票证时验证用户兑换其。<br /><br /> **安全**必须是 SSO 管理员才能设置此标志。|  
|appTicketTimeOut|指定特定于关联应用程序的票证超时值。 这可以设置仅在更新关联应用程序，不能在创建它时。<br /><br /> 如果为此应用程序启用了票证，并且此属性不是，在 SSO 系统 （全局） 指定的超时值使用级别。<br /><br /> **安全**必须是 SSO 管理员才能设置此标志。|  
|timeoutTickets|确定票证是否有过期时间。 默认值为是。<br /><br /> **安全**除非必需，否则不要禁用票证超时 （否）。<br /><br /> **安全**必须是 SSO 管理员才能设置此标志。|  
|allowLocalAccounts|确定是否允许使用本地组和帐户在 SSO 系统中。 只能在单计算机方案中配置为是此标志。|  
|adminAccountSame|确定是否使用 SSO affiliate administrator 组作为 application administrator 组。<br /><br /> 创建应用程序后，不能更改此属性。<br /><br /> **安全**必须是 SSO 管理员或 SSO 关联管理员才能设置此标志。|  
  
|应用程序字段|Description|Description|  
|------------------------|-----------------|-----------------|  
|字段 [0]|\<*凭据*\>:屏蔽/未掩码|确定最终用户要连接到关联应用程序，必须提供的凭据 （用户 ID、 密码、 智能卡） 的类型以及是否屏蔽此凭据 (即，是否在屏幕上显示该用户类型的字符) 或不。<br /><br /> 您可以输入任意数量的字段没有凭据的关联应用程序，但第一个字段必须是用户 id。<br /><br /> 创建应用程序后，不能更改此属性。|  
  
## <a name="see-also"></a>请参阅  
 [管理关联应用程序](../core/managing-affiliate-applications.md)   
 [SSO 映射](../core/sso-mappings.md)   
 [管理用户映射](../core/managing-user-mappings.md)