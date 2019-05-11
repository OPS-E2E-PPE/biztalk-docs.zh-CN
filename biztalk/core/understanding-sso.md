---
title: 了解 SSO |Microsoft Docs
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
ms.openlocfilehash: 7c8d312c008159d5eebede8e65909b5fef9ce442
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292732"
---
# <a name="understanding-sso"></a>了解 SSO
若要了解企业单一登录，最好立即查看三种类型的单一登录服务可用：Windows 集成、 extranet 和 intranet。 这些如下所述，使用企业单一登录归为第三个类别。  
  
## <a name="windows-integrated-single-sign-on"></a>Windows 集成单一登录  
 这些服务，你可以连接到多个网络中使用的应用程序的常见身份验证机制。 这些服务请求，并登录到网络，并使用你的凭据来确定可以执行的操作根据你的用户权限后，验证你的凭据。 例如，如果应用程序集成后系统对你的用户凭据进行身份验证使用 Kerberos，您可以访问与 Kerberos 集成的网络中的任何资源。  
  
## <a name="extranet-single-sign-on-web-sso"></a>Extranet 单一登录 (Web SSO)  
 这些服务，可通过使用一组用户凭据通过 Internet 访问资源。 用户提供的凭据登录到属于不同组织的不同网站上的一组。 此类型的单一登录的一个示例是基于应用程序的使用者的 Windows Live ID。 对于联合方案，Microsoft Active Directory 联合身份验证服务启用 Web SSO。  
  
## <a name="server-based-intranet-single-sign-on"></a>基于服务器的 Intranet 单一登录  
 这些服务，您将多个异类应用程序和企业环境中的系统进行集成。 这些应用程序和系统不能使用常见的身份验证。 每个应用程序都有其自己的用户目录存储。 例如，在组织中，Windows 使用 Active Directory 目录服务进行身份验证的用户，而大型机则使用 IBM 的资源的访问控制工具 (RACF) 相同的用户进行身份验证。 在企业内中间件应用程序集成的前端和后端应用程序。 企业单一登录可使企业中用户只使用一组凭据的同时连接到前端和后端。 它允许 Windows 启动的单一登录 （在其中的初始请求执行从 Windows 域环境） 和主机启动的单一登录 （在其中的初始请求执行在非 Windows 域环境中） 来访问中的资源Windows 域。  
  
 此外，**密码同步**简化了管理 SSO 数据库中，并保留密码各个用户目录间保持同步。 这是通过使用密码同步适配器，你可以配置和使用密码同步工具进行管理。  
  
## <a name="the-enterprise-single-sign-on-system"></a>企业单一登录系统  
 企业单一登录 (SSO) 提供的服务来存储和传输加密用户凭据跨本地和网络边界，其中包括域边界。 SSO 将凭据存储在 SSO 数据库中。 由于 SSO 提供了一个泛型单一登录解决方案，中间件应用程序和自定义适配器可以利用 SSO 来安全地存储和传输整个环境的用户凭据。 最终用户无需记住的不同应用程序不同的凭据。  
  
 单一登录系统包含 SSO 数据库、 主密钥服务器和一个或多个单一登录服务器。  
  
 SSO 系统包含管理员定义的关联应用程序。 关联应用程序是表示系统或如主机、 后端系统或业务线应用程序的子系统的逻辑实体连接到使用企业单一登录。 每个关联应用程序具有多个用户映射;例如，它具有在 Active Directory 中用户的凭据和其对应的 RACF 凭据之间的映射。  
  
 SSO 数据库是存储有关关联应用程序，以及所有关联应用程序的所有加密的用户凭据的信息的 SQL Server 数据库。  
  
 主密钥服务器是存储主密钥的企业单一登录服务器。 中的所有其他单一登录服务器系统从主密钥服务器获取主密钥。  
  
 SSO 系统还包含一个或多个 SSO 服务器。 这些服务器之间进行映射的 Windows 和后端凭据，查找在 SSO 数据库中，凭据和管理员可使用这些来维护 SSO 系统。  
  
> [!NOTE]
>  SSO 系统中，可以有一个主密钥服务器和一个 SSO 数据库。 SSO 数据库可以是远程连接到主密钥服务器。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SSO 用户组](../core/sso-user-groups.md)  
  
-   [SSO 组件](../core/sso-components.md)  
  
-   [SSO 服务器](../core/sso-server.md)  
  
-   [主密钥服务器](../core/master-secret-server.md)  
  
-   [SSO 关联应用程序](../core/sso-affiliate-applications.md)  
  
-   [SSO 映射](../core/sso-mappings.md)  
  
-   [SSO 票证](../core/sso-tickets.md)  
  
-   [配置 SSO](../core/configuring-sso.md)