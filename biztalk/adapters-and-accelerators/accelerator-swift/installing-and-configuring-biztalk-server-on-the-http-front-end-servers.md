---
title: "安装和 HTTP 前端服务器上配置 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Server
- BizTalk Server, installing on HTTP servers
ms.assetid: dc1b3675-483a-478f-b30d-62efb73ad13c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772c240ef95c294e5e884d94b361d4cd0b102b07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-http-front-end-servers"></a><span data-ttu-id="14e82-102">安装和 HTTP 前端服务器上配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="14e82-102">Installing and Configuring BizTalk Server on the HTTP Front-End Servers</span></span>
<span data-ttu-id="14e82-103">本部分介绍如何安装和配置[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]托管 MRSR 站点为 HTTP 前端服务器用于与[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]模板窗体。</span><span class="sxs-lookup"><span data-stu-id="14e82-103">This section describes how to install and configure [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] to be used as the HTTP front-end server for hosting the MRSR site and the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] template forms.</span></span>  
  
### <a name="to-install-and-configure-biztalk-server-on-the-biztalk-http-front-end-servers"></a><span data-ttu-id="14e82-104">若要安装和配置 BizTalk HTTP 前端服务器上的 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="14e82-104">To install and configure BizTalk Server on the BizTalk HTTP front-end servers</span></span>  
  
1.  <span data-ttu-id="14e82-105">执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]选择以下功能：**业务规则引擎**和**SharePoint 适配器**。</span><span class="sxs-lookup"><span data-stu-id="14e82-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing the following features: **Business Rules Engine** and **SharePoint Adapter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14e82-106">其他功能则不需要此安装。</span><span class="sxs-lookup"><span data-stu-id="14e82-106">Other features are not required for this installation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14e82-107">上一个 BizTalk HTTP 前端服务器中，当你执行配置，创建 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="14e82-107">On one of the BizTalk HTTP front-end servers, when you perform configuration, create the BizTalk Group.</span></span>  
  
2.  <span data-ttu-id="14e82-108">执行配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="14e82-108">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="14e82-109">安装所需的任何其他修补程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]为可安装指南中。</span><span class="sxs-lookup"><span data-stu-id="14e82-109">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>