---
title: 安装和配置 BizTalk Server HTTP 前端服务器上 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Server
- BizTalk Server, installing on HTTP servers
ms.assetid: dc1b3675-483a-478f-b30d-62efb73ad13c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6f2b656a45b8ef86df96d1234eb25344cf0cbd7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377375"
---
# <a name="installing-and-configuring-biztalk-server-on-the-http-front-end-servers"></a><span data-ttu-id="2d005-102">安装和配置 BizTalk Server HTTP 前端服务器上</span><span class="sxs-lookup"><span data-stu-id="2d005-102">Installing and Configuring BizTalk Server on the HTTP Front-End Servers</span></span>
<span data-ttu-id="2d005-103">本部分介绍如何安装和配置 BizTalk Server 用作托管 MRSR 站点 HTTP 前端服务器和[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]模板窗体。</span><span class="sxs-lookup"><span data-stu-id="2d005-103">This section describes how to install and configure BizTalk Server to be used as the HTTP front-end server for hosting the MRSR site and the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] template forms.</span></span>  

### <a name="to-install-and-configure-biztalk-server-on-the-biztalk-http-front-end-servers"></a><span data-ttu-id="2d005-104">若要安装和配置 BizTalk HTTP 前端服务器上的 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2d005-104">To install and configure BizTalk Server on the BizTalk HTTP front-end servers</span></span>  

1. <span data-ttu-id="2d005-105">执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]选择以下功能：**业务规则引擎**并**SharePoint 适配器**。</span><span class="sxs-lookup"><span data-stu-id="2d005-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing the following features: **Business Rules Engine** and **SharePoint Adapter**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="2d005-106">不需要此安装其他功能。</span><span class="sxs-lookup"><span data-stu-id="2d005-106">Other features are not required for this installation.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="2d005-107">在其中一个 BizTalk HTTP 前端服务器时执行配置，创建 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="2d005-107">On one of the BizTalk HTTP front-end servers, when you perform configuration, create the BizTalk Group.</span></span>  

2. <span data-ttu-id="2d005-108">执行的配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2d005-108">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

3. <span data-ttu-id="2d005-109">安装所需的任何其他修补程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]安装指南中为可用。</span><span class="sxs-lookup"><span data-stu-id="2d005-109">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>
