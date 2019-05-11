---
title: Windows SharePoint 服务的安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Windows SharePoint Services
- Windows SharePoint Services, security
- security, BAS
- BAS, security
ms.assetid: ada6abd3-b867-49a6-8ee0-1466adc87dc5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0979e0a7c75cf3f1450500253569fc47b3dae8b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376902"
---
# <a name="windows-sharepoint-services-security"></a><span data-ttu-id="9de19-102">Windows SharePoint Services 安全性</span><span class="sxs-lookup"><span data-stu-id="9de19-102">Windows SharePoint Services Security</span></span>
<span data-ttu-id="9de19-103">Windows SharePoint Services 3.0 使用 Windows SharePoint Services 站点组来管理站点范围的安全性。</span><span class="sxs-lookup"><span data-stu-id="9de19-103">Windows SharePoint Services 3.0 uses Windows SharePoint Services site groups to manage site-wide security.</span></span> <span data-ttu-id="9de19-104">每个站点组都拥有相应权限。</span><span class="sxs-lookup"><span data-stu-id="9de19-104">Each site group possesses corresponding rights.</span></span> <span data-ttu-id="9de19-105">权限是用户可以执行的操作，如查看、 编辑和删除站点资源。</span><span class="sxs-lookup"><span data-stu-id="9de19-105">Rights are actions that users can perform—such as view, edit, and delete site resources.</span></span> <span data-ttu-id="9de19-106">资源包括站点列表、 文档库和网站管理。</span><span class="sxs-lookup"><span data-stu-id="9de19-106">Resources include site lists, document libraries, and site administration.</span></span> <span data-ttu-id="9de19-107">在配置文件 Web 客户端需要定义 Windows SharePoint 服务站点组并相应地将权限分配到每个资源组中创建每个角色具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="9de19-107">For each role created in the Profile Web Client you need to define a Windows SharePoint Service site group and assign rights accordingly to each resource to which that group has access.</span></span>  
  
 <span data-ttu-id="9de19-108">WSS 3.0 安全有关的详细信息，请参阅 WSS 3.0 评估指南，网址[ http://go.microsoft.com/fwlink/?LinkID=94370 ](http://go.microsoft.com/fwlink/?LinkID=94370)。</span><span class="sxs-lookup"><span data-stu-id="9de19-108">For more information about WSS 3.0 security, see the WSS 3.0 evaluation guide at [http://go.microsoft.com/fwlink/?LinkID=94370](http://go.microsoft.com/fwlink/?LinkID=94370).</span></span>  
  
 <span data-ttu-id="9de19-109">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="9de19-109">This section contains:</span></span>  
  
-   [<span data-ttu-id="9de19-110">配置 A4SWIFT 用户</span><span class="sxs-lookup"><span data-stu-id="9de19-110">Configuring A4SWIFT Users</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-a4swift-users.md)  
  
-   [<span data-ttu-id="9de19-111">配置 A4SWIFT 站点组</span><span class="sxs-lookup"><span data-stu-id="9de19-111">Configuring A4SWIFT Site Groups</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-a4swift-site-groups.md)  
  
-   [<span data-ttu-id="9de19-112">分配权限</span><span class="sxs-lookup"><span data-stu-id="9de19-112">Assigning Rights</span></span>](../../adapters-and-accelerators/accelerator-swift/assigning-rights.md)