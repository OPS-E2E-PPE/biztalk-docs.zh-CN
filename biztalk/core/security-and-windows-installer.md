---
title: 安全性和 Windows 安装程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Windows installer
- Windows installer
ms.assetid: efa68c3e-2006-4665-bd41-07defaf4e2e2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9d452fc92e9fcd1c238086513a08b4b392caaa5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017519"
---
# <a name="security-and-windows-installer"></a><span data-ttu-id="5368f-102">安全性和 Windows 安装程序</span><span class="sxs-lookup"><span data-stu-id="5368f-102">Security and Windows Installer</span></span>
<span data-ttu-id="5368f-103">Windows Installer 是一种用于安装和更新 BizTalk 应用程序的强大工具。</span><span class="sxs-lookup"><span data-stu-id="5368f-103">Windows Installer is a powerful tool for installing and updating BizTalk applications.</span></span> <span data-ttu-id="5368f-104">使用 Windows Installer 时，应注意可能由恶意 Windows Installer (.msi) 文件创建者造成的安全问题，并应采取措施防止此类问题发生。</span><span class="sxs-lookup"><span data-stu-id="5368f-104">When using Windows Installer, you should be aware of the security issues that can be created by malicious Windows Installer (.msi) file creators and take steps to prevent them.</span></span>  
  
 <span data-ttu-id="5368f-105">通常由管理员运行 .msi 文件，因而在安装和更新应用程序期间运行的进程具有非常高的权限。</span><span class="sxs-lookup"><span data-stu-id="5368f-105">Administrators typically run .msi files, and therefore the processes that run during application installation or update have very high privileges.</span></span> <span data-ttu-id="5368f-106">恶意 .msi 文件创建者可以通过多种方式来利用此缺陷，其中包括：</span><span class="sxs-lookup"><span data-stu-id="5368f-106">A malicious .msi file creator could exploit this fact in a number of ways, including the following:</span></span>  
  
- <span data-ttu-id="5368f-107">运行会对您的系统或文件进行非法更改的脚本文件。</span><span class="sxs-lookup"><span data-stu-id="5368f-107">Running script files that make undesirable changes to your system or files.</span></span>  
  
- <span data-ttu-id="5368f-108">覆盖 COM 目录。</span><span class="sxs-lookup"><span data-stu-id="5368f-108">Overwriting the COM catalog.</span></span>  
  
- <span data-ttu-id="5368f-109">覆盖注册表值。</span><span class="sxs-lookup"><span data-stu-id="5368f-109">Overwriting registry values.</span></span> <span data-ttu-id="5368f-110">不能回滚这些更改。</span><span class="sxs-lookup"><span data-stu-id="5368f-110">These changes cannot be rolled back.</span></span>  
  
- <span data-ttu-id="5368f-111">填满整个文件系统。</span><span class="sxs-lookup"><span data-stu-id="5368f-111">Flooding the file system.</span></span>  
  
  <span data-ttu-id="5368f-112">处理 .msi 文件时，至少应采取以下防范措施：</span><span class="sxs-lookup"><span data-stu-id="5368f-112">When dealing with .msi files, you should take the following precautions at a minimum:</span></span>  
  
- <span data-ttu-id="5368f-113">只安装完全信任的 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="5368f-113">Install only .msi files that you completely trust.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5368f-114">作为一种最佳实践，负责生成 .msi 文件的人员应采取额外措施来对 .msi 文件进行签名，以便用户可以验证 .msi 文件的来源是否是可信的。</span><span class="sxs-lookup"><span data-stu-id="5368f-114">As a best practice, individuals who are responsible for generating .msi files should take additional steps to sign the .msi files so that users can verify that the source of the file is trusted.</span></span>  
  
- <span data-ttu-id="5368f-115">在生产环境中使用 .msi 文件之前对其进行彻底测试。</span><span class="sxs-lookup"><span data-stu-id="5368f-115">Thoroughly test your .msi files before using them in a production environment.</span></span>  
  
- <span data-ttu-id="5368f-116">将 .msi 文件存储在用适当的随机访问控制列表 (DACL) 进行保护的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5368f-116">Store the .msi files in protected folders that are secured with appropriate discretionary access control lists (DACLs).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5368f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5368f-117">See Also</span></span>  
 [<span data-ttu-id="5368f-118">应用程序部署的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="5368f-118">Security Considerations for Application Deployment</span></span>](../core/security-considerations-for-application-deployment.md)