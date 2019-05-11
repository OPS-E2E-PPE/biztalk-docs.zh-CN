---
title: 如何注册和删除 BizTalk 程序集查看器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f80b906-0a9e-4bcd-984d-db4550f2e51f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b78aeb8f0ebdbc1a7e05c8cfc45137b991b6eb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384395"
---
# <a name="how-to-register-and-remove-the-biztalk-assembly-viewer"></a><span data-ttu-id="853e0-102">如何注册和删除 BizTalk 程序集查看器</span><span class="sxs-lookup"><span data-stu-id="853e0-102">How to Register and Remove the BizTalk Assembly Viewer</span></span>
<span data-ttu-id="853e0-103">在 BizTalk Server 安装期间不自动注册 BizTalk 程序集查看器。</span><span class="sxs-lookup"><span data-stu-id="853e0-103">The BizTalk Assembly Viewer is not registered automatically during BizTalk Server setup.</span></span> <span data-ttu-id="853e0-104">若要注册或删除 BizTalk 程序集查看器，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="853e0-104">To register or remove the BizTalk Assembly Viewer, follow these steps.</span></span>  
  
### <a name="to-add-assembly-viewer-to-the-windows-registry"></a><span data-ttu-id="853e0-105">若要将程序集查看器添加到 Windows 注册表</span><span class="sxs-lookup"><span data-stu-id="853e0-105">To add Assembly Viewer to the Windows registry</span></span>  
  
1.  <span data-ttu-id="853e0-106">从**启动**菜单上，单击**运行**。</span><span class="sxs-lookup"><span data-stu-id="853e0-106">From the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="853e0-107">在运行对话框中，键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="853e0-107">In the Run dialog box, type **cmd**.</span></span>  
  
3.  <span data-ttu-id="853e0-108">从命令行中，导航到\< *BizTalk Server 安装文件夹*\>\developer tools\ BTSAsmExt.dll 所在的位置。</span><span class="sxs-lookup"><span data-stu-id="853e0-108">From the command line, navigate to \<*BizTalk Server Installation Folder*\>\Developer Tools\ where BTSAsmExt.dll resides.</span></span>  
  
4.  <span data-ttu-id="853e0-109">在命令行中，键入：</span><span class="sxs-lookup"><span data-stu-id="853e0-109">At the command line, type:</span></span>  
  
     <span data-ttu-id="853e0-110">regsvr32 BTSAsmExt.dll</span><span class="sxs-lookup"><span data-stu-id="853e0-110">regsvr32 BTSAsmExt.dll</span></span>  
  
5.  <span data-ttu-id="853e0-111">若要开始使用程序集视图，请先注销，然后再登录计算机。</span><span class="sxs-lookup"><span data-stu-id="853e0-111">To begin using Assembly View, log off and then log back onto the computer.</span></span>  
  
### <a name="to-remove-assembly-viewer-from-the-windows-registry"></a><span data-ttu-id="853e0-112">若要从 Windows 注册表删除程序集查看器</span><span class="sxs-lookup"><span data-stu-id="853e0-112">To remove Assembly Viewer from the Windows registry</span></span>  
  
1.  <span data-ttu-id="853e0-113">从**启动**菜单上，单击**运行**。</span><span class="sxs-lookup"><span data-stu-id="853e0-113">From the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="853e0-114">在中**运行**对话框中，键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="853e0-114">In the **Run** dialog box, type **cmd**.</span></span>  
  
3.  <span data-ttu-id="853e0-115">从命令行中，导航到\< *BizTalk Server 安装文件夹*\>\developer tools\ BTSAsmExt.dll 所在的位置。</span><span class="sxs-lookup"><span data-stu-id="853e0-115">From the command line, navigate to \<*BizTalk Server Installation Folder*\>\Developer Tools\ where BTSAsmExt.dll resides.</span></span>  
  
4.  <span data-ttu-id="853e0-116">在命令行中，键入：</span><span class="sxs-lookup"><span data-stu-id="853e0-116">At the command line, type:</span></span>  
  
     <span data-ttu-id="853e0-117">regsvr32/u BTSAsmExt.dll</span><span class="sxs-lookup"><span data-stu-id="853e0-117">regsvr32/u BTSAsmExt.dll</span></span>  
  
5.  <span data-ttu-id="853e0-118">若要完成删除，先注销，然后再登录计算机。</span><span class="sxs-lookup"><span data-stu-id="853e0-118">To complete the removal, log off and then log back onto the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="853e0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="853e0-119">See Also</span></span>  
 [<span data-ttu-id="853e0-120">使用 BizTalk 程序集查看器查看程序集</span><span class="sxs-lookup"><span data-stu-id="853e0-120">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)