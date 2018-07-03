---
title: 标准 SSO 安装选项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, installing
ms.assetid: 59aeb503-f369-4145-8a3c-ab60e9ed31a8
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a734114bb6d89c73b275e1060719c6b2cb638566
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981718"
---
# <a name="standard-sso-installation-options"></a>标准 SSO 安装选项
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 利用安全地存储凭据的企业单一登录 (SSO) 功能，以启用单一登录方案。  
  
 BizTalk Server 也可使用 SSO 来安全地存储适配器的自定义配置数据。 为此，BizTalk Server 运行时和管理功能需要将 SSO 安装为依存功能。 默认情况下，安装 BizTalk Server 时会安装企业 SSO。  
  
> [!NOTE]
>  安装企业单一登录（服务器组件）时，需要相应地进行配置。 安装 SSO 系统的第一步是配置主密钥服务器。 建议设置独立的主密钥服务器。 只需从 BizTalk Server 安装程序的自定义功能树中选择“企业单一登录”即可实现此目的。  
>   
>  同时还建议运行企业单一登录的所有计算机都要运行时间同步服务。 这可以确保计算机时间与系统中其他计算机的时间保持同步，这一点对于 SSO 票证服务的正常运行是非常必要的。  
  
 **安装选项的列表**： 运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。 选择**自定义安装**，然后从以下列表中选择相应的选项：  
  
- **企业单一登录管理 ―** 映射并连接到企业单一登录服务用于管理和客户端工具。  
  
- **企业单一登录主密钥服务器 ―** 充当 SSO 系统中的主密钥服务器。 这是 SSO 系统中需要部署的第一个服务器，使用该服务器可创建 SSO 数据库。  
  
  完成安装后，您还可以使用“添加或删除程序”实用工具添加以下项：  
  
- **服务器运行时 ―** 核心服务，以启用单一登录，并安全地存储/访问配置数据。  
  
- **企业单一登录管理 ―** 映射并连接到企业单一登录服务用于管理和客户端工具。  
  
- **企业单一登录服务与密码同步 ―** 服务以启用企业 SSO 系统中的密码同步功能。 这些服务也与 Microsoft 密码更改通知服务相集成。 安装核心的企业单一登录服务之后，就可以通过 BizTalk Server 包安装企业 SSO 的密码同步功能了，方法是启动 \Platform\SSO\Setup.exe，然后选择密码同步功能。  
  
- **软件开发工具包**编程和参考信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何安装 SSO 管理组件](../core/how-to-install-the-sso-administration-component.md)  
  
-   [如何安装 SSO 客户端实用工具](../core/how-to-install-the-sso-client-utility.md)