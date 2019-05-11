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
ms.openlocfilehash: fad36a25bac5d3319a55529cbedb02a5c5803070
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251116"
---
# <a name="security-and-windows-installer"></a><span data-ttu-id="f5443-102">安全性和 Windows 安装程序</span><span class="sxs-lookup"><span data-stu-id="f5443-102">Security and Windows Installer</span></span>
<span data-ttu-id="f5443-103">Windows 安装程序是用于安装和更新 BizTalk 应用程序的强大工具。</span><span class="sxs-lookup"><span data-stu-id="f5443-103">Windows Installer is a powerful tool for installing and updating BizTalk applications.</span></span> <span data-ttu-id="f5443-104">使用 Windows 安装程序，应注意的安全问题，可能由恶意 Windows Installer (.msi) 文件创建者和采取措施来阻止它们。</span><span class="sxs-lookup"><span data-stu-id="f5443-104">When using Windows Installer, you should be aware of the security issues that can be created by malicious Windows Installer (.msi) file creators and take steps to prevent them.</span></span>  
  
 <span data-ttu-id="f5443-105">通常由管理员运行.msi 文件，因此在应用程序安装或更新过程中运行的进程具有非常高的权限。</span><span class="sxs-lookup"><span data-stu-id="f5443-105">Administrators typically run .msi files, and therefore the processes that run during application installation or update have very high privileges.</span></span> <span data-ttu-id="f5443-106">恶意.msi 文件创建者可能会利用多种方式，包括以下这一事实：</span><span class="sxs-lookup"><span data-stu-id="f5443-106">A malicious .msi file creator could exploit this fact in a number of ways, including the following:</span></span>  
  
- <span data-ttu-id="f5443-107">正在运行的系统或文件进行非法更改的脚本文件。</span><span class="sxs-lookup"><span data-stu-id="f5443-107">Running script files that make undesirable changes to your system or files.</span></span>  
  
- <span data-ttu-id="f5443-108">覆盖 COM 目录。</span><span class="sxs-lookup"><span data-stu-id="f5443-108">Overwriting the COM catalog.</span></span>  
  
- <span data-ttu-id="f5443-109">覆盖注册表值。</span><span class="sxs-lookup"><span data-stu-id="f5443-109">Overwriting registry values.</span></span> <span data-ttu-id="f5443-110">不能回滚这些更改。</span><span class="sxs-lookup"><span data-stu-id="f5443-110">These changes cannot be rolled back.</span></span>  
  
- <span data-ttu-id="f5443-111">流量激增的文件系统。</span><span class="sxs-lookup"><span data-stu-id="f5443-111">Flooding the file system.</span></span>  
  
  <span data-ttu-id="f5443-112">当处理.msi 文件时，应至少采取以下预防措施：</span><span class="sxs-lookup"><span data-stu-id="f5443-112">When dealing with .msi files, you should take the following precautions at a minimum:</span></span>  
  
- <span data-ttu-id="f5443-113">安装在完全信任的.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="f5443-113">Install only .msi files that you completely trust.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f5443-114">最佳做法是，负责生成.msi 文件的人员应采取额外措施，以便用户可以验证文件的源是受信任签名的.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="f5443-114">As a best practice, individuals who are responsible for generating .msi files should take additional steps to sign the .msi files so that users can verify that the source of the file is trusted.</span></span>  
  
- <span data-ttu-id="f5443-115">在生产环境中使用它们之前进行全面测试您的.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="f5443-115">Thoroughly test your .msi files before using them in a production environment.</span></span>  
  
- <span data-ttu-id="f5443-116">将.msi 文件存储在使用适当的随机访问控制列表 (Dacl) 保护的受保护文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f5443-116">Store the .msi files in protected folders that are secured with appropriate discretionary access control lists (DACLs).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5443-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5443-117">See Also</span></span>  
 [<span data-ttu-id="f5443-118">应用程序部署的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="f5443-118">Security Considerations for Application Deployment</span></span>](../core/security-considerations-for-application-deployment.md)