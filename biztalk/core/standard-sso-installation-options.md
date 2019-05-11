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
ms.openlocfilehash: 61cbba3615048b8028f5daebcadd8a649afb0f16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392995"
---
# <a name="standard-sso-installation-options"></a>标准 SSO 安装选项
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 利用安全地存储凭据的企业单一登录 (SSO) 功能，以启用单一登录方案。  
  
 BizTalk Server 还使用 SSO 来安全地存储适配器的自定义配置数据。 若要执行此操作，BizTalk Server 运行时和管理功能安装为依存功能的 SSO。 BizTalk Server 的默认安装时会安装企业 SSO。  
  
> [!NOTE]
>  安装企业单一登录 （服务器组件） 时，需要进行配置。 若要设置 SSO 系统的第一步是配置主密钥服务器。 建议设置独立的主密钥服务器。 这可以通过仅从 BizTalk Server 安装程序中的自定义功能树选择企业单一登录。  
>   
>  我们还建议的任何计算机运行企业单一登录已运行的时间同步服务。 这会使计算机时间与系统，这是对于 SSO 票证服务才能正常运行所必需的其余部分保持同步。  
  
 **安装选项的列表**:运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装程序。 选择**自定义安装**，然后从以下列表中选择相应的选项：  
  
- **企业单一登录管理 ―** 映射并连接到企业单一登录服务用于管理和客户端工具。  
  
- **企业单一登录主密钥服务器 ―** 充当 SSO 系统中的主密钥服务器。 这是需要部署在 SSO 系统中的第一个服务器，这使您可以创建 SSO 数据库。  
  
  此外可以使用添加或删除程序实用程序来添加安装完成后，以下：  
  
- **服务器运行时 ―** 核心服务，以启用单一登录，并安全地存储/访问配置数据。  
  
- **企业单一登录管理 ―** 映射并连接到企业单一登录服务用于管理和客户端工具。  
  
- **企业单一登录服务与密码同步 ―** 服务以启用企业 SSO 系统中的密码同步功能。 这些服务还与 Microsoft 密码更改通知服务集成。 一旦您已安装的核心企业单一登录服务，你可以安装企业 SSO 密码同步功能从 BizTalk Server 包启动 \Platform\SSO\Setup.exe，然后选择密码同步功能。  
  
- **软件开发工具包**编程和参考信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何安装 SSO 管理组件](../core/how-to-install-the-sso-administration-component.md)  
  
-   [如何安装 SSO 客户端实用工具](../core/how-to-install-the-sso-client-utility.md)