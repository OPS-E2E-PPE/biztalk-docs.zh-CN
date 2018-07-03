---
title: 如何将一个 64 位项目添加到应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, 64-bit support
- scripts, 64-bit support
- virtual directories, 64-bit support
- artifacts, applications
- 64-bit support, COM components
- 64-bit support, virtual directories
- applications, artifacts
- 64-bit support, scripts
- 64-bit support, artifacts
- COM components, 64-bit support
- BizTalk Server, 64-bit support
- applications, 64-bit support
ms.assetid: 46aca7d4-c5be-421e-b16d-7f3095c8cc67
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979b7be419be6b39c5a80fcd1548af7404588e01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012862"
---
# <a name="how-to-add-a-64-bit-artifact-to-an-application"></a><span data-ttu-id="4b4d1-102">如何将一个 64 位项目添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="4b4d1-102">How to Add a 64-Bit Artifact to an Application</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4b4d1-103"> 包括对 64 位应用程序的支持。</span><span class="sxs-lookup"><span data-stu-id="4b4d1-103"> includes support for 64-bit applications.</span></span> <span data-ttu-id="4b4d1-104">这意味着，您可以采用与 32 位项目相同的方式将 64 位项目添加到 BizTalk 应用程序中；但是，在 32 位计算机上安装以下 64 位项目时，您可能会遇到以下问题：</span><span class="sxs-lookup"><span data-stu-id="4b4d1-104">This means that you can add 64-bit artifacts to a BizTalk application in the same manner as 32-bit artifacts; however, you may encounter the following issues when installing the following 64-bit artifacts on a 32-bit computer:</span></span>  
  
- <span data-ttu-id="4b4d1-105">**从 Web 服务器正在运行 64 位辅助进程的虚拟目录。**</span><span class="sxs-lookup"><span data-stu-id="4b4d1-105">**Virtual directory from a Web server that is running a 64-bit worker process.**</span></span> <span data-ttu-id="4b4d1-106">虚拟目录将安装在 32 位计算机上，但无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="4b4d1-106">The virtual directory will install on a 32-bit computer, but it may not function correctly.</span></span> <span data-ttu-id="4b4d1-107">在日志中将记录不匹配。</span><span class="sxs-lookup"><span data-stu-id="4b4d1-107">A mismatch will be logged.</span></span>  
  
- <span data-ttu-id="4b4d1-108">**非托管的 COM 或托管 COM + 组件标记为 64 位。**</span><span class="sxs-lookup"><span data-stu-id="4b4d1-108">**Unmanaged COM or Managed COM+ components marked as 64 bit.**</span></span> <span data-ttu-id="4b4d1-109">这些组件将不安装在 32 位计算机上。</span><span class="sxs-lookup"><span data-stu-id="4b4d1-109">These components will not install on a 32-bit computer.</span></span>  
  
- <span data-ttu-id="4b4d1-110">**64 位脚本另存为.exe 文件。**</span><span class="sxs-lookup"><span data-stu-id="4b4d1-110">**64-bit scripts saved as .exe files.**</span></span> <span data-ttu-id="4b4d1-111">此类型的脚本将无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="4b4d1-111">This type of script may not function correctly.</span></span>  
  
  <span data-ttu-id="4b4d1-112">添加项目的一般说明，请参阅[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)。</span><span class="sxs-lookup"><span data-stu-id="4b4d1-112">For general instructions on adding artifacts, see [How to Create or Add an Artifact](../core/how-to-create-or-add-an-artifact.md).</span></span> <span data-ttu-id="4b4d1-113">有关添加特定项目类型的说明，请参阅[管理项目](../core/managing-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="4b4d1-113">For instructions on adding specific artifact types, see [Managing Artifacts](../core/managing-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b4d1-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b4d1-114">See Also</span></span>  
 <span data-ttu-id="4b4d1-115">[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="4b4d1-115">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="4b4d1-116">如何安装 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="4b4d1-116">How to Install a BizTalk Application</span></span>](../core/how-to-install-a-biztalk-application.md)