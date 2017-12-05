---
title: "SSO Affiliate 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1621973fed0c7a87538e3ed18161f05c4c9cf9e6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="sso-affiliate-applications"></a>SSO 关联应用程序
企业单一登录 (SSO) 关联应用程序是用于表示使用 SSO 连接到的诸如主机、后端系统或业务应用程序之类的系统或子系统的逻辑实体。 关联应用程序可以表示诸如大型机或 UNIX 计算机之类的后端系统。 它还可以表示应用程序（如 SAP）或系统分支（如“福利待遇”子系统或“付款存根”子系统）。  
  
 当 SSO 管理员或 SSO 关联管理员定义关联应用程序时，还必须确定将管理关联应用程序的人员（应用程序管理员）、关联应用程序的用户（应用程序用户）以及 SSO 系统将用于对此关联应用程序的用户进行验证的参数（用户 ID、密码、PIN 号码等等）。 有关应用程序管理员和应用程序用户的详细信息，请参阅[SSO 用户组](../core/sso-user-groups.md)。  
  
## <a name="affiliate-application-types"></a>关联应用程序类型  
 企业 SSO 定义了几种不同的应用程序类型。 不同的应用程序类型支持 Windows 帐户与非 Windows 系统中帐户之间不同类型的映射。  
  
 这些应用程序类型包括：  
  
 **单个**单个应用程序支持的 Windows 帐户和非 Windows 帐户之间的一对一映射。 在“单项”类型的应用程序中，一个 Windows 帐户只映射到一个非 Windows 帐户。 为此应用程序设置的标志决定了可按哪个方向使用该映射，即从 Windows 帐户到非 Windows 帐户或从非 Windows 帐户到 Windows 帐户，或者同时双向使用该映射。 因此，“单项”应用程序可用于 Windows 启动的 SSO 或主机启动的 SSO，也可以同时用于这两种类型。  
  
 **组**组应用程序支持到一个单个的非 Windows 帐户的一个 Windows 组之间的映射。 使用 Application Users 帐户可以定义将用于此“组”应用程序的 Windows 组。 只能为“组”应用程序定义一个映射，并且该映射必须是 Windows 组与此 Windows 组的所有成员将用于访问非 Windows 系统的单个非 Windows 帐户之间的映射。 “组”应用程序只能用于 Windows 启动的 SSO。  
  
 **主机组**主机组应用程序从概念上讲是组应用程序的相反值。 “主机组”应用程序支持定义的一组非 Windows 帐户到单个 Windows 帐户之间的映射。 这些非 Windows 帐户使用的单个 Windows 帐户是由该应用程序的 Application Users 帐户定义的。 通过为每个非 Windows 帐户创建映射可定义允许访问此应用程序的非 Windows 帐户组。 “主机组”应用程序只能用于主机启动的 SSO。  
  
## <a name="designing-an-affiliate-application"></a>设计关联应用程序  
 在创建关联应用程序之前，SSO 关联管理员或 SSO 管理员必须做出以下决策：  
  
1.  **此关联应用程序将代表什么？** 您需要知道在 SSO 系统中该关联应用程序将表示的非 Windows 应用程序。 例如：  
  
     应用程序名称： APP1  
  
     描述： 支付存根 （stub） 部门的应用程序  
  
     联系人：administrator@companyname.com  
  
2.  **谁将管理此关联应用程序？** 您需要确定此关联应用程序的管理员。 这些管理员组成了此关联应用程序的 Windows Administrators 组。 例如，Domain\APP1AdminGroup  
  
3.  **谁将使用此关联应用程序？** 您需要确定此关联应用程序的最终用户。 这些用户表示此关联应用程序的 Windows 用户组；例如，Domain\DomainUsers。 对于付款存根的应用程序，您可能希望所有用户都能访问其付款存根信息，因此可将域用户组指定为此应用程序的用户组。  
  
4.  **什么凭据？ 关联应用程序使用其用户进行身份验证** 不同的应用程序使用不同的凭据来验证用户。 例如，某些应用程序可能使用用户 ID、密码、PIN 或这些项的组合。 还必须确定系统是否需要在用户提供这些凭据时将凭据屏蔽。  
  
5.  **将单独的映射或组映射对使用此关联应用程序？** 是否每个 Windows 用户在后端系统中都具有相应的帐户，或者后端系统具有一个用于所有 Windows 用户的帐户？ 在付款存根系统中，每个用户都使用其自己的帐户来访问其付款存根信息，因此需要使用单项映射。  
  
 创建关联应用程序后，将无法修改以下属性：  
  
