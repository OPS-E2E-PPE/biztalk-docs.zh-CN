---
title: 了解 SSO |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- Windows Integrated Single Sign-On
- Extranet Single Sign-On (Web SSO)
- Server-Based Intranet Single Sign-On
ms.assetid: 03f78a7b-4880-408f-9733-d07e19775d21
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736fee720f2abf0dd051b1f754dd0fd6b8c42ab6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286981"
---
# <a name="understanding-sso"></a>了解 SSO
若要了解企业单一登录，最好今天查看上单一登录服务可用的三种类型： Windows 集成的 extranet 和 intranet。 下面对这三种类型进行了说明，其中将企业单一登录归为第三个类别。  
  
## <a name="windows-integrated-single-sign-on"></a>Windows 集成单一登录  
 通过这些服务，您可以连接到网络中使用通用验证机制的多个应用程序。 在您登录到网络后，这些服务将请求并验证您的凭据，并使用这些凭据来基于用户权限确定您可以执行的操作。 例如，如果应用程序使用 Kerberos 进行集成，则在系统对用户凭据进行验证后，您可以访问网络中与 Kerberos 集成的任何资源。  
  
## <a name="extranet-single-sign-on-web-sso"></a>Extranet 单一登录 (Web SSO)  
 通过这些服务，您可以使用单独的一组用户凭据来通过 Internet 访问资源。 用户提供一组凭据以登录到属于不同组织的不同网站。 此类单一登录的一个示例是基于使用者的应用程序的 Windows Live ID。 对于联合方案，Microsoft Active Directory 联合服务将启用 Web SSO。  
  
## <a name="server-based-intranet-single-sign-on"></a>基于服务器的 Intranet 单一登录  
 通过这些服务，您可以在企业环境内集成多个不同类型的应用程序和系统。 这些应用程序和系统可能不使用通用的验证机制。 每个应用程序都具有其自己的用户目录存储区。 例如，在某个组织中，Windows 使用 Active Directory 目录服务来对用户进行验证，而大型机则使用 IBM 的资源访问控制工具 (RACF) 来验证相同的用户。 在该企业中，中间件应用程序将前端应用程序和后端应用程序集成在一起。 通过企业单一登录，该企业内的用户可以在仅使用一组凭据的情况下同时连接到前端和后端。 使用企业单一登录，Windows 启动的单一登录（其中的初始请求是从 Windows 域环境中生成的）和主机启动的单一登录（其中的初始请求是从非 Windows 域环境中生成的）都可以访问 Windows 域中的资源。  
  
 此外，**密码同步**，来简化管理 SSO 数据库中，并保留密码跨用户目录同步。 此功能是通过使用密码同步适配器实现的，您可以使用密码同步工具配置和管理这些适配器。  
  
## <a name="the-enterprise-single-sign-on-system"></a>企业单一登录系统  
 使用企业单一登录 (SSO) 提供的服务，可以跨本地和网络边界（包括域边界）存储和传输加密的用户凭据。 SSO 将凭据存储在 SSO 数据库中。 由于 SSO 提供了通用的单一登录解决方案，因此中间件应用程序和自定义适配器可以利用 SSO 来跨环境安全地存储和传输用户凭据。 最终用户不必为不同的应用程序记住不同的凭据。  
  
 单一登录系统由以下部分组成：SSO 数据库、主密钥服务器以及一个或多个单一登录服务器。  
  
 SSO 系统包含管理员定义的 关联应用程序 。 关联应用程序 是用于表示使用企业单一登录连接到的诸如主机、后端系统或业务应用程序之类的系统或子系统的逻辑实体。 每个关联应用程序都具有多个用户映射；例如，关联应用程序具有 Active Directory 中的用户凭据与其对应的 RACF 凭据之间的映射。  
  
 SSO 数据库是用于存储有关关联应用程序的信息以及用于所有关联应用程序的全部加密用户凭据的 SQL Server 数据库。  
  
 主密钥服务器 是存储主密钥的企业单一登录服务器。 系统中的其他所有单一登录服务器都从主密钥服务器中获取主密钥。  
  
 SSO 系统还包含一个或多个 SSO 服务器。 这些服务器在 Windows 凭据和后端凭据之间进行映射，并在 SSO 数据库中查找凭据，管理员可使用这些服务器来维护 SSO 系统。  
  
> [!NOTE]
>  在 SSO 系统中，只能包含一个主密钥服务器和一个 SSO 数据库。 SSO 数据库可以不位于主密钥服务器上。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SSO 用户组](../core/sso-user-groups.md)  
  
-   [SSO 组件](../core/sso-components.md)  
  
-   [SSO 服务器](../core/sso-server.md)  
  
-   [主密钥服务器](../core/master-secret-server.md)  
  
-   [SSO 关联应用程序](../core/sso-affiliate-applications.md)  
  
-   [SSO 映射](../core/sso-mappings.md)  
  
-   [SSO 票证](../core/sso-tickets.md)  
  
-   [配置 SSO](../core/configuring-sso.md)