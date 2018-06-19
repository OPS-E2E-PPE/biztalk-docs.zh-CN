---
title: 故障排除 BizTalk Server 工具 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 038a5f5c-d6eb-42db-88d6-70f3deba7a8a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7aedd8977042d15176781b0595bd5bb225a2fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279765"
---
# <a name="troubleshooting-biztalk-server-tools"></a><span data-ttu-id="6042b-102">BizTalk Server 工具问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="6042b-102">Troubleshooting BizTalk Server Tools</span></span>
<span data-ttu-id="6042b-103">本主题集中提供了有关使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包含的工具时遇到的常见问题的信息。</span><span class="sxs-lookup"><span data-stu-id="6042b-103">This topic provides a centralized location for information about common problems encountered while using the tools included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="6042b-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="6042b-104">Known Issues</span></span>  
  
### <a name="biztalk-server-tools-and-utilities-may-not-function-correctly-on-a-windows-system-that-supports-uac"></a><span data-ttu-id="6042b-105">BizTalk Server 工具和实用程序在支持 UAC 的 Windows 系统上可能无法正确工作</span><span class="sxs-lookup"><span data-stu-id="6042b-105">BizTalk Server Tools and Utilities May Not Function Correctly on a Windows System That Supports UAC</span></span>  
 <span data-ttu-id="6042b-106">**问题**</span><span class="sxs-lookup"><span data-stu-id="6042b-106">**Problem**</span></span>  
  
 <span data-ttu-id="6042b-107">当在支持用户帐户控制 (UAC) 的系统上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中包含的工具可能无法正常启动或正常工作。</span><span class="sxs-lookup"><span data-stu-id="6042b-107">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a system that supports User Account Control (UAC), the tools included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may not launch successfully, or may not function correctly.</span></span>  
  
 <span data-ttu-id="6042b-108">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="6042b-108">**Cause**</span></span>  
  
 <span data-ttu-id="6042b-109">运行被标记为具有特定权限级别的应用程序时，如果要求的级别高于运行应用程序的用户的级别，则 UAC 将提示你暂时将应用程序的权限提升为所需的级别。</span><span class="sxs-lookup"><span data-stu-id="6042b-109">When running an application that has been flagged for a specific privilege level, if the required level is higher than that of the user running the application, the UAC will display a prompt that allows you to temporarily elevate the application privilege to the required level.</span></span> <span data-ttu-id="6042b-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 随附的工具没有用来自动请求权限提升的正确标记，因此该工具将尝试使用运行应用程序的用户的当前权限级别运行，如果要求使用更高级别，则此工具将无法运行。</span><span class="sxs-lookup"><span data-stu-id="6042b-110">The tools shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have the correct flags enabled to automatically request privilege elevation, so the tool will attempt to run at the current privilege level of the user running the application and will fail if a higher privilege level is required.</span></span>  
  
 <span data-ttu-id="6042b-111">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="6042b-111">**Resolution**</span></span>  
  
 <span data-ttu-id="6042b-112">若要解决此问题，请使用管理权限运行所有 BizTalk Server 工具。</span><span class="sxs-lookup"><span data-stu-id="6042b-112">To resolve this problem, run all BizTalk Server tools with Administrative privileges.</span></span> <span data-ttu-id="6042b-113">要使用管理权限运行工具，请右键单击应用程序，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="6042b-113">To run a tool with Administrative privileges, right-click the application and then select **Run as administrator**.</span></span>  
  
 <span data-ttu-id="6042b-114">有关用户帐户控制的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167)。</span><span class="sxs-lookup"><span data-stu-id="6042b-114">For more information about the User Account Control, see [http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167).</span></span>  
  
### <a name="sometimes-biztalk-mapper-toolbox-may-appear-empty"></a><span data-ttu-id="6042b-115">有时 BizTalk 映射器工具箱可能会显示为空白</span><span class="sxs-lookup"><span data-stu-id="6042b-115">Sometimes BizTalk Mapper Toolbox May Appear Empty</span></span>  
 <span data-ttu-id="6042b-116">**问题**</span><span class="sxs-lookup"><span data-stu-id="6042b-116">**Problem**</span></span>  
  
 <span data-ttu-id="6042b-117">有时，当你打开 Visual Studio 中的映射器工具箱时，会看到工具箱中没有任何 functoid。</span><span class="sxs-lookup"><span data-stu-id="6042b-117">Sometimes, when you open the Mapper toolbox in Visual Studio, you do not see any functoids in the toolbox.</span></span>  
  
 <span data-ttu-id="6042b-118">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="6042b-118">**Cause**</span></span>  
  
 <span data-ttu-id="6042b-119">可能是由于安装/卸载 Visual Studio 加载项和/或路径造成的损坏。</span><span class="sxs-lookup"><span data-stu-id="6042b-119">Might be a probable corruption by install/uninstall of Visual Studio add-ins and/or patch(es).</span></span>  
  
 <span data-ttu-id="6042b-120">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="6042b-120">**Resolution**</span></span>  
  
 <span data-ttu-id="6042b-121">解决此问题：</span><span class="sxs-lookup"><span data-stu-id="6042b-121">To resolve this problem:</span></span>  
  
1.  <span data-ttu-id="6042b-122">关闭所有运行的 Visual Studio 实例。</span><span class="sxs-lookup"><span data-stu-id="6042b-122">Close all running instances of Visual Studio.</span></span>  
  
2.  <span data-ttu-id="6042b-123">启动**Visual Studio 命令提示符**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="6042b-123">Start **Visual Studio Command Prompt** as an administrator.</span></span>  
  
3.  <span data-ttu-id="6042b-124">在命令提示符下，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="6042b-124">At the command prompt, type the following command:</span></span>  
  
    ```  
    devenv.exe /setup  
    ```