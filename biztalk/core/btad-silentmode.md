---
title: BTAD_SilentMode |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAD_SilentMode [environment variable], about BTAS_SilentMode
- BTAD_SilentMode [environment variable]
- BTAD_SilentMode [environment variable], warnings
ms.assetid: 271835cf-1587-44c5-b5af-b4df4e981ab4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31715835c98d2f60a3b5f1c18251571ea57641d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231325"
---
# <a name="btadsilentmode"></a><span data-ttu-id="eecdc-102">BTAD_SilentMode</span><span class="sxs-lookup"><span data-stu-id="eecdc-102">BTAD_SilentMode</span></span>
<span data-ttu-id="eecdc-103">BTAD_SilentMode 为以无提示模式运行脚本指定一些选项。</span><span class="sxs-lookup"><span data-stu-id="eecdc-103">BTAD_SilentMode specifies options for running the script in silent mode.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eecdc-104">注释</span><span class="sxs-lookup"><span data-stu-id="eecdc-104">Remarks</span></span>  
 <span data-ttu-id="eecdc-105">在您为无提示模式指定选项时，BTS Installer 会将其值置于 BTAD_SilentMode 变量中。</span><span class="sxs-lookup"><span data-stu-id="eecdc-105">When you specify an option for silent mode, BTS Installer places its value into the BTAD_SilentMode variable.</span></span>  
  
 <span data-ttu-id="eecdc-106">BTAD_SilentMode 的默认值为 2，指定脚本以无提示模式运行。</span><span class="sxs-lookup"><span data-stu-id="eecdc-106">The default value of BTAD_SilentMode is 2, which specifies that the script runs in silent mode.</span></span> <span data-ttu-id="eecdc-107">下表描述 BTAD_SilentMode 的可能值。</span><span class="sxs-lookup"><span data-stu-id="eecdc-107">The following table describes the possible values for BTAD_SilentMode.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="eecdc-108">如果您从脚本启动 BizTalk Server 用户界面，则模式对话框可能不可见或没有焦点，因此导致这些对话框难于查看和关闭。</span><span class="sxs-lookup"><span data-stu-id="eecdc-108">If you start the BizTalk Server user interface from scripts, modal dialog boxes may not be visible or have focus, making them difficult to view and dismiss.</span></span> <span data-ttu-id="eecdc-109">在模式对话框打开时，BizTalk 数据库可能会被锁定并且无法访问。</span><span class="sxs-lookup"><span data-stu-id="eecdc-109">The BizTalk databases can become locked and inaccessible while modal dialog boxes are open.</span></span> <span data-ttu-id="eecdc-110">因此，在生产系统上，所有脚本都应以无提示模式运行。</span><span class="sxs-lookup"><span data-stu-id="eecdc-110">For this reason, on production systems, all scripts should run in silent mode.</span></span>  
  
|<span data-ttu-id="eecdc-111">值</span><span class="sxs-lookup"><span data-stu-id="eecdc-111">Value</span></span>|<span data-ttu-id="eecdc-112">说明</span><span class="sxs-lookup"><span data-stu-id="eecdc-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eecdc-113">0</span><span class="sxs-lookup"><span data-stu-id="eecdc-113">0</span></span>|<span data-ttu-id="eecdc-114">不更改用户界面 (UI) 级别。</span><span class="sxs-lookup"><span data-stu-id="eecdc-114">Does not change the user interface (UI) level.</span></span>|  
|<span data-ttu-id="eecdc-115">1</span><span class="sxs-lookup"><span data-stu-id="eecdc-115">1</span></span>|<span data-ttu-id="eecdc-116">使用默认用户界面级别。</span><span class="sxs-lookup"><span data-stu-id="eecdc-116">Uses the default UI level.</span></span>|  
|<span data-ttu-id="eecdc-117">2</span><span class="sxs-lookup"><span data-stu-id="eecdc-117">2</span></span>|<span data-ttu-id="eecdc-118">执行无提示安装（默认设置）。</span><span class="sxs-lookup"><span data-stu-id="eecdc-118">Performs a silent installation (the default).</span></span>|  
|<span data-ttu-id="eecdc-119">3</span><span class="sxs-lookup"><span data-stu-id="eecdc-119">3</span></span>|<span data-ttu-id="eecdc-120">提供简单的进度和错误处理。</span><span class="sxs-lookup"><span data-stu-id="eecdc-120">Provides simple progress and error handling.</span></span>|  
|<span data-ttu-id="eecdc-121">4</span><span class="sxs-lookup"><span data-stu-id="eecdc-121">4</span></span>|<span data-ttu-id="eecdc-122">提供创作的用户界面，不显示向导。</span><span class="sxs-lookup"><span data-stu-id="eecdc-122">Provides authored UI; suppresses wizards.</span></span>|  
|<span data-ttu-id="eecdc-123">0x80</span><span class="sxs-lookup"><span data-stu-id="eecdc-123">0x80</span></span>|<span data-ttu-id="eecdc-124">如果与上述任何值一起使用，则在当脚本已成功执行或存在错误时，Windows Installer 将显示一个模式对话框。</span><span class="sxs-lookup"><span data-stu-id="eecdc-124">If combined with any above value, Windows Installer displays a modal dialog box if the script has executed successfully or if there has been an error.</span></span> <span data-ttu-id="eecdc-125">如果用户取消该操作，则不会显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="eecdc-125">No dialog box is displayed if the user cancels the operation.</span></span>|  
|<span data-ttu-id="eecdc-126">0x40</span><span class="sxs-lookup"><span data-stu-id="eecdc-126">0x40</span></span>|<span data-ttu-id="eecdc-127">如果与值 3 一起使用，则 Windows Installer 将显示进度对话框，但不显示任何模式对话框或错误对话框。</span><span class="sxs-lookup"><span data-stu-id="eecdc-127">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
|<span data-ttu-id="eecdc-128">0x20</span><span class="sxs-lookup"><span data-stu-id="eecdc-128">0x20</span></span>|<span data-ttu-id="eecdc-129">如果与值 3 一起使用，则 Windows Installer 将显示进度对话框，但不显示任何模式对话框或错误对话框。</span><span class="sxs-lookup"><span data-stu-id="eecdc-129">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
|<span data-ttu-id="eecdc-130">0x100</span><span class="sxs-lookup"><span data-stu-id="eecdc-130">0x100</span></span>|<span data-ttu-id="eecdc-131">如果与值 3 一起使用，则 Windows Installer 将显示进度对话框，但不显示任何模式对话框或错误对话框。</span><span class="sxs-lookup"><span data-stu-id="eecdc-131">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eecdc-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eecdc-132">See Also</span></span>  
 <span data-ttu-id="eecdc-133">[前期和后期处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="eecdc-133">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="eecdc-134">环境变量如何指示部署状态</span><span class="sxs-lookup"><span data-stu-id="eecdc-134">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)