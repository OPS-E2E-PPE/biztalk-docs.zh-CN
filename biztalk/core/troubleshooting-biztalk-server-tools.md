---
title: BizTalk Server 工具进行故障排除 |Microsoft Docs
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
ms.openlocfilehash: c3b492c4ee6d22c1eb360f24c60efee1c1106d3b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292928"
---
# <a name="troubleshooting-biztalk-server-tools"></a><span data-ttu-id="7c5cd-102">BizTalk Server 工具进行故障排除</span><span class="sxs-lookup"><span data-stu-id="7c5cd-102">Troubleshooting BizTalk Server Tools</span></span>
<span data-ttu-id="7c5cd-103">本主题提供有关使用附带的工具时遇到的常见问题的信息的一个集中的位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-103">This topic provides a centralized location for information about common problems encountered while using the tools included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="7c5cd-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="7c5cd-104">Known Issues</span></span>  
  
### <a name="biztalk-server-tools-and-utilities-may-not-function-correctly-on-a-windows-system-that-supports-uac"></a><span data-ttu-id="7c5cd-105">BizTalk Server 工具和实用程序可能无法正常工作支持 UAC 的 Windows 系统上</span><span class="sxs-lookup"><span data-stu-id="7c5cd-105">BizTalk Server Tools and Utilities May Not Function Correctly on a Windows System That Supports UAC</span></span>  
 <span data-ttu-id="7c5cd-106">**问题**</span><span class="sxs-lookup"><span data-stu-id="7c5cd-106">**Problem**</span></span>  
  
 <span data-ttu-id="7c5cd-107">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持用户帐户控制 (UAC) 附带的工具的系统上安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不成功，启动或可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-107">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a system that supports User Account Control (UAC), the tools included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may not launch successfully, or may not function correctly.</span></span>  
  
 <span data-ttu-id="7c5cd-108">**原因**</span><span class="sxs-lookup"><span data-stu-id="7c5cd-108">**Cause**</span></span>  
  
 <span data-ttu-id="7c5cd-109">UAC 时运行的应用程序被标记为特定的权限级别，如果所需的级别高于运行该应用程序的用户的将显示一个提示，您可以暂时提升到应用程序的权限所需的级别。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-109">When running an application that has been flagged for a specific privilege level, if the required level is higher than that of the user running the application, the UAC will display a prompt that allows you to temporarily elevate the application privilege to the required level.</span></span> <span data-ttu-id="7c5cd-110">随附的工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不具有正确的标志来自动请求权限提升，因此该工具将尝试在运行该应用程序的用户当前的权限级别运行和更高的特权级别时将失败必填。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-110">The tools shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have the correct flags enabled to automatically request privilege elevation, so the tool will attempt to run at the current privilege level of the user running the application and will fail if a higher privilege level is required.</span></span>  
  
 <span data-ttu-id="7c5cd-111">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="7c5cd-111">**Resolution**</span></span>  
  
 <span data-ttu-id="7c5cd-112">若要解决此问题，请使用管理权限运行所有 BizTalk Server 工具。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-112">To resolve this problem, run all BizTalk Server tools with Administrative privileges.</span></span> <span data-ttu-id="7c5cd-113">要使用管理权限运行工具，用鼠标右键单击该应用程序，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-113">To run a tool with Administrative privileges, right-click the application and then select **Run as administrator**.</span></span>  
  
 <span data-ttu-id="7c5cd-114">有关用户帐户控制的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=99167 ](http://go.microsoft.com/fwlink/?LinkId=99167)。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-114">For more information about the User Account Control, see [http://go.microsoft.com/fwlink/?LinkId=99167](http://go.microsoft.com/fwlink/?LinkId=99167).</span></span>  
  
### <a name="sometimes-biztalk-mapper-toolbox-may-appear-empty"></a><span data-ttu-id="7c5cd-115">有时 BizTalk 映射器工具箱可能显示为空</span><span class="sxs-lookup"><span data-stu-id="7c5cd-115">Sometimes BizTalk Mapper Toolbox May Appear Empty</span></span>  
 <span data-ttu-id="7c5cd-116">**问题**</span><span class="sxs-lookup"><span data-stu-id="7c5cd-116">**Problem**</span></span>  
  
 <span data-ttu-id="7c5cd-117">有时，当在 Visual Studio 中打开映射器工具箱，看不在工具箱中的所有 functoid。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-117">Sometimes, when you open the Mapper toolbox in Visual Studio, you do not see any functoids in the toolbox.</span></span>  
  
 <span data-ttu-id="7c5cd-118">**原因**</span><span class="sxs-lookup"><span data-stu-id="7c5cd-118">**Cause**</span></span>  
  
 <span data-ttu-id="7c5cd-119">可能是有可能损坏的安装/卸载 Visual Studio 加载项和/或损坏。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-119">Might be a probable corruption by install/uninstall of Visual Studio add-ins and/or patch(es).</span></span>  
  
 <span data-ttu-id="7c5cd-120">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="7c5cd-120">**Resolution**</span></span>  
  
 <span data-ttu-id="7c5cd-121">解决此问题：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-121">To resolve this problem:</span></span>  
  
1.  <span data-ttu-id="7c5cd-122">关闭所有正在运行的 Visual Studio 实例。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-122">Close all running instances of Visual Studio.</span></span>  
  
2.  <span data-ttu-id="7c5cd-123">启动**Visual Studio 命令提示符**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="7c5cd-123">Start **Visual Studio Command Prompt** as an administrator.</span></span>  
  
3.  <span data-ttu-id="7c5cd-124">在命令提示符下，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="7c5cd-124">At the command prompt, type the following command:</span></span>  
  
    ```  
    devenv.exe /setup  
    ```