---
title: 升级到 BizTalk Server 2013 和 2013 R2 |Microsoft Docs
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
ms.openlocfilehash: dbd8b2eda26ff6de37288612db55815d27020c34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401450"
---
# <a name="upgrade-to-biztalk-server-2013-and-2013-r2"></a><span data-ttu-id="2af5e-102">升级到 BizTalk Server 2013 和 2013 R2</span><span class="sxs-lookup"><span data-stu-id="2af5e-102">Upgrade to BizTalk Server 2013 and 2013 R2</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2af5e-103">旨在允许升级便捷地从以前的版本。</span><span class="sxs-lookup"><span data-stu-id="2af5e-103">is designed to allow for an easy upgrade experience from previous versions.</span></span> <span data-ttu-id="2af5e-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013年和 2013 R2 升级指南位于[相关的安装指南与 BizTalk Server 2013](http://www.microsoft.com/download/details.aspx?id=35552)。</span><span class="sxs-lookup"><span data-stu-id="2af5e-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 and 2013 R2 Upgrade Guide is available at [Installation Guides Related to BizTalk Server 2013](http://www.microsoft.com/download/details.aspx?id=35552).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2af5e-105">当执行升级时，将替换架构的压缩的文件。</span><span class="sxs-lookup"><span data-stu-id="2af5e-105">The compressed file of schemas will be replaced when an upgrade is performed.</span></span> <span data-ttu-id="2af5e-106">如果升级 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到更高版本 （例如，从测试版到发布版），在安装中的 MicrosoftEdiXSDTemplates.exe 文件将替换与关联的 MicrosoftEdiXSDTemplates.exe 文件升级。</span><span class="sxs-lookup"><span data-stu-id="2af5e-106">If you upgrade Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a later build (for example, from a beta version to the retail release version), the MicrosoftEdiXSDTemplates.exe file in your installation will be replaced with the MicrosoftEdiXSDTemplates.exe file associated with the upgrade.</span></span> <span data-ttu-id="2af5e-107">如果你打算继续使用旧压缩文件中的架构，将不再可以访问到压缩的文件在升级后除非您备份了旧压缩文件。</span><span class="sxs-lookup"><span data-stu-id="2af5e-107">If you plan to continue to use the schemas from the old compressed file, you will no longer have access to the compressed file after the upgrade unless you back up the old compressed file.</span></span> <span data-ttu-id="2af5e-108">有关详细信息，请参阅**安装 EDI 架构**处[用于优化环境的配置后步骤](post-configuration-steps-to-optimize-your-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="2af5e-108">For more information, see **Install EDI schemas** at [Post-configuration steps to optimize your environment](post-configuration-steps-to-optimize-your-environment.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2af5e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="2af5e-109">See Also</span></span>  
[<span data-ttu-id="2af5e-110">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2af5e-110">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)