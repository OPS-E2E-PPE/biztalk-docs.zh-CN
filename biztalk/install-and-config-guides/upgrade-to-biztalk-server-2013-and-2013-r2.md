---
title: 升级到 BizTalk Server 2013 和 2013 R2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, BizTalk Server
- deploying [BizTalk Server], upgrading
- BizTalk Server, upgrading
- upgrading
ms.assetid: acb0a96e-091b-45c3-8d41-affe9ffcf134
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97337438ca6be06b542baf61ad8d26fa2045180a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300029"
---
# <a name="upgrade-to-biztalk-server-2013-and-2013-r2"></a><span data-ttu-id="d127b-102">升级到 BizTalk Server 2013 和 2013 R2</span><span class="sxs-lookup"><span data-stu-id="d127b-102">Upgrade to BizTalk Server 2013 and 2013 R2</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d127b-103"> 经过设计，可以便捷地从以前版本进行升级。</span><span class="sxs-lookup"><span data-stu-id="d127b-103"> is designed to allow for an easy upgrade experience from previous versions.</span></span> <span data-ttu-id="d127b-104">[与 BizTalk Server 2013 相关的安装指南](http://www.microsoft.com/download/details.aspx?id=35552)页面上提供了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 和 2013 R2 升级指南。</span><span class="sxs-lookup"><span data-stu-id="d127b-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 and 2013 R2 Upgrade Guide is available at [Installation Guides Related to BizTalk Server 2013](http://www.microsoft.com/download/details.aspx?id=35552).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d127b-105">执行升级时将替换架构的压缩文件。</span><span class="sxs-lookup"><span data-stu-id="d127b-105">The compressed file of schemas will be replaced when an upgrade is performed.</span></span> <span data-ttu-id="d127b-106">如果将 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 升级到更高版本（例如，从测试版到发布版），则安装中的 MicrosoftEdiXSDTemplates.exe 文件将替换为与升级关联的 MicrosoftEdiXSDTemplates.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="d127b-106">If you upgrade Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a later build (for example, from a beta version to the retail release version), the MicrosoftEdiXSDTemplates.exe file in your installation will be replaced with the MicrosoftEdiXSDTemplates.exe file associated with the upgrade.</span></span> <span data-ttu-id="d127b-107">如果你计划继续使用旧压缩文件的架构，那么除非你备份了旧压缩文件，否则升级之后你将不能再访问此压缩文件。</span><span class="sxs-lookup"><span data-stu-id="d127b-107">If you plan to continue to use the schemas from the old compressed file, you will no longer have access to the compressed file after the upgrade unless you back up the old compressed file.</span></span> <span data-ttu-id="d127b-108">有关详细信息，请参阅**安装 EDI 架构**在[后配置步骤来优化您的环境](post-configuration-steps-to-optimize-your-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="d127b-108">For more information, see **Install EDI schemas** at [Post-configuration steps to optimize your environment](post-configuration-steps-to-optimize-your-environment.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d127b-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d127b-109">See Also</span></span>  
[<span data-ttu-id="d127b-110">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d127b-110">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)