-   关联应用程序的名称  
  
-   与关联应用程序关联的字段  
  
-   关联应用程序类型（主机组、单项或配置存储）  
  
-   与 Affiliate Administrators 组相同的管理帐户。 （如果选择此属性，则会将 Affiliate Administrators 组用作此关联应用程序的 Application Administrators 帐户。）  
  
## <a name="affiliate-application-properties"></a>关联应用程序属性  
 下表列出了需要为您创建的每个关联应用程序定义的属性：  
  
|属性|Description|  
|--------------|-----------------|  
|应用程序名称|关联应用程序的名称。 创建关联应用程序后，无法更改此属性|  
|Description|关联应用程序的简要描述|  
|联系人|用户可以联系的此关联应用程序的主要联系人。 （可以是电子邮件地址。）|  
|appUserAccount|Windows 组，包含将使用此关联应用程序的最终用户的用户帐户。|  
|appAdminAccount|Windows 组，包含将管理此关联应用程序的管理员帐户。 **注意：**不需要定义此属性，如果将 adminAccountSame 设置为是。|  
  
|应用程序标志|Description|  
|----------------------|-----------------|  
|enableApp|此关联应用程序的状态。|  
|groupApp|确定此应用程序是使用组映射（是）还是单项映射（否）。<br /><br /> 在创建应用程序后不能更改此属性。|  
|configStoreApp|确定此关联应用程序是否为配置存储类型的应用程序（“是”）。<br /><br /> 在创建应用程序后不能更改此属性。|  
|hostInitiatedSSO|如果关联应用程序为主机启动的 SSO 类型应用程序，则启用此项。 默认值是不可以。|  
|windowsInitiatedSSO|如果关联应用程序为 Windows 启动的 SSO 类型应用程序，则启用此项。 默认值为“是”。|  
|validatePassword|此项仅适用于主机启动的 SSO 应用程序。 应用程序尝试检索凭据时，必须提供 SSO 服务进行验证时所使用的 SSO 数据库密码。 默认值为“是”。|  
|disableCredCache|SSO 服务器将凭据存储在缓存中以加快访问速度。 默认值是不可以。|  
|allowTickets|确定 SSO 系统是否对此关联应用程序使用票证。<br /><br /> **安全**必须是 SSO 管理员才能设置此标志。|  
|validateTickets|确定 SSO 系统是否在用户兑换票证时验证这些票证。<br /><br /> **安全**必须是 SSO 管理员才能设置此标志。|  
|appTicketTimeOut|指定特定于关联应用程序的票证超时值。 只能在更新关联应用程序时设置此选项，而不能在创建关联应用程序时设置此选项。<br /><br /> 如果对此应用程序启用了票证，但未启用此属性，则将使用对 SSO 系统（全局）级别指定的超时值。<br /><br /> **安全**必须是 SSO 管理员才能设置此标志。|  
|timeoutTickets|确定票证是否有过期时间。 默认值为“是”。<br /><br /> **安全**是必需的除非不禁用票证超时 （否）。<br /><br /> **安全**必须是 SSO 管理员才能设置此标志。|  
|allowLocalAccounts|确定是否允许在 SSO 系统中使用本地组和帐户。 在单机情况下，只能将此标志配置为“是”。|  
|adminAccountSame|确定是否使用 SSO Affiliate Administrator 组作为 Application Administrator 组。<br /><br /> 在创建应用程序后不能更改此属性。<br /><br /> **安全**必须是 SSO 管理员或 SSO 关联管理员设置此标志。|  
  
|应用程序字段|Description|Description|  
|------------------------|-----------------|-----------------|  
|字段 [0]|\<*凭据*\>： 屏蔽/Unmasked|确定要连接到关联应用程序最终用户所必须提供的凭据的类型（用户 ID、密码和智能卡），以及是否屏蔽此凭据（即是否在屏幕中显示用户键入的字符）。<br /><br /> 可以输入与关联应用程序凭据数相同数量的字段，但第一个字段必须为用户 ID。<br /><br /> 在创建应用程序后不能更改此属性。|  
  
## <a name="see-also"></a>另请参阅  
 [管理关联应用程序](../core/managing-affiliate-applications.md)   
 [SSO 映射](../core/sso-mappings.md)   
 [管理用户映射](../core/managing-user-mappings.md)