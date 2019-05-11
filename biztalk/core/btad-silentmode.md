---
title: BTAD_SilentMode |Microsoft Docs
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
ms.openlocfilehash: 9433dde06cf40b0c7c94091f48af4f4b37f9bdf2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357813"
---
# <a name="btadsilentmode"></a><span data-ttu-id="efe41-102">BTAD_SilentMode</span><span class="sxs-lookup"><span data-stu-id="efe41-102">BTAD_SilentMode</span></span>
<span data-ttu-id="efe41-103">BTAD_SilentMode 指定在静默模式下运行该脚本的选项。</span><span class="sxs-lookup"><span data-stu-id="efe41-103">BTAD_SilentMode specifies options for running the script in silent mode.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efe41-104">备注</span><span class="sxs-lookup"><span data-stu-id="efe41-104">Remarks</span></span>  
 <span data-ttu-id="efe41-105">当指定为无提示模式的选项时，BTS Installer 会置于 BTAD_SilentMode 变量将其值。</span><span class="sxs-lookup"><span data-stu-id="efe41-105">When you specify an option for silent mode, BTS Installer places its value into the BTAD_SilentMode variable.</span></span>  
  
 <span data-ttu-id="efe41-106">BTAD_SilentMode 的默认值为 2，它指定在静默模式下运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="efe41-106">The default value of BTAD_SilentMode is 2, which specifies that the script runs in silent mode.</span></span> <span data-ttu-id="efe41-107">下表描述 btad_silentmode 的可能值。</span><span class="sxs-lookup"><span data-stu-id="efe41-107">The following table describes the possible values for BTAD_SilentMode.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="efe41-108">如果从脚本启动 BizTalk Server 用户界面，模式对话框可能不可见或没有焦点，使它们难以查看和解除。</span><span class="sxs-lookup"><span data-stu-id="efe41-108">If you start the BizTalk Server user interface from scripts, modal dialog boxes may not be visible or have focus, making them difficult to view and dismiss.</span></span> <span data-ttu-id="efe41-109">当模式对话框打开时，会锁定且无法访问 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="efe41-109">The BizTalk databases can become locked and inaccessible while modal dialog boxes are open.</span></span> <span data-ttu-id="efe41-110">出于此原因，在生产系统中，应以静默模式运行所有脚本。</span><span class="sxs-lookup"><span data-stu-id="efe41-110">For this reason, on production systems, all scripts should run in silent mode.</span></span>  
  
|<span data-ttu-id="efe41-111">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="efe41-111">Value</span></span>|<span data-ttu-id="efe41-112">Description</span><span class="sxs-lookup"><span data-stu-id="efe41-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="efe41-113">0</span><span class="sxs-lookup"><span data-stu-id="efe41-113">0</span></span>|<span data-ttu-id="efe41-114">不会更改用户界面 (UI) 级别。</span><span class="sxs-lookup"><span data-stu-id="efe41-114">Does not change the user interface (UI) level.</span></span>|  
|<span data-ttu-id="efe41-115">1</span><span class="sxs-lookup"><span data-stu-id="efe41-115">1</span></span>|<span data-ttu-id="efe41-116">使用默认用户界面级别。</span><span class="sxs-lookup"><span data-stu-id="efe41-116">Uses the default UI level.</span></span>|  
|<span data-ttu-id="efe41-117">2</span><span class="sxs-lookup"><span data-stu-id="efe41-117">2</span></span>|<span data-ttu-id="efe41-118">执行无提示安装 （默认值）。</span><span class="sxs-lookup"><span data-stu-id="efe41-118">Performs a silent installation (the default).</span></span>|  
|<span data-ttu-id="efe41-119">3</span><span class="sxs-lookup"><span data-stu-id="efe41-119">3</span></span>|<span data-ttu-id="efe41-120">提供了简单的进度和错误处理。</span><span class="sxs-lookup"><span data-stu-id="efe41-120">Provides simple progress and error handling.</span></span>|  
|<span data-ttu-id="efe41-121">4</span><span class="sxs-lookup"><span data-stu-id="efe41-121">4</span></span>|<span data-ttu-id="efe41-122">提供创作的用户界面;不显示向导。</span><span class="sxs-lookup"><span data-stu-id="efe41-122">Provides authored UI; suppresses wizards.</span></span>|  
|<span data-ttu-id="efe41-123">0x80</span><span class="sxs-lookup"><span data-stu-id="efe41-123">0x80</span></span>|<span data-ttu-id="efe41-124">如果与上述任何值一起使用，Windows 安装程序将显示模式对话框，如果已成功执行脚本或已出现错误。</span><span class="sxs-lookup"><span data-stu-id="efe41-124">If combined with any above value, Windows Installer displays a modal dialog box if the script has executed successfully or if there has been an error.</span></span> <span data-ttu-id="efe41-125">如果用户取消了操作，不显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="efe41-125">No dialog box is displayed if the user cancels the operation.</span></span>|  
|<span data-ttu-id="efe41-126">0x40</span><span class="sxs-lookup"><span data-stu-id="efe41-126">0x40</span></span>|<span data-ttu-id="efe41-127">如果与值 3 一起使用，Windows 安装程序将显示进度对话框，但不显示任何模式对话框或错误对话框。</span><span class="sxs-lookup"><span data-stu-id="efe41-127">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
|<span data-ttu-id="efe41-128">0x20</span><span class="sxs-lookup"><span data-stu-id="efe41-128">0x20</span></span>|<span data-ttu-id="efe41-129">如果与值 3 一起使用，Windows 安装程序将显示进度对话框，但不显示任何模式对话框或错误对话框。</span><span class="sxs-lookup"><span data-stu-id="efe41-129">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
|<span data-ttu-id="efe41-130">0x100</span><span class="sxs-lookup"><span data-stu-id="efe41-130">0x100</span></span>|<span data-ttu-id="efe41-131">如果与值 3 一起使用，Windows 安装程序将显示进度对话框，但不显示任何模式对话框或错误对话框。</span><span class="sxs-lookup"><span data-stu-id="efe41-131">If combined with the 3 value, Windows Installer displays progress dialog boxes but does not display any modal dialog boxes or error dialog boxes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efe41-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="efe41-132">See Also</span></span>  
 <span data-ttu-id="efe41-133">[预处理和后处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="efe41-133">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="efe41-134">环境变量如何指示部署状态</span><span class="sxs-lookup"><span data-stu-id="efe41-134">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)